---
title: 'Lync Server 2013: クラスごとのスキーマ属性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09978d9b0cad055b4c3b33976df838ba5543887d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="8dc2c-102">Lync Server 2013 のクラス別のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="8dc2c-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dc2c-103">_**最終更新日:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="8dc2c-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="8dc2c-104">このセクションでは、各 Lync Server 2013 クラスに含めることができるスキーマ属性と、他のクラスに含めることができるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8dc2c-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="8dc2c-105">すべてのクラスとその説明の一覧については、「 [Lync Server 2013 でのスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dc2c-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="8dc2c-106">すべての属性と説明の一覧については、「 [Lync Server 2013 でのスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dc2c-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="8dc2c-107">クラスごとの属性</span><span class="sxs-lookup"><span data-stu-id="8dc2c-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc2c-108">クラス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-108">Class</span></span></th>
<th><span data-ttu-id="8dc2c-109">以下の属性が含まれている可能性がある</span><span class="sxs-lookup"><span data-stu-id="8dc2c-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-110">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="8dc2c-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-111">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="8dc2c-112">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="8dc2c-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="8dc2c-113">Msrtcsip-userenabled true-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="8dc2c-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="8dc2c-114">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="8dc2c-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="8dc2c-115">Msrtcsip-userenabled true-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="8dc2c-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="8dc2c-116">Msrtcsip-userenabled true-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="8dc2c-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="8dc2c-117">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="8dc2c-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="8dc2c-119">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-120">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="8dc2c-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="8dc2c-121">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-122">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="8dc2c-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="8dc2c-123">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="8dc2c-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="8dc2c-124">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="8dc2c-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="8dc2c-125">Msrtcsip-userenabled true-Sid</span><span class="sxs-lookup"><span data-stu-id="8dc2c-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="8dc2c-126">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="8dc2c-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="8dc2c-127">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="8dc2c-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="8dc2c-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="8dc2c-129">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="8dc2c-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="8dc2c-130">Msrtcsip-userenabled true-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8dc2c-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="8dc2c-131">Msrtcsip-userenabled true-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="8dc2c-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="8dc2c-132">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="8dc2c-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="8dc2c-133">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="8dc2c-134">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="8dc2c-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="8dc2c-135">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-136">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="8dc2c-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="8dc2c-137">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="8dc2c-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="8dc2c-138">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="8dc2c-139">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="8dc2c-140">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8dc2c-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="8dc2c-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8dc2c-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-142">メール受信者</span><span class="sxs-lookup"><span data-stu-id="8dc2c-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8dc2c-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-145">Msrtcsip-userenabled true-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-146">Msrtcsip-userenabled true-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="8dc2c-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-147">Msrtcsip-userenabled true-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-148">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="8dc2c-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="8dc2c-149">Msrtcsip-userenabled true-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="8dc2c-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="8dc2c-150">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-151">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-152">Msrtcsip-userenabled true-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="8dc2c-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-153">Msrtcsip-userenabled true-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="8dc2c-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="8dc2c-154">Msrtcsip-userenabled true-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="8dc2c-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="8dc2c-155">Msrtcsip-userenabled true-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="8dc2c-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="8dc2c-156">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-157">Msrtcsip-userenabled true-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="8dc2c-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-158">Msrtcsip-userenabled true-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="8dc2c-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="8dc2c-159">Msrtcsip-userenabled true-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="8dc2c-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-160">Msrtcsip-userenabled true-ドメイン</span><span class="sxs-lookup"><span data-stu-id="8dc2c-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-161">Msrtcsip-userenabled true-既定値</span><span class="sxs-lookup"><span data-stu-id="8dc2c-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="8dc2c-162">Msrtcsip-userenabled true-DomainData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="8dc2c-163">Msrtcsip-userenabled true-ドメイン名</span><span class="sxs-lookup"><span data-stu-id="8dc2c-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-164">Msrtcsip-userenabled true-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-165">Msrtcsip-userenabled true-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="8dc2c-166">Msrtcsip-userenabled true-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-167">Msrtcsip-userenabled true-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-168">Msrtcsip-userenabled true-MCUData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="8dc2c-169">Msrtcsip-userenabled true-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="8dc2c-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="8dc2c-170">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-171">Msrtcsip-userenabled true-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-172">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-173">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="8dc2c-174">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="8dc2c-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-175">Msrtcsip-userenabled true-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-176">Msrtcsip-userenabled true-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="8dc2c-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="8dc2c-177">Msrtcsip-userenabled true-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="8dc2c-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="8dc2c-178">Msrtcsip-userenabled true-ServerData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="8dc2c-179">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-180">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="8dc2c-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-181">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="8dc2c-182">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-183">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="8dc2c-184">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-185">Msrtcsip-userenabled true-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="8dc2c-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-186">Msrtcsip-userenabled true-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="8dc2c-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-187">Msrtcsip-userenabled true-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="8dc2c-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-188">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-189">Msrtcsip-userenabled true-MappingContact</span><span class="sxs-lookup"><span data-stu-id="8dc2c-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="8dc2c-190">Msrtcsip-userenabled true-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="8dc2c-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-191">Msrtcsip-userenabled true-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="8dc2c-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-192">Msrtcsip-userenabled true-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="8dc2c-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="8dc2c-193">Msrtcsip-userenabled true-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="8dc2c-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-194">Msrtcsip-userenabled true-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="8dc2c-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-195">Msrtcsip-userenabled true-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="8dc2c-196">Msrtcsip-userenabled true-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="8dc2c-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="8dc2c-197">msrtcsip-userenabled true-mcuser</span><span class="sxs-lookup"><span data-stu-id="8dc2c-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="8dc2c-198">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="8dc2c-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="8dc2c-199">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="8dc2c-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="8dc2c-200">Msrtcsip-userenabled true-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="8dc2c-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="8dc2c-201">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-202">Msrtcsip-userenabled true-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-203">Msrtcsip-userenabled true-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="8dc2c-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-204">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="8dc2c-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-205">Msrtcsip-userenabled true-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="8dc2c-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="8dc2c-206">Msrtcsip-userenabled true-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-207">Msrtcsip-userenabled true-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="8dc2c-208">dnsHostName</span></span></p>
<p><span data-ttu-id="8dc2c-209">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-210">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-211">Msrtcsip-userenabled true プール</span><span class="sxs-lookup"><span data-stu-id="8dc2c-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-212">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="8dc2c-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="8dc2c-213">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="8dc2c-214">Msrtcsip-userenabled true-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="8dc2c-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="8dc2c-215">Msrtcsip-userenabled true-PoolData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="8dc2c-216">Msrtcsip-userenabled true-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="8dc2c-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="8dc2c-217">Msrtcsip-userenabled true-Pooldomaqdn</span><span class="sxs-lookup"><span data-stu-id="8dc2c-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-218">Msrtcsip-userenabled true-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="8dc2c-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="8dc2c-219">Msrtcsip-userenabled true-PoolType</span><span class="sxs-lookup"><span data-stu-id="8dc2c-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="8dc2c-220">Msrtcsip-userenabled true-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="8dc2c-221">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="8dc2c-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-222">Msrtcsip-userenabled true-PoolService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-223">Msrtcsip-userenabled true-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="8dc2c-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-224">Msrtcsip-userenabled true-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-225">Msrtcsip-userenabled true-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="8dc2c-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="8dc2c-226">Msrtcsip-userenabled true-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-227">Msrtcsip-userenabled true-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="8dc2c-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-228">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="8dc2c-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="8dc2c-229">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="8dc2c-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="8dc2c-230">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="8dc2c-231">Msrtcsip-userenabled true-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="8dc2c-232">Msrtcsip-userenabled true-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-233">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-234">Msrtcsip-userenabled true-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-235">Msrtcsip-userenabled true-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="8dc2c-236">Msrtcsip-userenabled true-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-237">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-238">Msrtcsip-userenabled true-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-239">Msrtcsip-userenabled true-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="8dc2c-240">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-241">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-242">Msrtcsip-userenabled true-TrustedService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-243">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="8dc2c-244">Msrtcsip-userenabled true-ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="8dc2c-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="8dc2c-245">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="8dc2c-246">Msrtcsip-userenabled true-ServerBL</span><span class="sxs-lookup"><span data-stu-id="8dc2c-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="8dc2c-247">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-248">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="8dc2c-249">Msrtcsip-userenabled true-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="8dc2c-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="8dc2c-250">Msrtcsip-userenabled true-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="8dc2c-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="8dc2c-251">Msrtcsip-userenabled true-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="8dc2c-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-252">Msrtcsip-userenabled true-Trustedwebのサーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-253">Msrtcsip-userenabled true-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="8dc2c-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="8dc2c-254">Msrtcsip-userenabled true-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="8dc2c-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="8dc2c-255">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-256">Msrtcsip-userenabled true-Webmessages サービス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-257">Msrtcsip-userenabled true-Webservers サーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-258">Msrtcsip-userenabled true-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-259">Msrtcsip-userenabled true-Webcontacts データ</span><span class="sxs-lookup"><span data-stu-id="8dc2c-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="8dc2c-260">Msrtcsip-userenabled true-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="8dc2c-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="8dc2c-261">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="8dc2c-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-262">ユーザー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-262">User</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-263">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="8dc2c-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="8dc2c-264">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="8dc2c-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="8dc2c-265">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="8dc2c-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="8dc2c-267">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-268">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="8dc2c-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="8dc2c-269">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-270">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="8dc2c-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="8dc2c-271">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="8dc2c-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="8dc2c-272">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="8dc2c-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="8dc2c-273">Msrtcsip-userenabled true-Sid</span><span class="sxs-lookup"><span data-stu-id="8dc2c-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="8dc2c-274">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="8dc2c-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="8dc2c-275">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="8dc2c-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="8dc2c-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="8dc2c-277">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="8dc2c-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="8dc2c-278">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="8dc2c-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="8dc2c-279">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="8dc2c-280">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="8dc2c-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="8dc2c-281">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="8dc2c-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="8dc2c-282">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="8dc2c-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="8dc2c-283">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="8dc2c-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="8dc2c-284">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="8dc2c-285">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="8dc2c-286">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="8dc2c-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="8dc2c-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8dc2c-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="8dc2c-288">他のクラスに含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dc2c-289">クラス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-289">Class</span></span></th>
<th><span data-ttu-id="8dc2c-290">このクラスを含めることができます</span><span class="sxs-lookup"><span data-stu-id="8dc2c-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="8dc2c-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-292">Msrtcsip-userenabled true-サーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="8dc2c-293">Msrtcsip-userenabled true-PoolService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="8dc2c-294">Msrtcsip-userenabled true-MCU</span><span class="sxs-lookup"><span data-stu-id="8dc2c-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="8dc2c-295">Msrtcsip-userenabled true-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="8dc2c-296">Msrtcsip-userenabled true-Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8dc2c-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="8dc2c-297">Msrtcsip-userenabled true-Webmessages サービス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="8dc2c-298">Msrtcsip-userenabled true-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="8dc2c-299">Msrtcsip-userenabled true-サービス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="8dc2c-300">Msrtcsip-userenabled true-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="8dc2c-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="8dc2c-301">Msrtcsip-userenabled true-MediationServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="8dc2c-302">Msrtcsip-userenabled true-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-303">Msrtcsip-userenabled true-サービス</span><span class="sxs-lookup"><span data-stu-id="8dc2c-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-304">Msrtcsip-userenabled true-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="8dc2c-305">Msrtcsip-userenabled true-プール</span><span class="sxs-lookup"><span data-stu-id="8dc2c-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="8dc2c-306">Msrtcsip-userenabled true-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="8dc2c-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="8dc2c-307">Msrtcsip-userenabled true-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="8dc2c-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="8dc2c-308">Msrtcsip-userenabled true-Trustedwebservers サーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="8dc2c-309">Msrtcsip-userenabled true-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="8dc2c-310">Msrtcsip-userenabled true-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="8dc2c-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="8dc2c-311">Msrtcsip-userenabled true-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="8dc2c-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="8dc2c-312">Msrtcsip-userenabled true-LocationContactMappings マッピング</span><span class="sxs-lookup"><span data-stu-id="8dc2c-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="8dc2c-313">Msrtcsip-userenabled true-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="8dc2c-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="8dc2c-314">Msrtcsip-userenabled true-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-315">Msrtcsip-userenabled true-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-316">Msrtcsip-userenabled true-ドメイン</span><span class="sxs-lookup"><span data-stu-id="8dc2c-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="8dc2c-317">Msrtcsip-userenabled true-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="8dc2c-318">Msrtcsip-userenabled true-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="8dc2c-319">Msrtcsip-userenabled true-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="8dc2c-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-320">Msrtcsip-userenabled true-プール</span><span class="sxs-lookup"><span data-stu-id="8dc2c-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-321">Msrtcsip-userenabled true プール</span><span class="sxs-lookup"><span data-stu-id="8dc2c-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-322">Msrtcsip-userenabled true-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="8dc2c-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-323">Msrtcsip-userenabled true-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="8dc2c-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-324">Msrtcsip-userenabled true-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="8dc2c-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-325">Msrtcsip-userenabled true-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="8dc2c-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-326">Msrtcsip-userenabled true-Trustedwebservers サーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-327">Msrtcsip-userenabled true-Trustedwebのサーバー</span><span class="sxs-lookup"><span data-stu-id="8dc2c-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-328">Msrtcsip-userenabled true-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="8dc2c-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-329">Msrtcsip-userenabled true-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="8dc2c-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-330">Msrtcsip-userenabled true-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="8dc2c-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-331">Msrtcsip-userenabled true-TrustedService</span><span class="sxs-lookup"><span data-stu-id="8dc2c-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-332">Msrtcsip-userenabled true-LocationContactMappings マッピング</span><span class="sxs-lookup"><span data-stu-id="8dc2c-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-333">Msrtcsip-userenabled true-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="8dc2c-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dc2c-334">Msrtcsip-userenabled true-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="8dc2c-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-335">Msrtcsip-userenabled true-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="8dc2c-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dc2c-336">Msrtcsip-userenabled true-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="8dc2c-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="8dc2c-337">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="8dc2c-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

