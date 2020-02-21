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
ms.openlocfilehash: 621020816ae7882d25f65ab2a40578ddebcfe837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="0c1d8-102">Lync Server 2013 の UserAgentDef テーブル</span><span class="sxs-lookup"><span data-stu-id="0c1d8-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c1d8-103">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="0c1d8-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="0c1d8-104">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="0c1d8-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="0c1d8-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="0c1d8-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0c1d8-106">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0c1d8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c1d8-107">UAType</span><span class="sxs-lookup"><span data-stu-id="0c1d8-107">UAType</span></span></th>
<th><span data-ttu-id="0c1d8-108">UAName</span><span class="sxs-lookup"><span data-stu-id="0c1d8-108">UAName</span></span></th>
<th><span data-ttu-id="0c1d8-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="0c1d8-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-110">1-d</span><span class="sxs-lookup"><span data-stu-id="0c1d8-110">1</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0c1d8-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="0c1d8-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-113">pbm-2</span><span class="sxs-lookup"><span data-stu-id="0c1d8-113">2</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="0c1d8-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="0c1d8-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-116">2/4</span><span class="sxs-lookup"><span data-stu-id="0c1d8-116">4</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-117">OC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-117">OC</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-118">OC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-119">8 </span><span class="sxs-lookup"><span data-stu-id="0c1d8-119">8</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="0c1d8-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="0c1d8-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-122">16 </span><span class="sxs-lookup"><span data-stu-id="0c1d8-122">16</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-123">LMC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-124">LMC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-125">32</span><span class="sxs-lookup"><span data-stu-id="0c1d8-125">32</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-126">DVT</span><span class="sxs-lookup"><span data-stu-id="0c1d8-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-127">DVT</span><span class="sxs-lookup"><span data-stu-id="0c1d8-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-128">64</span><span class="sxs-lookup"><span data-stu-id="0c1d8-128">64</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-129">MM</span><span class="sxs-lookup"><span data-stu-id="0c1d8-129">MM</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-130">MM</span><span class="sxs-lookup"><span data-stu-id="0c1d8-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-131">64</span><span class="sxs-lookup"><span data-stu-id="0c1d8-131">64</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-132">MC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-132">MC</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-133">MM</span><span class="sxs-lookup"><span data-stu-id="0c1d8-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-134">128</span><span class="sxs-lookup"><span data-stu-id="0c1d8-134">128</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-135">Um</span><span class="sxs-lookup"><span data-stu-id="0c1d8-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-136">Um</span><span class="sxs-lookup"><span data-stu-id="0c1d8-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-137">256</span><span class="sxs-lookup"><span data-stu-id="0c1d8-137">256</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="0c1d8-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-139">CA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-140">512</span><span class="sxs-lookup"><span data-stu-id="0c1d8-140">512</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="0c1d8-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-142">CAA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-143">512</span><span class="sxs-lookup"><span data-stu-id="0c1d8-143">512</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="0c1d8-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-145">CAA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-146">1024</span><span class="sxs-lookup"><span data-stu-id="0c1d8-146">1024</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="0c1d8-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-148">RG</span><span class="sxs-lookup"><span data-stu-id="0c1d8-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-149">1032</span><span class="sxs-lookup"><span data-stu-id="0c1d8-149">1032</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="0c1d8-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-151">CPS</span><span class="sxs-lookup"><span data-stu-id="0c1d8-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-152">1040</span><span class="sxs-lookup"><span data-stu-id="0c1d8-152">1040</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="0c1d8-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-154">AS</span><span class="sxs-lookup"><span data-stu-id="0c1d8-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-155">2048</span><span class="sxs-lookup"><span data-stu-id="0c1d8-155">2048</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-156">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0c1d8-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-157">CC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-158">16386</span><span class="sxs-lookup"><span data-stu-id="0c1d8-158">16386</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="0c1d8-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="0c1d8-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-161">16387</span><span class="sxs-lookup"><span data-stu-id="0c1d8-161">16387</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="0c1d8-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="0c1d8-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-164">16388</span><span class="sxs-lookup"><span data-stu-id="0c1d8-164">16388</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="0c1d8-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="0c1d8-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-167">16389</span><span class="sxs-lookup"><span data-stu-id="0c1d8-167">16389</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="0c1d8-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="0c1d8-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-170">16393</span><span class="sxs-lookup"><span data-stu-id="0c1d8-170">16393</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="0c1d8-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="0c1d8-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-173">16395</span><span class="sxs-lookup"><span data-stu-id="0c1d8-173">16395</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="0c1d8-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-175">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="0c1d8-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-176">16396</span><span class="sxs-lookup"><span data-stu-id="0c1d8-176">16396</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-177">停止</span><span class="sxs-lookup"><span data-stu-id="0c1d8-177">ST</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-178">停止</span><span class="sxs-lookup"><span data-stu-id="0c1d8-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-179">16397</span><span class="sxs-lookup"><span data-stu-id="0c1d8-179">16397</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="0c1d8-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="0c1d8-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-182">16398</span><span class="sxs-lookup"><span data-stu-id="0c1d8-182">16398</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-185">16399</span><span class="sxs-lookup"><span data-stu-id="0c1d8-185">16399</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-188">16400</span><span class="sxs-lookup"><span data-stu-id="0c1d8-188">16400</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-191">16401</span><span class="sxs-lookup"><span data-stu-id="0c1d8-191">16401</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-194">16402</span><span class="sxs-lookup"><span data-stu-id="0c1d8-194">16402</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="0c1d8-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-197">16403</span><span class="sxs-lookup"><span data-stu-id="0c1d8-197">16403</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="0c1d8-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="0c1d8-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-200">16404</span><span class="sxs-lookup"><span data-stu-id="0c1d8-200">16404</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-201">CPC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-202">CPC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-203">16405</span><span class="sxs-lookup"><span data-stu-id="0c1d8-203">16405</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-204">LWA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-205">LWA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-206">16406</span><span class="sxs-lookup"><span data-stu-id="0c1d8-206">16406</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-207">OWA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-208">OWA</span><span class="sxs-lookup"><span data-stu-id="0c1d8-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-209">16407</span><span class="sxs-lookup"><span data-stu-id="0c1d8-209">16407</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="0c1d8-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-211">の「c」</span><span class="sxs-lookup"><span data-stu-id="0c1d8-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-212">16408</span><span class="sxs-lookup"><span data-stu-id="0c1d8-212">16408</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-213">GCC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-214">GCC</span><span class="sxs-lookup"><span data-stu-id="0c1d8-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-215">16409</span><span class="sxs-lookup"><span data-stu-id="0c1d8-215">16409</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="0c1d8-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="0c1d8-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-218">16410</span><span class="sxs-lookup"><span data-stu-id="0c1d8-218">16410</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="0c1d8-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="0c1d8-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c1d8-221">32769</span><span class="sxs-lookup"><span data-stu-id="0c1d8-221">32769</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="0c1d8-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-223">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="0c1d8-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c1d8-224">32770</span><span class="sxs-lookup"><span data-stu-id="0c1d8-224">32770</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="0c1d8-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="0c1d8-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="0c1d8-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

