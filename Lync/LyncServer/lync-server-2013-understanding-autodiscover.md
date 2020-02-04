---
title: 'Lync Server 2013: 自動検出について'
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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Lync Server 2013 での自動検出について

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-06-03_

Lync Server 2013 自動検出サービスは、最初に Microsoft Lync server 2010 で導入された機能です。 Lync Server 2010: 2011 の累積的な更新プログラムの一部として使用されています。 この累積的な更新プログラムでは、修正に加えて、Lync Mobile および Lync 2013 クライアントのサポートが提供されています。

Lync Server 2013 では、自動検出サービスは、外部および内部のモバイルクライアントの操作の重要な部分であり、自動検出も Windows 8 向けの最近導入された Lync Windows ストアアプリなどの新しいクライアントにも拡張されています。 自動検出は、Lync 2013 デスクトップクライアントでも使用されます。 自動検出は、Lync Server では、必要なドメインネームシステム (DNS) レコード lyncdiscover によって認識され**ます。\<domain\> **と**lyncdiscoverinternal。\<ドメイン\>**。 さらに、新しいバージョンの Lync 2010 および Lync 2013 デスクトップクライアントでは、lyncdiscover の場合にのみ DNS SRV レコードを使用して、ドメインネームシステム (DNS) SRV レコードを自動検出します。\<domain\>または lyncdiscoverinternal\<ドメイン\>が応答しないか、解決されません。 Windows 8 および Lync Mobile 用の Lync Windows ストアアプリでは、自動検出のみが使用され、従来の DNS SRV レコードは参照されません。

Lync Server 2013 では、自動検出が拡張され、クライアントに対して、どの要素、機能、通信方法がクライアントから利用可能であるかが表示されます。 情報は、クライアントから送信された要求によって伝達され、Lync Server web サービスは、クライアントが利用できるものと同じように、明確に定義された応答で応答し、自動検出の形式でそれらの機能に連絡する方法を示します。応答ドキュメント。

このドキュメントを通じて web サービスがクライアントに機能をどのようにやり取りするかなど、自動検出応答ドキュメントを理解する最良の方法は、Lync web サービス自動検出応答ドキュメントからの一般的な応答で各行を dissect して定義することです。

<div class="">


> [!NOTE]  
> この後の詳細では、ユーザーは認証要求に応答して、既にホームサーバーに対して認証されています。



</div>

<div class="">


> [!NOTE]  
> Lync 自動検出 Web サービスは、microsoft <STRONG>Developer Network</STRONG> (MSDN) ライブラリの [<STRONG>定義を開く</STRONG>] セクションの<STRONG>microsoft Office プロトコル</STRONG>で定義されます。 詳細については、「Lync の自動検出 Web サービスプロトコル」を参照して<A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>ください。 認証の詳細については、「」の「OC Authentication <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>Web Service Protocol」を参照してください。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web サービスの自動検出の応答

自動検出要求が送信されたときに返される応答は、内部または外部クライアントに対して同じです。 場所によっては、一部のパラメーターが変わることがあります。 クライアント要求を受信したが、実際のプールが、連絡されたもの以外の場合は、ユーザーのホームプールがそのユーザーに設定されます。 ユーザーアカウントが別のプールにあるが、同じ office からログインしている同僚は、若干異なる応答を得ることができます。 応答には、そのユーザーの正しいフロントエンドサーバーまたはフロントエンドプールが示されます。

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

自動検出応答ドキュメントは、次の2つの形式のいずれかで指定できます。 既定の形式は、JavaScript オブジェクト表記 (JSON) です。 その他の形式としては、拡張マークアップ言語 (XML) ドキュメントがあります。 この例では XML が使用されます。 ドキュメントには、書式を決定する定義済みのスキーマが含まれているため、要求と応答は予測可能です。 使用しているスキーマを説明する文書内の行は、要求または応答の最初の行です。

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**Accesslocation = "external"** の定義では、要求が外部ユーザーから行われたことを示します。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess と SipServerExternalAccess は現在使用されていません。 これらのエントリは将来使用するために予約されています。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess と SipClientExternalAccess は、内部または外部のクライアントが定義された SIP サーバーへのアクセスに使用する完全修飾ドメイン名とポートについて説明します。 Lync デスクトップクライアントと Lync Windows ストアアプリでは、これらのエントリを場所 (内部または外部) に基づいて、ディレクターまたはフロントエンドサーバーを見つけるために使用します。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

参照`Autodiscover`には、自動検出サービスのサービスエントリポイントが含まれています。 Token 属性にはサービス名が含まれ、href は、サービスが検出されるクライアントに対して定義する URL です。 外部ネットワーク上のクライアントは、 `External/Autodiscover`を使用します。 自動検出サービスは展開プロセスの一部としてインストールされます。 `Internal/Autodiscover`は現在使用されておらず、将来使用するために予約されています。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

参照`AuthBroker`には、内部および外部認証ブローカーサービスのサービスエントリポイント (この場合は、sip-pstn) が含まれています。 Token 属性にはサービス名が含まれ、href は、サービスが検出されるクライアントに対して定義する URL です。 使用`Internal/AuthBroker`している内部ネットワーク上のクライアント。 外部ネットワーク上のクライアントは、 `External/AuthBroker`を使用します。 AuthBroker サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

トークン`WebScheduler`は、Lync Server 会議の web ベースのスケジュールに対するクライアントアクセスの url を参照します。 現時点では、 `External/WebScheduler`が使用されています。 WebScheduler は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`および`External/Mcx`は、Lync Server 2010 用の累積更新プログラム (2011 年11月) で導入されたモビリティサービスの場所です。 これらの参照は、サポートされているすべてのデバイスで Lync 2010 Mobile によって引き続き使用されます。 Mcx サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされています。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/** ucwa、 **External/Ucwa** 、 **Ucwa**は、クライアントがユニファイドコミュニケーションの WEB アプリケーションプログラミングインターフェイス (ucwa API、または単に ucwa) にアクセスするための手段を提供します。 `Internal/Ucwa``External/Ucwa`仮想ディレクトリは、将来の機能拡張のために予約されているアクセスポイントであり、使用されません。 仮想`Ucwa`ディレクトリは、サポートされているすべてのデバイスで Microsoft lync Mobile (lync Server 2013 で導入) に使用されます。 UCWA サービスは、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、 **External/xframe**と**xframe**は、ucwa ベースのサーバーアプリケーションへのアクセスを提供します。 XFrame は、内部の Lync Server 2013 展開 web サービスの展開プロセスの一部としてインストールされます。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

トークン`Self`は、要求を行うクライアント (ユーザー応答の型) に固有の情報を参照します。 この要求を行ったクライアントは外部であり、この自動検出参照は自動検出サービスのユーザー部分に対するものです。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Lync Server 2013 での自動検出の計画](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

