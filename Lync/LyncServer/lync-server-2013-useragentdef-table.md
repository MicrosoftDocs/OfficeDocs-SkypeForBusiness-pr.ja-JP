---
title: 'Lync Server 2013: UserAgentDef テーブル'
description: 'Lync Server 2013: UserAgentDef テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b12239d0d6ba6e04a708708a1740dbf02c0e07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548643"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="6da44-103">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="6da44-103">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6da44-104">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="6da44-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="6da44-105">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="6da44-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="6da44-106">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="6da44-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6da44-107">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6da44-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6da44-108">UAType</span><span class="sxs-lookup"><span data-stu-id="6da44-108">UAType</span></span></th>
<th><span data-ttu-id="6da44-109">UAName</span><span class="sxs-lookup"><span data-stu-id="6da44-109">UAName</span></span></th>
<th><span data-ttu-id="6da44-110">UACategory</span><span class="sxs-lookup"><span data-stu-id="6da44-110">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6da44-111">1-d</span><span class="sxs-lookup"><span data-stu-id="6da44-111">1</span></span></p></td>
<td><p><span data-ttu-id="6da44-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6da44-112">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="6da44-113">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6da44-113">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-114">pbm-2</span><span class="sxs-lookup"><span data-stu-id="6da44-114">2</span></span></p></td>
<td><p><span data-ttu-id="6da44-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6da44-115">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="6da44-116">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6da44-116">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-117">4 </span><span class="sxs-lookup"><span data-stu-id="6da44-117">4</span></span></p></td>
<td><p><span data-ttu-id="6da44-118">OC</span><span class="sxs-lookup"><span data-stu-id="6da44-118">OC</span></span></p></td>
<td><p><span data-ttu-id="6da44-119">OC</span><span class="sxs-lookup"><span data-stu-id="6da44-119">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-120">8 </span><span class="sxs-lookup"><span data-stu-id="6da44-120">8</span></span></p></td>
<td><p><span data-ttu-id="6da44-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6da44-121">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="6da44-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6da44-122">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-123">16 </span><span class="sxs-lookup"><span data-stu-id="6da44-123">16</span></span></p></td>
<td><p><span data-ttu-id="6da44-124">LMC</span><span class="sxs-lookup"><span data-stu-id="6da44-124">LMC</span></span></p></td>
<td><p><span data-ttu-id="6da44-125">LMC</span><span class="sxs-lookup"><span data-stu-id="6da44-125">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-126">32</span><span class="sxs-lookup"><span data-stu-id="6da44-126">32</span></span></p></td>
<td><p><span data-ttu-id="6da44-127">DVT</span><span class="sxs-lookup"><span data-stu-id="6da44-127">DVT</span></span></p></td>
<td><p><span data-ttu-id="6da44-128">DVT</span><span class="sxs-lookup"><span data-stu-id="6da44-128">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-129">64</span><span class="sxs-lookup"><span data-stu-id="6da44-129">64</span></span></p></td>
<td><p><span data-ttu-id="6da44-130">MM</span><span class="sxs-lookup"><span data-stu-id="6da44-130">MM</span></span></p></td>
<td><p><span data-ttu-id="6da44-131">MM</span><span class="sxs-lookup"><span data-stu-id="6da44-131">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-132">64</span><span class="sxs-lookup"><span data-stu-id="6da44-132">64</span></span></p></td>
<td><p><span data-ttu-id="6da44-133">MC</span><span class="sxs-lookup"><span data-stu-id="6da44-133">MC</span></span></p></td>
<td><p><span data-ttu-id="6da44-134">MM</span><span class="sxs-lookup"><span data-stu-id="6da44-134">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-135">128</span><span class="sxs-lookup"><span data-stu-id="6da44-135">128</span></span></p></td>
<td><p><span data-ttu-id="6da44-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="6da44-136">Attendant</span></span></p></td>
<td><p><span data-ttu-id="6da44-137">Attendant</span><span class="sxs-lookup"><span data-stu-id="6da44-137">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-138">256</span><span class="sxs-lookup"><span data-stu-id="6da44-138">256</span></span></p></td>
<td><p><span data-ttu-id="6da44-139">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="6da44-139">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6da44-140">CA</span><span class="sxs-lookup"><span data-stu-id="6da44-140">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-141">512</span><span class="sxs-lookup"><span data-stu-id="6da44-141">512</span></span></p></td>
<td><p><span data-ttu-id="6da44-142">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="6da44-142">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6da44-143">CAA</span><span class="sxs-lookup"><span data-stu-id="6da44-143">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-144">512</span><span class="sxs-lookup"><span data-stu-id="6da44-144">512</span></span></p></td>
<td><p><span data-ttu-id="6da44-145">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="6da44-145">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6da44-146">CAA</span><span class="sxs-lookup"><span data-stu-id="6da44-146">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-147">1024</span><span class="sxs-lookup"><span data-stu-id="6da44-147">1024</span></span></p></td>
<td><p><span data-ttu-id="6da44-148">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="6da44-148">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="6da44-149">RG</span><span class="sxs-lookup"><span data-stu-id="6da44-149">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-150">1032</span><span class="sxs-lookup"><span data-stu-id="6da44-150">1032</span></span></p></td>
<td><p><span data-ttu-id="6da44-151">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="6da44-151">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6da44-152">CPS</span><span class="sxs-lookup"><span data-stu-id="6da44-152">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-153">1040</span><span class="sxs-lookup"><span data-stu-id="6da44-153">1040</span></span></p></td>
<td><p><span data-ttu-id="6da44-154">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="6da44-154">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="6da44-155">AS</span><span class="sxs-lookup"><span data-stu-id="6da44-155">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-156">2048</span><span class="sxs-lookup"><span data-stu-id="6da44-156">2048</span></span></p></td>
<td><p><span data-ttu-id="6da44-157">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6da44-157">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="6da44-158">CC</span><span class="sxs-lookup"><span data-stu-id="6da44-158">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-159">16386</span><span class="sxs-lookup"><span data-stu-id="6da44-159">16386</span></span></p></td>
<td><p><span data-ttu-id="6da44-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="6da44-160">CoMo</span></span></p></td>
<td><p><span data-ttu-id="6da44-161">CoMo</span><span class="sxs-lookup"><span data-stu-id="6da44-161">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-162">16387</span><span class="sxs-lookup"><span data-stu-id="6da44-162">16387</span></span></p></td>
<td><p><span data-ttu-id="6da44-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="6da44-163">CWA</span></span></p></td>
<td><p><span data-ttu-id="6da44-164">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="6da44-164">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-165">16388</span><span class="sxs-lookup"><span data-stu-id="6da44-165">16388</span></span></p></td>
<td><p><span data-ttu-id="6da44-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6da44-166">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="6da44-167">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6da44-167">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-168">16389</span><span class="sxs-lookup"><span data-stu-id="6da44-168">16389</span></span></p></td>
<td><p><span data-ttu-id="6da44-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6da44-169">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="6da44-170">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6da44-170">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-171">16393</span><span class="sxs-lookup"><span data-stu-id="6da44-171">16393</span></span></p></td>
<td><p><span data-ttu-id="6da44-172">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="6da44-172">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="6da44-173">ExUM</span><span class="sxs-lookup"><span data-stu-id="6da44-173">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-174">16395</span><span class="sxs-lookup"><span data-stu-id="6da44-174">16395</span></span></p></td>
<td><p><span data-ttu-id="6da44-175">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="6da44-175">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="6da44-176">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="6da44-176">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-177">16396</span><span class="sxs-lookup"><span data-stu-id="6da44-177">16396</span></span></p></td>
<td><p><span data-ttu-id="6da44-178">停止</span><span class="sxs-lookup"><span data-stu-id="6da44-178">ST</span></span></p></td>
<td><p><span data-ttu-id="6da44-179">停止</span><span class="sxs-lookup"><span data-stu-id="6da44-179">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-180">16397</span><span class="sxs-lookup"><span data-stu-id="6da44-180">16397</span></span></p></td>
<td><p><span data-ttu-id="6da44-181">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="6da44-181">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="6da44-182">ASMCU</span><span class="sxs-lookup"><span data-stu-id="6da44-182">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-183">16398</span><span class="sxs-lookup"><span data-stu-id="6da44-183">16398</span></span></p></td>
<td><p><span data-ttu-id="6da44-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="6da44-184">WPLync</span></span></p></td>
<td><p><span data-ttu-id="6da44-185">WPLync</span><span class="sxs-lookup"><span data-stu-id="6da44-185">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-186">16399</span><span class="sxs-lookup"><span data-stu-id="6da44-186">16399</span></span></p></td>
<td><p><span data-ttu-id="6da44-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6da44-187">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="6da44-188">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6da44-188">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-189">16400</span><span class="sxs-lookup"><span data-stu-id="6da44-189">16400</span></span></p></td>
<td><p><span data-ttu-id="6da44-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6da44-190">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="6da44-191">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6da44-191">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-192">16401</span><span class="sxs-lookup"><span data-stu-id="6da44-192">16401</span></span></p></td>
<td><p><span data-ttu-id="6da44-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6da44-193">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="6da44-194">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6da44-194">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-195">16402</span><span class="sxs-lookup"><span data-stu-id="6da44-195">16402</span></span></p></td>
<td><p><span data-ttu-id="6da44-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6da44-196">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="6da44-197">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6da44-197">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-198">16403</span><span class="sxs-lookup"><span data-stu-id="6da44-198">16403</span></span></p></td>
<td><p><span data-ttu-id="6da44-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6da44-199">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="6da44-200">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6da44-200">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-201">16404</span><span class="sxs-lookup"><span data-stu-id="6da44-201">16404</span></span></p></td>
<td><p><span data-ttu-id="6da44-202">CPC</span><span class="sxs-lookup"><span data-stu-id="6da44-202">PCS</span></span></p></td>
<td><p><span data-ttu-id="6da44-203">CPC</span><span class="sxs-lookup"><span data-stu-id="6da44-203">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-204">16405</span><span class="sxs-lookup"><span data-stu-id="6da44-204">16405</span></span></p></td>
<td><p><span data-ttu-id="6da44-205">LWA</span><span class="sxs-lookup"><span data-stu-id="6da44-205">LWA</span></span></p></td>
<td><p><span data-ttu-id="6da44-206">LWA</span><span class="sxs-lookup"><span data-stu-id="6da44-206">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-207">16406</span><span class="sxs-lookup"><span data-stu-id="6da44-207">16406</span></span></p></td>
<td><p><span data-ttu-id="6da44-208">OWA</span><span class="sxs-lookup"><span data-stu-id="6da44-208">OWA</span></span></p></td>
<td><p><span data-ttu-id="6da44-209">OWA</span><span class="sxs-lookup"><span data-stu-id="6da44-209">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-210">16407</span><span class="sxs-lookup"><span data-stu-id="6da44-210">16407</span></span></p></td>
<td><p><span data-ttu-id="6da44-211">の「c」</span><span class="sxs-lookup"><span data-stu-id="6da44-211">AOC</span></span></p></td>
<td><p><span data-ttu-id="6da44-212">の「c」</span><span class="sxs-lookup"><span data-stu-id="6da44-212">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-213">16408</span><span class="sxs-lookup"><span data-stu-id="6da44-213">16408</span></span></p></td>
<td><p><span data-ttu-id="6da44-214">GCC</span><span class="sxs-lookup"><span data-stu-id="6da44-214">GCC</span></span></p></td>
<td><p><span data-ttu-id="6da44-215">GCC</span><span class="sxs-lookup"><span data-stu-id="6da44-215">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-216">16409</span><span class="sxs-lookup"><span data-stu-id="6da44-216">16409</span></span></p></td>
<td><p><span data-ttu-id="6da44-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6da44-217">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="6da44-218">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6da44-218">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-219">16410</span><span class="sxs-lookup"><span data-stu-id="6da44-219">16410</span></span></p></td>
<td><p><span data-ttu-id="6da44-220">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="6da44-220">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="6da44-221">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="6da44-221">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6da44-222">32769</span><span class="sxs-lookup"><span data-stu-id="6da44-222">32769</span></span></p></td>
<td><p><span data-ttu-id="6da44-223">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6da44-223">Gateway</span></span></p></td>
<td><p><span data-ttu-id="6da44-224">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6da44-224">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6da44-225">32770</span><span class="sxs-lookup"><span data-stu-id="6da44-225">32770</span></span></p></td>
<td><p><span data-ttu-id="6da44-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="6da44-226">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="6da44-227">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="6da44-227">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

