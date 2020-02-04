---
title: 'Lync Server 2013: ProgressReport テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="edbab-102">Lync Server 2013 の ProgressReport テーブル</span><span class="sxs-lookup"><span data-stu-id="edbab-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edbab-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="edbab-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="edbab-104">進行状況レポートは、呼び出しまたはセッションが完了した後に、クライアントからデータベースにアップロードされたデータに基づいています。</span><span class="sxs-lookup"><span data-stu-id="edbab-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="edbab-105">進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。</span><span class="sxs-lookup"><span data-stu-id="edbab-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="edbab-106">ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="edbab-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edbab-107">列</span><span class="sxs-lookup"><span data-stu-id="edbab-107">Column</span></span></th>
<th><span data-ttu-id="edbab-108">データ型</span><span class="sxs-lookup"><span data-stu-id="edbab-108">Data Type</span></span></th>
<th><span data-ttu-id="edbab-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="edbab-109">Key/Index</span></span></th>
<th><span data-ttu-id="edbab-110">詳細</span><span class="sxs-lookup"><span data-stu-id="edbab-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edbab-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-112">datetime</span><span class="sxs-lookup"><span data-stu-id="edbab-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="edbab-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="edbab-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="edbab-114">この進捗状況レポートが含まれる進捗状況エラーレポートの日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="edbab-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="edbab-115">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edbab-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbab-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-117">int</span><span class="sxs-lookup"><span data-stu-id="edbab-117">int</span></span></p></td>
<td><p><span data-ttu-id="edbab-118">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="edbab-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="edbab-119">ID 番号は、ErrorTime と共に使用されます。進捗レポートは、進行状況レポートを一意に識別するために使われます。</span><span class="sxs-lookup"><span data-stu-id="edbab-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="edbab-120">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edbab-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbab-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-122">int</span><span class="sxs-lookup"><span data-stu-id="edbab-122">int</span></span></p></td>
<td><p><span data-ttu-id="edbab-123">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="edbab-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="edbab-124">エラーレポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="edbab-124">ID number that identifies the error report.</span></span> <span data-ttu-id="edbab-125">エラーレポートを一意に識別するには、ErrorReporSeq と ErrorTime との組み合わせで使用されます。</span><span class="sxs-lookup"><span data-stu-id="edbab-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="edbab-126">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edbab-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="edbab-127">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edbab-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbab-128"><strong>進捗状況レポート Seq</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-129">int</span><span class="sxs-lookup"><span data-stu-id="edbab-129">int</span></span></p></td>
<td><p><span data-ttu-id="edbab-130">Primary</span><span class="sxs-lookup"><span data-stu-id="edbab-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="edbab-131">進捗状況レポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="edbab-131">ID number to identify the progress report.</span></span> <span data-ttu-id="edbab-132">ErrorTime と ErrorReportSeq と組み合わせて、進行状況レポートを一意に識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edbab-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbab-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-134">int</span><span class="sxs-lookup"><span data-stu-id="edbab-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edbab-135">進行状況レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="edbab-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="edbab-136">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edbab-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbab-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-138">int</span><span class="sxs-lookup"><span data-stu-id="edbab-138">int</span></span></p></td>
<td><p><span data-ttu-id="edbab-139">外部</span><span class="sxs-lookup"><span data-stu-id="edbab-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="edbab-140">エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="edbab-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="edbab-141">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edbab-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbab-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-143">int</span><span class="sxs-lookup"><span data-stu-id="edbab-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edbab-144">レポートの作成に関する Lync Server プロセス。</span><span class="sxs-lookup"><span data-stu-id="edbab-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="edbab-145">詳しくは、アプリケーションの表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="edbab-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbab-146"><strong>[詳細]</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-147">画像</span><span class="sxs-lookup"><span data-stu-id="edbab-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edbab-148">サイズを節約するためのバイナリ形式で保存された進行状況レポートの詳細。このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="edbab-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="edbab-149">cast (cast (varbinary (max) としての Detail (max))</span><span class="sxs-lookup"><span data-stu-id="edbab-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edbab-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-151">長さ</span><span class="sxs-lookup"><span data-stu-id="edbab-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edbab-152">会議に参加しているさまざまなコンポーネントの参加時間情報を関連付ける一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="edbab-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="edbab-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edbab-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edbab-154"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="edbab-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="edbab-155">int</span><span class="sxs-lookup"><span data-stu-id="edbab-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="edbab-156">特定のコンポーネントが会議に参加するまでの時間 (ミリ秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="edbab-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="edbab-157">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edbab-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

