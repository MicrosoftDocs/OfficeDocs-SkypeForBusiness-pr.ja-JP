---
title: 'Lync Server 2013: Session テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f927957f21c67a8cfca6b169b99f7de9275740fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013 の Session テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-09_

各レコードは、音声またはオーディオとビデオを含む1つのセッションを表します。 このファイルには、セッションに関する全体的な情報が含まれています。 セッションは、2つのエンドポイント間のオーディオまたはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。


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
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 のダイアログテーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議キー。 <a href="lync-server-2013-conference-table.md">Lync Server 2013 の会議テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>関連付けキー。 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>' このカテゴリ</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>ダイアログのカテゴリ。0は Lync Server から仲介サーバーまでです。1は仲介サーバーから PSTN ゲートウェイレグになります。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>通話がバイパスされたかどうかを示すフラグ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mediabypasswarnings フラグ</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 Lync Server では、1つの値のみが定義されています。</p>
<p>0x0001 - 既定のネットワーク アダプターのバイパス ID が不明です。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>通話の開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>通話の終了時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のプール。 <a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者のプール。 <a href="lync-server-2013-pool-table.md">Lync Server 2013 のプールテーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>受信エンドポイントの SIP p アサートされた id (PAI) の SIP URI。 <a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の URI。 <a href="lync-server-2013-user-table.md">Lync Server 2013 のユーザーテーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のエンドポイント。 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>若干</p></td>
<td><p>外部</p></td>
<td><p>発信者のユーザーエージェント。 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>この通話の優先度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>この列は推奨されておらず、Microsoft Lync Server 2013 では使用されていません。 代わりに、この情報はメディアごとの回線ベースで報告されます。 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>P-アサート済み-通話を発信したユーザーの Id。 P アサートされた Id (PAI) は、呼び出しを行ったユーザーの真の id を伝えるために使用されます。</p></td>
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
<td><p>通話を受信したユーザーによって使用されているユーザーエージェント。 ユーザーエージェントは、クライアントエンドポイントデバイスを表します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーの SIP URI。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

