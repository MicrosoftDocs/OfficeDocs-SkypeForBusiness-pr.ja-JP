---
title: 'Lync Server 2013: UserAgentDef テーブル (QoE)'
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
ms.openlocfilehash: ebddb1e0313d0c47acb4171929d12d352f69c260
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="ee39b-102">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="ee39b-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee39b-103">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="ee39b-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="ee39b-104">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="ee39b-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="ee39b-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="ee39b-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee39b-106">UAType</span><span class="sxs-lookup"><span data-stu-id="ee39b-106">UAType</span></span></th>
<th><span data-ttu-id="ee39b-107">UAName</span><span class="sxs-lookup"><span data-stu-id="ee39b-107">UAName</span></span></th>
<th><span data-ttu-id="ee39b-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="ee39b-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-109">1 </span><span class="sxs-lookup"><span data-stu-id="ee39b-109">1</span></span></p></td>
<td><p><span data-ttu-id="ee39b-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ee39b-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="ee39b-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ee39b-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-112">2 </span><span class="sxs-lookup"><span data-stu-id="ee39b-112">2</span></span></p></td>
<td><p><span data-ttu-id="ee39b-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="ee39b-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="ee39b-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="ee39b-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-115">4 </span><span class="sxs-lookup"><span data-stu-id="ee39b-115">4</span></span></p></td>
<td><p><span data-ttu-id="ee39b-116">OC</span><span class="sxs-lookup"><span data-stu-id="ee39b-116">OC</span></span></p></td>
<td><p><span data-ttu-id="ee39b-117">OC</span><span class="sxs-lookup"><span data-stu-id="ee39b-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-118">8 </span><span class="sxs-lookup"><span data-stu-id="ee39b-118">8</span></span></p></td>
<td><p><span data-ttu-id="ee39b-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ee39b-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="ee39b-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ee39b-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-121">16 </span><span class="sxs-lookup"><span data-stu-id="ee39b-121">16</span></span></p></td>
<td><p><span data-ttu-id="ee39b-122">LMC</span><span class="sxs-lookup"><span data-stu-id="ee39b-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="ee39b-123">LMC</span><span class="sxs-lookup"><span data-stu-id="ee39b-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-124">32</span><span class="sxs-lookup"><span data-stu-id="ee39b-124">32</span></span></p></td>
<td><p><span data-ttu-id="ee39b-125">DVT</span><span class="sxs-lookup"><span data-stu-id="ee39b-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="ee39b-126">DVT</span><span class="sxs-lookup"><span data-stu-id="ee39b-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-127">64</span><span class="sxs-lookup"><span data-stu-id="ee39b-127">64</span></span></p></td>
<td><p><span data-ttu-id="ee39b-128">MM</span><span class="sxs-lookup"><span data-stu-id="ee39b-128">MM</span></span></p></td>
<td><p><span data-ttu-id="ee39b-129">MM</span><span class="sxs-lookup"><span data-stu-id="ee39b-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-130">64</span><span class="sxs-lookup"><span data-stu-id="ee39b-130">64</span></span></p></td>
<td><p><span data-ttu-id="ee39b-131">MC</span><span class="sxs-lookup"><span data-stu-id="ee39b-131">MC</span></span></p></td>
<td><p><span data-ttu-id="ee39b-132">MM</span><span class="sxs-lookup"><span data-stu-id="ee39b-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-133">128</span><span class="sxs-lookup"><span data-stu-id="ee39b-133">128</span></span></p></td>
<td><p><span data-ttu-id="ee39b-134">Um</span><span class="sxs-lookup"><span data-stu-id="ee39b-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="ee39b-135">Um</span><span class="sxs-lookup"><span data-stu-id="ee39b-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-136">256</span><span class="sxs-lookup"><span data-stu-id="ee39b-136">256</span></span></p></td>
<td><p><span data-ttu-id="ee39b-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="ee39b-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="ee39b-138">CA</span><span class="sxs-lookup"><span data-stu-id="ee39b-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-139">512</span><span class="sxs-lookup"><span data-stu-id="ee39b-139">512</span></span></p></td>
<td><p><span data-ttu-id="ee39b-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="ee39b-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="ee39b-141">CAA</span><span class="sxs-lookup"><span data-stu-id="ee39b-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-142">512</span><span class="sxs-lookup"><span data-stu-id="ee39b-142">512</span></span></p></td>
<td><p><span data-ttu-id="ee39b-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="ee39b-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="ee39b-144">CAA</span><span class="sxs-lookup"><span data-stu-id="ee39b-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-145">1024</span><span class="sxs-lookup"><span data-stu-id="ee39b-145">1024</span></span></p></td>
<td><p><span data-ttu-id="ee39b-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="ee39b-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="ee39b-147">RG</span><span class="sxs-lookup"><span data-stu-id="ee39b-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-148">1032</span><span class="sxs-lookup"><span data-stu-id="ee39b-148">1032</span></span></p></td>
<td><p><span data-ttu-id="ee39b-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="ee39b-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="ee39b-150">CPS</span><span class="sxs-lookup"><span data-stu-id="ee39b-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-151">1040</span><span class="sxs-lookup"><span data-stu-id="ee39b-151">1040</span></span></p></td>
<td><p><span data-ttu-id="ee39b-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="ee39b-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="ee39b-153">AS</span><span class="sxs-lookup"><span data-stu-id="ee39b-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-154">2048</span><span class="sxs-lookup"><span data-stu-id="ee39b-154">2048</span></span></p></td>
<td><p><span data-ttu-id="ee39b-155">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ee39b-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="ee39b-156">CC</span><span class="sxs-lookup"><span data-stu-id="ee39b-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-157">16386</span><span class="sxs-lookup"><span data-stu-id="ee39b-157">16386</span></span></p></td>
<td><p><span data-ttu-id="ee39b-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="ee39b-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="ee39b-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="ee39b-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-160">16387</span><span class="sxs-lookup"><span data-stu-id="ee39b-160">16387</span></span></p></td>
<td><p><span data-ttu-id="ee39b-161">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="ee39b-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="ee39b-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="ee39b-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-163">16388</span><span class="sxs-lookup"><span data-stu-id="ee39b-163">16388</span></span></p></td>
<td><p><span data-ttu-id="ee39b-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="ee39b-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="ee39b-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="ee39b-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-166">16389</span><span class="sxs-lookup"><span data-stu-id="ee39b-166">16389</span></span></p></td>
<td><p><span data-ttu-id="ee39b-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="ee39b-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="ee39b-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="ee39b-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-169">16393</span><span class="sxs-lookup"><span data-stu-id="ee39b-169">16393</span></span></p></td>
<td><p><span data-ttu-id="ee39b-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="ee39b-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="ee39b-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="ee39b-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-172">16395</span><span class="sxs-lookup"><span data-stu-id="ee39b-172">16395</span></span></p></td>
<td><p><span data-ttu-id="ee39b-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="ee39b-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="ee39b-174">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="ee39b-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-175">16396</span><span class="sxs-lookup"><span data-stu-id="ee39b-175">16396</span></span></p></td>
<td><p><span data-ttu-id="ee39b-176">停止</span><span class="sxs-lookup"><span data-stu-id="ee39b-176">ST</span></span></p></td>
<td><p><span data-ttu-id="ee39b-177">停止</span><span class="sxs-lookup"><span data-stu-id="ee39b-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-178">16397</span><span class="sxs-lookup"><span data-stu-id="ee39b-178">16397</span></span></p></td>
<td><p><span data-ttu-id="ee39b-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="ee39b-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="ee39b-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="ee39b-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-181">16398</span><span class="sxs-lookup"><span data-stu-id="ee39b-181">16398</span></span></p></td>
<td><p><span data-ttu-id="ee39b-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="ee39b-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-184">16399</span><span class="sxs-lookup"><span data-stu-id="ee39b-184">16399</span></span></p></td>
<td><p><span data-ttu-id="ee39b-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="ee39b-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-187">16400</span><span class="sxs-lookup"><span data-stu-id="ee39b-187">16400</span></span></p></td>
<td><p><span data-ttu-id="ee39b-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="ee39b-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-190">16401</span><span class="sxs-lookup"><span data-stu-id="ee39b-190">16401</span></span></p></td>
<td><p><span data-ttu-id="ee39b-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="ee39b-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-193">16402</span><span class="sxs-lookup"><span data-stu-id="ee39b-193">16402</span></span></p></td>
<td><p><span data-ttu-id="ee39b-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="ee39b-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ee39b-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-196">16403</span><span class="sxs-lookup"><span data-stu-id="ee39b-196">16403</span></span></p></td>
<td><p><span data-ttu-id="ee39b-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="ee39b-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="ee39b-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="ee39b-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-199">16404</span><span class="sxs-lookup"><span data-stu-id="ee39b-199">16404</span></span></p></td>
<td><p><span data-ttu-id="ee39b-200">CPC</span><span class="sxs-lookup"><span data-stu-id="ee39b-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="ee39b-201">CPC</span><span class="sxs-lookup"><span data-stu-id="ee39b-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-202">16405</span><span class="sxs-lookup"><span data-stu-id="ee39b-202">16405</span></span></p></td>
<td><p><span data-ttu-id="ee39b-203">LWA</span><span class="sxs-lookup"><span data-stu-id="ee39b-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="ee39b-204">LWA</span><span class="sxs-lookup"><span data-stu-id="ee39b-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-205">16406</span><span class="sxs-lookup"><span data-stu-id="ee39b-205">16406</span></span></p></td>
<td><p><span data-ttu-id="ee39b-206">OWA</span><span class="sxs-lookup"><span data-stu-id="ee39b-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="ee39b-207">OWA</span><span class="sxs-lookup"><span data-stu-id="ee39b-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-208">16407</span><span class="sxs-lookup"><span data-stu-id="ee39b-208">16407</span></span></p></td>
<td><p><span data-ttu-id="ee39b-209">の「c」</span><span class="sxs-lookup"><span data-stu-id="ee39b-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="ee39b-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="ee39b-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-211">16408</span><span class="sxs-lookup"><span data-stu-id="ee39b-211">16408</span></span></p></td>
<td><p><span data-ttu-id="ee39b-212">GCC</span><span class="sxs-lookup"><span data-stu-id="ee39b-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="ee39b-213">GCC</span><span class="sxs-lookup"><span data-stu-id="ee39b-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-214">16409</span><span class="sxs-lookup"><span data-stu-id="ee39b-214">16409</span></span></p></td>
<td><p><span data-ttu-id="ee39b-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="ee39b-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="ee39b-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="ee39b-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-217">16410</span><span class="sxs-lookup"><span data-stu-id="ee39b-217">16410</span></span></p></td>
<td><p><span data-ttu-id="ee39b-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="ee39b-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="ee39b-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="ee39b-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee39b-220">32769</span><span class="sxs-lookup"><span data-stu-id="ee39b-220">32769</span></span></p></td>
<td><p><span data-ttu-id="ee39b-221">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ee39b-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="ee39b-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ee39b-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee39b-223">32770</span><span class="sxs-lookup"><span data-stu-id="ee39b-223">32770</span></span></p></td>
<td><p><span data-ttu-id="ee39b-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="ee39b-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="ee39b-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="ee39b-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

