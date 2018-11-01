---
title: フロントエンド プールの DNS 要件
TOCTitle: フロントエンド プールの DNS 要件
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48273388
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# フロントエンド プールの DNS 要件

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、フロントエンド プールの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

## フロントエンド プールの DNS レコード

次の表に、Lync Server 2013 フロントエンド プール展開における DNS の要件を示します。

### フロントエンド プールでの DNS の要件

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
<td><p>複数のフロントエンド サーバーと 1 つのロード バランサー機器で構成されるフロントエンド プール (DNS 負荷分散もそのプールで展開されているかどうかは無関係)</p></td>
<td><p>DNS 負荷分散とロード バランサー機器の両方を使用する場合は、ホスト (A) レコードが必要になります。DNS 負荷分散用のフロント エンド プールの完全修飾ドメイン名 (FQDN) を解決する内部 A レコードを作成します。ロード バランサーの仮想 IP (VIP) アドレスに対する内部 Web サービスの内部ホスト (A) レコードを作成します。トポロジ ビルダーで定義されている内部 Web サービス名を使用する必要があります。</p>
<p>たとえば、DNS 負荷分散とハードウェア負荷分散の両方を使用する場合、DNS 負荷分散用のプール内のフロント エンド サーバーごとに A レコードが 1 つ、ロード バランサー機器の仮想 IP をポイントする内部 Web サービス用に A レコードが 1 つ必要です。</p>
<ul>
<li><p>DNS 負荷分散:   Pool01.contoso.net   プールの IP アドレス   10.10.10.5</p>
<div>

> [!WARNING]
> 各フロント エンド サーバーにも一意の A レコードがあります。


</div>
<ol>
<li><p>FE01.contoso.net    10.10.10.1</p></li>
<li><p>FE02.contoso.net    10.10.10.2</p></li>
<li><p>FE03.contoso.net    10.10.10.3</p></li>
<li><p>FE04.contoso.net    10.10.10.4</p></li>
</ol></li>
<li><p>ハードウェア負荷分散:   WebInternal.contoso.net   HLB VIP の IP アドレス   192.168.10.5</p></li>
</ul>
<p>HTTP/HTTPS トラフィックを除くすべてのトラフィックは、Pool01.contoso.net レコードを使用します。HTTP/HTTPS トラフィックは、定義された内部 Web サービス アドレス 192.168.10.5 を使用します。</p></td>
</tr>
<tr class="even">
<td><p>DNS 負荷分散が展開されているフロントエンド プール</p></td>
<td><p>プールの FQDN をそのプールの各サーバーの IP アドレスに解決する内部 A レコードのセット。プール内のサーバーごとに A レコードが 1 つ必要です。</p></td>
</tr>
<tr class="odd">
<td><p>DNS 負荷分散が展開されているフロントエンド プール</p></td>
<td><p>プール内の各サーバーの FQDN をそのサーバーの IP アドレスに解決する内部 A レコードのセット。詳細については、「計画」のドキュメントの「<a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 での DNS 負荷分散</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>1 つのフロントエンド サーバーおよび専用のバックエンド データベースを備え、ロード バランサーは備えていないフロントエンド プール</p></td>
<td><p>フロントエンド プールの FQDN を 1 つの Enterprise Edition フロントエンド サーバーの IP アドレスに解決する内部 A レコード。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>自動クライアント サインイン</p></td>
<td><p>サポートされている SIP ドメインごとの _sipinternaltls._tcp.&lt;ドメイン&gt; の SRV レコード (ポート 5061 経由)。このレコードは、サインインのクライアント要求を認証およびリダイレクトするフロントエンド プールの FQDN にマップされます。詳細については、「<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアント サインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>デバイス更新 Web サービスをホストするフロントエンド プールの IP アドレスに解決する、名前が ucupdates-r2.&lt;SIP ドメイン&gt; の内部 A レコード。UC デバイスが有効になっていても、ユーザーがデバイスにログインしたことがない場合、デバイスは、A レコードを使用して、デバイス更新 Web サービスをホストするフロントエンド プールを検出し、更新プログラムを取得できます。この方法を実行しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてこの情報を取得します。</p>
<div>

> [!IMPORTANT]
> Lync Server 2010 にデバイス更新 Web サービスの既存の展開がある場合は、ucupdates.&lt;SIP ドメイン&gt; という名前の内部 A レコードが既に作成されています。Microsoft Office Communications Server 2007 R2 の場合は、名前が ucupdates-r2.&lt;SIP ドメイン&gt; の追加の DNS A レコードを作成する必要があります。


</div></td>
</tr>
<tr class="odd">
<td><p>HTTP トラフィックをサポートするためのリバース プロキシ</p></td>
<td><p>Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。詳細については、「計画」のドキュメントの「<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS の要件を確認する</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>


次の表に、内部 Web ファームの FQDN で必要な DNS レコードの例を示します。

### 内部 Web ファームの FQDN のための DNS レコードの例

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
<td><p>フロントエンド サーバーが使用するロード バランサーの VIP アドレスに解決する ee-pool.contoso.com の DNS A レコード。</p>
<p>フロントエンド サーバーが使用するロード バランサーの VIP アドレスに解決する webcon.contoso.com の DNS A レコード。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>フロントエンド プールの Enterprise Edition フロントエンド サーバーが使用するロード バランサーの仮想 IP (VIP) アドレスに解決する ee-pool.contoso.com の DNS A レコード。</p>
<p>このプールで DNS 負荷分散を使用する場合は、フロントエンド プールと内部 Web ファームで同じ FQDN を使用することはできません。</p></td>
</tr>
</tbody>
</table>

