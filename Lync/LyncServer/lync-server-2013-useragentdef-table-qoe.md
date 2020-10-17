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
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530104"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="180cb-102">Lync Server 2013 の UserAgentDef テーブル (QoE)</span><span class="sxs-lookup"><span data-stu-id="180cb-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180cb-103">_**トピックの最終更新日:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="180cb-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="180cb-104">UserAgentDef テーブルでは、ユーザー エージェントの識別子をエージェントの説明的な名前にマップします。</span><span class="sxs-lookup"><span data-stu-id="180cb-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="180cb-105">ユーザーエージェントは、Microsoft Lync Server 2013 に接続するために使用されるソフトウェアクライアントです。</span><span class="sxs-lookup"><span data-stu-id="180cb-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180cb-106">UAType</span><span class="sxs-lookup"><span data-stu-id="180cb-106">UAType</span></span></th>
<th><span data-ttu-id="180cb-107">UAName</span><span class="sxs-lookup"><span data-stu-id="180cb-107">UAName</span></span></th>
<th><span data-ttu-id="180cb-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="180cb-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180cb-109">1-d</span><span class="sxs-lookup"><span data-stu-id="180cb-109">1</span></span></p></td>
<td><p><span data-ttu-id="180cb-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="180cb-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="180cb-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="180cb-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-112">pbm-2</span><span class="sxs-lookup"><span data-stu-id="180cb-112">2</span></span></p></td>
<td><p><span data-ttu-id="180cb-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="180cb-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="180cb-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="180cb-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-115">4 </span><span class="sxs-lookup"><span data-stu-id="180cb-115">4</span></span></p></td>
<td><p><span data-ttu-id="180cb-116">OC</span><span class="sxs-lookup"><span data-stu-id="180cb-116">OC</span></span></p></td>
<td><p><span data-ttu-id="180cb-117">OC</span><span class="sxs-lookup"><span data-stu-id="180cb-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-118">8 </span><span class="sxs-lookup"><span data-stu-id="180cb-118">8</span></span></p></td>
<td><p><span data-ttu-id="180cb-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="180cb-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="180cb-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="180cb-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-121">16 </span><span class="sxs-lookup"><span data-stu-id="180cb-121">16</span></span></p></td>
<td><p><span data-ttu-id="180cb-122">LMC</span><span class="sxs-lookup"><span data-stu-id="180cb-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="180cb-123">LMC</span><span class="sxs-lookup"><span data-stu-id="180cb-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-124">32</span><span class="sxs-lookup"><span data-stu-id="180cb-124">32</span></span></p></td>
<td><p><span data-ttu-id="180cb-125">DVT</span><span class="sxs-lookup"><span data-stu-id="180cb-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="180cb-126">DVT</span><span class="sxs-lookup"><span data-stu-id="180cb-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-127">64</span><span class="sxs-lookup"><span data-stu-id="180cb-127">64</span></span></p></td>
<td><p><span data-ttu-id="180cb-128">MM</span><span class="sxs-lookup"><span data-stu-id="180cb-128">MM</span></span></p></td>
<td><p><span data-ttu-id="180cb-129">MM</span><span class="sxs-lookup"><span data-stu-id="180cb-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-130">64</span><span class="sxs-lookup"><span data-stu-id="180cb-130">64</span></span></p></td>
<td><p><span data-ttu-id="180cb-131">MC</span><span class="sxs-lookup"><span data-stu-id="180cb-131">MC</span></span></p></td>
<td><p><span data-ttu-id="180cb-132">MM</span><span class="sxs-lookup"><span data-stu-id="180cb-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-133">128</span><span class="sxs-lookup"><span data-stu-id="180cb-133">128</span></span></p></td>
<td><p><span data-ttu-id="180cb-134">Attendant</span><span class="sxs-lookup"><span data-stu-id="180cb-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="180cb-135">Attendant</span><span class="sxs-lookup"><span data-stu-id="180cb-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-136">256</span><span class="sxs-lookup"><span data-stu-id="180cb-136">256</span></span></p></td>
<td><p><span data-ttu-id="180cb-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="180cb-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="180cb-138">CA</span><span class="sxs-lookup"><span data-stu-id="180cb-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-139">512</span><span class="sxs-lookup"><span data-stu-id="180cb-139">512</span></span></p></td>
<td><p><span data-ttu-id="180cb-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="180cb-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="180cb-141">CAA</span><span class="sxs-lookup"><span data-stu-id="180cb-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-142">512</span><span class="sxs-lookup"><span data-stu-id="180cb-142">512</span></span></p></td>
<td><p><span data-ttu-id="180cb-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="180cb-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="180cb-144">CAA</span><span class="sxs-lookup"><span data-stu-id="180cb-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-145">1024</span><span class="sxs-lookup"><span data-stu-id="180cb-145">1024</span></span></p></td>
<td><p><span data-ttu-id="180cb-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="180cb-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="180cb-147">RG</span><span class="sxs-lookup"><span data-stu-id="180cb-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-148">1032</span><span class="sxs-lookup"><span data-stu-id="180cb-148">1032</span></span></p></td>
<td><p><span data-ttu-id="180cb-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="180cb-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="180cb-150">CPS</span><span class="sxs-lookup"><span data-stu-id="180cb-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-151">1040</span><span class="sxs-lookup"><span data-stu-id="180cb-151">1040</span></span></p></td>
<td><p><span data-ttu-id="180cb-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="180cb-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="180cb-153">AS</span><span class="sxs-lookup"><span data-stu-id="180cb-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-154">2048</span><span class="sxs-lookup"><span data-stu-id="180cb-154">2048</span></span></p></td>
<td><p><span data-ttu-id="180cb-155">Microsoft では、アプリケーション</span><span class="sxs-lookup"><span data-stu-id="180cb-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="180cb-156">CC</span><span class="sxs-lookup"><span data-stu-id="180cb-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-157">16386</span><span class="sxs-lookup"><span data-stu-id="180cb-157">16386</span></span></p></td>
<td><p><span data-ttu-id="180cb-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="180cb-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="180cb-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="180cb-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-160">16387</span><span class="sxs-lookup"><span data-stu-id="180cb-160">16387</span></span></p></td>
<td><p><span data-ttu-id="180cb-161">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="180cb-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="180cb-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="180cb-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-163">16388</span><span class="sxs-lookup"><span data-stu-id="180cb-163">16388</span></span></p></td>
<td><p><span data-ttu-id="180cb-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="180cb-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="180cb-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="180cb-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-166">16389</span><span class="sxs-lookup"><span data-stu-id="180cb-166">16389</span></span></p></td>
<td><p><span data-ttu-id="180cb-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="180cb-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="180cb-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="180cb-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-169">16393</span><span class="sxs-lookup"><span data-stu-id="180cb-169">16393</span></span></p></td>
<td><p><span data-ttu-id="180cb-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="180cb-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="180cb-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="180cb-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-172">16395</span><span class="sxs-lookup"><span data-stu-id="180cb-172">16395</span></span></p></td>
<td><p><span data-ttu-id="180cb-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="180cb-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="180cb-174">アーキテクチャエージェント</span><span class="sxs-lookup"><span data-stu-id="180cb-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-175">16396</span><span class="sxs-lookup"><span data-stu-id="180cb-175">16396</span></span></p></td>
<td><p><span data-ttu-id="180cb-176">停止</span><span class="sxs-lookup"><span data-stu-id="180cb-176">ST</span></span></p></td>
<td><p><span data-ttu-id="180cb-177">停止</span><span class="sxs-lookup"><span data-stu-id="180cb-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-178">16397</span><span class="sxs-lookup"><span data-stu-id="180cb-178">16397</span></span></p></td>
<td><p><span data-ttu-id="180cb-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="180cb-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="180cb-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="180cb-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-181">16398</span><span class="sxs-lookup"><span data-stu-id="180cb-181">16398</span></span></p></td>
<td><p><span data-ttu-id="180cb-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="180cb-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="180cb-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="180cb-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-184">16399</span><span class="sxs-lookup"><span data-stu-id="180cb-184">16399</span></span></p></td>
<td><p><span data-ttu-id="180cb-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="180cb-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="180cb-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="180cb-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-187">16400</span><span class="sxs-lookup"><span data-stu-id="180cb-187">16400</span></span></p></td>
<td><p><span data-ttu-id="180cb-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="180cb-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="180cb-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="180cb-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-190">16401</span><span class="sxs-lookup"><span data-stu-id="180cb-190">16401</span></span></p></td>
<td><p><span data-ttu-id="180cb-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="180cb-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="180cb-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="180cb-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-193">16402</span><span class="sxs-lookup"><span data-stu-id="180cb-193">16402</span></span></p></td>
<td><p><span data-ttu-id="180cb-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="180cb-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="180cb-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="180cb-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-196">16403</span><span class="sxs-lookup"><span data-stu-id="180cb-196">16403</span></span></p></td>
<td><p><span data-ttu-id="180cb-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="180cb-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="180cb-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="180cb-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-199">16404</span><span class="sxs-lookup"><span data-stu-id="180cb-199">16404</span></span></p></td>
<td><p><span data-ttu-id="180cb-200">CPC</span><span class="sxs-lookup"><span data-stu-id="180cb-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="180cb-201">CPC</span><span class="sxs-lookup"><span data-stu-id="180cb-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-202">16405</span><span class="sxs-lookup"><span data-stu-id="180cb-202">16405</span></span></p></td>
<td><p><span data-ttu-id="180cb-203">LWA</span><span class="sxs-lookup"><span data-stu-id="180cb-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="180cb-204">LWA</span><span class="sxs-lookup"><span data-stu-id="180cb-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-205">16406</span><span class="sxs-lookup"><span data-stu-id="180cb-205">16406</span></span></p></td>
<td><p><span data-ttu-id="180cb-206">OWA</span><span class="sxs-lookup"><span data-stu-id="180cb-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="180cb-207">OWA</span><span class="sxs-lookup"><span data-stu-id="180cb-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-208">16407</span><span class="sxs-lookup"><span data-stu-id="180cb-208">16407</span></span></p></td>
<td><p><span data-ttu-id="180cb-209">の「c」</span><span class="sxs-lookup"><span data-stu-id="180cb-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="180cb-210">の「c」</span><span class="sxs-lookup"><span data-stu-id="180cb-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-211">16408</span><span class="sxs-lookup"><span data-stu-id="180cb-211">16408</span></span></p></td>
<td><p><span data-ttu-id="180cb-212">GCC</span><span class="sxs-lookup"><span data-stu-id="180cb-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="180cb-213">GCC</span><span class="sxs-lookup"><span data-stu-id="180cb-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-214">16409</span><span class="sxs-lookup"><span data-stu-id="180cb-214">16409</span></span></p></td>
<td><p><span data-ttu-id="180cb-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="180cb-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="180cb-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="180cb-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-217">16410</span><span class="sxs-lookup"><span data-stu-id="180cb-217">16410</span></span></p></td>
<td><p><span data-ttu-id="180cb-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="180cb-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="180cb-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="180cb-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-220">32769</span><span class="sxs-lookup"><span data-stu-id="180cb-220">32769</span></span></p></td>
<td><p><span data-ttu-id="180cb-221">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="180cb-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="180cb-222">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="180cb-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-223">32770</span><span class="sxs-lookup"><span data-stu-id="180cb-223">32770</span></span></p></td>
<td><p><span data-ttu-id="180cb-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="180cb-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="180cb-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="180cb-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

