---
title: 'Lync Server 2013: ピアツーピアセッション詳細レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c977b2f9f9a6248ab7ba5d5391397d4cd4326a18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="754b7-102">Lync Server 2013 のピアツーピアセッション詳細レポート</span><span class="sxs-lookup"><span data-stu-id="754b7-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="754b7-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="754b7-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="754b7-p101">ピアツーピア セッション詳細レポートは、ピアツーピア セッションに関する詳細情報を提供します。たとえば、インスタント メッセージング セッションを選択すると、セッション中に 2 人のユーザーのそれぞれが送信したメッセージ数がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="754b7-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="754b7-106">ピアツーピア セッション詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="754b7-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="754b7-107">ピアツーピア セッション詳細レポートには、次のいずれかのレポートからアクセスできます (これらのレポートはすべて、監視レポートのホーム ページからアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="754b7-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="754b7-108">IP 電話インベントリ レポート</span><span class="sxs-lookup"><span data-stu-id="754b7-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="754b7-109">ユーザー アクティビティ レポート</span><span class="sxs-lookup"><span data-stu-id="754b7-109">User Activity Report</span></span>

  - <span data-ttu-id="754b7-110">通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="754b7-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="754b7-111">エラー リスト レポート</span><span class="sxs-lookup"><span data-stu-id="754b7-111">Failure List Report</span></span>

<span data-ttu-id="754b7-112">ピアツーピアセッション詳細レポート内から、診断レポート (詳細) 指標をクリックして[Lync Server 2013 の診断レポート](lync-server-2013-diagnostic-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="754b7-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="754b7-113">次のいずれかの指標をクリックしてトップ エラー レポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="754b7-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="754b7-114">応答</span><span class="sxs-lookup"><span data-stu-id="754b7-114">Response</span></span>

  - <span data-ttu-id="754b7-115">診断 ID</span><span class="sxs-lookup"><span data-stu-id="754b7-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="754b7-116">ピアツーピア セッション詳細レポートの有効活用</span><span class="sxs-lookup"><span data-stu-id="754b7-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="754b7-p103">ピアツーピア セッション詳細レポートには数多くの指標が含まれています。システム管理者にとって馴染みのないものも多いかもしれませんが、通常は、指標のラベルにマウス ポインターを置くと簡単な説明を示したヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="754b7-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="754b7-p104">レポートに表示される実際の指標は、選択したピアツーピア セッションの種類によって決まります。音声ビデオ セッションのレポートに表示される指標は、インスタント メッセージング セッションの指標とは異なります。</span><span class="sxs-lookup"><span data-stu-id="754b7-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="754b7-121">また、応答コードおよび診断 ID の指標にマウス ポインターを置くと、その値の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="754b7-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="754b7-122">フィルター</span><span class="sxs-lookup"><span data-stu-id="754b7-122">Filters</span></span>

<span data-ttu-id="754b7-p105">なし。ピアツーピア セッション詳細レポートはフィルターできません。</span><span class="sxs-lookup"><span data-stu-id="754b7-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="754b7-125">セッション情報の指標</span><span class="sxs-lookup"><span data-stu-id="754b7-125">Session Information Metrics</span></span>

<span data-ttu-id="754b7-126">次の表に、ピアツーピア セッション詳細レポートでセッションごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="754b7-127">セッション情報の指標</span><span class="sxs-lookup"><span data-stu-id="754b7-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="754b7-128">名前</span><span class="sxs-lookup"><span data-stu-id="754b7-128">Name</span></span></th>
<th><span data-ttu-id="754b7-129">説明</span><span class="sxs-lookup"><span data-stu-id="754b7-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="754b7-130">[<strong>プールの FQDN</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-131">セッションに関与したレジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="754b7-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-132">[<strong>招待時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-133">セッションへの招待が最初に送信された日時です。</span><span class="sxs-lookup"><span data-stu-id="754b7-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-134">[<strong>応答時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-135">招待の承諾を受信した日時です。</span><span class="sxs-lookup"><span data-stu-id="754b7-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-136">[<strong>送信元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-137">セッションを開始したユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="754b7-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-138">[<strong>送信元ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-139">セッションを開始したユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="754b7-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-140">[<strong>内部の送信元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-141">セッションを開始したユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-142">[<strong>電話と統合された送信元ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-143">セッションを開始したユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-144">[<strong>セッションの優先順位</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-p106">セッションに割り当てられた優先順位。有効な優先順位として、不明、非緊急、標準、至急、および緊急があります。</span><span class="sxs-lookup"><span data-stu-id="754b7-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-147">[<strong>応答コード</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-148">セッションでエラーが発生したときに送信された SIP 応答コードです。</span><span class="sxs-lookup"><span data-stu-id="754b7-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-149">[<strong>フロントエンド</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-150">電話会議で使用されたフロントエンド サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="754b7-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-151">[<strong>キャプチャ時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-152">セッションの情報が記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="754b7-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-153">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-154">セッションが終了した日時です。</span><span class="sxs-lookup"><span data-stu-id="754b7-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-155">[<strong>送信先ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-156">セッションに招待されたユーザーの SIP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="754b7-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-157">[<strong>送信先ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-158">セッションに招待されたユーザーのエンドポイントで使用されているソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="754b7-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-159">[<strong>内部の送信先ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-160">セッションに招待されたユーザーが内部ネットワークにログオンしていたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-161">[<strong>電話と統合された送信先ユーザー</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-162">セッションに招待されたユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-163">[<strong>再試行セッション</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-164">以前エラーが発生したセッションを再試行するためのセッションかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-165">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-p107">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。マウス ポインターを ID 番号の上に置くと、その ID に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="754b7-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="754b7-168">モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="754b7-168">Metrics for Modalities</span></span>

<span data-ttu-id="754b7-169">次の表に、ピアツーピア セッション詳細レポートでセッションのモダリティごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="754b7-170">モダリティの指標</span><span class="sxs-lookup"><span data-stu-id="754b7-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="754b7-171">名前</span><span class="sxs-lookup"><span data-stu-id="754b7-171">Name</span></span></th>
<th><span data-ttu-id="754b7-172">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="754b7-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="754b7-173">説明</span><span class="sxs-lookup"><span data-stu-id="754b7-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="754b7-174"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="754b7-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-175">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-p108">セッションで使用されるモダリティ。インスタント メッセージング (IM)、ファイル送信など。</span><span class="sxs-lookup"><span data-stu-id="754b7-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-178">[<strong>送信元ユーザー メッセージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-179">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-180">セッションを開始したユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="754b7-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-181">[<strong>送信先ユーザー メッセージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-182">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-182">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-183">セッションに招待されたユーザーが送信したメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="754b7-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="754b7-184">診断レポートの指標</span><span class="sxs-lookup"><span data-stu-id="754b7-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="754b7-185">次の表に、ピアツーピア セッション詳細レポートで診断レポートごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="754b7-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="754b7-186">診断レポートの指標</span><span class="sxs-lookup"><span data-stu-id="754b7-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="754b7-187">名前</span><span class="sxs-lookup"><span data-stu-id="754b7-187">Name</span></span></th>
<th><span data-ttu-id="754b7-188">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="754b7-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="754b7-189">説明</span><span class="sxs-lookup"><span data-stu-id="754b7-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="754b7-190"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="754b7-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-191">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-192">この項目をクリックすると、セッションの診断レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="754b7-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-193">[<strong>レポート時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-194">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-195">レポートが記録された日時です。</span><span class="sxs-lookup"><span data-stu-id="754b7-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-196"><strong>要求</strong></span><span class="sxs-lookup"><span data-stu-id="754b7-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-197">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-197">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-p109">SIP 要求の種類。INVITE、BYE など。</span><span class="sxs-lookup"><span data-stu-id="754b7-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-200">[<strong>診断 ID</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-201">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-202">エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。</span><span class="sxs-lookup"><span data-stu-id="754b7-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="754b7-203"><strong>コンテンツの種類</strong></span><span class="sxs-lookup"><span data-stu-id="754b7-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-204">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-p110">会議で使用されたメディア コンテンツの種類。たとえば、一般的なコンテンツの種類は "アプリケーション/sdp" です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションへの招待、およびその他の形のマルチメディア セッションの開始で使用される標準的なインターネット プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="754b7-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="754b7-208">[<strong>レポート作成者</strong>]</span><span class="sxs-lookup"><span data-stu-id="754b7-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="754b7-209">いいえ</span><span class="sxs-lookup"><span data-stu-id="754b7-209">No</span></span></p></td>
<td><p><span data-ttu-id="754b7-210">問題を報告したコンピューター (クライアントまたはサーバー) です。</span><span class="sxs-lookup"><span data-stu-id="754b7-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

