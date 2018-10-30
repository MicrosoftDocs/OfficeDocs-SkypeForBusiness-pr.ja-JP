---
title: Standard Edition サーバーの DNS 要件
TOCTitle: Standard Edition サーバーの DNS 要件
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48271855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standard Edition サーバーの DNS 要件

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、Standard Edition サーバーの展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

## Standard Edition サーバーの DNS レコード

次の表に、Lync Server 2013 Standard Edition サーバーの展開のための DNS 要件を示します。

### Standard Edition サーバーの DNS 要件

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
<td><p>Standard Edition サーバー</p></td>
<td><p>サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</p></td>
</tr>
<tr class="even">
<td><p>自動クライアント サインイン</p></td>
<td><p>サポートされている SIP ドメインごとの _sipinternaltls._tcp.<em>&lt;ドメイン&gt;</em> の SRV レコード (ポート 5061 経由)。このレコードは、サインインのクライアント要求を認証およびリダイレクトする Standard Edition サーバーの FQDN にマップされます。詳細については、「<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 での自動クライアント サインインの DNS 要件</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>統合コミュニケーション (UC) デバイスによるデバイス更新 Web サービスの検出</p></td>
<td><p>デバイス更新 Web サービスをホストする Standard Edition サーバーの IP アドレスに解決する、名前が ucupdates-r2.&lt;SIP ドメイン&gt; の内部 A レコード。UC デバイスが有効でもユーザーがデバイスにログインしていない場合、A レコードを使用して、デバイスでデバイス更新 Web サービスをホストするサーバーを検出し、更新プログラムを取得できます。この方法を使用しない場合、デバイスはユーザーが最初にログインしたときにインバンド プロビジョニングを通じてサーバー情報を取得します。</p></td>
</tr>
<tr class="even">
<td><p>HTTP トラフィックをサポートするためのリバース プロキシ</p></td>
<td><p>Web ファームの外部 FQDN を、リバース プロキシの外部 IP アドレスに解決する外部 A レコード。クライアントと UC デバイスは、このレコードを使用してリバース プロキシに接続します。詳細については、「計画」のドキュメントの「<a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013 の DNS の要件を確認する</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

