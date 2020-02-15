---
title: 'Lync Server 2013: UserAgentDef テーブル'
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
ms.openlocfilehash: 0996abb7098ba636fc31d27388257f570a549ce2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="4bf54-102">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="4bf54-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bf54-103">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="4bf54-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="4bf54-104">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="4bf54-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="4bf54-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="4bf54-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4bf54-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4bf54-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bf54-107">UAType</span><span class="sxs-lookup"><span data-stu-id="4bf54-107">UAType</span></span></th>
<th><span data-ttu-id="4bf54-108">UAName</span><span class="sxs-lookup"><span data-stu-id="4bf54-108">UAName</span></span></th>
<th><span data-ttu-id="4bf54-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="4bf54-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-110">1 </span><span class="sxs-lookup"><span data-stu-id="4bf54-110">1</span></span></p></td>
<td><p><span data-ttu-id="4bf54-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="4bf54-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="4bf54-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="4bf54-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-113">2 </span><span class="sxs-lookup"><span data-stu-id="4bf54-113">2</span></span></p></td>
<td><p><span data-ttu-id="4bf54-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="4bf54-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="4bf54-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="4bf54-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-116">4 </span><span class="sxs-lookup"><span data-stu-id="4bf54-116">4</span></span></p></td>
<td><p><span data-ttu-id="4bf54-117">OC</span><span class="sxs-lookup"><span data-stu-id="4bf54-117">OC</span></span></p></td>
<td><p><span data-ttu-id="4bf54-118">OC</span><span class="sxs-lookup"><span data-stu-id="4bf54-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-119">8 </span><span class="sxs-lookup"><span data-stu-id="4bf54-119">8</span></span></p></td>
<td><p><span data-ttu-id="4bf54-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4bf54-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="4bf54-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4bf54-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-122">16 </span><span class="sxs-lookup"><span data-stu-id="4bf54-122">16</span></span></p></td>
<td><p><span data-ttu-id="4bf54-123">LMC</span><span class="sxs-lookup"><span data-stu-id="4bf54-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="4bf54-124">LMC</span><span class="sxs-lookup"><span data-stu-id="4bf54-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-125">32</span><span class="sxs-lookup"><span data-stu-id="4bf54-125">32</span></span></p></td>
<td><p><span data-ttu-id="4bf54-126">DVT</span><span class="sxs-lookup"><span data-stu-id="4bf54-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="4bf54-127">DVT</span><span class="sxs-lookup"><span data-stu-id="4bf54-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-128">64</span><span class="sxs-lookup"><span data-stu-id="4bf54-128">64</span></span></p></td>
<td><p><span data-ttu-id="4bf54-129">MM</span><span class="sxs-lookup"><span data-stu-id="4bf54-129">MM</span></span></p></td>
<td><p><span data-ttu-id="4bf54-130">MM</span><span class="sxs-lookup"><span data-stu-id="4bf54-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-131">64</span><span class="sxs-lookup"><span data-stu-id="4bf54-131">64</span></span></p></td>
<td><p><span data-ttu-id="4bf54-132">MC</span><span class="sxs-lookup"><span data-stu-id="4bf54-132">MC</span></span></p></td>
<td><p><span data-ttu-id="4bf54-133">MM</span><span class="sxs-lookup"><span data-stu-id="4bf54-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-134">128</span><span class="sxs-lookup"><span data-stu-id="4bf54-134">128</span></span></p></td>
<td><p><span data-ttu-id="4bf54-135">Um</span><span class="sxs-lookup"><span data-stu-id="4bf54-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="4bf54-136">Um</span><span class="sxs-lookup"><span data-stu-id="4bf54-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-137">256</span><span class="sxs-lookup"><span data-stu-id="4bf54-137">256</span></span></p></td>
<td><p><span data-ttu-id="4bf54-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="4bf54-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="4bf54-139">CA</span><span class="sxs-lookup"><span data-stu-id="4bf54-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-140">512</span><span class="sxs-lookup"><span data-stu-id="4bf54-140">512</span></span></p></td>
<td><p><span data-ttu-id="4bf54-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="4bf54-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="4bf54-142">CAA</span><span class="sxs-lookup"><span data-stu-id="4bf54-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-143">512</span><span class="sxs-lookup"><span data-stu-id="4bf54-143">512</span></span></p></td>
<td><p><span data-ttu-id="4bf54-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="4bf54-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="4bf54-145">CAA</span><span class="sxs-lookup"><span data-stu-id="4bf54-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-146">1024</span><span class="sxs-lookup"><span data-stu-id="4bf54-146">1024</span></span></p></td>
<td><p><span data-ttu-id="4bf54-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="4bf54-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="4bf54-148">RG</span><span class="sxs-lookup"><span data-stu-id="4bf54-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-149">1032</span><span class="sxs-lookup"><span data-stu-id="4bf54-149">1032</span></span></p></td>
<td><p><span data-ttu-id="4bf54-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="4bf54-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="4bf54-151">CPS</span><span class="sxs-lookup"><span data-stu-id="4bf54-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-152">1040</span><span class="sxs-lookup"><span data-stu-id="4bf54-152">1040</span></span></p></td>
<td><p><span data-ttu-id="4bf54-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="4bf54-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="4bf54-154">AS</span><span class="sxs-lookup"><span data-stu-id="4bf54-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-155">2048</span><span class="sxs-lookup"><span data-stu-id="4bf54-155">2048</span></span></p></td>
<td><p><span data-ttu-id="4bf54-156">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="4bf54-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="4bf54-157">CC</span><span class="sxs-lookup"><span data-stu-id="4bf54-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-158">16386</span><span class="sxs-lookup"><span data-stu-id="4bf54-158">16386</span></span></p></td>
<td><p><span data-ttu-id="4bf54-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="4bf54-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="4bf54-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="4bf54-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-161">16387</span><span class="sxs-lookup"><span data-stu-id="4bf54-161">16387</span></span></p></td>
<td><p><span data-ttu-id="4bf54-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="4bf54-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="4bf54-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="4bf54-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-164">16388</span><span class="sxs-lookup"><span data-stu-id="4bf54-164">16388</span></span></p></td>
<td><p><span data-ttu-id="4bf54-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="4bf54-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="4bf54-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="4bf54-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-167">16389</span><span class="sxs-lookup"><span data-stu-id="4bf54-167">16389</span></span></p></td>
<td><p><span data-ttu-id="4bf54-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="4bf54-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="4bf54-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="4bf54-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-170">16393</span><span class="sxs-lookup"><span data-stu-id="4bf54-170">16393</span></span></p></td>
<td><p><span data-ttu-id="4bf54-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="4bf54-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="4bf54-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="4bf54-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-173">16395</span><span class="sxs-lookup"><span data-stu-id="4bf54-173">16395</span></span></p></td>
<td><p><span data-ttu-id="4bf54-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="4bf54-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="4bf54-175">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="4bf54-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-176">16396</span><span class="sxs-lookup"><span data-stu-id="4bf54-176">16396</span></span></p></td>
<td><p><span data-ttu-id="4bf54-177">停止</span><span class="sxs-lookup"><span data-stu-id="4bf54-177">ST</span></span></p></td>
<td><p><span data-ttu-id="4bf54-178">停止</span><span class="sxs-lookup"><span data-stu-id="4bf54-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-179">16397</span><span class="sxs-lookup"><span data-stu-id="4bf54-179">16397</span></span></p></td>
<td><p><span data-ttu-id="4bf54-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="4bf54-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="4bf54-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="4bf54-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-182">16398</span><span class="sxs-lookup"><span data-stu-id="4bf54-182">16398</span></span></p></td>
<td><p><span data-ttu-id="4bf54-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="4bf54-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-185">16399</span><span class="sxs-lookup"><span data-stu-id="4bf54-185">16399</span></span></p></td>
<td><p><span data-ttu-id="4bf54-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="4bf54-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-188">16400</span><span class="sxs-lookup"><span data-stu-id="4bf54-188">16400</span></span></p></td>
<td><p><span data-ttu-id="4bf54-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="4bf54-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-191">16401</span><span class="sxs-lookup"><span data-stu-id="4bf54-191">16401</span></span></p></td>
<td><p><span data-ttu-id="4bf54-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="4bf54-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-194">16402</span><span class="sxs-lookup"><span data-stu-id="4bf54-194">16402</span></span></p></td>
<td><p><span data-ttu-id="4bf54-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="4bf54-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="4bf54-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-197">16403</span><span class="sxs-lookup"><span data-stu-id="4bf54-197">16403</span></span></p></td>
<td><p><span data-ttu-id="4bf54-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="4bf54-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="4bf54-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="4bf54-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-200">16404</span><span class="sxs-lookup"><span data-stu-id="4bf54-200">16404</span></span></p></td>
<td><p><span data-ttu-id="4bf54-201">CPC</span><span class="sxs-lookup"><span data-stu-id="4bf54-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="4bf54-202">CPC</span><span class="sxs-lookup"><span data-stu-id="4bf54-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-203">16405</span><span class="sxs-lookup"><span data-stu-id="4bf54-203">16405</span></span></p></td>
<td><p><span data-ttu-id="4bf54-204">LWA</span><span class="sxs-lookup"><span data-stu-id="4bf54-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="4bf54-205">LWA</span><span class="sxs-lookup"><span data-stu-id="4bf54-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-206">16406</span><span class="sxs-lookup"><span data-stu-id="4bf54-206">16406</span></span></p></td>
<td><p><span data-ttu-id="4bf54-207">OWA</span><span class="sxs-lookup"><span data-stu-id="4bf54-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="4bf54-208">OWA</span><span class="sxs-lookup"><span data-stu-id="4bf54-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-209">16407</span><span class="sxs-lookup"><span data-stu-id="4bf54-209">16407</span></span></p></td>
<td><p><span data-ttu-id="4bf54-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="4bf54-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="4bf54-211">の「c」</span><span class="sxs-lookup"><span data-stu-id="4bf54-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-212">16408</span><span class="sxs-lookup"><span data-stu-id="4bf54-212">16408</span></span></p></td>
<td><p><span data-ttu-id="4bf54-213">GCC</span><span class="sxs-lookup"><span data-stu-id="4bf54-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="4bf54-214">GCC</span><span class="sxs-lookup"><span data-stu-id="4bf54-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-215">16409</span><span class="sxs-lookup"><span data-stu-id="4bf54-215">16409</span></span></p></td>
<td><p><span data-ttu-id="4bf54-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="4bf54-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="4bf54-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="4bf54-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-218">16410</span><span class="sxs-lookup"><span data-stu-id="4bf54-218">16410</span></span></p></td>
<td><p><span data-ttu-id="4bf54-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="4bf54-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="4bf54-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="4bf54-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bf54-221">32769</span><span class="sxs-lookup"><span data-stu-id="4bf54-221">32769</span></span></p></td>
<td><p><span data-ttu-id="4bf54-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4bf54-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="4bf54-223">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4bf54-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bf54-224">32770</span><span class="sxs-lookup"><span data-stu-id="4bf54-224">32770</span></span></p></td>
<td><p><span data-ttu-id="4bf54-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="4bf54-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="4bf54-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="4bf54-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

