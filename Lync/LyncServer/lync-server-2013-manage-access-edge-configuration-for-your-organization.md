---
title: 'Lync Server 2013: 組織のアクセス エッジ構成の管理'
TOCTitle: 組織のアクセス エッジ構成の管理
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ552443(v=OCS.15)
ms:contentKeyID: 49115196
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での組織のアクセス エッジ構成の管理

 

_**トピックの最終更新日:** 2012-11-01_

このドキュメントは暫定版であり、変更される可能性があります。空白のトピックがプレースホルダーとして含まれています。

1 台以上の エッジ サーバーを展開した後、組織でサポートされる エッジ サーバーを利用した、電話会議への外部ドメインまたはプロバイダー アクセス、リモート ユーザー アクセス、および匿名ユーザー アクセスの種類を有効にする必要があります。

こうしたオプションには、\[**アクセス エッジ構成**\] ページで構成できる次の種類のアクセスが含まれます。

  - \[**フェデレーションとパブリック IM 接続を有効にする**\]   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、この設定を有効にします。この設定は、\[**外部アクセス ポリシー**\] ページ上でグローバル、サイト、またはユーザーの各スコープで構成されている SIP フェデレーションと XMPP フェデレーションの両方に適用されます。各フェデレーションの設定を適用するには、双方のページでフェデレーションのサポートを構成する必要があります。
    
    フェデレーション パートナーの検出方法に関する省略可能な設定と、(部門でアーカイブが有効になっていること、また通信の詳細情報がアーカイブされることを、通信するフェデレーション連絡先に通知する) アーカイブについての免責事項を連絡先に送信するかどうかという 2 つのオプションが存在します。
    
      - \[**パートナー ドメインの検出を有効にする**\]   このオプションを選択すると、フェデレーションが可能なドメインの自動検出が有効になります。Lync Server 2013 は、ドメイン ネーム システム (DNS) のレコードを使用して、許可済みのドメイン一覧にないドメインを検出しようとします。同時に、検出されたフェデレーション パートナーからの受信トラフィックが自動的に評価され、信頼レベル、トラフィック量、および管理者設定に応じてそのトラフィックが制限または禁止されます。このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。詳細については、「[Lync Server 2013 での、許可された外部ドメイン向けサポートの構成](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。
    
      - \[**フェデレーション パートナーにアーカイブについての免責事項を送信する**\]   このオプションを選択すると、通信の詳細情報が記録されていることを通知するアーカイブについての免責事項のメッセージをフェデレーション パートナーに送信できます。フェデレーション パートナー ドメインとの外部通信をアーカイブする場合は、アーカイブについての免責事項の通知を有効にして、メッセージや通信の詳細情報が部門によってアーカイブされることをパートナーに警告する必要があります。アーカイブの詳細については、「[Lync Server 2013 でのアーカイブ要件の定義](lync-server-2013-defining-your-requirements-for-archiving.md)」を参照してください。

  - \[**リモート ユーザー アクセスを有効にする**\]   ファイアウォールの外側にいる組織のユーザー (在宅勤務者、出張中のユーザーなど) が Lync Server に接続できるようにする場合は、このオプションを有効にします。詳細については、「[Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化](lync-server-2013-enable-or-disable-remote-user-access.md)」を参照してください。

  - \[**電話会議への匿名ユーザー アクセスを有効にする**\]   内部のユーザーが自分たちの開催する電話会議に外部の匿名ユーザーを招待する場合は、このオプションを有効にします。この設定を有効にするだけで、匿名ユーザーが電話会議に参加できます。電話会議でユーザーがどんなことをどのように行えるのか、また匿名ユーザーの参加の有無を定義する、電話会議のエクスペリエンスおよびオプションを構成する場合の詳細については、「[サイトまたはユーザーのグループの会議のユーザー エクスペリエンスを作成または変更する](https://technet.microsoft.com/ja-jp/library/gg429715\(v=ocs.15\))」と「[Lync Server 2013 での会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。

> [!NOTE]
> 外部ユーザー アクセスのサポートを有効にする以外に、いずれかの種類の外部ユーザー アクセスを利用可能にする前に、組織内でのリモート ユーザー アクセスの使用を制御するポリシーの構成も行います。外部ユーザー アクセスのポリシーの作成、構成、および適用の詳細については、「<a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 での組織の外部アクセス ポリシーの管理</a>」を参照してください。


**Windows PowerShell コマンドレットを使用したアクセス エッジ構成情報の表示**

  - アクセス エッジ構成情報は、Windows PowerShell と **Get-CsAccessEdgeConfiguration** コマンドレットを使用して表示できます。このコマンドレットは、Lync Server 2013 管理シェル または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。
    
    すべてのアクセス エッジ構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
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

## このセクション中

  - [Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Lync Server 2013 匿名ユーザー アクセスの有効化または無効化](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

