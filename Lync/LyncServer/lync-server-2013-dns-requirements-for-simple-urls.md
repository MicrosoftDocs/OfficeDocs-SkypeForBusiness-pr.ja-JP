---
title: 'Lync Server 2013: 簡易 URL の DNS 要件'
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
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 の簡易 URL の DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

Lync Server 2013 は、簡単な Url をサポートしており、ユーザーは会議に簡単に参加できます。また、管理者は Lync Server の管理ツールに簡単にアクセスすることができます。 単純な Url の詳細については、「 [Lync Server 2013 での単純な url の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。

Lync Server では、次の3つの簡単な Url (会議、ダイヤルイン、管理) がサポートされています。会議とダイヤルインの簡単な url を設定する必要があります。管理者の単純な URL は省略可能です。 単純な Url をサポートするために必要なドメインネームシステム (DNS) レコードは、これらの単純な Url を定義した方法と、単純な Url の障害回復をサポートするかどうかによって異なります。

<div>

## <a name="simple-url-option-1"></a>単純な URL オプション1

オプション1では、各シンプル URL の新しいベース URL を作成します。

<div class="">


> [!NOTE]  
> ユーザーが簡単な URL 会議リンクをクリックすると、DNS A レコードが解決するサーバーによって、開始する適切なクライアントソフトウェアが決定されます。 クライアントソフトウェアが開始されると、会議がホストされているプールと自動的に通信します。 こうすることで、ユーザーは、どのサーバーまたはプールでも、DNS A レコードが解決される単純な URL を使用するかに関係なく、会議コンテンツに適したサーバーに転送されます。



</div>

### <a name="simple-url-option-1"></a>単純な URL オプション1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://meet.contoso.com、 https://meet.fabrikam.comなどの場合 (組織の SIP ドメインごとに1つ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


オプション1を使用する場合は、次のように定義する必要があります。

  - 両方の会議の単純 URL について、DNS A レコードが必要です。このレコードを使用している場合、ディレクターの IP アドレスに対して URL を解決する必要があります。 それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。
    
    組織内に複数の SIP ドメインがある場合にこのオプションを使用するには、各 SIP ドメインに対して単純な Url を指定する必要があります。また、各会議の単純な URL には DNS A レコードが必要です。 たとえば、contoso.com と fabrikam.com の両方がある場合は、とhttps://meet.contoso.com https://meet.fabrikam.comの両方の DNS A レコードを作成します。
    
    または、複数の SIP ドメインがあり、これらの単純な Url の DNS レコードと証明書の要件を最小限に抑える必要がある場合は、このトピックの後半で説明するように、オプション3を使用します。

  - ダイヤルインのシンプルな URL の場合は、DNS A レコードが必要です。これにより、ディレクターが展開されている場合は、その IP アドレスへの URL が解決されます。 それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。

  - 管理者の簡易 URL は内部のみです。 展開されたディレクターの IP アドレスに URL を解決する DNS A レコードが必要です。 それ以外の場合は、フロントエンドプールのロードバランサーの IP アドレスに解決される必要があります。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。

</div>

<div>

## <a name="simple-url-option-2"></a>単純な URL オプション2

オプション2では、[会議]、[ダイヤルイン]、および [管理者の単純な Url] には、lync.contoso.com などの共通のベース URL があります。 そのため、これらの単純な Url には1つの DNS A レコードのみが必要です。これにより、lync.contoso.com がディレクタープールまたはフロントエンドプールの IP アドレスに解決されます。 プールを展開しておらず、Standard Edition サーバーの展開を使用している場合、DNS A レコードは組織内の1つの Standard Edition サーバーの IP アドレスに解決される必要があります。

組織内に複数の SIP ドメインがある場合は、各 SIP ドメインについての単純な Url の会議を作成する必要があります。また、各会議の単純 URL には DNS A レコードが必要です。 この例では、3つの単純な Url は lync.contoso.com に基づいていますが、fabrikam.com の追加の単純な URL は、別のベース URL で設定されています。 この例では、とhttps://lync.contoso.com https://lync.fabrikam.comの両方の DNS A レコードを作成する必要があります。 [シンプル URL] オプション3には、複数の SIP ドメインがある場合に、名前付けと DNS A レコードを処理する別の方法が表示されます。

### <a name="simple-url-option-2"></a>単純な URL オプション2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meetなどの場合 (組織の SIP ドメインごとに1つ)</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>単純な URL オプション3

オプション3は、多数の SIP ドメインを持っていて、それらのドメインに個別の単純な Url を持たせたいが、DNS レコードと証明書の要件を最小限に抑える必要がある場合に最も役立ちます。 この例では、lync.contoso.com がディレクタープールまたはフロントエンドプールの IP アドレスに解決される DNS A レコードが1つだけ必要です。

### <a name="simple-url-option-3"></a>単純な URL オプション3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>単純な URL</strong></p></td>
<td><p><strong>例</strong></p></td>
</tr>
<tr class="even">
<td><p>即時</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>同期</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>簡単な Url の障害回復オプション

フロントエンドプールが含まれている複数のサイトがあり、DNS プロバイダーが GeoDNS をサポートしている場合は、フロントエンドプール全体が停止した場合でも、簡単な URL 機能が続行されるように、単純な URL の DNS レコードを設定することができます。 この障害回復機能は、会議とダイヤルインのシンプルな Url をサポートしています。

これを構成するには、2つの GeoDNS アドレスを作成します。 各アドレスには2つの DNS A レコードまたは CNAME レコードがあり、これらは1つのプールに対応しているため、それらは共に災害回復目的でペアリングされます。 内部アクセスには1つの GeoDNS アドレスが使われ、2つのプールの内部 web FQDN またはロードバランサー IP アドレスに解決されます。 その他の GeoDNS アドレスは、外部アクセスに使われ、2つのプールの外部 web FQDN またはロードバランサー IP アドレスに解決されます。 次に示すのは、プールの Fqdn を使用した [simple URL の会議] の例です。

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

次に、会議の単純な URL (meet.contoso.com など) を2つの GeoDNS アドレスに解決する CNAME レコードを作成します。

<div class="">


> [!NOTE]  
> ネットワークで<EM>hairpinning</EM> (組織内のトラフィックを含む、すべての単純な url トラフィックをルーティングします) が使用されている場合は、外部 geodns アドレスを構成して、その外部アドレスのみを対象にした単純 url を解決することができます。



</div>

この方法を使用する場合は、ラウンドロビン方式を使って要求を2つのプールに配布するか、主に1つのプール (地理的に近い場所にあるプールなど) に接続して、次の場合にのみ他のプールを使用するように、各 GeoDNS アドレスを構成できます。接続に失敗します。

ダイヤルインの単純な URL に同じ構成を設定することができます。 これを行うには、前の例のように、DNS レコード`dialin`で`meet`の代用として、他のレコードを作成します。 管理者の簡易 URL については、このセクションで既に説明した3つのオプションのいずれかを使用します。

この構成が設定されたら、監視アプリケーションを使用して、エラーを監視するために HTTP 監視を設定する必要があります。 外部アクセスの場合は、2つのプールの外部 web FQDN またはロードバランサー IP アドレスへの HTTPS GET autodiscovery 要求が成功したことを監視して確認します。 たとえば、次の要求には**ACCEPT**ヘッダーが含まれておらず、 **200 OK**を返す必要があります。

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

内部アクセスの場合は、2つのプールの内部 web FQDN またはロードバランサー IP アドレスのポート5061を監視する必要があります。 接続エラーが検出された場合、これらのプールの VIP は、ポート80、443、444を閉じる必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

