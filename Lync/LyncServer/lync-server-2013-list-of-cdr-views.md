---
title: 'Lync Server 2013: CDR ビューのリスト'
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
ms.openlocfilehash: e8903edb911168bfe80a6eed8b0e7e78842e43a0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013 の CDR ビューのリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。 実際の CDR データベーステーブルを使用する代わりに、ビューを使用してカスタムレポートを作成することをお勧めします。これは、データベースビューが Lync Server の今後のリリースとの下位互換性を維持する可能性が高くなるためです。


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
<td><p>通信セッションで使用されているクライアント ソフトウェアおよびデバイスについての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 の ConferenceMessageCount ビュー</a></p></td>
<td><p>電話会議でユーザーによって送信されたメッセージ数についての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013 の会議ビュー</a></p></td>
<td><p>開始時刻、終了時刻、電話会議の開催者などの、電話会議情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 の ConferenceSessionDetails ビュー</a></p></td>
<td><p>開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID などの、すべての電話会議セッションのセッション詳細を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 の ConferenceUris ビュー</a></p></td>
<td><p>電話会議で使用される電話会議 URI についての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 の ErrorReport ビュー</a></p></td>
<td><p>セッション中に発生したエラーについての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 の FileTransfers ビュー</a></p></td>
<td><p>ファイル名、送信の状態 (受け入れ、拒否、取り消し) などの、ファイル送信セッションについての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 の FocusJoinsAndLeaves ビュー</a></p></td>
<td><p>会議の参加と退出のアクティビティについての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 の McuJoinsAndLeaves ビュー</a></p></td>
<td><p>会議の参加と退出のアクティビティを組み合わせた情報を返します (会議の参加と、対応する退出の情報を組み合わせて返します)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013 の mcu ビュー</a></p></td>
<td><p>電話会議サーバーについての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013 のメディア表示</a></p></td>
<td><p>ピアツーピアの通信セッションで使用されるメディアの種類についての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 の進捗レポートの表示</a></p></td>
<td><p>完了したセッションについての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013 の登録ビュー</a></p></td>
<td><p>Lync Server での登録に関する情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の SessionDetails ビュー</a></p></td>
<td><p>VoIP 間の通話、2 者間の IM セッション、その他のピアツーピア通信セッションなど、ピアツーピア セッションについての情報を返します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013 のユーザービュー</a></p></td>
<td><p>通信セッションに参加したユーザーについての情報を返します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 の VoIPDetails ビュー</a></p></td>
<td><p>少なくとも一方が VoIP (ボイス オーバー IP) ユーザーであるピアツーピア セッションの情報を返します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

