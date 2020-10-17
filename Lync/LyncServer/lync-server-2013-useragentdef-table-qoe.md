---
title: 'Lync Server 2013: UserAgentDef テーブル (QoE)'
description: 'Lync Server 2013: UserAgentDef テーブル (QoE)。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8546a33e607524b23755e9abf3edb2d5e2e417d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547343"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="5bb47-103">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="5bb47-103">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bb47-104">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="5bb47-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="5bb47-105">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="5bb47-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="5bb47-106">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="5bb47-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bb47-107">UAType</span><span class="sxs-lookup"><span data-stu-id="5bb47-107">UAType</span></span></th>
<th><span data-ttu-id="5bb47-108">UAName</span><span class="sxs-lookup"><span data-stu-id="5bb47-108">UAName</span></span></th>
<th><span data-ttu-id="5bb47-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="5bb47-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-110">1-d</span><span class="sxs-lookup"><span data-stu-id="5bb47-110">1</span></span></p></td>
<td><p><span data-ttu-id="5bb47-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="5bb47-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="5bb47-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="5bb47-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-113">pbm-2</span><span class="sxs-lookup"><span data-stu-id="5bb47-113">2</span></span></p></td>
<td><p><span data-ttu-id="5bb47-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="5bb47-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="5bb47-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="5bb47-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-116">4 </span><span class="sxs-lookup"><span data-stu-id="5bb47-116">4</span></span></p></td>
<td><p><span data-ttu-id="5bb47-117">OC</span><span class="sxs-lookup"><span data-stu-id="5bb47-117">OC</span></span></p></td>
<td><p><span data-ttu-id="5bb47-118">OC</span><span class="sxs-lookup"><span data-stu-id="5bb47-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-119">8 </span><span class="sxs-lookup"><span data-stu-id="5bb47-119">8</span></span></p></td>
<td><p><span data-ttu-id="5bb47-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="5bb47-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="5bb47-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="5bb47-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-122">16 </span><span class="sxs-lookup"><span data-stu-id="5bb47-122">16</span></span></p></td>
<td><p><span data-ttu-id="5bb47-123">LMC</span><span class="sxs-lookup"><span data-stu-id="5bb47-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="5bb47-124">LMC</span><span class="sxs-lookup"><span data-stu-id="5bb47-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-125">32</span><span class="sxs-lookup"><span data-stu-id="5bb47-125">32</span></span></p></td>
<td><p><span data-ttu-id="5bb47-126">DVT</span><span class="sxs-lookup"><span data-stu-id="5bb47-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="5bb47-127">DVT</span><span class="sxs-lookup"><span data-stu-id="5bb47-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-128">64</span><span class="sxs-lookup"><span data-stu-id="5bb47-128">64</span></span></p></td>
<td><p><span data-ttu-id="5bb47-129">MM</span><span class="sxs-lookup"><span data-stu-id="5bb47-129">MM</span></span></p></td>
<td><p><span data-ttu-id="5bb47-130">MM</span><span class="sxs-lookup"><span data-stu-id="5bb47-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-131">64</span><span class="sxs-lookup"><span data-stu-id="5bb47-131">64</span></span></p></td>
<td><p><span data-ttu-id="5bb47-132">MC</span><span class="sxs-lookup"><span data-stu-id="5bb47-132">MC</span></span></p></td>
<td><p><span data-ttu-id="5bb47-133">MM</span><span class="sxs-lookup"><span data-stu-id="5bb47-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-134">128</span><span class="sxs-lookup"><span data-stu-id="5bb47-134">128</span></span></p></td>
<td><p><span data-ttu-id="5bb47-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="5bb47-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="5bb47-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="5bb47-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-137">256</span><span class="sxs-lookup"><span data-stu-id="5bb47-137">256</span></span></p></td>
<td><p><span data-ttu-id="5bb47-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="5bb47-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="5bb47-139">CA</span><span class="sxs-lookup"><span data-stu-id="5bb47-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-140">512</span><span class="sxs-lookup"><span data-stu-id="5bb47-140">512</span></span></p></td>
<td><p><span data-ttu-id="5bb47-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="5bb47-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="5bb47-142">CAA</span><span class="sxs-lookup"><span data-stu-id="5bb47-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-143">512</span><span class="sxs-lookup"><span data-stu-id="5bb47-143">512</span></span></p></td>
<td><p><span data-ttu-id="5bb47-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="5bb47-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="5bb47-145">CAA</span><span class="sxs-lookup"><span data-stu-id="5bb47-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-146">1024</span><span class="sxs-lookup"><span data-stu-id="5bb47-146">1024</span></span></p></td>
<td><p><span data-ttu-id="5bb47-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="5bb47-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="5bb47-148">RG</span><span class="sxs-lookup"><span data-stu-id="5bb47-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-149">1032</span><span class="sxs-lookup"><span data-stu-id="5bb47-149">1032</span></span></p></td>
<td><p><span data-ttu-id="5bb47-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="5bb47-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="5bb47-151">CPS</span><span class="sxs-lookup"><span data-stu-id="5bb47-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-152">1040</span><span class="sxs-lookup"><span data-stu-id="5bb47-152">1040</span></span></p></td>
<td><p><span data-ttu-id="5bb47-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="5bb47-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="5bb47-154">AS</span><span class="sxs-lookup"><span data-stu-id="5bb47-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-155">2048</span><span class="sxs-lookup"><span data-stu-id="5bb47-155">2048</span></span></p></td>
<td><p><span data-ttu-id="5bb47-156">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5bb47-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="5bb47-157">CC</span><span class="sxs-lookup"><span data-stu-id="5bb47-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-158">16386</span><span class="sxs-lookup"><span data-stu-id="5bb47-158">16386</span></span></p></td>
<td><p><span data-ttu-id="5bb47-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="5bb47-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="5bb47-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="5bb47-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-161">16387</span><span class="sxs-lookup"><span data-stu-id="5bb47-161">16387</span></span></p></td>
<td><p><span data-ttu-id="5bb47-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="5bb47-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="5bb47-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="5bb47-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-164">16388</span><span class="sxs-lookup"><span data-stu-id="5bb47-164">16388</span></span></p></td>
<td><p><span data-ttu-id="5bb47-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="5bb47-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="5bb47-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="5bb47-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-167">16389</span><span class="sxs-lookup"><span data-stu-id="5bb47-167">16389</span></span></p></td>
<td><p><span data-ttu-id="5bb47-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="5bb47-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="5bb47-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="5bb47-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-170">16393</span><span class="sxs-lookup"><span data-stu-id="5bb47-170">16393</span></span></p></td>
<td><p><span data-ttu-id="5bb47-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="5bb47-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="5bb47-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="5bb47-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-173">16395</span><span class="sxs-lookup"><span data-stu-id="5bb47-173">16395</span></span></p></td>
<td><p><span data-ttu-id="5bb47-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="5bb47-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="5bb47-175">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="5bb47-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-176">16396</span><span class="sxs-lookup"><span data-stu-id="5bb47-176">16396</span></span></p></td>
<td><p><span data-ttu-id="5bb47-177">停止</span><span class="sxs-lookup"><span data-stu-id="5bb47-177">ST</span></span></p></td>
<td><p><span data-ttu-id="5bb47-178">停止</span><span class="sxs-lookup"><span data-stu-id="5bb47-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-179">16397</span><span class="sxs-lookup"><span data-stu-id="5bb47-179">16397</span></span></p></td>
<td><p><span data-ttu-id="5bb47-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="5bb47-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="5bb47-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="5bb47-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-182">16398</span><span class="sxs-lookup"><span data-stu-id="5bb47-182">16398</span></span></p></td>
<td><p><span data-ttu-id="5bb47-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="5bb47-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-185">16399</span><span class="sxs-lookup"><span data-stu-id="5bb47-185">16399</span></span></p></td>
<td><p><span data-ttu-id="5bb47-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="5bb47-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-188">16400</span><span class="sxs-lookup"><span data-stu-id="5bb47-188">16400</span></span></p></td>
<td><p><span data-ttu-id="5bb47-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="5bb47-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-191">16401</span><span class="sxs-lookup"><span data-stu-id="5bb47-191">16401</span></span></p></td>
<td><p><span data-ttu-id="5bb47-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="5bb47-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-194">16402</span><span class="sxs-lookup"><span data-stu-id="5bb47-194">16402</span></span></p></td>
<td><p><span data-ttu-id="5bb47-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="5bb47-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="5bb47-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-197">16403</span><span class="sxs-lookup"><span data-stu-id="5bb47-197">16403</span></span></p></td>
<td><p><span data-ttu-id="5bb47-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="5bb47-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="5bb47-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="5bb47-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-200">16404</span><span class="sxs-lookup"><span data-stu-id="5bb47-200">16404</span></span></p></td>
<td><p><span data-ttu-id="5bb47-201">CPC</span><span class="sxs-lookup"><span data-stu-id="5bb47-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="5bb47-202">CPC</span><span class="sxs-lookup"><span data-stu-id="5bb47-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-203">16405</span><span class="sxs-lookup"><span data-stu-id="5bb47-203">16405</span></span></p></td>
<td><p><span data-ttu-id="5bb47-204">LWA</span><span class="sxs-lookup"><span data-stu-id="5bb47-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="5bb47-205">LWA</span><span class="sxs-lookup"><span data-stu-id="5bb47-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-206">16406</span><span class="sxs-lookup"><span data-stu-id="5bb47-206">16406</span></span></p></td>
<td><p><span data-ttu-id="5bb47-207">OWA</span><span class="sxs-lookup"><span data-stu-id="5bb47-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="5bb47-208">OWA</span><span class="sxs-lookup"><span data-stu-id="5bb47-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-209">16407</span><span class="sxs-lookup"><span data-stu-id="5bb47-209">16407</span></span></p></td>
<td><p><span data-ttu-id="5bb47-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="5bb47-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="5bb47-211">の「c」</span><span class="sxs-lookup"><span data-stu-id="5bb47-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-212">16408</span><span class="sxs-lookup"><span data-stu-id="5bb47-212">16408</span></span></p></td>
<td><p><span data-ttu-id="5bb47-213">GCC</span><span class="sxs-lookup"><span data-stu-id="5bb47-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="5bb47-214">GCC</span><span class="sxs-lookup"><span data-stu-id="5bb47-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-215">16409</span><span class="sxs-lookup"><span data-stu-id="5bb47-215">16409</span></span></p></td>
<td><p><span data-ttu-id="5bb47-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="5bb47-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="5bb47-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="5bb47-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-218">16410</span><span class="sxs-lookup"><span data-stu-id="5bb47-218">16410</span></span></p></td>
<td><p><span data-ttu-id="5bb47-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="5bb47-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="5bb47-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="5bb47-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb47-221">32769</span><span class="sxs-lookup"><span data-stu-id="5bb47-221">32769</span></span></p></td>
<td><p><span data-ttu-id="5bb47-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="5bb47-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="5bb47-223">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="5bb47-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb47-224">32770</span><span class="sxs-lookup"><span data-stu-id="5bb47-224">32770</span></span></p></td>
<td><p><span data-ttu-id="5bb47-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="5bb47-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="5bb47-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="5bb47-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

