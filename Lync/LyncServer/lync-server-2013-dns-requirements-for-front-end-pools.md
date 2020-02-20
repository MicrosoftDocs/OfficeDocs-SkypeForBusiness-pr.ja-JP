---
title: 'Lync Server 2013: フロントエンドプールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18c5b7d16cf5bb7fe13c68a025e9033899c62c4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 のフロントエンドプールの DNS 要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-07_

ここでは、フロント エンド プールの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

<div>

## <a name="dns-records-for-front-end-pools"></a>フロント エンド プールの DNS レコード

次の表は、Lync Server 2013 フロントエンドプール展開の DNS 要件を示しています。

### <a name="dns-requirements-for-a-front-end-pool"></a>フロント エンド プールでの DNS の要件

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
<td><p>複数のフロント エンド サーバーと 1 つのロード バランサー機器で構成されるフロント エンド プール (DNS 負荷分散もそのプールで展開されているかどうかは無関係)</p></td>
<td><p>DNS 負荷分散とロード バランサー機器の両方を使用する場合、ホスト (A) レコードが必要です。 DNS 負荷分散用にフロント エンド プールの完全修飾ドメイン名 (FQDN) を解決する内部 A レコードを作成します。 ロード バランサーの仮想 IP (VIP) アドレスに解決する、内部 Web サービス用の内部ホスト (A) レコードを作成します。 トポロジビルダーで定義されているように、内部 Web サービスの名前を使用する必要があります。</p>
<p>たとえば、DNS 負荷分散とハードウェア負荷分散の両方を使用する場合は、DNS 負荷分散用のプール内の各フロントエンドサーバー用の A レコードと、ロードバランサー機器の仮想 IP を指す内部 Web サービスの A レコードが存在します。:</p>
<ul>
<li><p>DNS 負荷分散:   Pool01.contoso.net   プールの IP アドレス   10.10.10.5</p>
<div>

> [!WARNING]  
> 各フロントエンドサーバーには、個別の A レコードもあります。


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>ハードウェア負荷分散:   WebInternal.contoso.net   HLB VIP の IP アドレス   192.168.10.5</p></li>
</ul>
<p>HTTP/HTTPS トラフィックを除くすべてのトラフィックで Pool01.contoso.net レコードが使用されます。HTTP/HTTPS トラフィックでは、定義済みの内部 Web サービス アドレスの 192.168.10.5 が使用されます。</p></td>
</tr>
<tr class="even">
<td><p>DNS 負荷分散が展開されているフロント エンド プール</p></td>
<td><p>プールの FQDN をそのプールの各サーバーの IP アドレスに解決する内部 A レコードのセット。プール内のサーバーごとに A レコードが 1 つ必要です。</p></td>
</tr>
<tr class="odd">
<td><p>DNS 負荷分散が展開されているフロント エンド プール</p></td>
<td><p>プール内の各サーバーの FQDN をそのサーバーの IP アドレスに解決する内部 A レコードのセット。 詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing In Lync Server 2013</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>1 つのフロント エンド サーバーおよび専用のバックエンド データベースを備え、ロード バランサーは備えていないフロント エンド プール</p></td>
<td><p>フロント エンド プールの FQDN を 1 つの Enterprise Edition フロント エンド サーバーの IP アドレスに解決する内部 A レコード。</p></td>
</tr>
<tr class="odd">
<td><p>自動クライアント サインイン</p></td>
<td><p>サポートされている各 SIP ドメインについて、_sipinternaltls の SRV レコード。 _tcp。&lt;サインイン&gt;のためのクライアント要求を認証およびリダイレクトするフロントエンドプールの FQDN にマップされる、ドメインオーバーポート5061。 詳細については、「 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアントサインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>Ucupdates-r2 という名前の内部 A レコード。&lt;デバイス更新&gt; Web サービスをホストするフロントエンドプールの IP アドレスに解決される SIP ドメイン。 UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするフロント エンド プールを検出し、更新プログラムを取得できます。 この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてこの情報を取得します。</p>
<div>

> [!IMPORTANT]  
> Lync Server 2010 でのデバイス更新 Web サービスの既存の展開がある場合は、ucupdates という名前の内部 A レコードが既に作成されています。&lt;SIP ドメイン&gt;。 Microsoft Office Communications Server 2007 R2 の場合は、ucupdates-R2 という名前で追加の DNS A レコードを作成する必要があります。&lt;SIP ドメイン&gt;。


</div></td>
</tr>
<tr class="odd">
<td><p>HTTP トラフィックをサポートするためのリバース プロキシ</p></td>
<td><p>Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。 クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。 詳細については、「計画」のドキュメントの「 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS 要件を決定</a>する」を参照してください。</p></td>
</tr>
</tbody>
</table>


次の表に、内部 Web ファームの FQDN で必要な DNS レコードの例を示します。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>内部 Web ファームの FQDN のための DNS レコードの例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>内部 Web ファームの FQDN</th>
<th>プールの FQDN</th>
<th>DNS A レコード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>フロント エンド サーバーが使用するロード バランサーの VIP アドレスに解決する ee-pool.contoso.com の DNS A レコード。</p>
<p>フロント エンド サーバーが使用するロード バランサーの VIP アドレスに解決する webcon.contoso.com の DNS A レコード。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>フロント エンド プールの Enterprise Edition フロント エンド サーバーが使用するロード バランサーの仮想 IP (VIP) アドレスに解決する ee-pool.contoso.com の DNS A レコード。</p>
<p>このプールで DNS 負荷分散を使用する場合は、フロント エンド プールと内部 Web ファームで同じ FQDN を使用することはできません。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

