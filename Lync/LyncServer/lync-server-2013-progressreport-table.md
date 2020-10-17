---
title: 'Lync Server 2013: 進捗レポートテーブル'
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
ms.openlocfilehash: c92adf48a09f83c3c3dec18f91e4aadc3a3cbd39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513234"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="9af4c-102">Lync Server 2013 の進捗レポートの表</span><span class="sxs-lookup"><span data-stu-id="9af4c-102">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9af4c-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9af4c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9af4c-104">進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。</span><span class="sxs-lookup"><span data-stu-id="9af4c-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="9af4c-105">進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9af4c-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="9af4c-106">ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="9af4c-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9af4c-107">Column</span><span class="sxs-lookup"><span data-stu-id="9af4c-107">Column</span></span></th>
<th><span data-ttu-id="9af4c-108">データ型</span><span class="sxs-lookup"><span data-stu-id="9af4c-108">Data Type</span></span></th>
<th><span data-ttu-id="9af4c-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="9af4c-109">Key/Index</span></span></th>
<th><span data-ttu-id="9af4c-110">詳細</span><span class="sxs-lookup"><span data-stu-id="9af4c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9af4c-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-112">日付型</span><span class="sxs-lookup"><span data-stu-id="9af4c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9af4c-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9af4c-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9af4c-114">この進行状況レポートを含む進行状況エラー レポートの日時。</span><span class="sxs-lookup"><span data-stu-id="9af4c-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="9af4c-115">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9af4c-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9af4c-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-117">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-117">int</span></span></p></td>
<td><p><span data-ttu-id="9af4c-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9af4c-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9af4c-119">進捗レポートを一意に識別するために ErrorTime、progress Reportseq と共に使用される ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9af4c-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="9af4c-120">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9af4c-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9af4c-121"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-122">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-122">int</span></span></p></td>
<td><p><span data-ttu-id="9af4c-123">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="9af4c-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9af4c-124">エラー レポートを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="9af4c-124">ID number that identifies the error report.</span></span> <span data-ttu-id="9af4c-125">ErrorReporSeq は、一意的にエラー レポートを識別する目的で ErrorTime と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9af4c-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="9af4c-126">詳細については、「 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9af4c-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="9af4c-127">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9af4c-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9af4c-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-129">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-129">int</span></span></p></td>
<td><p><span data-ttu-id="9af4c-130">Primary</span><span class="sxs-lookup"><span data-stu-id="9af4c-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="9af4c-p105">進行状況レポートを識別するための ID 番号。進行状況レポートを一意に識別するために ErrorTime と ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="9af4c-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9af4c-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-134">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9af4c-135">進行状況レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="9af4c-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="9af4c-136">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9af4c-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9af4c-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-138">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-138">int</span></span></p></td>
<td><p><span data-ttu-id="9af4c-139">外部</span><span class="sxs-lookup"><span data-stu-id="9af4c-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9af4c-140">エラーレポートを送信したサーバー (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="9af4c-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="9af4c-141">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9af4c-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9af4c-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-143">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9af4c-p107">レポートの対象となる Lync Server プロセス。詳細については、「アプリケーション テーブル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9af4c-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9af4c-146"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-147">image</span><span class="sxs-lookup"><span data-stu-id="9af4c-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9af4c-148">進行状況レポートの詳細。記憶域を節約するできるようにバイナリ形式で格納されます。このデータは、次のコードを使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="9af4c-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="9af4c-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="9af4c-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9af4c-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-151">識別子</span><span class="sxs-lookup"><span data-stu-id="9af4c-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9af4c-152">電話会議に関係するさまざまなコンポーネントの参加時間情報を関連付ける一意識別子。</span><span class="sxs-lookup"><span data-stu-id="9af4c-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="9af4c-153">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9af4c-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9af4c-154"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="9af4c-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9af4c-155">int</span><span class="sxs-lookup"><span data-stu-id="9af4c-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9af4c-156">特定のコンポーネントが電話会議に参加する時間 (単位はミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="9af4c-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="9af4c-157">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9af4c-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

