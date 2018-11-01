---
title: 'Lync Server 2013: tblADCookie'
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48271208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblADCookie

 

_**トピックの最終更新日:** 2015-03-09_

tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>監視対象のドメインのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Active Directory ドメイン サービス の同期に使用される現在のドメイン コントローラーの完全修飾ドメイン名 (FQDN)。情報提供のための値です。</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (バイナリ)</p></td>
<td><p>Active Directory の同期 Cookie。</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>行更新時刻でのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。</p></td>
</tr>
</tbody>
</table>


### キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Principal.prinGuid テーブル内の参照による外部キー。</p></td>
</tr>
</tbody>
</table>

