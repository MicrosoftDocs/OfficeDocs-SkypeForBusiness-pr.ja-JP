---
title: 'Lync Server 2013: UserAgentDef テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b378b6d71bb5163d1d2d2e9146cf3877c0d38a19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="4d0c4-102">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="4d0c4-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d0c4-103">_**最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="4d0c4-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="4d0c4-104">UserAgentDef テーブルは、ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="4d0c4-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="4d0c4-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="4d0c4-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4d0c4-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4d0c4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0c4-107">UAType</span><span class="sxs-lookup"><span data-stu-id="4d0c4-107">UAType</span></span></th>
<th><span data-ttu-id="4d0c4-108">UAName</span><span class="sxs-lookup"><span data-stu-id="4d0c4-108">UAName</span></span></th>
<th><span data-ttu-id="4d0c4-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="4d0c4-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-110">1</span><span class="sxs-lookup"><span data-stu-id="4d0c4-110">1</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="4d0c4-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="4d0c4-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-113">2</span><span class="sxs-lookup"><span data-stu-id="4d0c4-113">2</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-116">4</span><span class="sxs-lookup"><span data-stu-id="4d0c4-116">4</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-117">OC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-117">OC</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-118">OC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-119">個</span><span class="sxs-lookup"><span data-stu-id="4d0c4-119">8</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4d0c4-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4d0c4-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-122">16</span><span class="sxs-lookup"><span data-stu-id="4d0c4-122">16</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-123">LMC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-124">LMC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-125">32</span><span class="sxs-lookup"><span data-stu-id="4d0c4-125">32</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-126">DVT</span><span class="sxs-lookup"><span data-stu-id="4d0c4-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-127">DVT</span><span class="sxs-lookup"><span data-stu-id="4d0c4-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-128">64</span><span class="sxs-lookup"><span data-stu-id="4d0c4-128">64</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-129">TU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-129">MM</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-130">TU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-131">64</span><span class="sxs-lookup"><span data-stu-id="4d0c4-131">64</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-132">MC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-132">MC</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-133">TU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-134">128</span><span class="sxs-lookup"><span data-stu-id="4d0c4-134">128</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="4d0c4-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-136">Attendant</span><span class="sxs-lookup"><span data-stu-id="4d0c4-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-137">256</span><span class="sxs-lookup"><span data-stu-id="4d0c4-137">256</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-138">Conferencing_Announcement_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="4d0c4-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-139">CAS</span><span class="sxs-lookup"><span data-stu-id="4d0c4-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-140">512</span><span class="sxs-lookup"><span data-stu-id="4d0c4-140">512</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-141">Conferencing_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="4d0c4-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-142">CAA を</span><span class="sxs-lookup"><span data-stu-id="4d0c4-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-143">512</span><span class="sxs-lookup"><span data-stu-id="4d0c4-143">512</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-144">Conference_Auto_Attendant_ 1.0</span><span class="sxs-lookup"><span data-stu-id="4d0c4-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-145">CAA を</span><span class="sxs-lookup"><span data-stu-id="4d0c4-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-146">1024</span><span class="sxs-lookup"><span data-stu-id="4d0c4-146">1024</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="4d0c4-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-148">RGS</span><span class="sxs-lookup"><span data-stu-id="4d0c4-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-149">1032</span><span class="sxs-lookup"><span data-stu-id="4d0c4-149">1032</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-150">Call_Park_Service_ 1.0</span><span class="sxs-lookup"><span data-stu-id="4d0c4-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-151">RESERVED</span><span class="sxs-lookup"><span data-stu-id="4d0c4-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-152">1040</span><span class="sxs-lookup"><span data-stu-id="4d0c4-152">1040</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="4d0c4-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-154">も</span><span class="sxs-lookup"><span data-stu-id="4d0c4-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-155">2048</span><span class="sxs-lookup"><span data-stu-id="4d0c4-155">2048</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-156">Microsoft Rtc. アプリケーションの Ccs</span><span class="sxs-lookup"><span data-stu-id="4d0c4-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-157">CCS</span><span class="sxs-lookup"><span data-stu-id="4d0c4-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-158">16386</span><span class="sxs-lookup"><span data-stu-id="4d0c4-158">16386</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="4d0c4-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="4d0c4-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-161">16387</span><span class="sxs-lookup"><span data-stu-id="4d0c4-161">16387</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-162">CWA</span><span class="sxs-lookup"><span data-stu-id="4d0c4-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-163">CWA</span><span class="sxs-lookup"><span data-stu-id="4d0c4-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-164">16388</span><span class="sxs-lookup"><span data-stu-id="4d0c4-164">16388</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="4d0c4-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="4d0c4-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-167">16389</span><span class="sxs-lookup"><span data-stu-id="4d0c4-167">16389</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="4d0c4-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="4d0c4-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-170">16393</span><span class="sxs-lookup"><span data-stu-id="4d0c4-170">16393</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="4d0c4-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="4d0c4-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-173">16395</span><span class="sxs-lookup"><span data-stu-id="4d0c4-173">16395</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="4d0c4-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-175">ARCH AGENT</span><span class="sxs-lookup"><span data-stu-id="4d0c4-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-176">16396</span><span class="sxs-lookup"><span data-stu-id="4d0c4-176">16396</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-177">短期</span><span class="sxs-lookup"><span data-stu-id="4d0c4-177">ST</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-178">短期</span><span class="sxs-lookup"><span data-stu-id="4d0c4-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-179">16397</span><span class="sxs-lookup"><span data-stu-id="4d0c4-179">16397</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="4d0c4-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-182">16398</span><span class="sxs-lookup"><span data-stu-id="4d0c4-182">16398</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-185">16399</span><span class="sxs-lookup"><span data-stu-id="4d0c4-185">16399</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-188">16400</span><span class="sxs-lookup"><span data-stu-id="4d0c4-188">16400</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-191">16401</span><span class="sxs-lookup"><span data-stu-id="4d0c4-191">16401</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-194">16402</span><span class="sxs-lookup"><span data-stu-id="4d0c4-194">16402</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="4d0c4-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-197">16403</span><span class="sxs-lookup"><span data-stu-id="4d0c4-197">16403</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="4d0c4-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="4d0c4-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-200">16404</span><span class="sxs-lookup"><span data-stu-id="4d0c4-200">16404</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-201">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="4d0c4-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-202">SKYDRIVE</span><span class="sxs-lookup"><span data-stu-id="4d0c4-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-203">16405</span><span class="sxs-lookup"><span data-stu-id="4d0c4-203">16405</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-204">LWA</span><span class="sxs-lookup"><span data-stu-id="4d0c4-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-205">LWA</span><span class="sxs-lookup"><span data-stu-id="4d0c4-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-206">16406</span><span class="sxs-lookup"><span data-stu-id="4d0c4-206">16406</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-207">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="4d0c4-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-208">OUTLOOK</span><span class="sxs-lookup"><span data-stu-id="4d0c4-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-209">16407</span><span class="sxs-lookup"><span data-stu-id="4d0c4-209">16407</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-210">AOC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-211">AOC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-212">16408</span><span class="sxs-lookup"><span data-stu-id="4d0c4-212">16408</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-213">GCC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-214">GCC</span><span class="sxs-lookup"><span data-stu-id="4d0c4-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-215">16409</span><span class="sxs-lookup"><span data-stu-id="4d0c4-215">16409</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="4d0c4-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-218">16410</span><span class="sxs-lookup"><span data-stu-id="4d0c4-218">16410</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="4d0c4-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="4d0c4-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d0c4-221">32769</span><span class="sxs-lookup"><span data-stu-id="4d0c4-221">32769</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4d0c4-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-223">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4d0c4-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d0c4-224">32770</span><span class="sxs-lookup"><span data-stu-id="4d0c4-224">32770</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="4d0c4-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="4d0c4-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="4d0c4-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

