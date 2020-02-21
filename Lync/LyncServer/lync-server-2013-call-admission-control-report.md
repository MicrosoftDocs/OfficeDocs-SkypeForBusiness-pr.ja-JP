---
title: 'Lync Server 2013: 通話受付管理レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d61e01574945fe090d3fd9425133f9569bd111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="f2178-102">Lync Server 2013 での通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="f2178-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2178-103">_**トピックの最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="f2178-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="f2178-104">通話受付管理レポートは、通話受付管理によって設けられた制限のもとで行われたピアツーピアおよび電話会議セッションに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2178-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="f2178-105">Microsoft Lync Server 2010 で導入された通話受付管理では、管理者は、帯域幅の制約に基づいて通信セッションを許可するか (許可しない) ことができます。</span><span class="sxs-lookup"><span data-stu-id="f2178-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="f2178-106">たとえば、管理者は音声通話やビデオ通話に使用可能な帯域幅を制限するポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2178-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="f2178-107">帯域幅の制限に達すると、現在の通話のいずれかが終了して必要なネットワーク リソースが解放されるまで、新しい音声通話やビデオ通話は行えません。</span><span class="sxs-lookup"><span data-stu-id="f2178-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="f2178-108">通話受付管理レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f2178-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="f2178-p102">通話受付管理レポートは、[監視レポート] ホーム ページからアクセスします。通話受付管理レポートから次のいずれかのレポートへドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="f2178-111">会議詳細レポート – このレポートにアクセスするには、電話会議セッションの [Details] (詳細) 指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2178-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="f2178-112">ピアツーピア セッション詳細レポート – このレポートにアクセスするには、ピアツーピア セッションの [Details] (詳細) 指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2178-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="f2178-113">通話受付管理レポートの活用</span><span class="sxs-lookup"><span data-stu-id="f2178-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="f2178-p103">帯域幅が十分になかったために失敗した通話の一覧を表示するには、[通話のカテゴリ] ドロップダウン リストから [通話受付管理により通話が拒否された] を選択します。ほとんどの返信通話は診断 ID が 5 になります。</span><span class="sxs-lookup"><span data-stu-id="f2178-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="f2178-p104">セッションを確立するために十分な帯域幅がありません。PSTN 再ルートを試してください。</span><span class="sxs-lookup"><span data-stu-id="f2178-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="f2178-118">通話受付管理の制限によって、VoIP ネットワーク上で通話ができなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f2178-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f2178-119">フィルター</span><span class="sxs-lookup"><span data-stu-id="f2178-119">Filters</span></span>

<span data-ttu-id="f2178-p105">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、通話受付管理レポートでは、通話を開始したユーザーや呼び出し先のユーザーに基づいて通話をフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、時間、日、週、または月を基準に通話がグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f2178-124">次の表に、通話受付管理レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="f2178-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="f2178-125">通話受付管理レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="f2178-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2178-126">名前</span><span class="sxs-lookup"><span data-stu-id="f2178-126">Name</span></span></th>
<th><span data-ttu-id="f2178-127">説明</span><span class="sxs-lookup"><span data-stu-id="f2178-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2178-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f2178-131">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2178-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2178-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2178-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="f2178-134">7/17/12012</span></span></p>
<p><span data-ttu-id="f2178-135">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f2178-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2178-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="f2178-136">7/13/2012</span></span></p>
<p><span data-ttu-id="f2178-137">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="f2178-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f2178-141">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2178-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2178-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2178-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="f2178-144">7/17/12012</span></span></p>
<p><span data-ttu-id="f2178-145">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f2178-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2178-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="f2178-146">7/13/2012</span></span></p>
<p><span data-ttu-id="f2178-147">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="f2178-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-p110">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-152">[<strong>動作状況の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-p111">活動の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2178-155">いずれ</span><span class="sxs-lookup"><span data-stu-id="f2178-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="f2178-156">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="f2178-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="f2178-157">室</span><span class="sxs-lookup"><span data-stu-id="f2178-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-158">[<strong>通話のカテゴリ</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-p112">通話に CAC が使用された理由を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2178-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2178-161">いずれ</span><span class="sxs-lookup"><span data-stu-id="f2178-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="f2178-162">通話受付管理により通話が拒否された</span><span class="sxs-lookup"><span data-stu-id="f2178-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="f2178-163">通話受付管理により通話が PSTN 経由で再ルーティングされた</span><span class="sxs-lookup"><span data-stu-id="f2178-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f2178-164">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2178-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="f2178-165">次の表に、通話受付管理レポートでピアツーピア セッション (2 人の参加者のみが関与するセッション) について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2178-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f2178-166">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2178-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2178-167">名前</span><span class="sxs-lookup"><span data-stu-id="f2178-167">Name</span></span></th>
<th><span data-ttu-id="f2178-168">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2178-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2178-169">説明</span><span class="sxs-lookup"><span data-stu-id="f2178-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2178-170"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-171">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-172">この項目をクリックすると、指定したセッションのピアツーピア セッション詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-173">[<strong>移動元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-174">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-175">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2178-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-176">[<strong>対象ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-177">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-178">セッションへの参加を招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2178-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-179"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-180">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-181">セッションで使用された通信モダリティ (音声、ビデオなど)。</span><span class="sxs-lookup"><span data-stu-id="f2178-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-182">[<strong>招待時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-183">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-184">セッションへの最初の招待が発信元ユーザーから送信された日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-185">[<strong>応答時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-186">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-187">招待の承諾を受信した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-188">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-189">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-190">セッションが終了した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-191">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-192">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-p113">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f2178-195">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2178-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="f2178-196">次の表に、通話受付管理レポートで電話会議セッション (3 人以上の参加者が関与するセッション) について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2178-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f2178-197">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="f2178-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2178-198">名前</span><span class="sxs-lookup"><span data-stu-id="f2178-198">Name</span></span></th>
<th><span data-ttu-id="f2178-199">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2178-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2178-200">説明</span><span class="sxs-lookup"><span data-stu-id="f2178-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2178-201">[<strong>会議 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-202">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-p114">電話会議の一意の識別子。この項目をクリックすると、個別の電話会議参加者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-205"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-206">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-207">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2178-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-209">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-210">電話会議で使用されたエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="f2178-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-211">[<strong>開始時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-212">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-213">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-214">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-215">はい</span><span class="sxs-lookup"><span data-stu-id="f2178-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2178-216">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="f2178-217">個別の電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="f2178-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="f2178-218">次の表に、通話受付管理レポートで個別の電話会議参加者について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f2178-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="f2178-219">個別の電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="f2178-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2178-220">名前</span><span class="sxs-lookup"><span data-stu-id="f2178-220">Name</span></span></th>
<th><span data-ttu-id="f2178-221">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="f2178-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2178-222">説明</span><span class="sxs-lookup"><span data-stu-id="f2178-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2178-223"><strong>ロール</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-224">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-225">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="f2178-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-226"><strong>参加者</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-227">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-227">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-228">電話会議の参加者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f2178-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-229"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-230">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-231">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="f2178-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-232"><strong>モーダル</strong></span><span class="sxs-lookup"><span data-stu-id="f2178-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-233">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-233">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-234">電話会議の種類 (音声ビデオ会議など)。</span><span class="sxs-lookup"><span data-stu-id="f2178-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-235">[<strong>参加時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-236">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-236">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-237">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2178-238">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-239">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-239">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-240">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="f2178-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2178-241">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="f2178-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2178-242">いいえ</span><span class="sxs-lookup"><span data-stu-id="f2178-242">No</span></span></p></td>
<td><p><span data-ttu-id="f2178-p115">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="f2178-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

