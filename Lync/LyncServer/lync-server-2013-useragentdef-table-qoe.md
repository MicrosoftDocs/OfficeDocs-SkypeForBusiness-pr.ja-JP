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
ms.openlocfilehash: d2daba0f4e37a07065edf6a9c80955047a7d26b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="00852-102">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="00852-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00852-103">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="00852-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="00852-104">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="00852-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="00852-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="00852-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00852-106">UAType</span><span class="sxs-lookup"><span data-stu-id="00852-106">UAType</span></span></th>
<th><span data-ttu-id="00852-107">UAName</span><span class="sxs-lookup"><span data-stu-id="00852-107">UAName</span></span></th>
<th><span data-ttu-id="00852-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="00852-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00852-109">1-d</span><span class="sxs-lookup"><span data-stu-id="00852-109">1</span></span></p></td>
<td><p><span data-ttu-id="00852-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="00852-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="00852-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="00852-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-112">pbm-2</span><span class="sxs-lookup"><span data-stu-id="00852-112">2</span></span></p></td>
<td><p><span data-ttu-id="00852-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="00852-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="00852-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="00852-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-115">2/4</span><span class="sxs-lookup"><span data-stu-id="00852-115">4</span></span></p></td>
<td><p><span data-ttu-id="00852-116">OC</span><span class="sxs-lookup"><span data-stu-id="00852-116">OC</span></span></p></td>
<td><p><span data-ttu-id="00852-117">OC</span><span class="sxs-lookup"><span data-stu-id="00852-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-118">8 </span><span class="sxs-lookup"><span data-stu-id="00852-118">8</span></span></p></td>
<td><p><span data-ttu-id="00852-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="00852-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="00852-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="00852-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-121">16 </span><span class="sxs-lookup"><span data-stu-id="00852-121">16</span></span></p></td>
<td><p><span data-ttu-id="00852-122">LMC</span><span class="sxs-lookup"><span data-stu-id="00852-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="00852-123">LMC</span><span class="sxs-lookup"><span data-stu-id="00852-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-124">32</span><span class="sxs-lookup"><span data-stu-id="00852-124">32</span></span></p></td>
<td><p><span data-ttu-id="00852-125">DVT</span><span class="sxs-lookup"><span data-stu-id="00852-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="00852-126">DVT</span><span class="sxs-lookup"><span data-stu-id="00852-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-127">64</span><span class="sxs-lookup"><span data-stu-id="00852-127">64</span></span></p></td>
<td><p><span data-ttu-id="00852-128">MM</span><span class="sxs-lookup"><span data-stu-id="00852-128">MM</span></span></p></td>
<td><p><span data-ttu-id="00852-129">MM</span><span class="sxs-lookup"><span data-stu-id="00852-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-130">64</span><span class="sxs-lookup"><span data-stu-id="00852-130">64</span></span></p></td>
<td><p><span data-ttu-id="00852-131">MC</span><span class="sxs-lookup"><span data-stu-id="00852-131">MC</span></span></p></td>
<td><p><span data-ttu-id="00852-132">MM</span><span class="sxs-lookup"><span data-stu-id="00852-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-133">128</span><span class="sxs-lookup"><span data-stu-id="00852-133">128</span></span></p></td>
<td><p><span data-ttu-id="00852-134">Um</span><span class="sxs-lookup"><span data-stu-id="00852-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="00852-135">Um</span><span class="sxs-lookup"><span data-stu-id="00852-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-136">256</span><span class="sxs-lookup"><span data-stu-id="00852-136">256</span></span></p></td>
<td><p><span data-ttu-id="00852-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="00852-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="00852-138">CA</span><span class="sxs-lookup"><span data-stu-id="00852-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-139">512</span><span class="sxs-lookup"><span data-stu-id="00852-139">512</span></span></p></td>
<td><p><span data-ttu-id="00852-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="00852-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="00852-141">CAA</span><span class="sxs-lookup"><span data-stu-id="00852-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-142">512</span><span class="sxs-lookup"><span data-stu-id="00852-142">512</span></span></p></td>
<td><p><span data-ttu-id="00852-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="00852-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="00852-144">CAA</span><span class="sxs-lookup"><span data-stu-id="00852-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-145">1024</span><span class="sxs-lookup"><span data-stu-id="00852-145">1024</span></span></p></td>
<td><p><span data-ttu-id="00852-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="00852-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="00852-147">RG</span><span class="sxs-lookup"><span data-stu-id="00852-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-148">1032</span><span class="sxs-lookup"><span data-stu-id="00852-148">1032</span></span></p></td>
<td><p><span data-ttu-id="00852-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="00852-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="00852-150">CPS</span><span class="sxs-lookup"><span data-stu-id="00852-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-151">1040</span><span class="sxs-lookup"><span data-stu-id="00852-151">1040</span></span></p></td>
<td><p><span data-ttu-id="00852-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="00852-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="00852-153">AS</span><span class="sxs-lookup"><span data-stu-id="00852-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-154">2048</span><span class="sxs-lookup"><span data-stu-id="00852-154">2048</span></span></p></td>
<td><p><span data-ttu-id="00852-155">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="00852-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="00852-156">CC</span><span class="sxs-lookup"><span data-stu-id="00852-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-157">16386</span><span class="sxs-lookup"><span data-stu-id="00852-157">16386</span></span></p></td>
<td><p><span data-ttu-id="00852-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="00852-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="00852-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="00852-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-160">16387</span><span class="sxs-lookup"><span data-stu-id="00852-160">16387</span></span></p></td>
<td><p><span data-ttu-id="00852-161">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="00852-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="00852-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="00852-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-163">16388</span><span class="sxs-lookup"><span data-stu-id="00852-163">16388</span></span></p></td>
<td><p><span data-ttu-id="00852-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="00852-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="00852-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="00852-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-166">16389</span><span class="sxs-lookup"><span data-stu-id="00852-166">16389</span></span></p></td>
<td><p><span data-ttu-id="00852-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="00852-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="00852-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="00852-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-169">16393</span><span class="sxs-lookup"><span data-stu-id="00852-169">16393</span></span></p></td>
<td><p><span data-ttu-id="00852-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="00852-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="00852-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="00852-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-172">16395</span><span class="sxs-lookup"><span data-stu-id="00852-172">16395</span></span></p></td>
<td><p><span data-ttu-id="00852-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="00852-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="00852-174">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="00852-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-175">16396</span><span class="sxs-lookup"><span data-stu-id="00852-175">16396</span></span></p></td>
<td><p><span data-ttu-id="00852-176">停止</span><span class="sxs-lookup"><span data-stu-id="00852-176">ST</span></span></p></td>
<td><p><span data-ttu-id="00852-177">停止</span><span class="sxs-lookup"><span data-stu-id="00852-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-178">16397</span><span class="sxs-lookup"><span data-stu-id="00852-178">16397</span></span></p></td>
<td><p><span data-ttu-id="00852-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="00852-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="00852-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="00852-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-181">16398</span><span class="sxs-lookup"><span data-stu-id="00852-181">16398</span></span></p></td>
<td><p><span data-ttu-id="00852-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="00852-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="00852-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="00852-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-184">16399</span><span class="sxs-lookup"><span data-stu-id="00852-184">16399</span></span></p></td>
<td><p><span data-ttu-id="00852-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="00852-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="00852-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="00852-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-187">16400</span><span class="sxs-lookup"><span data-stu-id="00852-187">16400</span></span></p></td>
<td><p><span data-ttu-id="00852-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="00852-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="00852-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="00852-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-190">16401</span><span class="sxs-lookup"><span data-stu-id="00852-190">16401</span></span></p></td>
<td><p><span data-ttu-id="00852-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="00852-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="00852-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="00852-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-193">16402</span><span class="sxs-lookup"><span data-stu-id="00852-193">16402</span></span></p></td>
<td><p><span data-ttu-id="00852-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="00852-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="00852-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="00852-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-196">16403</span><span class="sxs-lookup"><span data-stu-id="00852-196">16403</span></span></p></td>
<td><p><span data-ttu-id="00852-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="00852-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="00852-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="00852-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-199">16404</span><span class="sxs-lookup"><span data-stu-id="00852-199">16404</span></span></p></td>
<td><p><span data-ttu-id="00852-200">CPC</span><span class="sxs-lookup"><span data-stu-id="00852-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="00852-201">CPC</span><span class="sxs-lookup"><span data-stu-id="00852-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-202">16405</span><span class="sxs-lookup"><span data-stu-id="00852-202">16405</span></span></p></td>
<td><p><span data-ttu-id="00852-203">LWA</span><span class="sxs-lookup"><span data-stu-id="00852-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="00852-204">LWA</span><span class="sxs-lookup"><span data-stu-id="00852-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-205">16406</span><span class="sxs-lookup"><span data-stu-id="00852-205">16406</span></span></p></td>
<td><p><span data-ttu-id="00852-206">OWA</span><span class="sxs-lookup"><span data-stu-id="00852-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="00852-207">OWA</span><span class="sxs-lookup"><span data-stu-id="00852-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-208">16407</span><span class="sxs-lookup"><span data-stu-id="00852-208">16407</span></span></p></td>
<td><p><span data-ttu-id="00852-209">の「c」</span><span class="sxs-lookup"><span data-stu-id="00852-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="00852-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="00852-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-211">16408</span><span class="sxs-lookup"><span data-stu-id="00852-211">16408</span></span></p></td>
<td><p><span data-ttu-id="00852-212">GCC</span><span class="sxs-lookup"><span data-stu-id="00852-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="00852-213">GCC</span><span class="sxs-lookup"><span data-stu-id="00852-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-214">16409</span><span class="sxs-lookup"><span data-stu-id="00852-214">16409</span></span></p></td>
<td><p><span data-ttu-id="00852-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="00852-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="00852-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="00852-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-217">16410</span><span class="sxs-lookup"><span data-stu-id="00852-217">16410</span></span></p></td>
<td><p><span data-ttu-id="00852-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="00852-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="00852-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="00852-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00852-220">32769</span><span class="sxs-lookup"><span data-stu-id="00852-220">32769</span></span></p></td>
<td><p><span data-ttu-id="00852-221">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="00852-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="00852-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="00852-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00852-223">32770</span><span class="sxs-lookup"><span data-stu-id="00852-223">32770</span></span></p></td>
<td><p><span data-ttu-id="00852-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="00852-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="00852-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="00852-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

