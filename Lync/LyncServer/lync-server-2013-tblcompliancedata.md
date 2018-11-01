---
title: 'Lync Server 2013: tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48271125
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblComplianceData

 

_**トピックの最終更新日:** 2015-03-09_

tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。

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
<td><p>cmplEventID</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>NULL でない smalldatetime</p></td>
<td><p>挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>NULL でない int</p></td>
<td><p>コンプライアンス イベントの種類。</p>
<ul>
<li><p>1: チャット</p></li>
<li><p>2: バックチャット</p></li>
<li><p>3: ファイル ダウンロード</p></li>
<li><p>4: ファイル アップロード</p></li>
<li><p>9: 暫定ファイル転送</p></li>
<li><p>10: (置き換えによる) チャットの削除</p></li>
<li><p>11: チャットの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>イベントのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>チャネルの URI (Uniform Resource Identifier)。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>チャット ID (tblChat.chatId テーブルに対応)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>ユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>メッセージ (エンコードは cmplType に依存)。</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

