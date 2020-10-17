---
title: 'Lync Server 2013: 通話受付管理レポート'
description: 'Lync Server 2013: 通話受付管理レポート'
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
ms.openlocfilehash: 8764e51603e7097095894bc1230c2a2bb1126b9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572363"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="abd34-103">Lync Server 2013 での通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="abd34-103">Call Admission Control Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd34-104">_**トピックの最終更新日:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="abd34-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="abd34-105">通話受付管理レポートは、通話受付管理によって設けられた制限のもとで行われたピアツーピアおよび電話会議セッションに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="abd34-105">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="abd34-106">Microsoft Lync Server 2010 で導入された通話受付管理では、管理者は、帯域幅の制約に基づいて通信セッションを許可するか (許可しない) ことができます。</span><span class="sxs-lookup"><span data-stu-id="abd34-106">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="abd34-107">たとえば、管理者は音声通話やビデオ通話に使用可能な帯域幅を制限するポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="abd34-107">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="abd34-108">帯域幅の制限に達すると、現在の通話のいずれかが終了して必要なネットワーク リソースが解放されるまで、新しい音声通話やビデオ通話は行えません。</span><span class="sxs-lookup"><span data-stu-id="abd34-108">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="abd34-109">通話受付管理レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="abd34-109">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="abd34-p102">通話受付管理レポートは、[監視レポート] ホーム ページからアクセスします。通話受付管理レポートから次のいずれかのレポートへドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="abd34-112">会議詳細レポート – このレポートにアクセスするには、電話会議セッションの [Details] (詳細) 指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abd34-112">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="abd34-113">ピアツーピア セッション詳細レポート – このレポートにアクセスするには、ピアツーピア セッションの [Details] (詳細) 指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abd34-113">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="abd34-114">通話受付管理レポートの活用</span><span class="sxs-lookup"><span data-stu-id="abd34-114">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="abd34-p103">帯域幅が十分になかったために失敗した通話の一覧を表示するには、[通話のカテゴリ] ドロップダウン リストから [通話受付管理により通話が拒否された] を選択します。ほとんどの返信通話は診断 ID が 5 になります。</span><span class="sxs-lookup"><span data-stu-id="abd34-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="abd34-p104">セッションを確立するために十分な帯域幅がありません。PSTN 再ルートを試してください。</span><span class="sxs-lookup"><span data-stu-id="abd34-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="abd34-119">通話受付管理の制限によって、VoIP ネットワーク上で通話ができなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="abd34-119">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="abd34-120">フィルター</span><span class="sxs-lookup"><span data-stu-id="abd34-120">Filters</span></span>

<span data-ttu-id="abd34-p105">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、通話受付管理レポートでは、通話を開始したユーザーや呼び出し先のユーザーに基づいて通話をフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、時間、日、週、または月を基準に通話がグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="abd34-125">次の表に、通話受付管理レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="abd34-125">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="abd34-126">通話受付管理レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="abd34-126">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abd34-127">名前</span><span class="sxs-lookup"><span data-stu-id="abd34-127">Name</span></span></th>
<th><span data-ttu-id="abd34-128">説明</span><span class="sxs-lookup"><span data-stu-id="abd34-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abd34-129"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-129"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="abd34-132">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="abd34-132">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="abd34-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="abd34-135">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="abd34-135">7/17/12012</span></span></p>
<p><span data-ttu-id="abd34-136">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="abd34-136">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="abd34-137">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="abd34-137">7/13/2012</span></span></p>
<p><span data-ttu-id="abd34-138">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="abd34-138">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-139"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-139"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="abd34-142">7/17/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="abd34-142">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="abd34-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="abd34-145">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="abd34-145">7/17/12012</span></span></p>
<p><span data-ttu-id="abd34-146">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="abd34-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="abd34-147">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="abd34-147">7/13/2012</span></span></p>
<p><span data-ttu-id="abd34-148">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="abd34-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-149"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-149"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-p110">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-153">[<strong>動作状況の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-153"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-p111">活動の種類。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="abd34-156">[All]</span><span class="sxs-lookup"><span data-stu-id="abd34-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="abd34-157">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="abd34-157">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="abd34-158">会議</span><span class="sxs-lookup"><span data-stu-id="abd34-158">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-159">[<strong>通話のカテゴリ</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-159"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-p112">通話に CAC が使用された理由を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="abd34-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="abd34-162">[All]</span><span class="sxs-lookup"><span data-stu-id="abd34-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="abd34-163">通話受付管理により通話が拒否された</span><span class="sxs-lookup"><span data-stu-id="abd34-163">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="abd34-164">通話受付管理により通話が PSTN 経由で再ルーティングされた</span><span class="sxs-lookup"><span data-stu-id="abd34-164">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="abd34-165">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="abd34-165">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="abd34-166">次の表に、通話受付管理レポートでピアツーピア セッション (2 人の参加者のみが関与するセッション) について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="abd34-166">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="abd34-167">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="abd34-167">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abd34-168">名前</span><span class="sxs-lookup"><span data-stu-id="abd34-168">Name</span></span></th>
<th><span data-ttu-id="abd34-169">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="abd34-169">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="abd34-170">説明</span><span class="sxs-lookup"><span data-stu-id="abd34-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abd34-171"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-171"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-172">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-173">この項目をクリックすると、指定したセッションのピアツーピア セッション詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-173">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-174">[<strong>移動元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-174"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-175">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-176">セッションを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="abd34-176">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-177">[<strong>対象ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-177"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-178">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-179">セッションへの参加を招待されたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="abd34-179">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-180"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-180"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-181">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-181">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-182">セッションで使用された通信モダリティ (音声、ビデオなど)。</span><span class="sxs-lookup"><span data-stu-id="abd34-182">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-183">[<strong>招待時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-183"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-184">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-185">セッションへの最初の招待が発信元ユーザーから送信された日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-185">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-186">[<strong>応答時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-186"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-187">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-188">招待の承諾を受信した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-188">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-189"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-189"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-190">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-190">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-191">セッションが終了した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-191">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-192">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-192"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-193">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-p113">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="abd34-196">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="abd34-196">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="abd34-197">次の表に、通話受付管理レポートで電話会議セッション (3 人以上の参加者が関与するセッション) について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="abd34-197">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="abd34-198">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="abd34-198">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abd34-199">名前</span><span class="sxs-lookup"><span data-stu-id="abd34-199">Name</span></span></th>
<th><span data-ttu-id="abd34-200">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="abd34-200">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="abd34-201">説明</span><span class="sxs-lookup"><span data-stu-id="abd34-201">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abd34-202">[<strong>会議 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-202"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-203">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-p114">電話会議の一意の識別子。この項目をクリックすると、個別の電話会議参加者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-206"><strong>開催者</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-206"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-207">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-208">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="abd34-208">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-209"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-209"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-210">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-211">電話会議で使用されたエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="abd34-211">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-212"><strong>開始時刻</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-212"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-213">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-214">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-214">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-215"><strong>終了時刻</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-215"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-216">はい</span><span class="sxs-lookup"><span data-stu-id="abd34-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="abd34-217">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-217">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="abd34-218">個別の電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="abd34-218">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="abd34-219">次の表に、通話受付管理レポートで個別の電話会議参加者について提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="abd34-219">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="abd34-220">個別の電話会議参加者の指標</span><span class="sxs-lookup"><span data-stu-id="abd34-220">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abd34-221">名前</span><span class="sxs-lookup"><span data-stu-id="abd34-221">Name</span></span></th>
<th><span data-ttu-id="abd34-222">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="abd34-222">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="abd34-223">説明</span><span class="sxs-lookup"><span data-stu-id="abd34-223">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abd34-224"><strong>役割</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-224"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-225">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-226">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="abd34-226">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-227"><strong>参加者</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-227"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-228">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-229">電話会議の参加者の SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="abd34-229">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-230"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-230"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-231">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-232">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="abd34-232">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-233"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="abd34-233"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-234">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-235">電話会議の種類 (音声ビデオ会議など)。</span><span class="sxs-lookup"><span data-stu-id="abd34-235">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-236">[<strong>参加時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-236"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-237">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-238">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-238">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd34-239">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-239"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-240">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-240">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-241">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="abd34-241">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd34-242">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="abd34-242"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="abd34-243">いいえ</span><span class="sxs-lookup"><span data-stu-id="abd34-243">No</span></span></p></td>
<td><p><span data-ttu-id="abd34-p115">SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダー形式)。その情報は、多くの場合、エラーのトラブルシューティングに役立ちます。診断ヘッダーはオプションで (このヘッダーを含まない SIP セッションがある可能性もあります)、診断 ID は、何らかの問題が生じたセッションについてのみ報告されます。</span><span class="sxs-lookup"><span data-stu-id="abd34-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

