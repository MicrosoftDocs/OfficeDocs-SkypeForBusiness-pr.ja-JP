---
title: 'Lync Server 2013: 会議詳細レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dce868d90d2811b36a4f11c159b4e7d9d29b5ffa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Lync Server 2013 の会議詳細レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。

<div>

## <a name="accessing-the-conference-detail-report"></a>会議詳細レポートへのアクセス

会議詳細レポートには、次のレポートからアクセスできます。

  - [Lync Server 2013 の通話受付管理レポート](lync-server-2013-call-admission-control-report.md)(会議の詳細指標をクリック)

  - [Lync Server 2013 のエラーリストレポート](lync-server-2013-failure-list-report.md)(電話会議指標をクリック)

  - [Lync Server 2013 のユーザーアクティビティレポート](lync-server-2013-user-activity-report.md)(電話会議 URI 指標をクリック)

会議詳細レポートから、診断レポート (詳細) 指標をクリックすることによって、 [Lync Server 2013 の診断レポート](lync-server-2013-diagnostic-report.md)にアクセスできます。

</div>

<div>

## <a name="filters"></a>フィルター

なし。会議詳細レポートにはフィルターを適用できません。

</div>

<div>

## <a name="metrics"></a>指標

次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。

### <a name="conference-information-metrics"></a>電話会議情報の指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>電話会議 URI</strong>]</p></td>
<td></td>
<td><p>電話会議に割り当てられる URI。次に例を示します。</p>
<p>sip: kmyer@litwareinc .com; gruu; 非透過 = app: conf: focus: id: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p>[<strong>プールの FQDN</strong>]</p></td>
<td></td>
<td><p>セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>開始時刻</strong>]</p></td>
<td></td>
<td><p>会議が開始した日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td></td>
<td><p>会議を開催したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>終了時刻</strong>]</p></td>
<td></td>
<td><p>会議が終了した日時。</p></td>
</tr>
</tbody>
</table>


次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。

### <a name="conference-participation-metrics"></a>電話会議参加の指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ユーザー</strong></p></td>
<td></td>
<td><p>会議に参加したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>役割</strong></p></td>
<td></td>
<td><p>電話会議の参加者が担った役割 (発表者など)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>接続</strong></p></td>
<td></td>
<td><p>参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</p></td>
</tr>
<tr class="even">
<td><p>[参加時間]</p></td>
<td></td>
<td><p>参加者が電話会議に参加した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>退場時間</strong>]</p></td>
<td></td>
<td><p>参加者が電話会議から退出した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ユーザー エージェント</strong>]</p></td>
<td></td>
<td><p>参観者のエンドポイントで使用されるソフトウェアの識別子。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>診断レポート</strong>]</p></td>
<td></td>
<td><p>診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</p></td>
</tr>
</tbody>
</table>


次の表は、会議詳細レポートの [電話会議のモダリティ] セクションで提供される情報を示しています。

### <a name="conference-modalities-metrics"></a>電話会議のモダリティの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ユーザー</strong></p></td>
<td></td>
<td><p>会議に参加したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>参加時間</strong>]</p></td>
<td></td>
<td><p>参加者が電話会議に参加した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>退場時間</strong>]</p></td>
<td></td>
<td><p>参加者が電話会議を退場した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>電話会議サーバー URI</strong>]</p></td>
<td></td>
<td><p>電話会議で使用された電話会議サーバーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診断レポート</strong></p></td>
<td></td>
<td><p>診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

