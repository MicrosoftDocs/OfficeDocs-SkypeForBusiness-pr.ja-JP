---
title: 'Lync Server 2013: Session テーブル'
TOCTitle: Session テーブル
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48272659
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Session テーブル

 

_**トピックの最終更新日:** 2015-03-09_

それぞれのレコードは、音声または音声ビデオを伴う 1 つのセッションを表します。各レコードには、そうしたセッションに関する全体的な情報が含まれます。セッションは、2 つのエンドポイント間の、音声または音声ビデオのセッション開始プロトコル (SIP) ダイアログとして定義されます。


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 の Dialog テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 の Dialog テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議のキー。 <a href="lync-server-2013-conference-table.md">Lync Server 2013 の Conference テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>関連付けキー。 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の SessionCorrelation テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>ダイアログのカテゴリ。0 は、 Lync Server - 仲介サーバー レグ。1 は、仲介サーバー - PSTN ゲートウェイ レグ。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>通話がバイパスされたかどうかを示すフラグ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 Lync Server では、値が 1 つしか定義されていません。</p>
<p>0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通話の開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通話の終了時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のプール。 <a href="lync-server-2013-pool-table.md">Lync Server 2013 の Pool テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の受信者のプール。 <a href="lync-server-2013-pool-table.md">Lync Server 2013 の Pool テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>受信側エンドポイントの SIP P-Asserted-Identity (PAI) における SIP URI。 <a href="lync-server-2013-user-table.md">Lync Server 2013 の User テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の URI。 <a href="lync-server-2013-user-table.md">Lync Server 2013 の User テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のエンドポイント。 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 の Endpoint テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>外部</p></td>
<td><p>発信者のユーザー エージェント。 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>この通話の優先順位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>この列は Microsoft Lync Server 2013 では使用されなくなりました。この情報は、メディア ラインごとに報告されるようになっています。詳細については、「<a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出しを開始したユーザーの P-Asserted-Identity。P-Asserted-Identity (PAI) は、呼び出しを行ったユーザーの真の ID を送信するのに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したエンドポイント。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーが使用しているユーザー エージェント。ユーザー エージェントはクライアントのエンドポイント デバイスを表します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーの SIP URI。</p></td>
</tr>
</tbody>
</table>

