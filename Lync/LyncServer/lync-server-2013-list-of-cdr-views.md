---
title: 'Lync Server 2013: CDR ビューの一覧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="c9078-102">Lync Server 2013 の CDR ビューの一覧</span><span class="sxs-lookup"><span data-stu-id="c9078-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9078-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c9078-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c9078-104">ビューは、CDR データベースからデータを返すために使用される最も一般的なシナリオに関する情報に簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9078-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="c9078-105">実際の CDR データベーステーブルを使う代わりに、ビューを使ってカスタムレポートを作成することをお勧めします。これは、データベースビューが、Lync Server の将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="c9078-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9078-106">ビュー名</span><span class="sxs-lookup"><span data-stu-id="c9078-106">View Name</span></span></th>
<th><span data-ttu-id="c9078-107">説明</span><span class="sxs-lookup"><span data-stu-id="c9078-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9078-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 の ClientVersions ビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-109">通信セッションで使用されているクライアントソフトウェア/デバイスについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 での ConferenceMessageCount の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-111">電話会議のユーザーから送信されたメッセージの数に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 での会議ビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-113">開始時刻、終了時刻、会議開催者などの会議情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 での ConferenceSessionDetails の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-115">開始時刻、終了時刻、ユーザー Id、応答コード、診断 Id など、すべての会議セッションのセッションの詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 での ConferenceUris の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-117">会議で使用されている会議の Uri に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 での ErrorReport の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-119">セッション中に発生したエラーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 の FileTransfers ビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-121">ファイルの名前、転送が承諾、拒否、またはキャンセルされたかどうかなど、ファイル転送セッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 での FocusJoinsAndLeaves の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-123">会議への参加と退席中のアクティビティに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 での McuJoinsAndLeaves の表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-125">会議への参加と休暇のアクティビティについての結合された情報を返します (各会議参加は、対応する会議の退出とペアリングされています)。</span><span class="sxs-lookup"><span data-stu-id="c9078-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 の mcu ビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-127">会議サーバーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-128"><a href="lync-server-2013-media-view.md">Lync Server 2013 でのメディアの表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-129">ピアツーピア通信セッションで使用されているメディアの種類についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 の進捗状況レポートビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-131">完了したセッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013 に表示される登録情報</a></span><span class="sxs-lookup"><span data-stu-id="c9078-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-133">Lync Server の登録に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 のセッション詳細表示</a></span><span class="sxs-lookup"><span data-stu-id="c9078-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-135">VoIP 電話、2パーティの IM セッション、またはピアツーピア通信セッションなど、ピアツーピアセッションに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9078-136"><a href="lync-server-2013-user-view.md">Lync Server 2013 のユーザービュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-137">コミュニケーションセッションに参加したユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9078-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 の VoIPDetails ビュー</a></span><span class="sxs-lookup"><span data-stu-id="c9078-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c9078-139">1つ以上の VoIP (ボイスオーバー IO) ユーザーを含むピアツーピアセッションの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c9078-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

