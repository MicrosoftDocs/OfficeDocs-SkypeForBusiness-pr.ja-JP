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
ms.openlocfilehash: 146c22b77ac6d2681c1844feade86242e1fcd72f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="607e2-102">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="607e2-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="607e2-103">_**最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="607e2-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="607e2-104">UserAgentDef テーブルは、ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="607e2-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="607e2-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="607e2-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="607e2-106">UAType</span><span class="sxs-lookup"><span data-stu-id="607e2-106">UAType</span></span></th>
<th><span data-ttu-id="607e2-107">UAName</span><span class="sxs-lookup"><span data-stu-id="607e2-107">UAName</span></span></th>
<th><span data-ttu-id="607e2-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="607e2-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="607e2-109">1</span><span class="sxs-lookup"><span data-stu-id="607e2-109">1</span></span></p></td>
<td><p><span data-ttu-id="607e2-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="607e2-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="607e2-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="607e2-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-112">両面</span><span class="sxs-lookup"><span data-stu-id="607e2-112">2</span></span></p></td>
<td><p><span data-ttu-id="607e2-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="607e2-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="607e2-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="607e2-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-115">4</span><span class="sxs-lookup"><span data-stu-id="607e2-115">4</span></span></p></td>
<td><p><span data-ttu-id="607e2-116">OC</span><span class="sxs-lookup"><span data-stu-id="607e2-116">OC</span></span></p></td>
<td><p><span data-ttu-id="607e2-117">OC</span><span class="sxs-lookup"><span data-stu-id="607e2-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-118">個</span><span class="sxs-lookup"><span data-stu-id="607e2-118">8</span></span></p></td>
<td><p><span data-ttu-id="607e2-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="607e2-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="607e2-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="607e2-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-121">16</span><span class="sxs-lookup"><span data-stu-id="607e2-121">16</span></span></p></td>
<td><p><span data-ttu-id="607e2-122">LMC</span><span class="sxs-lookup"><span data-stu-id="607e2-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="607e2-123">LMC</span><span class="sxs-lookup"><span data-stu-id="607e2-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-124">32</span><span class="sxs-lookup"><span data-stu-id="607e2-124">32</span></span></p></td>
<td><p><span data-ttu-id="607e2-125">DVT</span><span class="sxs-lookup"><span data-stu-id="607e2-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="607e2-126">DVT</span><span class="sxs-lookup"><span data-stu-id="607e2-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-127">64</span><span class="sxs-lookup"><span data-stu-id="607e2-127">64</span></span></p></td>
<td><p><span data-ttu-id="607e2-128">TU</span><span class="sxs-lookup"><span data-stu-id="607e2-128">MM</span></span></p></td>
<td><p><span data-ttu-id="607e2-129">TU</span><span class="sxs-lookup"><span data-stu-id="607e2-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-130">64</span><span class="sxs-lookup"><span data-stu-id="607e2-130">64</span></span></p></td>
<td><p><span data-ttu-id="607e2-131">MC</span><span class="sxs-lookup"><span data-stu-id="607e2-131">MC</span></span></p></td>
<td><p><span data-ttu-id="607e2-132">TU</span><span class="sxs-lookup"><span data-stu-id="607e2-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-133">128</span><span class="sxs-lookup"><span data-stu-id="607e2-133">128</span></span></p></td>
<td><p><span data-ttu-id="607e2-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="607e2-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="607e2-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="607e2-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-136">256</span><span class="sxs-lookup"><span data-stu-id="607e2-136">256</span></span></p></td>
<td><p><span data-ttu-id="607e2-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="607e2-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="607e2-138">CAS</span><span class="sxs-lookup"><span data-stu-id="607e2-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-139">512</span><span class="sxs-lookup"><span data-stu-id="607e2-139">512</span></span></p></td>
<td><p><span data-ttu-id="607e2-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="607e2-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="607e2-141">CAA を</span><span class="sxs-lookup"><span data-stu-id="607e2-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-142">512</span><span class="sxs-lookup"><span data-stu-id="607e2-142">512</span></span></p></td>
<td><p><span data-ttu-id="607e2-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="607e2-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="607e2-144">CAA を</span><span class="sxs-lookup"><span data-stu-id="607e2-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-145">1024</span><span class="sxs-lookup"><span data-stu-id="607e2-145">1024</span></span></p></td>
<td><p><span data-ttu-id="607e2-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="607e2-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="607e2-147">RGS</span><span class="sxs-lookup"><span data-stu-id="607e2-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-148">1032</span><span class="sxs-lookup"><span data-stu-id="607e2-148">1032</span></span></p></td>
<td><p><span data-ttu-id="607e2-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="607e2-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="607e2-150">RESERVED</span><span class="sxs-lookup"><span data-stu-id="607e2-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-151">1040</span><span class="sxs-lookup"><span data-stu-id="607e2-151">1040</span></span></p></td>
<td><p><span data-ttu-id="607e2-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="607e2-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="607e2-153">も</span><span class="sxs-lookup"><span data-stu-id="607e2-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-154">2048</span><span class="sxs-lookup"><span data-stu-id="607e2-154">2048</span></span></p></td>
<td><p><span data-ttu-id="607e2-155">Microsoft Rtc. アプリケーションの Ccs</span><span class="sxs-lookup"><span data-stu-id="607e2-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="607e2-156">CCS</span><span class="sxs-lookup"><span data-stu-id="607e2-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-157">16386</span><span class="sxs-lookup"><span data-stu-id="607e2-157">16386</span></span></p></td>
<td><p><span data-ttu-id="607e2-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="607e2-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="607e2-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="607e2-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-160">16387</span><span class="sxs-lookup"><span data-stu-id="607e2-160">16387</span></span></p></td>
<td><p><span data-ttu-id="607e2-161">CWA</span><span class="sxs-lookup"><span data-stu-id="607e2-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="607e2-162">CWA</span><span class="sxs-lookup"><span data-stu-id="607e2-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-163">16388</span><span class="sxs-lookup"><span data-stu-id="607e2-163">16388</span></span></p></td>
<td><p><span data-ttu-id="607e2-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="607e2-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="607e2-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="607e2-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-166">16389</span><span class="sxs-lookup"><span data-stu-id="607e2-166">16389</span></span></p></td>
<td><p><span data-ttu-id="607e2-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="607e2-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="607e2-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="607e2-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-169">16393</span><span class="sxs-lookup"><span data-stu-id="607e2-169">16393</span></span></p></td>
<td><p><span data-ttu-id="607e2-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="607e2-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="607e2-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="607e2-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-172">16395</span><span class="sxs-lookup"><span data-stu-id="607e2-172">16395</span></span></p></td>
<td><p><span data-ttu-id="607e2-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="607e2-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="607e2-174">ARCH AGENT</span><span class="sxs-lookup"><span data-stu-id="607e2-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-175">16396</span><span class="sxs-lookup"><span data-stu-id="607e2-175">16396</span></span></p></td>
<td><p><span data-ttu-id="607e2-176">短期</span><span class="sxs-lookup"><span data-stu-id="607e2-176">ST</span></span></p></td>
<td><p><span data-ttu-id="607e2-177">短期</span><span class="sxs-lookup"><span data-stu-id="607e2-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-178">16397</span><span class="sxs-lookup"><span data-stu-id="607e2-178">16397</span></span></p></td>
<td><p><span data-ttu-id="607e2-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="607e2-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="607e2-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="607e2-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-181">16398</span><span class="sxs-lookup"><span data-stu-id="607e2-181">16398</span></span></p></td>
<td><p><span data-ttu-id="607e2-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="607e2-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="607e2-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="607e2-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-184">16399</span><span class="sxs-lookup"><span data-stu-id="607e2-184">16399</span></span></p></td>
<td><p><span data-ttu-id="607e2-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="607e2-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="607e2-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="607e2-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-187">16400</span><span class="sxs-lookup"><span data-stu-id="607e2-187">16400</span></span></p></td>
<td><p><span data-ttu-id="607e2-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="607e2-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="607e2-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="607e2-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-190">16401</span><span class="sxs-lookup"><span data-stu-id="607e2-190">16401</span></span></p></td>
<td><p><span data-ttu-id="607e2-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="607e2-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="607e2-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="607e2-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-193">16402</span><span class="sxs-lookup"><span data-stu-id="607e2-193">16402</span></span></p></td>
<td><p><span data-ttu-id="607e2-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="607e2-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="607e2-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="607e2-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-196">16403</span><span class="sxs-lookup"><span data-stu-id="607e2-196">16403</span></span></p></td>
<td><p><span data-ttu-id="607e2-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="607e2-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="607e2-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="607e2-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-199">16404</span><span class="sxs-lookup"><span data-stu-id="607e2-199">16404</span></span></p></td>
<td><p><span data-ttu-id="607e2-200">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="607e2-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="607e2-201">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="607e2-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-202">16405</span><span class="sxs-lookup"><span data-stu-id="607e2-202">16405</span></span></p></td>
<td><p><span data-ttu-id="607e2-203">LWA</span><span class="sxs-lookup"><span data-stu-id="607e2-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="607e2-204">LWA</span><span class="sxs-lookup"><span data-stu-id="607e2-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-205">16406</span><span class="sxs-lookup"><span data-stu-id="607e2-205">16406</span></span></p></td>
<td><p><span data-ttu-id="607e2-206">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="607e2-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="607e2-207">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="607e2-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-208">16407</span><span class="sxs-lookup"><span data-stu-id="607e2-208">16407</span></span></p></td>
<td><p><span data-ttu-id="607e2-209">AOC</span><span class="sxs-lookup"><span data-stu-id="607e2-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="607e2-210">AOC</span><span class="sxs-lookup"><span data-stu-id="607e2-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-211">16408</span><span class="sxs-lookup"><span data-stu-id="607e2-211">16408</span></span></p></td>
<td><p><span data-ttu-id="607e2-212">GCC</span><span class="sxs-lookup"><span data-stu-id="607e2-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="607e2-213">GCC</span><span class="sxs-lookup"><span data-stu-id="607e2-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-214">16409</span><span class="sxs-lookup"><span data-stu-id="607e2-214">16409</span></span></p></td>
<td><p><span data-ttu-id="607e2-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="607e2-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="607e2-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="607e2-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-217">16410</span><span class="sxs-lookup"><span data-stu-id="607e2-217">16410</span></span></p></td>
<td><p><span data-ttu-id="607e2-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="607e2-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="607e2-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="607e2-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="607e2-220">32769</span><span class="sxs-lookup"><span data-stu-id="607e2-220">32769</span></span></p></td>
<td><p><span data-ttu-id="607e2-221">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="607e2-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="607e2-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="607e2-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="607e2-223">32770</span><span class="sxs-lookup"><span data-stu-id="607e2-223">32770</span></span></p></td>
<td><p><span data-ttu-id="607e2-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="607e2-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="607e2-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="607e2-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

