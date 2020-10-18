---
title: 'Lync Server 2013: 進捗レポートビュー'
description: 'Lync Server 2013: 進捗レポートビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579793"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="fe684-103">Lync Server 2013 の進捗レポートの表示</span><span class="sxs-lookup"><span data-stu-id="fe684-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe684-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fe684-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fe684-105">ProgressReport ビューは、完了したセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="fe684-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="fe684-106">進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fe684-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="fe684-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fe684-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe684-108">ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。</span><span class="sxs-lookup"><span data-stu-id="fe684-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe684-109">Column</span><span class="sxs-lookup"><span data-stu-id="fe684-109">Column</span></span></th>
<th><span data-ttu-id="fe684-110">データ型</span><span class="sxs-lookup"><span data-stu-id="fe684-110">Data Type</span></span></th>
<th><span data-ttu-id="fe684-111">詳細</span><span class="sxs-lookup"><span data-stu-id="fe684-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe684-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-113">日付型</span><span class="sxs-lookup"><span data-stu-id="fe684-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe684-p102">エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</span><span class="sxs-lookup"><span data-stu-id="fe684-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe684-116"><strong>Errorreportseq、</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-117">int</span><span class="sxs-lookup"><span data-stu-id="fe684-117">int</span></span></p></td>
<td><p><span data-ttu-id="fe684-p103">エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</span><span class="sxs-lookup"><span data-stu-id="fe684-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe684-120"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-121">int</span><span class="sxs-lookup"><span data-stu-id="fe684-121">int</span></span></p></td>
<td><p><span data-ttu-id="fe684-122">進行状況レポートを識別するための ID。</span><span class="sxs-lookup"><span data-stu-id="fe684-122">ID to identify the progress report.</span></span> <span data-ttu-id="fe684-123">同じエラー レポートの進行状況レポートを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe684-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe684-124"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-125">int</span><span class="sxs-lookup"><span data-stu-id="fe684-125">int</span></span></p></td>
<td><p><span data-ttu-id="fe684-126">エラー レポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="fe684-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe684-127"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe684-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe684-129">エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="fe684-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe684-130"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe684-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe684-132">エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="fe684-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe684-133"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-134">識別子</span><span class="sxs-lookup"><span data-stu-id="fe684-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe684-135">会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fe684-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe684-136"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-137">int</span><span class="sxs-lookup"><span data-stu-id="fe684-137">int</span></span></p></td>
<td><p><span data-ttu-id="fe684-138">特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="fe684-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe684-139"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="fe684-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="fe684-140">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="fe684-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="fe684-141">追加のエラー情報。</span><span class="sxs-lookup"><span data-stu-id="fe684-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

