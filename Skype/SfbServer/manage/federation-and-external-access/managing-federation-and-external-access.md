---
title: 'Lync Server 2013: Skype for Business Server へのフェデレーションおよび外部アクセスの管理'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが Skype for Business Server の内部ユーザーと共同作業できるかどうかを制御します。
ms.openlocfilehash: a5437cb15f47a9414ed33dca94e55b770f36d651
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221651"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Skype for Business Server へのフェデレーションおよび外部アクセスの管理

外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。 エッジサーバーの展開の詳細については、「 [Deploy Edge server In Skype For Business server](../../deploy/deploy-edge-server/deploy-edge-server.md)」を参照してください。

Skype for Business Server の内部展開をインストールして構成すると、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。 共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。 外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが Skype for Business Server の内部ユーザーと共同作業できるかどうかを制御します。 外部ユーザーには、展開のリモートユーザー、フェデレーションユーザー (パブリックインスタントメッセージング (IM) サービスプロバイダーのサポート対象ユーザーを含む)、および会議の匿名参加者を含めることができます。

展開に Skype for Business Server エッジサーバーまたはエッジプールのインストールが含まれていた場合、可能な通信の種類の範囲は、外部ユーザーアクセス用のさまざまなオプションと、他の SIP フェデレーションドメインおよび SIP フェデレーションプロバイダーのメンバーとの通信によって大幅に拡張されます。 エッジサーバーまたはエッジプールを設定したら、指定する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。 Skype for business Server では、タスクの要件に基づいて、Skype for Business Server コントロールパネル、 [skype For Business Server 管理シェル](../management-shell.md)、またはその両方を使用して、外部ユーザーのアクセスとポリシーを有効にし、構成します。 



> [!IMPORTANT]  
> 外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。 1つのポリシーレベルで適用されている Skype for Business Server のポリシー設定は、別のポリシーレベルで適用される設定を上書きすることができます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。 外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。 これには、次の外部アクセス ポリシーが含まれます。

  - **グローバル ポリシー**   グローバル ポリシーは、エッジ サーバーを展開する際に作成されます。 既定では、グローバル ポリシーではどの外部ユーザー アクセス オプションも有効ではありません。 グローバル レベルで外部ユーザー アクセスをサポートするには、1 つ以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。 グローバル ポリシーは組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーをオーバーライドします。 グローバル ポリシーを削除することはできません。 代わりに、既定の設定にリセットします。

  - **サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成および構成できます。 サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。 たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。 既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。

  - **ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成および構成できます。 ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。 たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。 ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。

どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。

**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**

トピック「 [configure policies to control remote user user](external-access-policies/configure-policies-to-control-remote-user-access.md)」の説明のとおりに設定を構成し、[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にします。

**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**

トピック「[匿名ユーザーをサポート](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)し、[電話会議ポリシーを作成](../conferencing/create-policies.md)するための会議ポリシーの割り当て」で説明されているとおりに設定を構成します。

**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**

トピック「 [configure policies to control フェデレーションユーザーアクセスを制御する](external-access-policies/configure-policies-to-control-federated-user-access.md)」、「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」、および「[組織の SIP フェデレーションドメインを管理](sip-domains/manage-sip-federated-domains-for-your-organization.md)する」の説明のとおりに設定を構成します。


**SIP フェデレーションドメインとの通信を有効にしている場合は、SIP フェデレーションの自動検出を有効にしますか。**

トピック「[フェデレーションパートナーの検出を有効または無効](access-edge/enable-or-disable-discovery-of-federation-partners.md)にする」の説明のとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**

トピック「[有効化または無効にする」の「フェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」の説明のとおりに設定を構成します。

**ユーザーに対して、パブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可しますか。**

トピック「 [configure policies to control public user access](external-access-policies/configure-policies-to-control-public-user-access.md)」、「 [Enable or disable FEDERATION and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)」、および「[パブリック SIP フェデレーションプロバイダーを作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)する」の説明のとおりに設定を構成します。


**ユーザーに対して、Microsoft 365 または Office 365 と Skype for Business Online を実行しているホストされているプロバイダーである SIP フェデレーションプロバイダーとの通信を許可するかどうか。**

トピック「 [Enable or disable federation and PUBLIC IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 」、および「 [hosted SIP フェデレーションプロバイダーを作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)する」の説明のとおりに設定を構成します。

**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**

トピック「 [configure policies to control フェデレーション user access](external-access-policies/configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)」、および「ホストされた[SIP フェデレーションプロバイダーの作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)」の説明のとおりに設定を構成します。


ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。

