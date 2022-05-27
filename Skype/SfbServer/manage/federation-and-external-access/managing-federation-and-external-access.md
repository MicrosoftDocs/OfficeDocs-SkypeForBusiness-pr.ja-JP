---
title: 'Lync Server 2013: Skype for Business Serverへのフェデレーションと外部アクセスの管理'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 外部ユーザー アクセスを有効にして構成し、サポートされている外部ユーザーが内部Skype for Business Server ユーザーと共同作業できるかどうかを制御します。
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676219"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Skype for Business Server のフェデレーションと外部アクセスの管理

外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。 エッジ サーバーの展開の詳細については、「[Skype for Business Serverでのエッジ サーバーの展開](../../deploy/deploy-edge-server/deploy-edge-server.md)」を参照してください。

Skype for Business Serverの内部展開をインストールして構成した後、組織内の内部ユーザーは、Active Directory Domain Services (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業できます。 共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。 外部ユーザー アクセスを有効にして構成し、サポートされている外部ユーザーが内部Skype for Business Server ユーザーと共同作業できるかどうかを制御します。 外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされているユーザーを含む)、会議の匿名参加者を含めることができます。

展開に Skype for Business Server Edge Server またはエッジ プールが含まれている場合、可能な通信の種類の範囲が大幅に拡大されます。 外部ユーザー アクセス、他の SIP フェデレーション ドメインのメンバーとの通信、および SIP フェデレーション プロバイダーの多くのオプションがあります。 Edge Server または Edge プールを設定した後、外部ユーザー アクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。 Skype for Business Serverでは、Skype for Business Server コントロール パネル、[Skype for Business Server管理シェル](../management-shell.md)、またはその両方を使用して、外部ユーザー アクセスとポリシーを有効にして構成します。

> [!IMPORTANT]
> 外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。 1 つのポリシー レベルで適用されるポリシー設定Skype for Business Server、別のポリシー レベルで適用される設定をオーバーライドできます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。

既定では、組織で外部ユーザー アクセスのサポートが既に有効になっている場合でも、外部ユーザー アクセス (リモート ユーザー アクセスとフェデレーション ユーザー アクセスを含む) はサポートされません。 外部ユーザー アクセスの使用を制御するには、1 つ以上のポリシーを構成する必要があります。 次のポリシーでは、サポートされている外部ユーザー アクセスの種類を指定します。

- **グローバル ポリシー**: グローバル ポリシーは、エッジ サーバーを展開するときに作成されます。 既定では、グローバル ポリシーではどの外部ユーザー アクセス オプションも有効ではありません。 グローバル レベルで外部ユーザー アクセスをサポートするには、1 つ以上の種類の外部ユーザー アクセスをサポートするようにグローバル ポリシーを構成します。 グローバル ポリシーは組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーをオーバーライドします。 グローバル ポリシーを削除することはできません。 代わりに、既定の設定にリセットします。

- **サイト ポリシー**: 特定のサイトへの外部ユーザー アクセスのサポートを制限するために、1 つ以上のサイト ポリシーを作成して構成できます。 サイト ポリシーの構成は、グローバル ポリシーよりも優先されますが、サイト ポリシーの対象となる特定のサイトに対してのみ適用されます。 既定では、サイト ポリシーはそのサイト内のすべてのユーザーに適用されますが、サイト ポリシー設定をオーバーライドするユーザー ポリシーが適用されます。

- **ユーザー ポリシー**: リモート ユーザー アクセスのサポートを特定のユーザーに制限するために、1 つ以上のユーザー ポリシーを作成して構成できます。 ユーザー ポリシーの構成は、グローバル ポリシーとサイト ポリシーよりも優先されますが、ポリシーが割り当てられている特定のユーザーに対してのみ適用されます。 ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。

どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。

**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**

[「リモート ユーザーのアクセスを制御するポリシーを構成する](external-access-policies/configure-policies-to-control-remote-user-access.md)」および「[フェデレーションとパブリック IM 接続を有効または無効にする](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)」のトピックで詳しく説明されている設定を構成します。

**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**

[匿名ユーザーをサポートする会議ポリシーの割り当てと会議ポリシーの](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)作成に関するトピックで詳しく説明されているように設定[を構成します](../conferencing/create-policies.md)。

**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**

「 [フェデレーション ユーザー アクセスを制御するポリシーの構成](external-access-policies/configure-policies-to-control-federated-user-access.md)」、フェデレーション [とパブリック IM 接続の有効化または無効化](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)、 [組織の SIP フェデレーション ドメインの管理](sip-domains/manage-sip-federated-domains-for-your-organization.md)に関するトピックで詳しく説明されている設定を構成します。

**SIP フェデレーション ドメインとの通信を有効にしている場合は、SIP フェデレーションの自動検出を有効にしますか?**

[フェデレーション パートナーの検出を有効または無効にする](access-edge/enable-or-disable-discovery-of-federation-partners.md)に関するトピックで詳しく説明されているように、設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**

[フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にする](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)に関するトピックで詳しく説明されているように設定を構成します。

**パブリック プロバイダーとの通信を可能にする SIP フェデレーション プロバイダーとの通信をユーザーに許可しますか?**

トピック「[ポリシーを構成してパブリック ユーザー アクセスを制御する](external-access-policies/configure-policies-to-control-public-user-access.md)、[フェデレーションとパブリック IM 接続を有効または無効にする、パブリック](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) [SIP フェデレーション プロバイダーを作成または編集する](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)」で詳しく説明されている設定を構成する

**ユーザーが、Microsoft 365または Office 365 および Skype for Business Online を実行しているホストされたプロバイダーである SIP フェデレーション プロバイダーと通信できるようにしますか?**

[「フェデレーションとパブリック IM 接続を有効または無効にする」と](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)「[ホストされている SIP フェデレーション プロバイダーを作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)する」のトピックで詳しく説明されているように、設定を構成します。

**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**

「 [フェデレーション ユーザー アクセスを制御するポリシーの構成](external-access-policies/configure-policies-to-control-federated-user-access.md)」のトピックで詳しく説明されているように設定を構成 [し、フェデレーションとパブリック IM 接続を有効または無効に](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)し、 [ホストされている SIP フェデレーション プロバイダーを作成または編集します](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセス設定を構成できます。 ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。 外部ユーザー アクセスが無効になっている場合、または外部ユーザー アクセス ポリシーがサポートするように構成されていない場合、外部ユーザーはユーザーと通信できません。

エッジデプロイは、外部ユーザーの種類を認証し、エッジ サポートの構成方法に基づいてアクセスを制御します。 このルールの例外は匿名ユーザーであり、会議 ID と、会議を作成して参加者を招待するときに匿名参加者に送信されるパスキーによって認証されます。 通信を制御するには、組織内外のユーザーが相互に通信する方法を定義する 1 つ以上のポリシーを構成できます。 ポリシーと設定には、作成および構成できる既定のグローバル ポリシー、サイト ポリシー、ユーザー ポリシーが含まれます。
