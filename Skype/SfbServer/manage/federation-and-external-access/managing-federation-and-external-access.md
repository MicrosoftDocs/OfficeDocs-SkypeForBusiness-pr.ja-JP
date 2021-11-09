---
title: 'Lync Server 2013: フェデレーションと外部アクセスを管理するSkype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: サポートされている外部ユーザーが内部ユーザーと共同作業できるかどうかを制御するために、外部ユーザー アクセスを有効にして構成Skype for Business Serverします。
ms.openlocfilehash: 42e0644cbad51681f979f83041e4c260788039d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836369"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>フェデレーションと外部アクセスの管理Skype for Business Server

外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。 エッジ サーバーの展開の詳細については[、「Deploy Edge Server in Skype for Business Server」 を参照してください](../../deploy/deploy-edge-server/deploy-edge-server.md)。

Skype for Business Server の内部展開をインストールして構成した後、組織内の内部ユーザーは、Active Directory ドメイン サービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業できます。 共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。 サポートされている外部ユーザーが内部ユーザーと共同作業できるかどうかを制御するために、外部ユーザー アクセスを有効にして構成Skype for Business Serverします。 外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされているユーザーを含む)、会議の匿名参加者を含めできます。

展開に Skype for Business Server エッジ サーバーまたはエッジ プールのインストールが含まれている場合、外部ユーザー アクセス、他の SIP フェデレーション ドメインのメンバーとの通信、および SIP フェデレーション プロバイダーとの通信に関して、可能な通信の種類の範囲が大幅に拡大されます。 エッジ サーバーまたはエッジ プールを設定した後、提供する外部ユーザー アクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。 このSkype for Business Server、タスク要件に基づいて、Skype for Business Server コントロール パネル[、Skype for Business Server 管理](../management-shell.md)シェル、または両方を使用して外部ユーザー アクセスとポリシーを有効にして構成します。 



> [!IMPORTANT]  
> 外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。 Skype for Business Serverレベルで適用されるポリシー設定は、別のポリシー レベルで適用される設定を上書きできます。 Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。 外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。 これには、次の外部アクセス ポリシーが含まれます。

  - **グローバル ポリシー**   エッジ サーバーの展開時に作成されます。 既定では、グローバル ポリシーで有効になっている外部ユーザー アクセスのオプションはありません。 外部ユーザー アクセスをグローバル レベルでサポートするには、1 つ以上の外部ユーザー アクセスのオプションの種類をサポートするグローバル ポリシーを構成します。 グローバル ポリシーは組織のすべてのユーザーに割り当てられますが、サイト ポリシーやユーザー ポリシーの方がグローバル ポリシーよりも優先されます。 グローバル ポリシーを消去しても、 ポリシーは取り除かれるのではなく、既定の設定にリセットされます。

  - **サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成および構成できます。 サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。 たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。 既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。

  - **ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成および構成できます。ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。

どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。

**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**

「リモート ユーザーのアクセス許可を制御[](external-access-policies/configure-policies-to-control-remote-user-access.md)するポリシーを構成する」および「フェデレーションとパブリック IM 接続を有効または無効にする」のトピックで詳しく説明されている設定[を構成します](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**

トピック「匿名ユーザーをサポートする会議ポリシー[](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)の割り当て」および「会議ポリシーの作成」の詳細に従って設定[を構成します](../conferencing/create-policies.md)。

**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**

「フェデレーション ユーザー アクセスを制御するための[](external-access-policies/configure-policies-to-control-federated-user-access.md)ポリシーの構成」、フェデレーションおよびパブリック[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)接続の有効化または無効化、および組織の SIP フェデレーション ドメインの管理に関するトピックで詳しく説明されている設定を[構成します](sip-domains/manage-sip-federated-domains-for-your-organization.md)。


**SIP フェデレーション ドメインとの通信を有効にしている場合、SIP フェデレーションの自動検出を有効にしますか?**

「フェデレーション パートナーの検出を有効または無効にする」のトピックで [詳しく説明されている設定を構成します](access-edge/enable-or-disable-discovery-of-federation-partners.md)。

**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**

「Enable or disableing the Archiving 免責事項をフェデレーション パートナーに送信する」のトピックで詳しく説明されている設定 [を構成します](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

**パブリック プロバイダーとの通信を有効にする SIP フェデレーション プロバイダーとの通信をユーザーに許可しますか?**

詳細については、「ポリシーを構成してパブリック[](external-access-policies/configure-policies-to-control-public-user-access.md)ユーザー アクセスを制御する、フェデレーションとパブリック[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)接続を有効または無効にする」、および「パブリック SIP フェデレーション プロバイダーを作成または編集する」で説明されている設定を[構成](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)します。


**ユーザーが、オンラインまたはオンラインで実行されているホストプロバイダーである SIP フェデレーション プロバイダーと通信Microsoft 365またはOffice 365許可Skype for Businessしますか?**

「フェデレーションとパブリック IM 接続を有効または無効にする」および「ホスト型 [SIP](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) フェデレーション プロバイダーを作成または編集する」のトピックで詳しく説明されている設定 [を構成します](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**

「フェデレーション ユーザー アクセスを制御する[](external-access-policies/configure-policies-to-control-federated-user-access.md)ポリシーの構成」、フェデレーションおよびパブリック[IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)接続の有効化または無効化、およびホスト型[SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)フェデレーション プロバイダーの作成または編集に関するトピックで詳しく説明されている設定を構成します。


ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。

