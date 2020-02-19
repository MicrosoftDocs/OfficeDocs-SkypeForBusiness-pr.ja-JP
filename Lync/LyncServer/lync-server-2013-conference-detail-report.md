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
ms.openlocfilehash: e51dc2a6834241e355f4a681e4b4d55ef95438fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="4f486-102">Lync Server 2013 の会議詳細レポート</span><span class="sxs-lookup"><span data-stu-id="4f486-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f486-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4f486-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4f486-p101">会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。</span><span class="sxs-lookup"><span data-stu-id="4f486-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="4f486-108">会議詳細レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4f486-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="4f486-109">会議詳細レポートには、次のレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f486-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="4f486-110">[Lync Server 2013 の通話受付管理レポート](lync-server-2013-call-admission-control-report.md)(会議の詳細指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="4f486-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="4f486-111">[Lync Server 2013 のエラーリストレポート](lync-server-2013-failure-list-report.md)(電話会議指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="4f486-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="4f486-112">[Lync Server 2013 のユーザーアクティビティレポート](lync-server-2013-user-activity-report.md)(電話会議 URI 指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="4f486-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="4f486-113">会議詳細レポートから、診断レポート (詳細) 指標をクリックすることによって、 [Lync Server 2013 の診断レポート](lync-server-2013-diagnostic-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f486-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4f486-114">フィルター</span><span class="sxs-lookup"><span data-stu-id="4f486-114">Filters</span></span>

<span data-ttu-id="4f486-p102">なし。会議詳細レポートにはフィルターを適用できません。</span><span class="sxs-lookup"><span data-stu-id="4f486-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4f486-117">指標</span><span class="sxs-lookup"><span data-stu-id="4f486-117">Metrics</span></span>

<span data-ttu-id="4f486-118">次の表は、会議詳細レポートの [電話会議情報] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f486-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="4f486-119">電話会議情報の指標</span><span class="sxs-lookup"><span data-stu-id="4f486-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f486-120">名前</span><span class="sxs-lookup"><span data-stu-id="4f486-120">Name</span></span></th>
<th><span data-ttu-id="4f486-121">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="4f486-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4f486-122">説明</span><span class="sxs-lookup"><span data-stu-id="4f486-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f486-123">[<strong>電話会議 URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-p103">電話会議に割り当てられる URI。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f486-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="4f486-126">sip: kmyer@litwareinc .com; gruu; 非透過 = app: conf: focus: id: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="4f486-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-127">[<strong>プールの FQDN</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-128">セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="4f486-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-129">[<strong>開始時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-130">会議が開始した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-131"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-132">会議を開催したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f486-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-133">[<strong>終了時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-134">会議が終了した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f486-135">次の表は、会議詳細レポートの [電話会議の参加] セクションに提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f486-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="4f486-136">電話会議参加の指標</span><span class="sxs-lookup"><span data-stu-id="4f486-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f486-137">名前</span><span class="sxs-lookup"><span data-stu-id="4f486-137">Name</span></span></th>
<th><span data-ttu-id="4f486-138">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="4f486-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4f486-139">説明</span><span class="sxs-lookup"><span data-stu-id="4f486-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f486-140"><strong>ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-141">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f486-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-142"><strong>ロール</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-143">電話会議の参加者が担った役割 (発表者など)。</span><span class="sxs-lookup"><span data-stu-id="4f486-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-144"><strong>接続</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-145">参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</span><span class="sxs-lookup"><span data-stu-id="4f486-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-146">[参加時間]</span><span class="sxs-lookup"><span data-stu-id="4f486-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-147">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-148">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-149">参加者が電話会議から退出した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-150">[<strong>ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-151">参観者のエンドポイントで使用されるソフトウェアの識別子。</span><span class="sxs-lookup"><span data-stu-id="4f486-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-152">[<strong>診断レポート</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-p104">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="4f486-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f486-155">次の表は、会議詳細レポートの [電話会議のモダリティ] セクションで提供される情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f486-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="4f486-156">電話会議のモダリティの指標</span><span class="sxs-lookup"><span data-stu-id="4f486-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f486-157">名前</span><span class="sxs-lookup"><span data-stu-id="4f486-157">Name</span></span></th>
<th><span data-ttu-id="4f486-158">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="4f486-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4f486-159">説明</span><span class="sxs-lookup"><span data-stu-id="4f486-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f486-160"><strong>ユーザー</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-161">会議に参加したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4f486-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-162">[<strong>参加時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-163">参加者が電話会議に参加した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-164">[<strong>退場時間</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-165">参加者が電話会議を退場した日時。</span><span class="sxs-lookup"><span data-stu-id="4f486-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f486-166">[<strong>電話会議サーバー URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="4f486-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-167">電話会議で使用された電話会議サーバーの URI。</span><span class="sxs-lookup"><span data-stu-id="4f486-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f486-168"><strong>診断レポート</strong></span><span class="sxs-lookup"><span data-stu-id="4f486-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f486-p105">診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</span><span class="sxs-lookup"><span data-stu-id="4f486-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

