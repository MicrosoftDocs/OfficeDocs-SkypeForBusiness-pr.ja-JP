---
title: Lync Server と Office Communications Server のフェデレーションの計画
TOCTitle: Lync Server と Office Communications Server のフェデレーションの計画
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48273570
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server と Office Communications Server のフェデレーションの計画

 

_**トピックの最終更新日:** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションは、ピアツーピアでマルチパーティの通信をサポートします。ピアツーピアの会話をマルチパーティの会話にエスカレートでき、臨時の会議を実行できます。会議 – Web 会議または音声ビデオ会議をスケジュールし、組織内の連絡先およびフェデレーションしているパートナーの連絡先を含めることができます。

Microsoft Office Live Communications Server 2005 で初めて登場し、サポートされる唯一の種類のフェデレーションは、直接フェデレーションでした。直接フェデレーションでは、フェデレーション パートナーのセッション開始プロトコル (SIP) ドメインと、パートナーのエッジ サーバーの完全修飾ドメイン名 (FQDN) を知っている必要がありました。Live Communications Server 2005 SP1 ではフェデレーションの種類が追加されましたが、そのすべてで、エッジ サーバーを探すためにドメイン ネーム システム (DNS) SRV レコードがフェデレーション パートナーによって公開されている必要がありました。そのリリースで使用されていた用語は次のとおりです。

  - *オープン拡張フェデレーション*: あらゆる SIP ドメイン名を受け入れ、DNS SRV を使用してパートナー エッジ サーバーを探す

  - *拡張フェデレーション*: パートナーの SIP ドメイン名を組織のフェデレーション パートナーとして構成し、DNS SRV を使用してパートナー エッジ サーバーを探す

  - *直接フェデレーション*: パートナーの SIP ドメイン名と、パートナーのエッジ サーバーに対する FQDN を構成する

  - *サーバー許可リスト*: あらゆるドメインを受け入れ、DNS SRV を使用してホスティング プロバイダーまたはパブリック インスタント メッセージング (IM) 接続プロバイダーのエッジ サーバーを探す

Microsoft Office Communications Server 2007 では、各フェデレーションの種類で実際に行われることをより的確に表すように、フェデレーションの種類の名前が変更されました。

  - オープン拡張フェデレーションは、*検出済みのパートナー ドメイン*に変更

  - 拡張フェデレーションは、*許可されたパートナー ドメイン*に変更

  - 直接フェデレーションは、*許可されたパートナー サーバー*に変更

  - サーバー許可リストは、*ホスティング プロバイダー*および*パブリック IM プロバイダー*に変更

Microsoft Lync Server 2010 では、Microsoft Lync Online 2010 と Microsoft Office 365 に従ってホスティング プロバイダーの定義が狭められるとともに、許可されたパートナー ドメインのフェデレーションの種類によって定義されるものと同じ許可リストに従うようになりました。

Microsoft Lync Server 2013、Lync Server 2010、および Office Communications Server の間のフェデレーションを有効にすると、エッジ サーバーとリバース プロキシを使用して、ユーザーが定義するルールと許可されたパートナー ドメインが適用されます。計画の観点からは、他の Lync Server および Office Communications Server とのフェデレーションには以下が必要になります。

  - トポロジ ビルダーでフェデレーションを有効にします。詳細については、「展開」のトピック「[Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)」を参照してください。

  - フェデレーションされたドメインの検出に対する要件を決定します。
    
      - フェデレーションを手動で構成する場合、パートナーのエッジ サーバーの完全修飾ドメイン名 (FQDN) つまりオンライン ドメイン名が必要です。これは、Lync Server コントロール パネル の \[**フェデレーションと外部アクセス**\]、\[**SIP フェデレーション ドメイン**\] に入力します。FQDN によってドメインを許可または禁止するには、ポリシーを**新規作成**するか、既存のポリシーを**編集**します。
        

        > [!WARNING]
        > フェデレーション パートナーのエッジ サーバーを手動で構成すると、パートナーがエッジ サーバーの IP アドレスを変更したときにエラーが発生しやすくなります。

        
        > [!NOTE]  
        > [<strong>新規 SIP フェデレーション ドメイン</strong>] については、Microsoft Lync Online、Microsoft Office 365 の [<strong>ドメイン名 (または FQDN)</strong>] を指定する必要があります。Microsoft Lync Server 2013、Lync Server 2010 および Office Communications Server については、[<strong>アクセス エッジ サービス (FQDN)</strong>] も指定する必要があります。
    
      - 検出済みのパートナーのフェデレーションの場合、パートナーがこちらのエッジ サーバーを検出できますが、エッジ サーバーのポート 5061 およびホスト (A) レコードをポイントする SRV レコードを、こちらの外部 DNS に作成します (\_sipfederationtls.\_tcp.contoso.com)。
        

        > [!IMPORTANT]
        > Windows Phone または Apple iPhone、iPad、その他の Apple デバイス上で Microsoft Lync Mobile クライアントをサポートしており、プッシュ通知サービスまたはプッシュ通知サービスを使用している場合、Lync Mobile クライアントを使用する SIP ドメインごとに _sipfederationtls._tcp. <EM>&lt;SIP ドメイン&gt;</EM> の SRV レコードを計画する必要があります。Android と Nokia Symbian の Lync Mobile はプッシュ通知を使用しないため、この要件は適用されません。



  - フェデレーションされたドメインをサポートするように外部ユーザー アクセス ポリシーを構成します

  - セッション開始プロトコル (SIP)、Web 会議、音声ビデオ用にファイアウォールのポートを開き、有効にしているフェデレーションまたは連絡先に対応します。詳細については、「[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)」を参照してください。

Microsoft Lync Server 2013 および Lync Server 2010 とのフェデレーション用の証明書、ポート/プロトコル、DNS の要件を定義するときは、次の情報が役に立ちます。

証明書、ファイアウォール、ポート/プロトコルの要件および DNS の要件の計画は、Microsoft Lync Server 2013 エッジ サーバーを計画または展開してある場合は一般に簡単なプロセスです。フェデレーションは既存のエッジ サーバーを使用する追加機能なので、計画の要件は通常はエッジ サーバーの計画と展開によって満たされます。次の表を使用して要件が満たされていることを確認し、それに従ってポート/プロトコルおよび DNS を変更します。


> [!IMPORTANT]
> エッジ サーバーのプールがあり、Lync Server 2013 または Lync Server 2010 のパートナーとフェデレーションしている場合は、エッジ サーバーの内側または外側で DNS 負荷分散またはロード バランサー機器を使用できます。Office Communications Server 2007 または Office Communications Server 2007 R2 とフェデレーションしている場合は、ロード バランサー機器によってエッジ サーバーの場合のフェールオーバー サポートが提供されます。Office Communications Server 2007 および Office Communications Server 2007 R2 は、DNS 負荷分散には対応していません。パートナーのエッジ サーバーは、プール内で最初に応答したエッジ サーバーと通信を確立します。そのエッジ サーバーで障害が発生した場合、通信は自動的にはフェールオーバーしません。



証明書の要件は、通常、選択したエッジ サーバーまたはプールされたエッジ サーバーの計画に対する証明書の計画によって満たされます。

## このセクション中

  - [証明書の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [ポートの概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## 関連項目

#### タスク

[Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### 概念

[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  

#### その他のリソース

[Lync Server 2013 での組織のアクセス エッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

