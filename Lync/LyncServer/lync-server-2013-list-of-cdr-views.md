---
title: 'Lync Server 2013: CDR ビューの一覧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe2620175c2a706bfb2c48fe7fb380d5fae4c09
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013 の CDR ビューの一覧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。 実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが、Lync Server の将来のリリースとの下位互換性を維持する可能性が高いためです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ビュー名</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 の ClientVersions ビュー</a></p></td>
<td><p>通信セッションで使用されているクライアントソフトウェア/デバイスについての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 での ConferenceMessageCount の表示</a></p></td>
<td><p>電話会議のユーザーから送信されたメッセージの数に関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013 での会議ビュー</a></p></td>
<td><p>開始時刻、終了時刻、会議開催者などの会議情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 での ConferenceSessionDetails の表示</a></p></td>
<td><p>開始時刻、終了時刻、ユーザー Id、応答コード、診断 Id など、すべての会議セッションのセッションの詳細を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 での ConferenceUris の表示</a></p></td>
<td><p>会議で使用されている会議の Uri に関する情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 での ErrorReport の表示</a></p></td>
<td><p>セッション中に発生したエラーに関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 の FileTransfers ビュー</a></p></td>
<td><p>ファイルの名前、転送が承諾、拒否、またはキャンセルされたかどうかなど、ファイル転送セッションに関する情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 での FocusJoinsAndLeaves の表示</a></p></td>
<td><p>会議への参加と退席中のアクティビティに関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 での McuJoinsAndLeaves の表示</a></p></td>
<td><p>会議への参加と休暇のアクティビティについての結合された情報を返します (各会議参加は、対応する会議の退出とペアリングされています)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013 の mcu ビュー</a></p></td>
<td><p>会議サーバーに関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013 でのメディアの表示</a></p></td>
<td><p>ピアツーピア通信セッションで使用されているメディアの種類についての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 の進捗状況レポートビュー</a></p></td>
<td><p>完了したセッションに関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013 に表示される登録情報</a></p></td>
<td><p>Lync Server の登録に関する情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 のセッション詳細表示</a></p></td>
<td><p>VoIP 電話、2パーティの IM セッション、またはピアツーピア通信セッションなど、ピアツーピアセッションに関する情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013 のユーザービュー</a></p></td>
<td><p>コミュニケーションセッションに参加したユーザーに関する情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 の VoIPDetails ビュー</a></p></td>
<td><p>1つ以上の VoIP (ボイスオーバー IO) ユーザーを含むピアツーピアセッションの情報を返します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

