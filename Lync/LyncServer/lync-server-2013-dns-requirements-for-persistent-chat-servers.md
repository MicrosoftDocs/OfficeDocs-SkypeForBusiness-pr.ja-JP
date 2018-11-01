---
title: 常設チャット サーバーの DNS 要件
TOCTitle: 常設チャット サーバーの DNS 要件
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48274160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 常設チャット サーバーの DNS 要件

 

_**トピックの最終更新日:** 2015-03-09_

このセクションでは、常設チャット サーバー の展開に必要なドメイン ネーム システム (DNS) レコードについて説明します。

## 常設チャット サーバー用 DNS レコード

次の表は、常設チャット サーバー の展開に必要な DNS の要件を示しています。

### 常設チャット サーバーの DNS 要件

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
<td><p>1 つの常設チャット サーバー</p></td>
<td><p>サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat プール</p></td>
<td><p>サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</p>
<p><strong>例</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>サーバーの完全修飾ドメイン名 (FQDN) を、そのサーバーの IP アドレスに解決する内部 A レコード。</p>
<p><strong>例</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

