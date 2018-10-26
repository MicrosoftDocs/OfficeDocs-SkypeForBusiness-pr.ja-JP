---
title: 'Lync Server 2013: tblChat'
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48273352
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblChat

 

_**トピックの最終更新日:** 2015-03-09_

tblChat には、すべてのチャット メッセージが格納されます。

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
<td><p>channelId</p></td>
<td><p>NULL でない int</p></td>
<td><p>ノード ID。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>チャット ルームの順番を定義する一意の連続番号 (ノード ID ごと)。tblLastChatId テーブルによって生成されます。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>チャット メッセージのタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>NULL でない int</p></td>
<td><p>投稿者のプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メッセージが警告メッセージの場合は True、警告メッセージでない場合は False。</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>NULL でない nvarchar (max)</p></td>
<td><p>チャットの内容 (プレーン テキスト バージョン)。内容は、通常、プレーン テキストですが、次の例外があります。</p>
<ul>
<li><p>ファイルは ma-filelink: リンクとして表されます。</p></li>
<li><p>リンクは HTML 要素として表されます (ただし、コンテンツの種類は HTML とは見なされません)。</p></li>
<li><p>ストーリーは 「[STORY]....」 のような形式でエンコードされます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>チャットの内容 (RTF バージョン)。クライアントによって提供されない場合は NULL になります。</p></td>
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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

