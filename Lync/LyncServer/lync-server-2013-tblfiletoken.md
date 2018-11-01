---
title: 'Lync Server 2013: tblFileToken'
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48271990
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblFileToken

 

_**トピックの最終更新日:** 2015-03-09_

tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。

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
<td><p>fileToken</p></td>
<td><p>NULL でない nvarchar (50)</p></td>
<td><p>一意のトークン (GUID)。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ファイルを転送するプリンシパルの ID。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>チャット ルーム ノードの GUID。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>有効期限。固定されていない場合、トークンの有効期限は 30 分 （この列の以下の説明を参照)。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>転送ファイルの URL (Compliance Service で使用)。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>転送ファイルのサムネイルの URL (Compliance Service で使用)。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>実際のファイル転送操作のタイムスタンプ (Compliance Service で使用)。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>アップロードの場合は True、ダウンロードの場合 False (Compliance Service で使用)。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>NULL でない bit</p></td>
<td><p>トークンが固定されている場合は True。Compliance Service が関連フィールドを取得できるようになるまで、テーブル内にトークンを維持するために使用されます。</p></td>
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
<td><p>fileToken</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>tblNode.nodeGuid テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

