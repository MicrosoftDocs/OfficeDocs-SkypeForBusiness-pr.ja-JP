---
title: 'Lync Server 2013: Skype for Business Server へのフェデレーションと外部アクセスの管理'
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
localization_priority: Normal
description: 外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが社内の Skype for Business Server ユーザーと共同作業できるようにするかどうかを制御します。
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280104"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Skype for Business Server へのフェデレーションと外部アクセスの管理

エッジサーバーまたはエッジプールの展開は、外部ユーザーをサポートするための最初の手順です。 エッジサーバーの展開の詳細については、「 [Skype For Business server でエッジサーバーを展開](../../deploy/deploy-edge-server/deploy-edge-server.md)する」を参照してください。

Skype for Business Server の内部展開をインストールして構成した後、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。 共同作業には、インスタントメッセージの送受信、プレゼンス状態の更新、会議 (「会議」とも呼ばれます) の参加が含まれます。 外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが社内の Skype for Business Server ユーザーと共同作業できるようにするかどうかを制御します。 外部ユーザーには、展開のリモートユーザー、フェデレーションされたユーザー (パブリックインスタントメッセージング (IM) サービスプロバイダーのサポート対象ユーザーを含む)、および会議の匿名参加者を含めることができます。

展開に Skype for Business Server Edge サーバーまたはエッジプールのインストールが含まれている場合は、可能な通信の種類の範囲が、外部ユーザーアクセスのさまざまなオプションを使用して大幅に拡張され、他の SIP フェデレーションのメンバーとの通信が可能になります。ドメインと SIP フェデレーションプロバイダー。 エッジサーバーまたはエッジプールをセットアップした後、提供する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するためのポリシーを構成します。 Skype for Business Server では、タスクの要件に基づいて、skype for Business Server コントロールパネル、 [skype For Business Server 管理シェル](../management-shell.md)、またはその両方を使用して、外部ユーザーのアクセスとポリシーを有効にして構成します。 



> [!IMPORTANT]  
> 外部ユーザーアクセスの構成とポリシーを設計する場合は、ポリシーの優先順位とポリシーの適用方法を理解しておく必要があります。 1つのポリシーレベルで適用される Skype for Business Server のポリシー設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。


既定では、組織で外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするようにポリシーは構成されません。 外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。 これには、次の外部アクセスポリシーが含まれます。

  - **グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。 既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。 グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。 グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。 グローバルポリシーを削除しても、削除されることはありません。 代わりに、既定の設定にリセットします。

  - **サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。 サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。 たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。 既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。

  - **ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。 ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。 たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。 ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。

作成または編集する必要のある構成設定とポリシーを決定するには、次の決定ポイントを参照してください。

**インスタントメッセージング、Web 会議、音声/ビデオを使用して、ドメインの内部および外部ユーザーが共同作業できるようにする必要がありますか?**

「リモートユーザーのアクセスを[制御するポリシーを構成する](external-access-policies/configure-policies-to-control-remote-user-access.md)」と「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明に従って設定を構成します。

**組織内のユーザーによってホストされている会議への参加を匿名ユーザーに許可するかどうかを指定します。**

「[会議ポリシーを割り当てて、匿名ユーザーをサポート](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)し、[会議ポリシーを作成](../conferencing/create-policies.md)する」で説明するように設定を構成します。

**SIP フェデレーションドメイン連絡先との通信をユーザーに許可しますか?**

「フェデレーションされたユーザーアクセスの制御」、「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」、または「[組織の SIP フェデレーションドメインを管理](sip-domains/manage-sip-federated-domains-for-your-organization.md)[するためのポリシーを構成する](external-access-policies/configure-policies-to-control-federated-user-access.md)」の説明に従って設定を構成します。


**SIP フェデレーションドメインとの通信を有効にしている場合、SIP フェデレーション自動検出を有効にしますか?**

「[フェデレーションパートナーの検出を有効または無効](access-edge/enable-or-disable-discovery-of-federation-partners.md)にする」のトピックで詳しく説明するように設定を構成します。

**SIP フェデレーションドメインとの通信を有効にしている場合は、アーカイブを使用していて、通信がアーカイブされていることを通知するフェデレーションされた連絡先への免責事項の送信を有効にしますか?**

「[統合パートナーへのアーカイブの免責事項の送信を有効または無効](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」のトピックで説明するように設定を構成します。

**パブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信をユーザーに許可しますか?**

「パブリックユーザーアクセスの制御」、「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」、「[パブリック SIP フェデレーションプロバイダーの作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)」という、「[ポリシーを構成する](external-access-policies/configure-policies-to-control-public-user-access.md)」のように設定を構成します。


**Microsoft Office 365 および Skype for Business Online を実行しているホスティングプロバイダーである SIP フェデレーションプロバイダーとの通信をユーザーに許可しますか?**

詳細については、「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」および「ホストされた[SIP フェデレーションプロバイダーを作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)する」を参考にして設定を構成します。

**展開は、分割 (ハイブリッド) ドメインで構成されます。一部のユーザーは、オンプレミスの展開でホームサーバーを使用していますが、他のユーザーはオンライン環境でホームサーバーを使用して構成されていますか?**

「ポリシーを構成して[フェデレーションユーザーアクセスの制御](external-access-policies/configure-policies-to-control-federated-user-access.md)」、「[フェデレーションとパブリック IM 接続を有効または無効](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)にする」、「ホストされた[SIP フェデレーションプロバイダーを作成または編集](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)する」のように設定を構成します。


外部ユーザーアクセスを制御するために使用するポリシーなど、組織の外部ユーザーアクセスを有効にしていない場合でも、外部ユーザーアクセスの設定を構成できます。 ただし、構成したポリシーとその他の設定は、組織で外部ユーザーのアクセスが有効になっている場合にのみ有効になります。 外部ユーザーのアクセスが無効になっている場合、または外部ユーザーのアクセスポリシーがサポートされていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開では、外部ユーザーの種類 (会議 ID によって認証された匿名ユーザー、会議の作成および参加者の招待時に匿名の参加者に送信されるパスキー) を認証します。edge サポートの構成方法に基づくアクセス。 通信を制御するために、1つまたは複数のポリシーを構成し、展開の内外のユーザーとの通信方法を定義する設定を構成することができます。 ポリシーと設定には、外部ユーザーアクセスの既定のグローバルポリシーに加えて、特定のサイトまたはユーザーに対して1つ以上の種類の外部ユーザーアクセスを有効にするために作成および構成できるサイトとユーザーのポリシーが含まれます。

