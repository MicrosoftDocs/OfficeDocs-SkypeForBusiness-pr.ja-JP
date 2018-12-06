---
title: 'Lync Server 2013: Conferences テーブル'
TOCTitle: Conferences テーブル
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48273516
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Conferences テーブル

 

_**トピックの最終更新日:** 2015-03-09_

このテーブル内の各レコードには、1 つの会議に関する通話の詳細が格納されています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p>CDR エージェントによって会議要求が取得された時刻。会議インスタンスを一意に識別するための主キーとしてのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>セッションを識別するための ID 番号。 <strong>SessionIdTime</strong> と合わせて使用して、会議インスタンスを一意に識別します。*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議 URI。詳細については、「<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>定期的な会議で役立ちます。定期的な会議の各インスタンスは、 <strong>ConferenceUri</strong> が同じで、 <strong>ConfInstance</strong> はそれぞれ異なります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>電話会議の終了時刻です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>電話会議の終了時刻です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議が取得されたプールを識別する ID 番号。詳細については、「<a href="lync-server-2013-pools-table.md">Lync Server 2013 の Pools テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>外部</p></td>
<td><p>この会議の開催者の URI を識別する ID 番号。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>フラグ</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>会議の属性が格納されているビット マスク。有効な値は次のとおりです。</p>
<ul>
<li><p>0X01</p></li>
<li><p>代理</p></li>
<li><p>トランザクション</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Processed</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>監視サービスが使用する内部フィールド。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。まったく同時に 2 つのセッションが開始した場合、一方の SessionIdSeq は 1、他方は 2、などとなります。

