---
title: 'Lync Server 2013: エラーリストレポート'
description: 'Lync Server 2013: エラーリストレポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575053"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="d8fb6-103">Lync Server 2013 のエラーリストレポート</span><span class="sxs-lookup"><span data-stu-id="d8fb6-103">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8fb6-104">_**トピックの最終更新日:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="d8fb6-104">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="d8fb6-p101">エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="d8fb6-107">エラー リスト レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d8fb6-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="d8fb6-108">エラーリストレポートにアクセスするには、 [Lync Server 2013 のエラー分布レポート](lync-server-2013-failure-distribution-report.md)で次のいずれかの指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="d8fb6-109">[トップの診断理由] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-109">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="d8fb6-110">[トップ モダリティ] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-110">Top modalities (sessions)</span></span>

  - <span data-ttu-id="d8fb6-111">[トップ プール] (セッション))</span><span class="sxs-lookup"><span data-stu-id="d8fb6-111">Top pools (sessions)</span></span>

  - <span data-ttu-id="d8fb6-112">[トップ ソース] (セッション))</span><span class="sxs-lookup"><span data-stu-id="d8fb6-112">Top sources (sessions)</span></span>

  - <span data-ttu-id="d8fb6-113">[トップ コンポーネント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-113">Top components (sessions)</span></span>

  - <span data-ttu-id="d8fb6-114">[トップの発信元ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-114">Top from users (sessions)</span></span>

  - <span data-ttu-id="d8fb6-115">[トップの発信先ユーザー] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-115">Top to users (sessions)</span></span>

  - <span data-ttu-id="d8fb6-116">[送信元ユーザー エージェント] (セッション)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-116">Top from user agents (sessions)</span></span>

<span data-ttu-id="d8fb6-117">エラーリストレポートでは、ピアツーピアセッションのセッション詳細指標をクリックすることによって、 [Lync Server 2013 のピアツーピアセッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="d8fb6-118">また、電話会議の電話会議の指標をクリックすると、会議詳細レポートにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="d8fb6-119">エラー リスト レポートの活用</span><span class="sxs-lookup"><span data-stu-id="d8fb6-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="d8fb6-p103">エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示することができます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次の説明がツールチップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="d8fb6-122">Internal server error creating media for user. (ユーザーのメディアの作成中に内部サーバー エラーが発生しました。)</span><span class="sxs-lookup"><span data-stu-id="d8fb6-122">Internal server error creating media for user.</span></span>

<span data-ttu-id="d8fb6-123">エラーリストレポートには、少なくとも1つの失敗したセッションに参加したすべてのユーザーの一覧を直接取得する簡単な方法が用意されているわけではありません。また、失敗したセッションに最も多く使用されているユーザーを特定することもできない点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="d8fb6-124">(1 つは、エラーリストレポートにはフィルター機能がありません)。ただし、データをエクスポートしてからコンマ区切り値ファイルに変換する場合は、Windows PowerShell を使用して、これらの質問に対する答えを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="d8fb6-125">たとえば、データをに保存するとします。C: \\ データエラーList.csv という名前の CSV ファイル \\ \_ 。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-125">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="d8fb6-126">このコマンドは、そのファイルに保存されているデータに基づいて、少なくとも1つの失敗したセッションに参加したすべてのユーザーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="d8fb6-127">このコマンドにより、次にような一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-127">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="d8fb6-128">次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="d8fb6-129">これにより、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-129">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d8fb6-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="d8fb6-130">Filters</span></span>

<span data-ttu-id="d8fb6-p105">なし。エラー リスト レポートはフィルターできません。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d8fb6-133">指標</span><span class="sxs-lookup"><span data-stu-id="d8fb6-133">Metrics</span></span>

<span data-ttu-id="d8fb6-134">次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="d8fb6-135">エラー リスト レポートの指標</span><span class="sxs-lookup"><span data-stu-id="d8fb6-135">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8fb6-136">名前</span><span class="sxs-lookup"><span data-stu-id="d8fb6-136">Name</span></span></th>
<th><span data-ttu-id="d8fb6-137">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="d8fb6-137">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d8fb6-138">説明</span><span class="sxs-lookup"><span data-stu-id="d8fb6-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8fb6-139"><strong>レポートされた時刻</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-139"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-140">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-141">レポートが記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-141">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb6-142"><strong>要求</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-142"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-143">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-p106">失敗した SIP 要求の種類です (INVITE、BYE など)。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb6-146"><strong>応答コード</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-146"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-147">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-148">会議にエラーが発生したときに送信された SIP 応答コードです。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-148">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb6-149">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="d8fb6-149"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-150">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-151">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb6-152">[<strong>Join cost time (ms)</strong>] (参加に要した時間 (ミリ秒))</span><span class="sxs-lookup"><span data-stu-id="d8fb6-152"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-153">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-154">ユーザーが会議に参加するのに要した時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb6-155"><strong>送信元ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-155"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-156">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-157">呼び出しを開始したユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-157">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb6-158"><strong>送信元ユーザー エージェント</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-158"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-159">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-160">呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-160">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb6-161"><strong>送信先ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="d8fb6-161"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="d8fb6-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="d8fb6-162">No</span></span></p></td>
<td><p><span data-ttu-id="d8fb6-163">呼び出しを受けたユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d8fb6-163">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

