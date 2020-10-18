---
title: 'Lync Server 2013: 進捗レポートテーブル'
description: 'Lync Server 2013: 進捗レポートの表。'
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
ms.openlocfilehash: d36ee2ab75410ea2462da4b647ef5b45afefb1bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579823"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="a0351-103">Lync Server 2013 の進捗レポートの表</span><span class="sxs-lookup"><span data-stu-id="a0351-103">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0351-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a0351-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a0351-105">進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。</span><span class="sxs-lookup"><span data-stu-id="a0351-105">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="a0351-106">進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a0351-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="a0351-107">ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="a0351-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0351-108">Column</span><span class="sxs-lookup"><span data-stu-id="a0351-108">Column</span></span></th>
<th><span data-ttu-id="a0351-109">データ型</span><span class="sxs-lookup"><span data-stu-id="a0351-109">Data Type</span></span></th>
<th><span data-ttu-id="a0351-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a0351-110">Key/Index</span></span></th>
<th><span data-ttu-id="a0351-111">詳細</span><span class="sxs-lookup"><span data-stu-id="a0351-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0351-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-113">日付型</span><span class="sxs-lookup"><span data-stu-id="a0351-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="a0351-114">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="a0351-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0351-115">この進行状況レポートを含む進行状況エラー レポートの日時。</span><span class="sxs-lookup"><span data-stu-id="a0351-115">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="a0351-116">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0351-116">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0351-117"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-117"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-118">int</span><span class="sxs-lookup"><span data-stu-id="a0351-118">int</span></span></p></td>
<td><p><span data-ttu-id="a0351-119">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="a0351-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0351-120">進捗レポートを一意に識別するために ErrorTime、progress Reportseq と共に使用される ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a0351-120">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="a0351-121">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0351-121">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0351-122"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-122"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-123">int</span><span class="sxs-lookup"><span data-stu-id="a0351-123">int</span></span></p></td>
<td><p><span data-ttu-id="a0351-124">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="a0351-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0351-125">エラー レポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a0351-125">ID number that identifies the error report.</span></span> <span data-ttu-id="a0351-126">ErrorReporSeq は、一意的にエラー レポートを識別する目的で ErrorTime と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0351-126">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="a0351-127">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0351-127">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="a0351-128">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0351-128">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0351-129"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-129"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-130">int</span><span class="sxs-lookup"><span data-stu-id="a0351-130">int</span></span></p></td>
<td><p><span data-ttu-id="a0351-131">Primary</span><span class="sxs-lookup"><span data-stu-id="a0351-131">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0351-p105">進行状況レポートを識別するための ID 番号。進行状況レポートを一意に識別するために ErrorTime と ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="a0351-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0351-134"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-134"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-135">int</span><span class="sxs-lookup"><span data-stu-id="a0351-135">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0351-136">進行状況レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="a0351-136">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="a0351-137">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0351-137">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0351-138"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-138"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-139">int</span><span class="sxs-lookup"><span data-stu-id="a0351-139">int</span></span></p></td>
<td><p><span data-ttu-id="a0351-140">外部</span><span class="sxs-lookup"><span data-stu-id="a0351-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a0351-141">エラーレポートを送信したサーバー (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="a0351-141">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="a0351-142">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0351-142">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0351-143"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-143"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-144">int</span><span class="sxs-lookup"><span data-stu-id="a0351-144">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0351-p107">レポートの対象となる Lync Server プロセス。詳細については、「アプリケーション テーブル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0351-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0351-147"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-147"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-148">image</span><span class="sxs-lookup"><span data-stu-id="a0351-148">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0351-149">進行状況レポートの詳細。記憶域を節約するできるようにバイナリ形式で格納されます。このデータは、次のコードを使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="a0351-149">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="a0351-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="a0351-150">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0351-151"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-151"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-152">識別子</span><span class="sxs-lookup"><span data-stu-id="a0351-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0351-153">電話会議に関係するさまざまなコンポーネントの参加時間情報を関連付ける一意識別子。</span><span class="sxs-lookup"><span data-stu-id="a0351-153">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="a0351-154">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0351-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0351-155"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="a0351-155"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a0351-156">int</span><span class="sxs-lookup"><span data-stu-id="a0351-156">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0351-157">特定のコンポーネントが電話会議に参加する時間 (単位はミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="a0351-157">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="a0351-158">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a0351-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

