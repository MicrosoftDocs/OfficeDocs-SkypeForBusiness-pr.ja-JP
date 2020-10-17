---
title: 'Lync Server 2013: 組織のアクセスエッジ構成の管理'
description: 'Lync Server 2013: 組織のアクセスエッジ構成を管理します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2161385f9c03f025bcf6f5e599b7e0276f6d592c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550643"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Lync Server 2013 での組織のアクセスエッジ構成の管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。 空白のトピックがプレースホルダーとして含まれています。

1つ以上のエッジサーバーを展開した後、外部ドメインまたはプロバイダーアクセス、リモートユーザーアクセス、および匿名ユーザーアクセスの種類を有効にして、組織でサポートされるエッジサーバー経由で会議を行う必要があります。

こうしたオプションには、[**アクセス エッジ構成**] ページで構成できる次の種類のアクセスが含まれます。

  - **フェデレーションとパブリック IM 接続**     を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。 この設定は、[ **外部アクセスポリシー** ] ページのグローバル、サイト、またはユーザースコープに対して構成されている SIP フェデレーションと xmpp フェデレーションの両方に適用されます。 フェデレーション設定を適用するには、両方のページでフェデレーションのサポートを構成する必要があります。
    
    フェデレーション パートナーの検出方法に関する省略可能な設定と、(部門でアーカイブが有効になっていること、また通信の詳細情報がアーカイブされることを、通信するフェデレーション連絡先に通知する) アーカイブについての免責事項を連絡先に送信するかどうかという 2 つのオプションが存在します。
    
      - **パートナードメインの検出**     を有効にするこのオプションを選択すると、フェデレーションを行うことができるドメインの自動検出が有効になります。 Lync Server 2013 は、ドメインネームシステム (DNS) レコードを使用して、許可されたドメインリストに含まれていないドメインの検出を試み、検出されたフェデレーションパートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィックの量、および管理設定に基づいてトラフィックを制限またはブロックします。 このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 詳細については、「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。
    
      - **フェデレーションパートナー**     へのアーカイブ免責事項の送信このオプションを選択すると、アーカイブ免責事項メッセージをフェデレーションパートナーに送信して、通信の詳細が記録されることを通知できます。 フェデレーションパートナードメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項の通知を有効にして、展開によってメッセージと通信の詳細がアーカイブされていることをパートナーに警告する必要があります。 アーカイブの詳細については、「 [Lync Server 2013 でのアーカイブの要件の定義](lync-server-2013-defining-your-requirements-for-archiving.md)」を参照してください。

  - **リモートユーザーアクセス**     を有効にするこのオプションを有効にするのは、ユーザーがファイアウォールの外側にいて、在宅中のユーザーが Lync Server に接続できるようにする場合です。 詳細については、「 [Lync Server 2013 でリモートユーザーアクセスを有効または無効](lync-server-2013-enable-or-disable-remote-user-access.md)にする」を参照してください。

  - **匿名ユーザーが会議にアクセスできるように**     する内部ユーザーが外部の匿名ユーザーを開催する会議に招待するようにする場合は、このオプションを有効にします。 この設定を有効にすると、匿名ユーザーのみが会議に対して許可します。 会議の機能と、ユーザーが会議に対して行うことができることと、匿名ユーザーの追加を行うためのオプションを構成するには、「 [サイトまたはユーザーのための会議ユーザーの操作を作成または変更](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) する」および「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。

<div>


> [!NOTE]  
> 外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。 外部ユーザーアクセスのポリシーの作成、構成、および適用の詳細については、「 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 の外部アクセスポリシーの管理</A>」を参照してください。



</div>

**Windows PowerShell コマンドレットを使用してアクセスエッジ構成情報を表示する**

  - アクセスエッジ構成情報は、Windows PowerShell と **set-csaccessedgeconfiguration** コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。
    
    アクセスエッジのすべての構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
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

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013 で匿名ユーザーアクセスを有効または無効にする](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

