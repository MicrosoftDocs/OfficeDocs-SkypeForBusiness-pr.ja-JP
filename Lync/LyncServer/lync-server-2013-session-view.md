---
title: Session ビュー
TOCTitle: Session ビュー
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49886948
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Session ビュー

 

_**トピックの最終更新日:** 2015-03-09_

セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。このビューは Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>MediaLine テーブルから参照されます。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>varchar(max)</p></td>
<td><p>セッションの関連付け ID。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>ダイアログのカテゴリ。0 は、Lync Server - 仲介サーバー レグ。1 は、仲介サーバー - PSTN ゲートウェイ レグ。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>通話がバイパスされたかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。Lync Server では、次の 1 つの値のみが定義されています。</p>
<p>0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>通話の開始時刻。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>通話の終了時刻。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者プールの FQDN。</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先プールの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>発信者の P-Asserted-Identity (PAI) URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>呼び出し先の P-Asserted-Identity (PAI) URI。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者のエンドポイント名。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者のエンドポイント名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者のユーザー エージェント文字列。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>発信者のユーザー エージェント タイプ。詳細については、「<a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>発信者のユーザー エージェントのカテゴリ。詳細については、「<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef テーブル (QoE)</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先のユーザー エージェント文字列。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し先のユーザー エージェント タイプ。詳細については、「<a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>呼び出し先のユーザー エージェントのカテゴリ。詳細については、「<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef テーブル (QoE)</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>発信者の URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>呼び出し先の URＩ。</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>通話の優先順位。</p></td>
</tr>
</tbody>
</table>

