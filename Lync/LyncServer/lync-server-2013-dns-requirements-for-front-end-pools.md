---
title: 'Lync Server 2013: フロントエンドプールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドプールの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-07_

このセクションでは、フロントエンドプールの展開に必要なドメインネームシステム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-front-end-pools"></a>フロントエンドプールの DNS レコード

次の表は、Lync Server 2013 フロントエンドプールの展開の DNS 要件を示しています。

### <a name="dns-requirements-for-a-front-end-pool"></a>フロントエンドプールの DNS 要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>展開シナリオ</th>
<th>DNS 要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>複数のフロントエンドサーバーとハードウェアロードバランサーを備えたフロントエンドプール (このプールには DNS 負荷分散も展開されているかどうかにかかわらず)</p></td>
<td><p>DNS ロードバランシングとハードウェアロードバランサーの両方を使用する場合は、(A) レコードをホストする必要があります。 DNS の負荷分散のために、フロントエンドプールの完全修飾ドメイン名 (FQDN) を解決する内部 A レコードを作成します。 内部 Web サービスの内部ホスト (A) レコードを、ロードバランサーの仮想 IP (VIP) アドレスに作成します。 トポロジビルダーで定義されている内部 Web サービス名を使用する必要があります。</p>
<p>たとえば、DNS の負荷分散とハードウェアの負荷分散の両方を使用する場合は、DNS の負荷分散用のプール内の各フロントエンドサーバーの A レコードと、ハードウェアロードバランサーの仮想 IP を指す内部 Web サービスの A レコードがあります。:</p>
<ul>
<li><p>DNS の負荷分散: Pool01.contoso.net プールの IP アドレス10.10.10.5</p>
<div>

> [!WARNING]  
> 各フロントエンドサーバーにも、個別のレコードがあります。


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>ハードウェア負荷分散: HLB VIP 192.168.10.5 の WebInternal.contoso.net IP アドレス</p></li>
</ul>
<p>HTTP/HTTPS トラフィック以外のすべてのトラフィックでは、Pool01.contoso.net レコードが使用されます。 HTTP/HTTPS トラフィックでは、定義された内部 Web サービスのアドレスを使用します192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>DNS 負荷分散が展開されたフロントエンドプール</p></td>
<td><p>プールの FQDN を、プールの各サーバーの IP アドレスに解決する内部 A レコードのセット。 プール内の各サーバーに1つのレコードが必要です。</p></td>
</tr>
<tr class="odd">
<td><p>DNS 負荷分散が展開されたフロントエンドプール</p></td>
<td><p>プール内の各サーバーの FQDN をそのサーバーの IP アドレスに解決する内部 A レコードのセット。 詳細については、計画ドキュメントの「 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 での DNS の負荷分散</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>フロントエンドサーバーと、専用のバックエンドデータベースを備えたフロントエンドプール (ロードバランサーはありません)</p></td>
<td><p>フロントエンドプールの FQDN を単一の Enterprise Edition フロントエンドサーバーの IP アドレスに解決する内部の A レコード。</p></td>
</tr>
<tr class="odd">
<td><p>自動クライアントサインイン</p></td>
<td><p>サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp&lt;サインイン&gt;のためのクライアント要求を認証してリダイレクトするフロントエンドプールの FQDN にマップされる、ポート5061経由のドメイン。 詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>ユニファイドコミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>"Ucupdates-r2" という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストしているフロントエンドプールの IP アドレスに解決される SIP ドメイン。 UC デバイスが有効になっている状態で、ユーザーがデバイスにログインしたことがない場合、A レコードにより、デバイスはデバイス更新 Web サービスをホストするフロントエンドプールを検出し、更新プログラムを入手できます。 そうしないと、デバイスは、ユーザーが初めてログインしたときに、インバンドプロビジョニングでこの情報を取得します。</p>
<div>

> [!IMPORTANT]  
> Lync Server 2010 で既存のデバイス更新 Web サービスを展開している場合は、「ucupdates」という名前の内部レコードが既に作成されています。&lt;SIP ドメイン&gt;。 Microsoft Office Communications Server 2007 R2 の場合は、ucupdates-R2 という名前の追加 DNS A レコードを作成する必要があります。&lt;SIP ドメイン&gt;。


</div></td>
</tr>
<tr class="odd">
<td><p>HTTP トラフィックをサポートする逆プロキシ</p></td>
<td><p>外部の web ファーム FQDN をリバースプロキシの外部 IP アドレスに解決する外部の A レコード。 クライアントと UC デバイスこのレコードを使ってリバースプロキシに接続します。 詳細については、「計画ドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


次の表は、内部 web ファーム FQDN に必要な DNS レコードの例を示しています。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>内部 Web ファーム FQDN の DNS レコードの例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>内部 web ファーム FQDN</th>
<th>プールの FQDN</th>
<th>DNS A レコード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS A フロントエンドサーバーによって使用されるロードバランサーの VIP アドレスに解決される ee-pool.contoso.com のレコード。</p>
<p>DNS A フロントエンドサーバーによって使用されるロードバランサーの VIP アドレスに解決される webcon.contoso.com のレコード。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS A ee-pool.contoso.com の A レコード。フロントエンドプールの Enterprise Edition フロントエンドサーバーによって使用されるロードバランサーの仮想 IP (VIP) アドレスに解決されます。</p>
<p>このプールで DNS の負荷分散を使用している場合は、フロントエンドプールと内部 web ファームの FQDN を同じにすることはできません。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

