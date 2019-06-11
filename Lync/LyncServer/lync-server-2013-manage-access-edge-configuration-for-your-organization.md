---
title: 'Lync Server 2013: 組織のアクセス エッジ構成の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Lync Server 2013 での組織のアクセス エッジ構成の管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。 空白のトピックがプレースホルダーとして含まれています。

1つ以上のエッジサーバーを展開した後、組織でサポートされているエッジサーバー経由での会議への外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、匿名ユーザーアクセスの種類を有効にする必要があります。

これらのオプションには、[**アクセスエッジ構成**] ページから構成できる次の種類のアクセスがあります。

  - **フェデレーションとパブリック IM 接続**   を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、この機能を有効にします。 この設定は、[**外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザーのスコープに対して構成される SIP フェデレーションと xmpp フェデレーションの両方に適用されます。 フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。
    
    フェデレーションパートナーの検出方法に関するオプションの設定である2つのオプションと、アーカイブの免責事項 (展開によって通信するフェデレーションされた連絡先に通知します。詳細がアーカイブされます) がコンタクトに送信されます。
    
      - **[パートナードメインの検出**   を有効にする] このオプションをオンにすると、フェデレーションできるドメインの自動検出が有効になります。 Lync Server 2013 は、ドメインネームシステム (DNS) レコードを使って、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーからの着信トラフィックを自動的に評価し、信頼レベルに基づいてそのトラフィックを制限またはブロックします。トラフィックの量と管理者の設定。 このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。 このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。 詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。
    
      - **[アーカイブに関する免責事項をフェデレーションパートナー**   に送信する] このオプションをオンにすると、フェデレーションパートナーにアーカイブの免責事項メッセージを送信し、通信の詳細が記録されることを通知します。 フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブの免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。 アーカイブの詳細については、「 [Lync Server 2013 でアーカイブするための要件を定義](lync-server-2013-defining-your-requirements-for-archiving.md)する」を参照してください。

  - **[リモートユーザーアクセス**   を有効にする] このオプションは、出張中の在宅勤務者やユーザーなど、組織内のユーザーが Lync Server に接続できるようにする場合に有効にします。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

  - **[匿名ユーザーが会議**   にアクセスできるようにする] このオプションを有効にすると、内部ユーザーが、自分が開催する会議に外部匿名ユーザーを招待することができます。 この設定を有効にすると、会議の匿名ユーザーのみを許可します。 会議のエクスペリエンスと、ユーザーが会議で何を行うことができるかを定義するオプションと、匿名ユーザーを含めるためのオプションについては、「[サイトまたはユーザーの会議ユーザーエクスペリエンスを作成または変更](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\))する」を参照し[てください。Lync Server 2013 の会議ポリシー設定のリファレンス](lync-server-2013-conferencing-policy-settings-reference.md)。

<div>


> [!NOTE]  
> 外部ユーザーアクセスのサポートを有効にするだけでなく、組織でのリモートユーザーアクセスの使用を制御するポリシーも構成して、ユーザーが外部ユーザーアクセスの種類を利用できるようにする必要があります。 外部ユーザーアクセスのポリシーの作成、構成、適用の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 で外部アクセスポリシーを管理</A>する」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**

  - Access Edge の構成情報は、Windows PowerShell と**CsAccessEdgeConfiguration**コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。
    
    すべてのアクセスエッジの構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsAccessEdgeConfiguration
    
    次のような情報が表示されます。
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013 匿名ユーザー アクセスの有効化または無効化](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

