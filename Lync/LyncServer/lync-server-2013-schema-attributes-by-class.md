---
title: 'Lync Server 2013: クラスごとのスキーマの属性'
description: 'Lync Server 2013: クラスごとのスキーマ属性。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd31e42ce825049903310d6021e13086fe07afd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557173"
---
# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="32898-103">Lync Server 2013 のクラスごとのスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="32898-103">Schema attributes by class in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32898-104">_**トピックの最終更新日:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="32898-104">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="32898-105">このセクションでは、各 Lync Server 2013 クラスに含めることができるスキーマ属性と、他のクラスに含めることができるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="32898-105">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="32898-106">すべてのクラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32898-106">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="32898-107">すべての属性とその説明の一覧については、「 [Lync Server 2013 のスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32898-107">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="32898-108">クラスごとの属性</span><span class="sxs-lookup"><span data-stu-id="32898-108">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32898-109">クラス</span><span class="sxs-lookup"><span data-stu-id="32898-109">Class</span></span></th>
<th><span data-ttu-id="32898-110">含まれる属性</span><span class="sxs-lookup"><span data-stu-id="32898-110">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32898-111">Contact</span><span class="sxs-lookup"><span data-stu-id="32898-111">Contact</span></span></p></td>
<td><p><span data-ttu-id="32898-112">Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="32898-112">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="32898-113">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="32898-113">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="32898-114">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="32898-114">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="32898-115">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="32898-115">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="32898-116">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="32898-116">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="32898-117">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="32898-117">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="32898-118">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-118">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="32898-119">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="32898-119">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="32898-120">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-120">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="32898-121">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="32898-121">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="32898-122">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-122">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="32898-123">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="32898-123">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="32898-124">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-124">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="32898-125">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="32898-125">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="32898-126">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="32898-126">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="32898-127">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="32898-127">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="32898-128">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="32898-128">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="32898-129">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="32898-129">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="32898-130">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="32898-130">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="32898-131">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="32898-131">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="32898-132">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="32898-132">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="32898-133">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="32898-133">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="32898-134">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="32898-134">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="32898-135">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="32898-135">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="32898-136">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-136">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="32898-137">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="32898-137">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="32898-138">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="32898-138">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="32898-139">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="32898-139">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="32898-140">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="32898-140">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="32898-141">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="32898-141">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="32898-142">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="32898-142">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-143">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="32898-143">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="32898-144">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="32898-144">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="32898-145">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="32898-145">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-146">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="32898-146">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="32898-147">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="32898-147">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-148">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="32898-148">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="32898-149">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="32898-149">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="32898-150">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="32898-150">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="32898-151">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-151">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-152">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-152">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-153">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="32898-153">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="32898-154">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="32898-154">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="32898-155">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="32898-155">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="32898-156">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="32898-156">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="32898-157">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-157">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-158">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="32898-158">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="32898-159">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="32898-159">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="32898-160">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="32898-160">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-161">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="32898-161">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="32898-162">msRTCSIP-既定値</span><span class="sxs-lookup"><span data-stu-id="32898-162">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="32898-163">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="32898-163">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="32898-164">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="32898-164">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-165">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="32898-165">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="32898-166">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="32898-166">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="32898-167">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-167">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-168">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="32898-168">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="32898-169">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="32898-169">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="32898-170">msRTCSIP-Msrtcsip-mcufactoryaddress です</span><span class="sxs-lookup"><span data-stu-id="32898-170">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="32898-171">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-171">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-172">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="32898-172">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="32898-173">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-173">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-174">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-174">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="32898-175">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="32898-175">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-176">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="32898-176">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="32898-177">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="32898-177">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="32898-178">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="32898-178">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="32898-179">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="32898-179">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="32898-180">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-180">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-181">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="32898-181">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="32898-182">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="32898-182">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="32898-183">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-183">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-184">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="32898-184">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="32898-185">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-185">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-186">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="32898-186">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="32898-187">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="32898-187">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-188">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="32898-188">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="32898-189">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-189">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-190">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="32898-190">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="32898-191">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="32898-191">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-192">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="32898-192">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="32898-193">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="32898-193">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="32898-194">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="32898-194">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-195">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="32898-195">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="32898-196">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="32898-196">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="32898-197">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="32898-197">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="32898-198">msRTCSIP-MCUServers ユーザー</span><span class="sxs-lookup"><span data-stu-id="32898-198">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="32898-199">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="32898-199">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="32898-200">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="32898-200">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="32898-201">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="32898-201">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="32898-202">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-202">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-203">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="32898-203">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="32898-204">msRTCSIP-Msrtcsip-mcufactorypath</span><span class="sxs-lookup"><span data-stu-id="32898-204">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-205">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-205">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="32898-206">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="32898-206">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="32898-207">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="32898-207">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="32898-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="32898-209">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="32898-209">dnsHostName</span></span></p>
<p><span data-ttu-id="32898-210">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-210">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-211">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-211">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-212">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-212">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="32898-213">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="32898-213">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="32898-214">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="32898-214">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="32898-215">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="32898-215">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="32898-216">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="32898-216">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="32898-217">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="32898-217">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="32898-218">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-218">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="32898-219">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="32898-219">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="32898-220">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="32898-220">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="32898-221">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="32898-221">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="32898-222">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="32898-222">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-223">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="32898-223">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="32898-224">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="32898-224">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-225">msRTCSIP-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="32898-225">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="32898-226">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="32898-226">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="32898-227">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="32898-227">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-228">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="32898-228">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="32898-229">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="32898-229">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="32898-230">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="32898-230">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="32898-231">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="32898-231">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="32898-232">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="32898-232">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="32898-233">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-233">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="32898-234">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-234">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-235">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="32898-235">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="32898-236">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="32898-236">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="32898-237">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-237">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="32898-238">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-238">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-239">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="32898-239">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="32898-240">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="32898-240">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="32898-241">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-241">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="32898-242">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-242">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-243">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="32898-243">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="32898-244">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="32898-244">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="32898-245">msRTCSIP ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="32898-245">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="32898-246">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="32898-246">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="32898-247">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="32898-247">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="32898-248">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="32898-248">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="32898-249">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-249">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="32898-250">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="32898-250">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="32898-251">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="32898-251">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="32898-252">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="32898-252">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-253">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="32898-253">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="32898-254">msRTCSIP-Trustedwebコンポーネント Serverdata</span><span class="sxs-lookup"><span data-stu-id="32898-254">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="32898-255">msRTCSIP-Trustedwebコンポーネント Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="32898-255">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="32898-256">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-256">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-257">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="32898-257">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="32898-258">msRTCSIP-Webコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="32898-258">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-259">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="32898-259">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="32898-260">msRTCSIP-Webコンポーネントデータ</span><span class="sxs-lookup"><span data-stu-id="32898-260">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="32898-261">msRTCSIP-Msrtcsip-webcomponentspooladdress</span><span class="sxs-lookup"><span data-stu-id="32898-261">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="32898-262">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="32898-262">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-263">User</span><span class="sxs-lookup"><span data-stu-id="32898-263">User</span></span></p></td>
<td><p><span data-ttu-id="32898-264">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="32898-264">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="32898-265">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="32898-265">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="32898-266">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-266">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="32898-267">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="32898-267">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="32898-268">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-268">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="32898-269">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="32898-269">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="32898-270">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-270">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="32898-271">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="32898-271">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="32898-272">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-272">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="32898-273">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="32898-273">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="32898-274">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="32898-274">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="32898-275">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="32898-275">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="32898-276">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="32898-276">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="32898-277">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="32898-277">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="32898-278">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="32898-278">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="32898-279">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="32898-279">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="32898-280">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="32898-280">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="32898-281">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="32898-281">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="32898-282">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="32898-282">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="32898-283">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="32898-283">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="32898-284">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="32898-284">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="32898-285">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="32898-285">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="32898-286">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="32898-286">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="32898-287">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="32898-287">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="32898-288">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="32898-288">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="32898-289">他のクラスに含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="32898-289">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32898-290">クラス</span><span class="sxs-lookup"><span data-stu-id="32898-290">Class</span></span></th>
<th><span data-ttu-id="32898-291">含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="32898-291">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32898-292">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="32898-292">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="32898-293">msRTCSIP-サーバー</span><span class="sxs-lookup"><span data-stu-id="32898-293">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="32898-294">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="32898-294">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="32898-295">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="32898-295">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="32898-296">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="32898-296">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="32898-297">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="32898-297">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="32898-298">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="32898-298">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="32898-299">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="32898-299">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="32898-300">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-300">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="32898-301">msRTCSIP-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="32898-301">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="32898-302">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="32898-302">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="32898-303">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="32898-303">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-304">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-304">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="32898-305">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="32898-305">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="32898-306">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-306">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="32898-307">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="32898-307">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="32898-308">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="32898-308">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="32898-309">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="32898-309">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="32898-310">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="32898-310">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="32898-311">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="32898-311">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="32898-312">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="32898-312">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="32898-313">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="32898-313">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="32898-314">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="32898-314">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="32898-315">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="32898-315">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-316">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="32898-316">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="32898-317">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="32898-317">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="32898-318">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="32898-318">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="32898-319">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="32898-319">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="32898-320">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="32898-320">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-321">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-321">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="32898-322">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="32898-322">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-323">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="32898-323">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="32898-324">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="32898-324">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-325">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="32898-325">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="32898-326">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="32898-326">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-327">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="32898-327">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="32898-328">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="32898-328">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-329">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="32898-329">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="32898-330">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="32898-330">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-331">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="32898-331">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="32898-332">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="32898-332">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-333">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="32898-333">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="32898-334">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="32898-334">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32898-335">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="32898-335">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="32898-336">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="32898-336">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32898-337">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="32898-337">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="32898-338">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="32898-338">msRTCSIP-GlobalTopologySetting</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

