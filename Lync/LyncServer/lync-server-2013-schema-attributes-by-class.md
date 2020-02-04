---
title: 'Lync Server 2013: クラスごとのスキーマ属性'
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
ms.openlocfilehash: 160a148705ececfcbe105dcbc3fca819d4790a0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="4e619-102">Lync Server 2013 のクラス別のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="4e619-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e619-103">_**最終更新日:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="4e619-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="4e619-104">このセクションでは、各 Lync Server 2013 クラスに含めることができるスキーマ属性と、他のクラスに含めることができるクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4e619-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="4e619-105">すべてのクラスとその説明の一覧については、「 [Lync Server 2013 でのスキーマクラスと説明](lync-server-2013-schema-classes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e619-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="4e619-106">すべての属性と説明の一覧については、「 [Lync Server 2013 でのスキーマの属性と説明](lync-server-2013-schema-attributes-and-descriptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e619-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="4e619-107">クラスごとの属性</span><span class="sxs-lookup"><span data-stu-id="4e619-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e619-108">クラス</span><span class="sxs-lookup"><span data-stu-id="4e619-108">Class</span></span></th>
<th><span data-ttu-id="4e619-109">以下の属性が含まれている可能性がある</span><span class="sxs-lookup"><span data-stu-id="4e619-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e619-110">問い合わせ</span><span class="sxs-lookup"><span data-stu-id="4e619-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="4e619-111">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="4e619-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="4e619-112">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="4e619-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="4e619-113">Msrtcsip-userenabled true-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="4e619-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="4e619-114">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="4e619-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="4e619-115">Msrtcsip-userenabled true-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="4e619-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="4e619-116">Msrtcsip-userenabled true-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="4e619-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="4e619-117">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="4e619-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="4e619-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="4e619-119">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="4e619-120">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="4e619-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="4e619-121">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="4e619-122">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="4e619-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="4e619-123">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="4e619-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="4e619-124">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="4e619-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="4e619-125">Msrtcsip-userenabled true-Sid</span><span class="sxs-lookup"><span data-stu-id="4e619-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="4e619-126">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="4e619-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="4e619-127">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="4e619-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="4e619-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="4e619-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="4e619-129">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="4e619-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="4e619-130">Msrtcsip-userenabled true-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4e619-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="4e619-131">Msrtcsip-userenabled true-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="4e619-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="4e619-132">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="4e619-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="4e619-133">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="4e619-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="4e619-134">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="4e619-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="4e619-135">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="4e619-136">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="4e619-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="4e619-137">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="4e619-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="4e619-138">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="4e619-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="4e619-139">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="4e619-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="4e619-140">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="4e619-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="4e619-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4e619-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-142">メール受信者</span><span class="sxs-lookup"><span data-stu-id="4e619-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="4e619-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="4e619-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="4e619-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-145">Msrtcsip-userenabled true-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="4e619-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="4e619-146">Msrtcsip-userenabled true-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="4e619-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-147">Msrtcsip-userenabled true-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-148">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="4e619-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="4e619-149">Msrtcsip-userenabled true-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="4e619-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="4e619-150">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-151">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-152">Msrtcsip-userenabled true-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="4e619-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="4e619-153">Msrtcsip-userenabled true-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="4e619-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="4e619-154">Msrtcsip-userenabled true-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="4e619-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="4e619-155">Msrtcsip-userenabled true-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="4e619-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="4e619-156">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-157">Msrtcsip-userenabled true-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="4e619-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="4e619-158">Msrtcsip-userenabled true-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="4e619-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="4e619-159">Msrtcsip-userenabled true-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="4e619-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-160">Msrtcsip-userenabled true-ドメイン</span><span class="sxs-lookup"><span data-stu-id="4e619-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="4e619-161">Msrtcsip-userenabled true-既定値</span><span class="sxs-lookup"><span data-stu-id="4e619-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="4e619-162">Msrtcsip-userenabled true-DomainData</span><span class="sxs-lookup"><span data-stu-id="4e619-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="4e619-163">Msrtcsip-userenabled true-ドメイン名</span><span class="sxs-lookup"><span data-stu-id="4e619-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-164">Msrtcsip-userenabled true-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="4e619-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="4e619-165">Msrtcsip-userenabled true-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="4e619-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="4e619-166">Msrtcsip-userenabled true-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-167">Msrtcsip-userenabled true-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-168">Msrtcsip-userenabled true-MCUData</span><span class="sxs-lookup"><span data-stu-id="4e619-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="4e619-169">Msrtcsip-userenabled true-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="4e619-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="4e619-170">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-171">Msrtcsip-userenabled true-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-172">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-173">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="4e619-174">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="4e619-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-175">Msrtcsip-userenabled true-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-176">Msrtcsip-userenabled true-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="4e619-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="4e619-177">Msrtcsip-userenabled true-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="4e619-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="4e619-178">Msrtcsip-userenabled true-ServerData</span><span class="sxs-lookup"><span data-stu-id="4e619-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="4e619-179">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-180">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="4e619-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="4e619-181">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="4e619-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="4e619-182">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-183">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="4e619-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="4e619-184">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-185">Msrtcsip-userenabled true-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="4e619-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="4e619-186">Msrtcsip-userenabled true-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="4e619-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-187">Msrtcsip-userenabled true-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="4e619-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="4e619-188">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-189">Msrtcsip-userenabled true-MappingContact</span><span class="sxs-lookup"><span data-stu-id="4e619-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="4e619-190">Msrtcsip-userenabled true-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="4e619-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-191">Msrtcsip-userenabled true-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="4e619-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="4e619-192">Msrtcsip-userenabled true-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="4e619-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="4e619-193">Msrtcsip-userenabled true-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="4e619-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-194">Msrtcsip-userenabled true-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="4e619-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="4e619-195">Msrtcsip-userenabled true-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="4e619-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="4e619-196">Msrtcsip-userenabled true-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="4e619-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="4e619-197">msrtcsip-userenabled true-mcuser</span><span class="sxs-lookup"><span data-stu-id="4e619-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="4e619-198">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="4e619-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="4e619-199">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="4e619-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="4e619-200">Msrtcsip-userenabled true-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="4e619-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="4e619-201">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-202">Msrtcsip-userenabled true-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="4e619-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="4e619-203">Msrtcsip-userenabled true-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="4e619-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-204">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="4e619-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="4e619-205">Msrtcsip-userenabled true-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="4e619-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="4e619-206">Msrtcsip-userenabled true-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="4e619-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-207">Msrtcsip-userenabled true-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="4e619-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="4e619-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="4e619-208">dnsHostName</span></span></p>
<p><span data-ttu-id="4e619-209">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-210">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-211">Msrtcsip-userenabled true プール</span><span class="sxs-lookup"><span data-stu-id="4e619-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="4e619-212">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="4e619-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="4e619-213">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="4e619-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="4e619-214">Msrtcsip-userenabled true-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="4e619-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="4e619-215">Msrtcsip-userenabled true-PoolData</span><span class="sxs-lookup"><span data-stu-id="4e619-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="4e619-216">Msrtcsip-userenabled true-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="4e619-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="4e619-217">Msrtcsip-userenabled true-Pooldomaqdn</span><span class="sxs-lookup"><span data-stu-id="4e619-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="4e619-218">Msrtcsip-userenabled true-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="4e619-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="4e619-219">Msrtcsip-userenabled true-PoolType</span><span class="sxs-lookup"><span data-stu-id="4e619-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="4e619-220">Msrtcsip-userenabled true-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="4e619-221">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="4e619-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-222">Msrtcsip-userenabled true-PoolService</span><span class="sxs-lookup"><span data-stu-id="4e619-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="4e619-223">Msrtcsip-userenabled true-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="4e619-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-224">Msrtcsip-userenabled true-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="4e619-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="4e619-225">Msrtcsip-userenabled true-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="4e619-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="4e619-226">Msrtcsip-userenabled true-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="4e619-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-227">Msrtcsip-userenabled true-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="4e619-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="4e619-228">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="4e619-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="4e619-229">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="4e619-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="4e619-230">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="4e619-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="4e619-231">Msrtcsip-userenabled true-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="4e619-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="4e619-232">Msrtcsip-userenabled true-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="4e619-233">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-234">Msrtcsip-userenabled true-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="4e619-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="4e619-235">Msrtcsip-userenabled true-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="4e619-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="4e619-236">Msrtcsip-userenabled true-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="4e619-237">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-238">Msrtcsip-userenabled true-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="4e619-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="4e619-239">Msrtcsip-userenabled true-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="4e619-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="4e619-240">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="4e619-241">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-242">Msrtcsip-userenabled true-TrustedService</span><span class="sxs-lookup"><span data-stu-id="4e619-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="4e619-243">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4e619-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="4e619-244">Msrtcsip-userenabled true-ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="4e619-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="4e619-245">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="4e619-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="4e619-246">Msrtcsip-userenabled true-ServerBL</span><span class="sxs-lookup"><span data-stu-id="4e619-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="4e619-247">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="4e619-248">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="4e619-249">Msrtcsip-userenabled true-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="4e619-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="4e619-250">Msrtcsip-userenabled true-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="4e619-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="4e619-251">Msrtcsip-userenabled true-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="4e619-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-252">Msrtcsip-userenabled true-Trustedwebのサーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="4e619-253">Msrtcsip-userenabled true-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="4e619-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="4e619-254">Msrtcsip-userenabled true-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="4e619-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="4e619-255">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-256">Msrtcsip-userenabled true-Webmessages サービス</span><span class="sxs-lookup"><span data-stu-id="4e619-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="4e619-257">Msrtcsip-userenabled true-Webservers サーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-258">Msrtcsip-userenabled true-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="4e619-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-259">Msrtcsip-userenabled true-Webcontacts データ</span><span class="sxs-lookup"><span data-stu-id="4e619-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="4e619-260">Msrtcsip-userenabled true-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="4e619-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="4e619-261">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="4e619-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-262">ユーザー</span><span class="sxs-lookup"><span data-stu-id="4e619-262">User</span></span></p></td>
<td><p><span data-ttu-id="4e619-263">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="4e619-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="4e619-264">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="4e619-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="4e619-265">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="4e619-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="4e619-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="4e619-267">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="4e619-268">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="4e619-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="4e619-269">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="4e619-270">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="4e619-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="4e619-271">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="4e619-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="4e619-272">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="4e619-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="4e619-273">Msrtcsip-userenabled true-Sid</span><span class="sxs-lookup"><span data-stu-id="4e619-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="4e619-274">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="4e619-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="4e619-275">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="4e619-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="4e619-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="4e619-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="4e619-277">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="4e619-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="4e619-278">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="4e619-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="4e619-279">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="4e619-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="4e619-280">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="4e619-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="4e619-281">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="4e619-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="4e619-282">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="4e619-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="4e619-283">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="4e619-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="4e619-284">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="4e619-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="4e619-285">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="4e619-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="4e619-286">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="4e619-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="4e619-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="4e619-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="4e619-288">他のクラスに含まれるクラス</span><span class="sxs-lookup"><span data-stu-id="4e619-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e619-289">クラス</span><span class="sxs-lookup"><span data-stu-id="4e619-289">Class</span></span></th>
<th><span data-ttu-id="4e619-290">このクラスを含めることができます</span><span class="sxs-lookup"><span data-stu-id="4e619-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e619-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="4e619-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="4e619-292">Msrtcsip-userenabled true-サーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="4e619-293">Msrtcsip-userenabled true-PoolService</span><span class="sxs-lookup"><span data-stu-id="4e619-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="4e619-294">Msrtcsip-userenabled true-MCU</span><span class="sxs-lookup"><span data-stu-id="4e619-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="4e619-295">Msrtcsip-userenabled true-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="4e619-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="4e619-296">Msrtcsip-userenabled true-Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4e619-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="4e619-297">Msrtcsip-userenabled true-Webmessages サービス</span><span class="sxs-lookup"><span data-stu-id="4e619-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="4e619-298">Msrtcsip-userenabled true-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="4e619-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="4e619-299">Msrtcsip-userenabled true-サービス</span><span class="sxs-lookup"><span data-stu-id="4e619-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="4e619-300">Msrtcsip-userenabled true-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="4e619-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="4e619-301">Msrtcsip-userenabled true-MediationServer</span><span class="sxs-lookup"><span data-stu-id="4e619-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="4e619-302">Msrtcsip-userenabled true-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="4e619-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-303">Msrtcsip-userenabled true-サービス</span><span class="sxs-lookup"><span data-stu-id="4e619-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="4e619-304">Msrtcsip-userenabled true-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="4e619-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="4e619-305">Msrtcsip-userenabled true-プール</span><span class="sxs-lookup"><span data-stu-id="4e619-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="4e619-306">Msrtcsip-userenabled true-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="4e619-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="4e619-307">Msrtcsip-userenabled true-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="4e619-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="4e619-308">Msrtcsip-userenabled true-Trustedwebservers サーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="4e619-309">Msrtcsip-userenabled true-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="4e619-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="4e619-310">Msrtcsip-userenabled true-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="4e619-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="4e619-311">Msrtcsip-userenabled true-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="4e619-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="4e619-312">Msrtcsip-userenabled true-LocationContactMappings マッピング</span><span class="sxs-lookup"><span data-stu-id="4e619-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="4e619-313">Msrtcsip-userenabled true-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="4e619-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="4e619-314">Msrtcsip-userenabled true-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="4e619-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-315">Msrtcsip-userenabled true-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="4e619-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="4e619-316">Msrtcsip-userenabled true-ドメイン</span><span class="sxs-lookup"><span data-stu-id="4e619-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="4e619-317">Msrtcsip-userenabled true-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="4e619-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="4e619-318">Msrtcsip-userenabled true-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="4e619-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="4e619-319">Msrtcsip-userenabled true-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="4e619-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-320">Msrtcsip-userenabled true-プール</span><span class="sxs-lookup"><span data-stu-id="4e619-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="4e619-321">Msrtcsip-userenabled true プール</span><span class="sxs-lookup"><span data-stu-id="4e619-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-322">Msrtcsip-userenabled true-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="4e619-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="4e619-323">Msrtcsip-userenabled true-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="4e619-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-324">Msrtcsip-userenabled true-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="4e619-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="4e619-325">Msrtcsip-userenabled true-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="4e619-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-326">Msrtcsip-userenabled true-Trustedwebservers サーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="4e619-327">Msrtcsip-userenabled true-Trustedwebのサーバー</span><span class="sxs-lookup"><span data-stu-id="4e619-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-328">Msrtcsip-userenabled true-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="4e619-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="4e619-329">Msrtcsip-userenabled true-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="4e619-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-330">Msrtcsip-userenabled true-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="4e619-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="4e619-331">Msrtcsip-userenabled true-TrustedService</span><span class="sxs-lookup"><span data-stu-id="4e619-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-332">Msrtcsip-userenabled true-LocationContactMappings マッピング</span><span class="sxs-lookup"><span data-stu-id="4e619-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="4e619-333">Msrtcsip-userenabled true-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="4e619-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e619-334">Msrtcsip-userenabled true-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="4e619-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="4e619-335">Msrtcsip-userenabled true-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="4e619-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e619-336">Msrtcsip-userenabled true-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="4e619-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="4e619-337">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="4e619-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

