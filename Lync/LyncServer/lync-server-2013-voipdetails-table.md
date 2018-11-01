---
title: 'Lync Server 2013: VoipDetails テーブル'
TOCTitle: VoipDetails テーブル
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48272473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の VoipDetails テーブル

 

_**トピックの最終更新日:** 2015-03-09_

それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。


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
<td><p>セッション要求の時間。<strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の <strong>PhoneId</strong> 。詳細については、「<a href="lync-server-2013-phones-table.md">Lync Server 2013 の Phones テーブル</a>」を参照してください。この値と <strong>FromGatewayId</strong> がどちらも NULL でない場合、発信者は PSTN ユーザーです。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の受信者の <strong>PhoneId</strong> 。詳細については、「<a href="lync-server-2013-phones-table.md">Lync Server 2013 の Phones テーブル</a>」を参照してください。この値と <strong>ToGatewayId</strong> がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信元の仲介サーバー。詳細については、「<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信先の仲介サーバー。詳細については、「<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信元のゲートウェイ。詳細については、「<a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信先のゲートウェイ。詳細については、「<a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>別の電話から切断された通話を切断した電話の ID。詳細については、「<a href="lync-server-2013-phones-table.md">Lync Server 2013 の Phones テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

