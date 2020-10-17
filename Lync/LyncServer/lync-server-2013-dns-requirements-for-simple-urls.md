---
title: 'Lync Server 2013: 簡易 Url の DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501374"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 の簡易 Url の DNS 要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

Lync Server 2013 は簡易 Url をサポートしており、ユーザーに対して会議に参加しやすくなります。また、管理者にとって Lync Server 管理ツールをより簡単に利用できるようになります。 簡易 Url の詳細については、「 [Lync Server 2013 の簡易 url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。

Lync Server は、次の3つの簡単な Url (会議、ダイヤルイン、および管理者) をサポートします。会議とダイヤルインの簡易 Url を設定する必要があり、管理者の簡易 URL はオプションです。 簡易 url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの簡易 Url の定義方法と、簡易 Url の障害復旧をサポートするかどうかによって決まります。

<div>

## <a name="simple-url-option-1"></a>簡易 URL のオプション 1

オプション 1 では、簡易 URL ごとに新しいベース URL を作成します。

<div class="">


> [!NOTE]  
> 簡易 URL の会議リンクをクリックすると、DNS A レコードによってサーバーが解決され、起動する適切なクライアント ソフトウェアが決定されます。 クライアント ソフトウェアは、起動後に会議がホストされているプールと自動的に通信します。 こうして、DNS A レコードによってどのサーバーまたはプールの簡易 URL に解決されるかに関係なく、適切な会議コンテンツのサーバーに到達できます。



</div>

### <a name="simple-url-option-1"></a>簡易 URL のオプション 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://meet.contoso.com、 https://meet.fabrikam.com など (組織内の SIP ドメインごとに1つずつ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


オプション 1 を使用する場合は、次の内容を定義する必要があります。

  - 簡単な会議 URL ごとに、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。 ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。
    
    組織内に複数の SIP ドメインがあり、このオプションを使用する場合は、各 SIP ドメインに対する会議の簡易 Url を作成する必要があります。また、各会議の簡単な URL の DNS A レコードが必要です。 たとえば、contoso.com と fabrikam.com の両方がある場合は、との両方の DNS A レコードを作成し https://meet.contoso.com https://meet.fabrikam.com ます。
    
    また、複数の SIP ドメインがあり、これらの簡易 URL の DNS レコードおよび証明書の要件を最小限にする場合は、後で説明するオプション 3 を使用します。

  - 簡単なダイヤルイン URL の場合は、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。

  - 簡単な管理 URL は、内部のみで使用します。 簡単な管理 URL では、URL をディレクターの IP アドレスに解決する DNS A レコードが必要です (ディレクターが展開されている場合)。ディレクターが展開されていない場合は、フロントエンド プールのロード バランサーの IP アドレスに解決されます。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。

</div>

<div>

## <a name="simple-url-option-2"></a>簡易 URL のオプション 2

オプション 2 では、会議、ダイヤルイン、および管理用の簡易 URL のベース URL がすべて共通です (lync.contoso.com など)。したがって、これらの簡易 URL に必要な DNS A レコードは 1 つだけです。この DNS A レコードによって、lync.contoso.com をディレクター プールまたはフロントエンド プールの IP アドレスに解決します。プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の 1 台の Standard Edition サーバーの IP アドレスに解決する必要があります。

組織内に複数の SIP ドメインがある状態でも、SIP ドメインごとに簡単な会議 URL を作成する必要があり、簡単な会議 URL ごとに DNS A レコードが必要であることに注意してください。 この例では、3 つの簡易 URL がすべて lync.contoso.com に基づいていますが、別のベース URL を使用して fabrikam.com の簡単な会議 URL を追加で設定します。 この例では、との両方の DNS A レコードを作成する必要があり https://lync.contoso.com https://lync.fabrikam.com ます。 簡易 URL のオプション 3 では、複数の SIP ドメインがある場合の、名前付けと DNS A レコードの処理方法について説明します。

### <a name="simple-url-option-2"></a>簡易 URL のオプション 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meet など (組織内の SIP ドメインごとに1つずつ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>簡易 URL のオプション 3

多くの SIP ドメインがあり、SIP ドメインの簡易 URL を別々にして、これらの簡易 URL の DNS レコードおよび証明書の要件を最小限に抑える場合は、オプション 3 が最も便利です。 この例では、必要な DNS A レコードは 1 つだけです。この DNS A レコードにより、lync.contoso.com をディレクター プールまたはフロントエンド プールの IP アドレスに解決します。

### <a name="simple-url-option-3"></a>簡易 URL のオプション 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>簡易 URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>満たせ</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理者</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>簡易 URL の障害復旧オプション

フロントエンドプールを含む複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体がダウンしても簡単な URL 機能が続行されるように、障害復旧をサポートするための簡単な URL の DNS レコードを設定できます。 この障害復旧機能は、会議とダイヤルインの簡易 Url をサポートしています。

これを構成するには、2 つの GeoDNS アドレスを作成します。各アドレスは、障害の復旧目的でペアになった 2 つのプールに解決される、2 つの DNS A または CNAME レコードを持っています。1 つの GeoDNS アドレスは内部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または内部 Web FQDN に解決されます。もう一つの GeoDNS アドレスは外部アクセスに使用され、2 つのプールのロード バランサー IP アドレス、または外部 Web FQDN に解決されます。以下は、プールの FQDN を使用した、会議簡易 URL の例です。

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

次に、(meet.contoso.com のような) 会議簡易 URL を 2 つの GeoDNS アドレスに解決する CNAME レコードを作成します。

<div class="">


> [!NOTE]  
> ネットワークが<EM></EM>ヘアピン (組織内部からのトラフィックを含め、すべての簡易 URL トラフィックを外部リンク経由でルーティングすること) を使用している場合は、外部 GeoDNS アドレスを構成して、その外部アドレスのみに会議簡易 URL を解決できます。



</div>

この方式を使用するとき、2 つのプールに要求を配布するラウンドロビン方式か、または (地理的に近いプールなど) 1 つのプールに主に接続し、もう 1 つのプールは接続障害の場合にのみ使用するように、各 GeoDNS アドレスを構成できます。

ダイヤルイン簡易 URL でも同じ構成をセットアップできます。 これを行うには、前の例のようなレコードを作成し、 `dialin` `meet` DNS レコードでをに置き換えます。 管理簡易 URL では、このセクションで以前に示した 3 つのオプションのいずれかを使用します。

この構成をセットアップした後に、監視アプリケーションを使用して、障害の監視用に HTTP 監視をセットアップする必要があります。 外部アクセスの場合、監視して、外部 web FQDN または2つのプールのロードバランサー IP アドレスに対する HTTPS の自動検出要求が成功していることを確認します。 たとえば、以下の要求では、**ACCEPT** ヘッダーが含まれないようにし、**200 OK** を戻す必要があります。

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

内部アクセスでは、内部 Web FQDN のポート 5061、または 2 つのプール用のロード バランサー IP アドレスを監視する必要があります。接続問題が検出された場合、これらのプールの VIP は、ポート 80、443、および 444 を閉じる必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

