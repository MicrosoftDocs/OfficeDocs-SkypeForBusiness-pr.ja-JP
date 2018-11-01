---
title: 'Lync Server 2013: UserAgent テーブル'
TOCTitle: UserAgent テーブル
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48273789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の UserAgent テーブル

 

_**トピックの最終更新日:** 2015-03-09_

UserAgent テーブルはサポート テーブルで、データベースに記録されるセッションに参加しているさまざまなユーザー エージェントの一覧が格納されます。テーブル内の各レコードは、1 つのユーザー エージェントを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このユーザー エージェントを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>ユーザー エージェントの文字列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 は仲介サーバーです。</p>
<p>2 は音声ビデオ会議サーバーです。</p>
<p>4 は Lync です。</p>
<p>8 は IP 電話です。</p>
<p>16 は Live Meeting コンソールです。</p>
<p>32 は展開検証ツール (DVT) です。</p>
<p>64 は Macintosh コンピューター上の Lync です。</p>
<p>128 は Office Communications Server 2007 R2 Attendant です。</p>
<p>256 は会議アナウンス サービスです。</p>
<p>512 は会議自動アテンダントです。</p>
<p>1024 は応答グループ アプリケーションです。</p>
<p>2048 は外部音声コントロールです。</p></td>
</tr>
</tbody>
</table>

