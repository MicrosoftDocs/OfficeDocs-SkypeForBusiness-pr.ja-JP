---
title: 'Lync Server 2013: クラスごとのスキーマの属性'
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
ms.openlocfilehash: 6b3a28d2691efb62663ea9cab3c695d78bf9e5e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510804"
---
# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="e211d-102">Lync Server 2013 のクラスごとのスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="e211d-102">Schema attributes by class in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e211d-103">_**トピックの最終更新日:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="e211d-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="e211d-104">このセクションでは、各 Lync Server 2013 クラスに含めることができるスキーマ属性と、他のクラスに含めることができるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e211d-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="e211d-105">すべてのクラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e211d-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="e211d-106">すべての属性とその説明の一覧については、「 [Lync Server 2013 のスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e211d-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="e211d-107">クラスごとの属性</span><span class="sxs-lookup"><span data-stu-id="e211d-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e211d-108">クラス</span><span class="sxs-lookup"><span data-stu-id="e211d-108">Class</span></span></th>
<th><span data-ttu-id="e211d-109">含まれる属性</span><span class="sxs-lookup"><span data-stu-id="e211d-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e211d-110">Contact</span><span class="sxs-lookup"><span data-stu-id="e211d-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="e211d-111">Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="e211d-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="e211d-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="e211d-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="e211d-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="e211d-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="e211d-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="e211d-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="e211d-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="e211d-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="e211d-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="e211d-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="e211d-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="e211d-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e211d-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="e211d-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="e211d-120">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="e211d-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="e211d-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="e211d-122">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="e211d-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="e211d-123">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="e211d-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="e211d-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="e211d-125">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="e211d-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="e211d-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="e211d-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="e211d-127">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="e211d-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="e211d-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e211d-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="e211d-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="e211d-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="e211d-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e211d-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="e211d-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="e211d-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="e211d-132">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="e211d-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="e211d-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="e211d-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="e211d-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="e211d-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="e211d-135">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="e211d-136">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="e211d-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="e211d-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="e211d-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="e211d-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="e211d-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="e211d-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e211d-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="e211d-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e211d-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="e211d-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e211d-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="e211d-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="e211d-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e211d-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="e211d-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="e211d-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="e211d-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="e211d-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="e211d-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="e211d-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="e211d-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="e211d-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="e211d-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="e211d-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="e211d-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="e211d-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="e211d-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="e211d-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="e211d-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="e211d-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="e211d-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="e211d-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="e211d-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="e211d-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="e211d-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-160">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="e211d-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="e211d-161">msRTCSIP-既定値</span><span class="sxs-lookup"><span data-stu-id="e211d-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="e211d-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="e211d-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="e211d-163">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="e211d-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="e211d-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="e211d-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="e211d-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="e211d-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="e211d-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="e211d-169">msRTCSIP-Msrtcsip-mcufactoryaddress です</span><span class="sxs-lookup"><span data-stu-id="e211d-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="e211d-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="e211d-174">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="e211d-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="e211d-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="e211d-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="e211d-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="e211d-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="e211d-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="e211d-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="e211d-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="e211d-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="e211d-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="e211d-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="e211d-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="e211d-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="e211d-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="e211d-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="e211d-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="e211d-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="e211d-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="e211d-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="e211d-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="e211d-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="e211d-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="e211d-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="e211d-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="e211d-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="e211d-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="e211d-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="e211d-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="e211d-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="e211d-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="e211d-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="e211d-197">msRTCSIP-MCUServers ユーザー</span><span class="sxs-lookup"><span data-stu-id="e211d-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="e211d-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="e211d-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="e211d-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="e211d-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="e211d-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="e211d-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="e211d-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="e211d-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="e211d-203">msRTCSIP-Msrtcsip-mcufactorypath</span><span class="sxs-lookup"><span data-stu-id="e211d-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-204">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="e211d-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="e211d-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="e211d-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="e211d-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="e211d-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="e211d-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="e211d-208">dnsHostName</span></span></p>
<p><span data-ttu-id="e211d-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-211">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="e211d-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="e211d-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="e211d-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="e211d-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="e211d-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="e211d-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="e211d-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="e211d-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="e211d-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="e211d-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="e211d-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="e211d-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="e211d-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="e211d-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="e211d-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="e211d-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="e211d-221">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="e211d-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="e211d-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="e211d-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="e211d-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-224">msRTCSIP-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="e211d-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="e211d-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="e211d-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="e211d-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="e211d-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="e211d-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="e211d-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="e211d-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="e211d-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="e211d-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="e211d-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="e211d-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="e211d-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="e211d-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="e211d-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="e211d-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="e211d-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="e211d-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="e211d-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="e211d-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="e211d-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="e211d-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="e211d-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="e211d-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="e211d-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="e211d-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="e211d-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="e211d-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="e211d-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="e211d-244">msRTCSIP ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="e211d-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="e211d-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="e211d-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="e211d-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="e211d-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="e211d-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="e211d-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="e211d-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="e211d-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="e211d-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="e211d-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="e211d-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="e211d-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="e211d-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-252">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="e211d-253">msRTCSIP-Trustedwebコンポーネント Serverdata</span><span class="sxs-lookup"><span data-stu-id="e211d-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="e211d-254">msRTCSIP-Trustedwebコンポーネント Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="e211d-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="e211d-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-256">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="e211d-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="e211d-257">msRTCSIP-Webコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="e211d-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-259">msRTCSIP-Webコンポーネントデータ</span><span class="sxs-lookup"><span data-stu-id="e211d-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="e211d-260">msRTCSIP-Msrtcsip-webcomponentspooladdress</span><span class="sxs-lookup"><span data-stu-id="e211d-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="e211d-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="e211d-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-262">User</span><span class="sxs-lookup"><span data-stu-id="e211d-262">User</span></span></p></td>
<td><p><span data-ttu-id="e211d-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="e211d-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="e211d-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="e211d-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="e211d-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="e211d-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="e211d-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="e211d-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="e211d-268">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="e211d-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="e211d-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="e211d-270">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="e211d-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="e211d-271">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="e211d-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="e211d-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="e211d-273">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="e211d-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="e211d-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="e211d-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="e211d-275">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="e211d-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="e211d-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="e211d-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="e211d-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="e211d-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="e211d-278">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="e211d-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="e211d-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="e211d-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="e211d-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="e211d-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="e211d-281">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="e211d-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="e211d-282">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="e211d-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="e211d-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="e211d-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="e211d-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="e211d-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="e211d-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="e211d-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="e211d-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="e211d-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="e211d-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e211d-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="e211d-288">他のクラスに含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="e211d-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e211d-289">クラス</span><span class="sxs-lookup"><span data-stu-id="e211d-289">Class</span></span></th>
<th><span data-ttu-id="e211d-290">含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="e211d-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e211d-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="e211d-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="e211d-292">msRTCSIP-サーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="e211d-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="e211d-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="e211d-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="e211d-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="e211d-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="e211d-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="e211d-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="e211d-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="e211d-297">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="e211d-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="e211d-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="e211d-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="e211d-299">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="e211d-300">msRTCSIP-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="e211d-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="e211d-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="e211d-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="e211d-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="e211d-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-303">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="e211d-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="e211d-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="e211d-305">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="e211d-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="e211d-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="e211d-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="e211d-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="e211d-308">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="e211d-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="e211d-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="e211d-310">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="e211d-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="e211d-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="e211d-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="e211d-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="e211d-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="e211d-313">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="e211d-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="e211d-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="e211d-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="e211d-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="e211d-316">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="e211d-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="e211d-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="e211d-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="e211d-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="e211d-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="e211d-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="e211d-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-320">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="e211d-321">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="e211d-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="e211d-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="e211d-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="e211d-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="e211d-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="e211d-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="e211d-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-326">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="e211d-327">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="e211d-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="e211d-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="e211d-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="e211d-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-330">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="e211d-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="e211d-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="e211d-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="e211d-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="e211d-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="e211d-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e211d-334">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="e211d-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="e211d-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="e211d-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e211d-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="e211d-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="e211d-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="e211d-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

