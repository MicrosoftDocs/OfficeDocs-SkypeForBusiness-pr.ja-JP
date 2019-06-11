---
title: 'Lync Server 2013: エラー一覧レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c1c9c15b1f539aa1a5213989674dfea268a684
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="e53f6-102">Lync Server 2013 のエラーリストレポート</span><span class="sxs-lookup"><span data-stu-id="e53f6-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e53f6-103">_**最終更新日:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="e53f6-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="e53f6-p101">エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e53f6-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="e53f6-106">エラー リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e53f6-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="e53f6-107">[エラー一覧] レポートにアクセスするには、「 [Lync Server 2013 のエラー配布レポート](lync-server-2013-failure-distribution-report.md)で、次のいずれかの指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e53f6-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="e53f6-108">トップの診断理由 (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="e53f6-109">トップのモダリティ (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="e53f6-110">トップのプール (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="e53f6-111">トップのソース (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="e53f6-112">トップのコンポーネント (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-112">Top components (sessions)</span></span>

  - <span data-ttu-id="e53f6-113">トップの発信元ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="e53f6-114">トップの発信先ユーザー (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="e53f6-115">トップの発信元ユーザー エージェント (セッション)</span><span class="sxs-lookup"><span data-stu-id="e53f6-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="e53f6-116">[エラー一覧] レポートから、Lync Server 2013 のピアツーピア[セッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)にアクセスできます。これには、ピアツーピアセッションのセッション詳細メトリックをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e53f6-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="e53f6-117">また、電話会議の [電話会議] の指標をクリックすると、会議詳細レポートにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="e53f6-118">エラー リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="e53f6-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="e53f6-p103">エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示できます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="e53f6-121">ユーザーのメディアの作成中に内部サーバー エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e53f6-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="e53f6-122">障害リストレポートでは、1つ以上のセッションに参加しているすべてのユーザーの一覧を直接取得する方法はありません。また、どのユーザーが失敗したかを判断する方法も提供されていない点に注意してください。セッション.</span><span class="sxs-lookup"><span data-stu-id="e53f6-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="e53f6-123">(1 つの問題については、エラーリストレポートにはフィルター機能はありません)。ただし、データをエクスポートして、コンマ区切り値ファイルに変換した場合は、Windows PowerShell を使用して、そのような質問に対する回答を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="e53f6-124">たとえば、データをに保存するとします。CSV ファイル名 C:\\データ\\エラー\_リスト .csv。</span><span class="sxs-lookup"><span data-stu-id="e53f6-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="e53f6-125">このコマンドは、そのファイルに保存されているデータに基づいて、1つ以上の失敗したセッションに参加していたすべてのユーザーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e53f6-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="e53f6-126">このコマンドを実行すると、次のような一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="e53f6-127">次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="e53f6-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="e53f6-128">この結果、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e53f6-129">フィルター</span><span class="sxs-lookup"><span data-stu-id="e53f6-129">Filters</span></span>

<span data-ttu-id="e53f6-p105">なし。エラー リスト レポートにフィルターを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e53f6-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e53f6-132">指標</span><span class="sxs-lookup"><span data-stu-id="e53f6-132">Metrics</span></span>

<span data-ttu-id="e53f6-133">次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e53f6-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="e53f6-134">エラー リスト レポートの指標</span><span class="sxs-lookup"><span data-stu-id="e53f6-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e53f6-135">名前</span><span class="sxs-lookup"><span data-stu-id="e53f6-135">Name</span></span></th>
<th><span data-ttu-id="e53f6-136">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="e53f6-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e53f6-137">説明</span><span class="sxs-lookup"><span data-stu-id="e53f6-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e53f6-138"><strong>レポートされた時刻</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-139">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-140">レポートが記録された日時。</span><span class="sxs-lookup"><span data-stu-id="e53f6-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e53f6-141"><strong>要求</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-142">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-p106">失敗した SIP 要求の種類 (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="e53f6-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e53f6-145"><strong>応答コード</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-146">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-147">会議にエラーが発生したときに送信された SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="e53f6-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e53f6-148"><strong>診断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-149">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-150">SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e53f6-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e53f6-151"><strong>参加コスト時間 (ミリ秒)</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-152">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-153">ユーザーが会議に参加するのに要した時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="e53f6-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e53f6-154"><strong>移動元ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-155">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-156">呼び出しを開始したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e53f6-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e53f6-157"><strong>送信元ユーザー エージェント</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="e53f6-158">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-159">呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="e53f6-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e53f6-160"><strong>対象ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="e53f6-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e53f6-161">不可</span><span class="sxs-lookup"><span data-stu-id="e53f6-161">No</span></span></p></td>
<td><p><span data-ttu-id="e53f6-162">呼び出しを受けたユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e53f6-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

