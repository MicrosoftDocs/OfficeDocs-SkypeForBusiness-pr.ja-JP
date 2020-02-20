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
ms.openlocfilehash: de760c2305ea4682ab53f3d0fabfcf3d06cf7e78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="6f105-102">Lync Server 2013 の CDR ビューのリスト</span><span class="sxs-lookup"><span data-stu-id="6f105-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f105-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6f105-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6f105-104">ビューを使用すると、CDR データベースからデータを返すために使用される最も一般的なシナリオについての情報に簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f105-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="6f105-105">実際の CDR データベーステーブルを使用する代わりに、ビューを使用してカスタムレポートを作成することをお勧めします。これは、データベースビューが Lync Server の今後のリリースとの下位互換性を維持する可能性が高くなるためです。</span><span class="sxs-lookup"><span data-stu-id="6f105-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f105-106">ビュー名</span><span class="sxs-lookup"><span data-stu-id="6f105-106">View Name</span></span></th>
<th><span data-ttu-id="6f105-107">説明</span><span class="sxs-lookup"><span data-stu-id="6f105-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f105-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 の ClientVersions ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-109">通信セッションで使用されているクライアント ソフトウェアおよびデバイスについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 の ConferenceMessageCount ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-111">電話会議でユーザーによって送信されたメッセージ数についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 の会議ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-113">開始時刻、終了時刻、電話会議の開催者などの、電話会議情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 の ConferenceSessionDetails ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-115">開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID などの、すべての電話会議セッションのセッション詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 の ConferenceUris ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-117">電話会議で使用される電話会議 URI についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 の ErrorReport ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-119">セッション中に発生したエラーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 の FileTransfers ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-121">ファイル名、送信の状態 (受け入れ、拒否、取り消し) などの、ファイル送信セッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 の FocusJoinsAndLeaves ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-123">会議の参加と退出のアクティビティについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 の McuJoinsAndLeaves ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-125">会議の参加と退出のアクティビティを組み合わせた情報を返します (会議の参加と、対応する退出の情報を組み合わせて返します)。</span><span class="sxs-lookup"><span data-stu-id="6f105-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 の mcu ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-127">電話会議サーバーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-128"><a href="lync-server-2013-media-view.md">Lync Server 2013 のメディア表示</a></span><span class="sxs-lookup"><span data-stu-id="6f105-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-129">ピアツーピアの通信セッションで使用されるメディアの種類についての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 の進捗レポートの表示</a></span><span class="sxs-lookup"><span data-stu-id="6f105-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-131">完了したセッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013 の登録ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-133">Lync Server での登録に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の SessionDetails ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-135">VoIP 間の通話、2 者間の IM セッション、その他のピアツーピア通信セッションなど、ピアツーピア セッションについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f105-136"><a href="lync-server-2013-user-view.md">Lync Server 2013 のユーザービュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-137">通信セッションに参加したユーザーについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f105-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 の VoIPDetails ビュー</a></span><span class="sxs-lookup"><span data-stu-id="6f105-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6f105-139">少なくとも一方が VoIP (ボイス オーバー IP) ユーザーであるピアツーピア セッションの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6f105-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

