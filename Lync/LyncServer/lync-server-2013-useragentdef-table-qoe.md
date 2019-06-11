---
title: 'Lync Server 2013: UserAgentDef テーブル (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adfe05a24d2a45cf5d6d279b29d77b1c7654012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="ae4ed-102">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="ae4ed-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae4ed-103">_**最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="ae4ed-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="ae4ed-104">UserAgentDef テーブルは、ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="ae4ed-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="ae4ed-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="ae4ed-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae4ed-106">UAType</span><span class="sxs-lookup"><span data-stu-id="ae4ed-106">UAType</span></span></th>
<th><span data-ttu-id="ae4ed-107">UAName</span><span class="sxs-lookup"><span data-stu-id="ae4ed-107">UAName</span></span></th>
<th><span data-ttu-id="ae4ed-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="ae4ed-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-109">1</span><span class="sxs-lookup"><span data-stu-id="ae4ed-109">1</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ae4ed-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ae4ed-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-112">2</span><span class="sxs-lookup"><span data-stu-id="ae4ed-112">2</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-115">4</span><span class="sxs-lookup"><span data-stu-id="ae4ed-115">4</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-116">OC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-116">OC</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-117">OC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-118">個</span><span class="sxs-lookup"><span data-stu-id="ae4ed-118">8</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ae4ed-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ae4ed-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-121">16</span><span class="sxs-lookup"><span data-stu-id="ae4ed-121">16</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-122">LMC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-123">LMC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-124">32</span><span class="sxs-lookup"><span data-stu-id="ae4ed-124">32</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-125">DVT</span><span class="sxs-lookup"><span data-stu-id="ae4ed-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-126">DVT</span><span class="sxs-lookup"><span data-stu-id="ae4ed-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-127">64</span><span class="sxs-lookup"><span data-stu-id="ae4ed-127">64</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-128">TU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-128">MM</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-129">TU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-130">64</span><span class="sxs-lookup"><span data-stu-id="ae4ed-130">64</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-131">MC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-131">MC</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-132">TU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-133">128</span><span class="sxs-lookup"><span data-stu-id="ae4ed-133">128</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="ae4ed-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="ae4ed-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-136">256</span><span class="sxs-lookup"><span data-stu-id="ae4ed-136">256</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-137">Conferencing_Announcement_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="ae4ed-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-138">CAS</span><span class="sxs-lookup"><span data-stu-id="ae4ed-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-139">512</span><span class="sxs-lookup"><span data-stu-id="ae4ed-139">512</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-140">Conferencing_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="ae4ed-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-141">CAA を</span><span class="sxs-lookup"><span data-stu-id="ae4ed-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-142">512</span><span class="sxs-lookup"><span data-stu-id="ae4ed-142">512</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-143">Conference_Auto_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="ae4ed-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-144">CAA を</span><span class="sxs-lookup"><span data-stu-id="ae4ed-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-145">1024</span><span class="sxs-lookup"><span data-stu-id="ae4ed-145">1024</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="ae4ed-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-147">RGS</span><span class="sxs-lookup"><span data-stu-id="ae4ed-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-148">1032</span><span class="sxs-lookup"><span data-stu-id="ae4ed-148">1032</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-149">Call_Park_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="ae4ed-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-150">RESERVED</span><span class="sxs-lookup"><span data-stu-id="ae4ed-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-151">1040</span><span class="sxs-lookup"><span data-stu-id="ae4ed-151">1040</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="ae4ed-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-153">も</span><span class="sxs-lookup"><span data-stu-id="ae4ed-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-154">2048</span><span class="sxs-lookup"><span data-stu-id="ae4ed-154">2048</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-155">Microsoft Rtc. アプリケーションの Ccs</span><span class="sxs-lookup"><span data-stu-id="ae4ed-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-156">CCS</span><span class="sxs-lookup"><span data-stu-id="ae4ed-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-157">16386</span><span class="sxs-lookup"><span data-stu-id="ae4ed-157">16386</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="ae4ed-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="ae4ed-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-160">16387</span><span class="sxs-lookup"><span data-stu-id="ae4ed-160">16387</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-161">CWA</span><span class="sxs-lookup"><span data-stu-id="ae4ed-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-162">CWA</span><span class="sxs-lookup"><span data-stu-id="ae4ed-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-163">16388</span><span class="sxs-lookup"><span data-stu-id="ae4ed-163">16388</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="ae4ed-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="ae4ed-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-166">16389</span><span class="sxs-lookup"><span data-stu-id="ae4ed-166">16389</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="ae4ed-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="ae4ed-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-169">16393</span><span class="sxs-lookup"><span data-stu-id="ae4ed-169">16393</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="ae4ed-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="ae4ed-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-172">16395</span><span class="sxs-lookup"><span data-stu-id="ae4ed-172">16395</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="ae4ed-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-174">ARCH AGENT</span><span class="sxs-lookup"><span data-stu-id="ae4ed-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-175">16396</span><span class="sxs-lookup"><span data-stu-id="ae4ed-175">16396</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-176">短期</span><span class="sxs-lookup"><span data-stu-id="ae4ed-176">ST</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-177">短期</span><span class="sxs-lookup"><span data-stu-id="ae4ed-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-178">16397</span><span class="sxs-lookup"><span data-stu-id="ae4ed-178">16397</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="ae4ed-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-181">16398</span><span class="sxs-lookup"><span data-stu-id="ae4ed-181">16398</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-184">16399</span><span class="sxs-lookup"><span data-stu-id="ae4ed-184">16399</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-187">16400</span><span class="sxs-lookup"><span data-stu-id="ae4ed-187">16400</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-190">16401</span><span class="sxs-lookup"><span data-stu-id="ae4ed-190">16401</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-193">16402</span><span class="sxs-lookup"><span data-stu-id="ae4ed-193">16402</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ae4ed-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-196">16403</span><span class="sxs-lookup"><span data-stu-id="ae4ed-196">16403</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="ae4ed-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="ae4ed-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-199">16404</span><span class="sxs-lookup"><span data-stu-id="ae4ed-199">16404</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-200">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="ae4ed-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-201">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="ae4ed-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-202">16405</span><span class="sxs-lookup"><span data-stu-id="ae4ed-202">16405</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-203">LWA</span><span class="sxs-lookup"><span data-stu-id="ae4ed-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-204">LWA</span><span class="sxs-lookup"><span data-stu-id="ae4ed-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-205">16406</span><span class="sxs-lookup"><span data-stu-id="ae4ed-205">16406</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-206">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="ae4ed-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-207">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="ae4ed-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-208">16407</span><span class="sxs-lookup"><span data-stu-id="ae4ed-208">16407</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-209">AOC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-210">AOC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-211">16408</span><span class="sxs-lookup"><span data-stu-id="ae4ed-211">16408</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-212">GCC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-213">GCC</span><span class="sxs-lookup"><span data-stu-id="ae4ed-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-214">16409</span><span class="sxs-lookup"><span data-stu-id="ae4ed-214">16409</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="ae4ed-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-217">16410</span><span class="sxs-lookup"><span data-stu-id="ae4ed-217">16410</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="ae4ed-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="ae4ed-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ed-220">32769</span><span class="sxs-lookup"><span data-stu-id="ae4ed-220">32769</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-221">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ae4ed-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ae4ed-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ed-223">32770</span><span class="sxs-lookup"><span data-stu-id="ae4ed-223">32770</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="ae4ed-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="ae4ed-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="ae4ed-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

