---
title: 'Lync Server 2013: 自動検出について'
description: 'Lync Server 2013: 自動検出について説明します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295aba4bffbe5d17070702203cfd933284cb12c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547353"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a>Lync Server 2013 の自動検出について

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-06-03_

Lync Server 2013 自動検出サービスは、Lync Server 2010:11 月 11 2011 日の累積的な更新プログラムの一部として、Microsoft Lync Server 2010 で最初に導入された機能です。 修正に加えて、この累積的な更新プログラムは Lync Mobile および Lync 2013 クライアントのサポートを提供していました。

Lync Server 2013 では、自動検出サービスは、外部および内部のモバイルクライアントの操作の重要な部分であり、自動検出も、Windows 8 用の最近導入された Lync Windows ストアアプリなどの新しいクライアントにまで拡張されます。 自動検出は、Lync 2013 デスクトップクライアントでも使用されます。 自動検出は、必要なドメインネームシステム (DNS) レコード lyncdiscover によって Lync Server で認識され**ます。 \<domain\> ** **lyncdiscoverinternal \<domain\> ** さらに、Lync 2010 および Lync 2013 デスクトップクライアントの新しいバージョンでは、lyncdiscover の場合にのみ DNS SRV レコードを使用して、ドメインネームシステム (DNS) SRV レコードよりも自動検出を優先します。\<domain\> または lyncdiscoverinternal。\<domain\> 応答しない、または解決されません。 Windows 8 および Lync Mobile 用の Lync Windows ストアアプリは、自動検出のみを使用し、従来の DNS SRV レコードを参照することはありません。

Lync Server 2013 では、自動検出が拡張され、クライアントが使用できる要素、機能、および通信方法をクライアントに通知します。 情報はクライアントから送信された要求を通じて伝達され、Lync Server web サービスは、クライアントが使用できるものという名前の明示的に定義された応答と共に応答し、それらの機能を自動検出応答ドキュメントの形式で連絡する方法を示します。

Web サービスがこのドキュメントを使用してクライアントに機能を伝達する方法など、自動検出応答ドキュメントを理解するための最善の方法は、dissect して、Lync web サービス自動検出応答ドキュメントからの一般的な応答で各行を定義することです。

<div class="">


> [!NOTE]  
> この後の詳細では、ユーザーは認証要求に応答して既にホームサーバーに認証されています。



</div>

<div class="">


> [!NOTE]  
> Lync 自動検出 Web サービスは、microsoft <STRONG>Developer Network</STRONG> (MSDN) ライブラリの [<STRONG>オープン仕様</STRONG>] セクションにある<STRONG>microsoft Office プロトコル</STRONG>で定義されています。 詳細については、「」の「完全な仕様書」、「Lync 自動検出 Web サービスプロトコル」、および「」を参照してください <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> 。 認証の詳細については、「」の「OC Authentication Web Service Protocol」を参照してください <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> 。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web サービスの自動検出応答

自動検出要求が送信されたときに返される応答は、内部または外部クライアントに対して同じです。 場所に対応する一部のパラメーターは変更される場合があります。 クライアント要求を受信したが、実際のプールが、接続されているもの以外の場合は、そのユーザーに対してユーザーのホームプールが設定されます。 ユーザーアカウントが異なるプールにあり、同じ office からログインしている同僚は、多少異なる応答をします。 応答は、そのユーザーの適切なフロントエンドサーバーまたはフロントエンドプールを示します。

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

<div>

## <a name="autodiscover-response-document-details"></a>自動検出応答ドキュメントの詳細

自動検出応答ドキュメントは、次の2つの形式のいずれかにすることができます。 既定の形式は、JavaScript Object Notation (JSON) です。 もう1つの形式は、拡張マークアップ言語 (XML) ドキュメントです。 この例では、XML を使用します。 ドキュメントには、形式を決定する定義済みスキーマがあるため、要求と応答は予測できます。 使用されるスキーマを記述するドキュメント内の行は、要求または応答の最初の行です。

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**Accesslocation = "external"** の定義は、要求が外部ユーザーから行われたことを示します。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess と SipServerExternalAccess は現在使用されていません。 これらのエントリは、今後の使用のために予約されています。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess and SipClientExternalAccess は、内部または外部のクライアントが定義された SIP サーバーへのアクセスに使用する完全修飾ドメイン名とポートを説明します。 Lync デスクトップクライアントおよび Lync Windows ストアアプリは、これらのエントリを、その場所 (内部または外部) に基づいて、ディレクターまたはフロントエンドサーバーを検索するために使用します。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

参照には、 `Autodiscover` 自動検出サービスのサービスエントリポイントが含まれています。 Token 属性には、サービスの名前が含まれ、href はサービスが存在するクライアントに対して定義される URL です。 外部ネットワーク上のクライアントは、を使用し `External/Autodiscover` ます。 自動検出サービスは、展開プロセスの一部としてインストールされます。 `Internal/Autodiscover` は現在使用されておらず、将来の使用のために予約されています。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

参照には、 `AuthBroker` 内部および外部認証ブローカーサービス (この場合は sip-pstn) のサービスエントリポイントが含まれています。 Token 属性には、サービスの名前が含まれ、href はサービスが存在するクライアントに対して定義される URL です。 使用している内部ネットワーク上のクライアント `Internal/AuthBroker` 。 外部ネットワーク上のクライアントは、を使用し `External/AuthBroker` ます。 AuthBroker サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

この `WebScheduler` トークンは、Lync Server 会議の web ベースのスケジュールに対するクライアントアクセスの url を参照します。 現時点では、 `External/WebScheduler` がのみ使用されます。 WebScheduler は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` および `External/Mcx` は、Mobility service の場所です。 Lync Server 2010 用の累積的な更新プログラム (11 月 2011) で導入されました。 これらの参照は、サポートされているすべてのデバイスで Lync 2010 Mobile によって引き続き使用されます。 Mcx サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/ucwa**、 **External/Ucwa** および **Ucwa** は、クライアントが統合コミュニケーション Web アプリケーションプログラミングインターフェイス (ucwa API、または単に ucwa) にアクセスする手段を提供します。 `Internal/Ucwa``External/Ucwa`仮想ディレクトリは、将来の機能拡張のために予約されたアクセスポイントであり、使用されません。 `Ucwa`サポートされているすべてのデバイスで、仮想ディレクトリが Microsoft Lync Mobile (Lync Server 2013 で導入されました) に使用されます。 UCWA サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`**外部/xframe**および**xframe**は、ucwa ベースのサーバーアプリケーションへのアクセスを提供します。 XFrame は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

トークンは、 `Self` 要求を行っているクライアント (ユーザー応答の種類) に固有の情報を参照します。 この要求を行ったクライアントは外部であり、この自動検出の参照は自動検出サービスのユーザー部分に対するものです。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Lync Server 2013 での自動検出の計画](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

