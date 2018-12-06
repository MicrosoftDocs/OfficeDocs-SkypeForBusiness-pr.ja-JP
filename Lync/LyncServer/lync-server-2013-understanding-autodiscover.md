---
title: 自動検出について
TOCTitle: 自動検出について
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945654(v=OCS.15)
ms:contentKeyID: 52056716
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 自動検出について

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 の自動検出サービスは、Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月の一部として、Microsoft Lync Server 2010 で最初に導入された機能です。この累積的な更新プログラムでは、修正プログラムを提供する以外に、Lync Mobile クライアントと Lync 2013 クライアントのサポートも行います。

Lync Server 2013 の自動検出サービスは、外部および内部モバイル クライアントの操作にとって不可欠なサービスであり、最近導入された Windows 8 用の Lync Windows ストア アプリのような新しいクライアントにも拡張されました。自動検出は、Lync 2013 デスクトップ クライアントでも使用されます。Lync Server では、自動検出は必須のドメイン ネーム システム (DNS) レコード **lyncdiscover.\<ドメイン\>** および **lyncdiscoverinternal.\<ドメイン\>** によって識別されます。また Lync 2010 および Lync 2013 デスクトップ クライアントの新しいバージョンは、ドメイン ネーム システム (DNS) SRV レコードよりも自動検出を優先し、DNS SRV レコードを使用するのは、lyncdiscover.\<ドメイン\> または lyncdiscoverinternal.\<ドメイン\> が応答しないか解決されない場合だけです。Windows 8 および Lync Mobile 用の Lync Windows ストア アプリ はもっぱら自動検出を使用し、従来の DNS SRV レコードは参照しません。

Lync Server 2013 では、自動検出は、どの要素、機能、および通信方法を利用できるかをクライアントに通知することができるようになりました。情報はクライアントから送信される要求を通して通知され、Lync Server Web サービスは、明確に定義された応答を使用して対応します。この応答には、クライアントが何を利用できるかや、これらの機能に接続する方法が、自動検出応答ドキュメントの形式で指定されています。

自動検出応答ドキュメントを通して Web サービスが機能をクライアントに通知する方法など、自動検出応答ドキュメントを理解する最適な方法は、Lync Web サービスの自動検出応答ドキュメントの一般的な応答の各行を調査し定義することです。

> [!NOTE]
> 後の詳細情報では、ユーザーは、認証要求に応答することによりホーム サーバーを既に認証しています。


> [!NOTE]
> Lync 自動検出 Web サービスは、<strong>Microsoft Developer Network</strong> (MSDN) ライブラリの「<strong>Open Specifications</strong>」セクションの「<strong>Microsoft Office Protocols</strong>」で定義されています。詳細については、完全な仕様のドキュメント「Lync Autodiscover Web Service Protocol」(<a href="http://go.microsoft.com/fwlink/?linkid=273839" class="uri">http://go.microsoft.com/fwlink/?linkid=273839</a>) を参照してください。認証の詳細については、「OC Authentication Web Service Protocol」(<a href="http://go.microsoft.com/fwlink/?linkid=279015" class="uri">http://go.microsoft.com/fwlink/?linkid=279015</a>) を参照してください。


## Lync Server Web サービスの自動検出応答

自動検出要求の送信時に返される応答は、内部クライアントの場合でも外部クライアントの場合でも同じです。位置情報を認識する一部のパラメーターは変更される場合があります。クライアント要求は受信されたが、実際のプールが接続されたプールと異なる場合は、ユーザーのホーム プールがそのユーザーに対して設定されます。ユーザー アカウントが別のプールにあるが、同じオフィスからログインする同僚は、やや違う応答を受信します。応答は、そのユーザーにとって正しいフロント エンド サーバーまたはフロント エンド プールを示します。

自動検出応答ドキュメントの例:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

## 自動検出応答ドキュメント詳細

自動検出応答ドキュメントの書式は 2 つのうちどちらかになります。既定の書式は、JavaScript Object Notation (JSON) です。もう 1 つの書式は、Extensible Markup Language (XML) ドキュメントです。この例では、XML が使用されます。ドキュメントには書式を決定する定義されたスキーマがあるため、要求および応答の書式は予測できます。使用されるスキーマを示すドキュメント内の行は、要求または応答の最初の行です。

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**AccessLocation=”External”** の定義は、外部ユーザーからの要求を示します。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

   &nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess と SipServerExternalAccess は現在使用されていません。これらのエントリは、将来使用するために予約されています。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

   &nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess と SipClientExternalAccess では、内部または外部クライアントが定義済みの SIP サーバーにアクセスするために使用する完全修飾ドメイン名とポートが示されます。Lync デスクトップ クライアントと Lync Windows ストア アプリは、場所 (内部または外部) に基づいてこれらのエントリを使用し、ディレクターとフロント エンド サーバーを見つけます。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

   &nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover` の参照には、自動検出サービスのサービス エントリ ポイントが含まれています。トークン属性には、サービスの名前が含まれ、href はサービスを検出できるクライアントに対して定義される URL です。外部ネットワーク上のクライアントは、`External/Autodiscover` を使用します。自動検出サービスは、展開プロセスの一環としてインストールされます。`Internal/Autodiscover` は現在使用されておらず、将来使用するために予約されています。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

   &nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker` の参照には、内部および外部認証ブローカー サービスのサービス エントリ ポイント (この場合は sip.svc) が含まれています。トークン属性にはサービスの名前が含まれ、href はサービスを検出できるクライアントに対して定義される URL です。内部ネットワーク上のクライアントは `Internal/AuthBroker` を使用します。外部ネットワーク上のクライアントは `External/AuthBroker` を使用します。AuthBroker サービスは、内部 Lync Server 2013 展開 Web サービスの展開プロセスの一環としてインストールされます。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

   &nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler` トークンは、Lync Server 会議の Web ベース スケジュールに対するクライアント アクセス用の URL を参照します。現在、`External/WebScheduler` が使用されています。WebScheduler は、内部 Lync Server 2013 展開 Web サービスの展開プロセスの一環としてインストールされます。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

   &nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` と `External/Mcx` は、モビリティ サービスの場所で、Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月で導入されました。これらの参照は、サポートされているすべてのデバイス上で Lync 2010 Mobile によって引き続き使用されます。Mcx サービスは、内部 Lync Server 2013 展開 Web サービスの展開プロセスの一環としてインストールされます。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

   &nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

   &nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**、**External/Ucwa**、および **Ucwa** を使用すると、クライアントは統合コミュニケーション Web アプリケーション プログラミング インターフェイス (UCWA API、または単に UCWA) にアクセスできるようになります。`Internal/Ucwa` および `External/Ucwa` 仮想ディレクトリは、将来の機能拡張のために予約されているアクセス ポイントで、現在使用されていません。`Ucwa` 仮想ディレクトリは、サポートされているすべてのデバイス上の Microsoft Lync Mobile (Lync Server 2013 で導入) で使用されます。UCWA サービスは、内部 Lync Server 2013 展開 Web サービスの展開プロセスの一環としてインストールされます。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

   &nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、**External/XFrame**、および **XFrame** を使用すると、UCWA ベースのサーバー アプリケーションにアクセスできます。XFrame は、内部 Lync Server 2013 展開 Web サービスの展開プロセスの一環としてインストールされます。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self` トークンは、要求を作成しているクライアントに固有の情報 (ユーザーの応答の種類) を参照します。この要求を作成したクライアントは外部クライアントで、この自動検出の参照先は自動検出サービスのユーザー部分です。

## 関連項目

#### その他のリソース

[Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[自動検出の計画](lync-server-2013-planning-for-autodiscover.md)

