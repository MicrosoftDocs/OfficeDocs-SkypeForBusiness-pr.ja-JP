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
ms.openlocfilehash: ccccb1ea43b4f2eb4646d2b0670feda238f8c2c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="15e0a-102">Lync Server 2013 のクラスごとのスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="15e0a-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e0a-103">_**トピックの最終更新日:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="15e0a-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="15e0a-104">このセクションでは、各 Lync Server 2013 クラスに含めることができるスキーマ属性と、他のクラスに含めることができるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="15e0a-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="15e0a-105">すべてのクラスとその説明の一覧については、「 [Lync Server 2013 のスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0a-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="15e0a-106">すべての属性とその説明の一覧については、「 [Lync Server 2013 のスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0a-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="15e0a-107">クラスごとの属性</span><span class="sxs-lookup"><span data-stu-id="15e0a-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15e0a-108">クラス</span><span class="sxs-lookup"><span data-stu-id="15e0a-108">Class</span></span></th>
<th><span data-ttu-id="15e0a-109">含まれる属性</span><span class="sxs-lookup"><span data-stu-id="15e0a-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-110">連絡先</span><span class="sxs-lookup"><span data-stu-id="15e0a-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="15e0a-111">Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="15e0a-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="15e0a-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="15e0a-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="15e0a-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="15e0a-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="15e0a-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="15e0a-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="15e0a-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="15e0a-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="15e0a-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="15e0a-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="15e0a-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="15e0a-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="15e0a-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="15e0a-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="15e0a-120">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="15e0a-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="15e0a-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="15e0a-122">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="15e0a-123">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="15e0a-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="15e0a-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="15e0a-125">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="15e0a-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="15e0a-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="15e0a-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="15e0a-127">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="15e0a-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="15e0a-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="15e0a-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="15e0a-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="15e0a-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="15e0a-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="15e0a-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="15e0a-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="15e0a-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="15e0a-132">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="15e0a-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="15e0a-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="15e0a-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="15e0a-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="15e0a-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="15e0a-135">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="15e0a-136">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="15e0a-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="15e0a-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="15e0a-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="15e0a-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="15e0a-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="15e0a-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="15e0a-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="15e0a-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="15e0a-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="15e0a-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="15e0a-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="15e0a-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="15e0a-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="15e0a-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="15e0a-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="15e0a-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="15e0a-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="15e0a-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="15e0a-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="15e0a-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="15e0a-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="15e0a-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="15e0a-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="15e0a-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="15e0a-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="15e0a-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="15e0a-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="15e0a-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="15e0a-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="15e0a-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="15e0a-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="15e0a-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="15e0a-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="15e0a-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="15e0a-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-160">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="15e0a-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="15e0a-161">msRTCSIP-既定値</span><span class="sxs-lookup"><span data-stu-id="15e0a-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="15e0a-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="15e0a-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="15e0a-163">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="15e0a-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="15e0a-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="15e0a-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="15e0a-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="15e0a-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="15e0a-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="15e0a-169">msRTCSIP-Msrtcsip-mcufactoryaddress です</span><span class="sxs-lookup"><span data-stu-id="15e0a-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="15e0a-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="15e0a-174">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="15e0a-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="15e0a-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="15e0a-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="15e0a-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="15e0a-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="15e0a-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="15e0a-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="15e0a-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="15e0a-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="15e0a-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="15e0a-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="15e0a-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="15e0a-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="15e0a-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="15e0a-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="15e0a-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="15e0a-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="15e0a-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="15e0a-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="15e0a-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="15e0a-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="15e0a-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="15e0a-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="15e0a-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="15e0a-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="15e0a-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="15e0a-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="15e0a-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="15e0a-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="15e0a-197">msRTCSIP-MCUServers ユーザー</span><span class="sxs-lookup"><span data-stu-id="15e0a-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="15e0a-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="15e0a-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="15e0a-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="15e0a-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="15e0a-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="15e0a-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="15e0a-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="15e0a-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="15e0a-203">msRTCSIP-Msrtcsip-mcufactorypath</span><span class="sxs-lookup"><span data-stu-id="15e0a-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-204">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="15e0a-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="15e0a-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="15e0a-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="15e0a-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="15e0a-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="15e0a-208">dnsHostName</span></span></p>
<p><span data-ttu-id="15e0a-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-211">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="15e0a-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="15e0a-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="15e0a-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="15e0a-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="15e0a-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="15e0a-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="15e0a-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="15e0a-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="15e0a-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="15e0a-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="15e0a-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="15e0a-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="15e0a-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="15e0a-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="15e0a-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="15e0a-221">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="15e0a-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="15e0a-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="15e0a-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="15e0a-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-224">msRTCSIP-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="15e0a-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="15e0a-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="15e0a-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="15e0a-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="15e0a-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="15e0a-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="15e0a-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="15e0a-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="15e0a-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="15e0a-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="15e0a-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="15e0a-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="15e0a-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="15e0a-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="15e0a-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="15e0a-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="15e0a-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="15e0a-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="15e0a-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="15e0a-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="15e0a-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="15e0a-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="15e0a-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="15e0a-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="15e0a-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="15e0a-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="15e0a-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="15e0a-244">msRTCSIP ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="15e0a-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="15e0a-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="15e0a-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="15e0a-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="15e0a-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="15e0a-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="15e0a-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="15e0a-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="15e0a-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="15e0a-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="15e0a-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="15e0a-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="15e0a-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-252">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="15e0a-253">msRTCSIP-Trustedwebコンポーネント Serverdata</span><span class="sxs-lookup"><span data-stu-id="15e0a-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="15e0a-254">msRTCSIP-Trustedwebコンポーネント Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="15e0a-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="15e0a-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-256">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="15e0a-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="15e0a-257">msRTCSIP-Webコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-259">msRTCSIP-Webコンポーネントデータ</span><span class="sxs-lookup"><span data-stu-id="15e0a-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="15e0a-260">msRTCSIP-Msrtcsip-webcomponentspooladdress</span><span class="sxs-lookup"><span data-stu-id="15e0a-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="15e0a-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="15e0a-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-262">ユーザー</span><span class="sxs-lookup"><span data-stu-id="15e0a-262">User</span></span></p></td>
<td><p><span data-ttu-id="15e0a-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="15e0a-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="15e0a-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="15e0a-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="15e0a-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="15e0a-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="15e0a-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="15e0a-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="15e0a-268">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="15e0a-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="15e0a-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="15e0a-270">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="15e0a-271">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="15e0a-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="15e0a-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="15e0a-273">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="15e0a-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="15e0a-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="15e0a-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="15e0a-275">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="15e0a-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="15e0a-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="15e0a-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="15e0a-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="15e0a-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="15e0a-278">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="15e0a-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="15e0a-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="15e0a-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="15e0a-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="15e0a-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="15e0a-281">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="15e0a-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="15e0a-282">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="15e0a-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="15e0a-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="15e0a-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="15e0a-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="15e0a-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="15e0a-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="15e0a-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="15e0a-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="15e0a-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="15e0a-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="15e0a-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="15e0a-288">他のクラスに含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="15e0a-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15e0a-289">クラス</span><span class="sxs-lookup"><span data-stu-id="15e0a-289">Class</span></span></th>
<th><span data-ttu-id="15e0a-290">含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="15e0a-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="15e0a-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="15e0a-292">msRTCSIP-サーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="15e0a-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="15e0a-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="15e0a-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="15e0a-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="15e0a-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="15e0a-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="15e0a-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="15e0a-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="15e0a-297">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="15e0a-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="15e0a-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="15e0a-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="15e0a-299">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="15e0a-300">msRTCSIP-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="15e0a-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="15e0a-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="15e0a-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-303">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="15e0a-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="15e0a-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="15e0a-305">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="15e0a-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="15e0a-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="15e0a-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="15e0a-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="15e0a-308">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="15e0a-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="15e0a-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="15e0a-310">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="15e0a-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="15e0a-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="15e0a-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="15e0a-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="15e0a-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="15e0a-313">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="15e0a-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="15e0a-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="15e0a-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="15e0a-316">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="15e0a-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="15e0a-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="15e0a-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="15e0a-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="15e0a-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="15e0a-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-320">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="15e0a-321">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="15e0a-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="15e0a-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="15e0a-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="15e0a-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="15e0a-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="15e0a-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="15e0a-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-326">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="15e0a-327">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="15e0a-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="15e0a-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="15e0a-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="15e0a-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-330">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="15e0a-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="15e0a-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="15e0a-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="15e0a-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="15e0a-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e0a-334">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="15e0a-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="15e0a-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="15e0a-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e0a-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="15e0a-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="15e0a-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="15e0a-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

