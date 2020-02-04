---
title: 'Lync Server 2013: 進捗状況レポートビュー'
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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="20472-102">Lync Server 2013 の進捗状況レポートビュー</span><span class="sxs-lookup"><span data-stu-id="20472-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20472-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="20472-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="20472-104">進捗レポートビューには、完了したセッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="20472-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="20472-105">進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。</span><span class="sxs-lookup"><span data-stu-id="20472-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="20472-106">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="20472-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20472-107">ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="20472-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20472-108">列</span><span class="sxs-lookup"><span data-stu-id="20472-108">Column</span></span></th>
<th><span data-ttu-id="20472-109">データ型</span><span class="sxs-lookup"><span data-stu-id="20472-109">Data Type</span></span></th>
<th><span data-ttu-id="20472-110">詳細</span><span class="sxs-lookup"><span data-stu-id="20472-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20472-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="20472-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-112">datetime</span><span class="sxs-lookup"><span data-stu-id="20472-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="20472-113">エラーが発生した時刻。</span><span class="sxs-lookup"><span data-stu-id="20472-113">Time of error occurred.</span></span> <span data-ttu-id="20472-114">エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。</span><span class="sxs-lookup"><span data-stu-id="20472-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="20472-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-116">int</span><span class="sxs-lookup"><span data-stu-id="20472-116">int</span></span></p></td>
<td><p><span data-ttu-id="20472-117">エラーを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="20472-117">ID number to identify the error.</span></span> <span data-ttu-id="20472-118">エラーを一意に識別するための ErrorTime と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="20472-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-119"><strong>進捗状況レポート Seq</strong></span><span class="sxs-lookup"><span data-stu-id="20472-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-120">int</span><span class="sxs-lookup"><span data-stu-id="20472-120">int</span></span></p></td>
<td><p><span data-ttu-id="20472-121">進行状況レポートを識別する ID。</span><span class="sxs-lookup"><span data-stu-id="20472-121">ID to identify the progress report.</span></span> <span data-ttu-id="20472-122">同じエラーレポートの進行状況レポートを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="20472-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="20472-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-124">int</span><span class="sxs-lookup"><span data-stu-id="20472-124">int</span></span></p></td>
<td><p><span data-ttu-id="20472-125">エラーレポートの診断 ID。</span><span class="sxs-lookup"><span data-stu-id="20472-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-126"><strong>ソース</strong></span><span class="sxs-lookup"><span data-stu-id="20472-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="20472-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="20472-128">エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="20472-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="20472-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="20472-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="20472-131">エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。</span><span class="sxs-lookup"><span data-stu-id="20472-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="20472-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-133">長さ</span><span class="sxs-lookup"><span data-stu-id="20472-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="20472-134">電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</span><span class="sxs-lookup"><span data-stu-id="20472-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-135"><strong>SessionSetupTime 時間</strong></span><span class="sxs-lookup"><span data-stu-id="20472-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-136">int</span><span class="sxs-lookup"><span data-stu-id="20472-136">int</span></span></p></td>
<td><p><span data-ttu-id="20472-137">特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="20472-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="20472-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="20472-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="20472-140">追加のエラー情報。</span><span class="sxs-lookup"><span data-stu-id="20472-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

