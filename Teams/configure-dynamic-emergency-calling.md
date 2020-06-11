---
title: 動的な緊急通話を構成する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 通話プランおよび電話システムダイレクトルーティングの動的な緊急通話機能を構成する方法について説明します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50e32c34b211766aa5fc3ad7732b1dd392ed8346
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690883"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="a9664-103">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="a9664-104">Microsoft 通話プランや電話システムのダイレクトルーティングの動的な緊急通話では、チームクライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="a9664-105">テナント管理者が定義したネットワークトポロジに基づいて、Teams クライアントは、位置情報サービス (LIS) に対する要求にネットワーク接続情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9664-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="a9664-106">一致する場合、LIS はクライアントに対して場所を返します。</span><span class="sxs-lookup"><span data-stu-id="a9664-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="a9664-107">この位置情報データはクライアントに戻されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="a9664-108">チームクライアントには、緊急通話の一部として位置情報データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9664-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="a9664-109">このデータは、緊急サービスプロバイダーによって、適切な公開安全性の応答ポイント (PSAP) を特定し、その呼び出しをその PSAP にルーティングすることによって、呼び出し元の位置情報を取得できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a9664-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="a9664-110">動的な緊急通話の場合は、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="a9664-111">ネットワーク管理者がネットワーク設定と LIS を構成して、ネットワーク/緊急対応の場所マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9664-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="a9664-112">直接ルーティングの場合は、緊急通話をルーティングするために追加の構成が必要になります。また、パートナー接続の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a9664-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="a9664-113">管理者は、緊急ルーティングサービス (管理者) プロバイダーへの接続を構成する**か**(米国)、緊急対応の位置情報識別番号 (ELIN) アプリケーションのセッションボーダーコントローラー (SBC) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="a9664-114">起動時と定期的に定期的に、またはネットワーク接続が変更されると、チームクライアントはネットワーク接続情報が含まれている場所要求をネットワーク設定と LIS に送信します。</span><span class="sxs-lookup"><span data-stu-id="a9664-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="a9664-115">[ネットワーク設定] サイトが表示されている場合、緊急通話のポリシーがそのサイトから Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="a9664-116">(ポリシーの詳細については、「[緊急ポリシーを構成する](#configure-emergency-policies)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a9664-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="a9664-117">LIS の一致がある場合は、Teams クライアントが接続されているネットワーク要素の緊急対応の場所が Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="a9664-118">チームクライアントが緊急通報を行うと、緊急対応の場所が PSTN ネットワークに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="a9664-119">直接ルーティングの場合、管理者は、アプリを緊急通報に送信するように SBC を構成するか、SBC ELIN アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="a9664-120">この記事は、次のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a9664-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="a9664-121">緊急対応の住所を設定する</span><span class="sxs-lookup"><span data-stu-id="a9664-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="a9664-122">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="a9664-123">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="a9664-124">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="a9664-125">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="a9664-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="a9664-126">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="a9664-126">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="a9664-127">適切な公開安全性の応答ポイント (PSAP) に自動的にルーティングする機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9664-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="a9664-128">緊急通話の詳細については、緊急対応の住所と緊急通話のルーティング、国に固有の情報、ネットワーク設定とネットワークトポロジに関する情報などの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-128">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="a9664-129">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a9664-130">クラウド音声機能のネットワーク設定を管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="a9664-131">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

## <a name="supported-clients"></a><span data-ttu-id="a9664-132">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="a9664-132">Supported clients</span></span>

<span data-ttu-id="a9664-133">現在、次のクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9664-133">The following clients are currently supported.</span></span>  <span data-ttu-id="a9664-134">このリストの更新を確認するには、もう一度チェックインします。</span><span class="sxs-lookup"><span data-stu-id="a9664-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="a9664-135">Microsoft Windows 向けの Teams デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="a9664-135">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="a9664-136">Apple macOS 用の Teams デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="a9664-136">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="a9664-137">Apple iOS クライアントバージョン1.0.92.2019121004 と App Store バージョン1.0.92 以上の Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="a9664-137">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="a9664-138">Android クライアントと Google Play ストアのバージョン 1416/1.0.0.2019121201 以上の Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="a9664-138">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="a9664-139">Teams 電話バージョン 1449/1.0.94.2019110802 以降</span><span class="sxs-lookup"><span data-stu-id="a9664-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="a9664-140">緊急対応の住所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9664-140">Assign emergency addresses</span></span>

<span data-ttu-id="a9664-141">緊急対応の住所は、通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-141">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="a9664-142">(Subnet および WiFi AP はサポートされています。イーサネットスイッチ/ポートのサポートは保留中)。</span><span class="sxs-lookup"><span data-stu-id="a9664-142">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="a9664-143">米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に関連する geo コードが含まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-143">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="a9664-144">(地理コードのない緊急対応の住所を、動的な場所に必要なネットワーク識別子に割り当てることはできません。)</span><span class="sxs-lookup"><span data-stu-id="a9664-144">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="a9664-145">Azure Maps は、位置ベースのサービスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-145">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="a9664-146">Microsoft Teams 管理センターを使用して緊急対応の住所を入力すると、チームは次のアドレスの Azure Maps を確認します。</span><span class="sxs-lookup"><span data-stu-id="a9664-146">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="a9664-147">一致するものが見つかった場合は、geo コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9664-147">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="a9664-148">一致が見つからない場合は、緊急対応の住所を手動で作成する機会があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-148">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="a9664-149">PIN のドロップ機能を使用して、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-149">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="a9664-150">これは、通話プランユーザに割り当てるために作成された既存の緊急対応の場所が、動的な場所を目的としている場合は、その住所を再作成して geo コードを含める必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a9664-150">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="a9664-151">2つの場所を区別するには、別の説明を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-151">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="a9664-152">以前の場所を持っているユーザーに新しい緊急対応の場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-152">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="a9664-153">完全に移行された場合、古い場所は削除できます。</span><span class="sxs-lookup"><span data-stu-id="a9664-153">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="a9664-154">Microsoft Teams 管理センターまたは PowerShell を使用して、緊急対応の住所を追加して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9664-154">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="a9664-155">詳細については、「[組織の緊急対応の場所を追加する](add-change-remove-emergency-location-organization.md)」および「[緊急対応の場所をユーザーに割り当てる](assign-change-emergency-location-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-155">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="a9664-156">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-156">Configure network settings</span></span>

<span data-ttu-id="a9664-157">[ネットワーク設定] は、Teams クライアントの場所を決定するために使用され、緊急通話ポリシーと緊急対応の場所を動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="a9664-157">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="a9664-158">組織で緊急電話が機能する方法に応じて、ネットワーク設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a9664-158">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="a9664-159">[ネットワーク設定] には、サブネットのコレクションが含まれているサイトが含まれます。これらは、ユーザーに対する動的なポリシーの割り当てに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-159">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="a9664-160">たとえば、緊急通話のポリシーと緊急通話のルーティングポリシーが "Redmond サイト" に割り当てられている可能性があります。これにより、自宅または別の Microsoft の場所からローミングするすべてのユーザーが、緊急電話番号、ルーティング、および Redmond に固有のセキュリティデスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-160">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="a9664-161">サブネットは、LIS で定義することもできます。また、緊急対応の場所に関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="a9664-161">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="a9664-162">次の定義を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="a9664-162">Keep the following definitions in mind.</span></span> <span data-ttu-id="a9664-163">詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-163">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="a9664-164">信頼された IP アドレスには、エンタープライズネットワークのインターネット外部 IP アドレスのコレクションが含まれており、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-164">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="a9664-165">動的なポリシーまたは場所を取得しようとしても、ユーザーの外部 IP アドレスが信頼された IP アドレスの IP アドレスと一致する場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="a9664-165">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="a9664-166">一致は、IPv4 または IPv6 の IP アドレスに対して行うことができます。また、ネットワーク設定に送信される IP パケットの形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a9664-166">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="a9664-167">(パブリック IP アドレスに IPv4 と IPv6 の両方が含まれている場合は、両方を信頼できる IP アドレスとして追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a9664-167">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="a9664-168">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9664-168">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="a9664-169">ネットワークサイトは、オフィス、建物のセット、キャンパスなど、組織の物理的な値が含まれている場所を表します。</span><span class="sxs-lookup"><span data-stu-id="a9664-169">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="a9664-170">これらのサイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-170">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="a9664-171">ネットワークサブネットは、特定のネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-171">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="a9664-172">クライアントの場所は、ネットワークサブネットと関連付けられたネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-172">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="a9664-173">ネットワーク設定は、Microsoft Teams 管理センターまたは PowerShell を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="a9664-173">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="a9664-174">詳細については、「[クラウド音声機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-174">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="a9664-175">ネットワーク設定の変更 (新しいアドレス、ネットワーク識別子など) がチームクライアントに伝達されて利用可能になるまでに少し時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-175">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="a9664-176">**通話プランユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="a9664-176">**For Calling Plan users:**</span></span>

- <span data-ttu-id="a9664-177">セキュリティデスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-177">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="a9664-178">動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-178">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="a9664-179">どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a9664-179">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="a9664-180">**ダイレクトルーティングユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="a9664-180">**For Direct Routing users:**</span></span>

- <span data-ttu-id="a9664-181">緊急通報またはセキュリティデスクの動的構成の通知が動的に使用されるようにするには、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-181">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="a9664-182">動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-182">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="a9664-183">どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a9664-183">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="a9664-184">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-184">Configure Location Information Service</span></span>

<span data-ttu-id="a9664-185">チームクライアントは、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9664-185">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="a9664-186">サブネットとワイヤレスアクセスポイント (Wap) はどちらもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9664-186">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="a9664-187">(イーサネットスイッチ/ポートのサポートは保留中です)。</span><span class="sxs-lookup"><span data-stu-id="a9664-187">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="a9664-188">クライアントが場所を取得するには、ネットワーク識別子 (サブネット、Wap、スイッチ、ポート) と緊急対応の場所で LIS を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-188">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="a9664-189">これは、Microsoft Teams 管理センターまたは PowerShell を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-189">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a9664-190">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a9664-190">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a9664-191">左側のナビゲーションで、 **[場所]**  >  **ネットワーク & 場所**に移動します。</span><span class="sxs-lookup"><span data-stu-id="a9664-191">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="a9664-192">追加するネットワーク識別子を示すタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9664-192">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="a9664-193">たとえば、[**サブネット**]、[ **wi-fi アクセスポイント**]、[**スイッチ**]、または [**ポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9664-193">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="a9664-194">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9664-194">Then click **Add**.</span></span>
3. <span data-ttu-id="a9664-195">フィールドに入力し、緊急対応の場所を追加して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9664-195">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a9664-196">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a9664-196">Using PowerShell</span></span>

<span data-ttu-id="a9664-197">次のコマンドレットを使用して、ポート、スイッチ、サブネット、Wap を LIS に追加します。</span><span class="sxs-lookup"><span data-stu-id="a9664-197">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="a9664-198">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -csonlinのサブネット</span><span class="sxs-lookup"><span data-stu-id="a9664-198">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="a9664-199">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-csonlinのスポーツ</span><span class="sxs-lookup"><span data-stu-id="a9664-199">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="a9664-200">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="a9664-200">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="a9664-201">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-csonlinの切り替え</span><span class="sxs-lookup"><span data-stu-id="a9664-201">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="a9664-202">サブネットがネットワークサイトの一部として使われている場合は、動的な場所を表示するために、場所情報サービスでサブネットを再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-202">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="a9664-203">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a9664-203">Configure emergency policies</span></span>

<span data-ttu-id="a9664-204">緊急通話を構成するには、次のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9664-204">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="a9664-205">これらのポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="a9664-205">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="a9664-206">**緊急通話ルーティングポリシー** –直接ルーティングにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-206">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="a9664-207">このポリシーでは、緊急電話番号、必要に応じて番号のマスク、および電話番号ごとの PSTN ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a9664-207">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="a9664-208">このポリシーは、ユーザー、ネットワークサイト、またはその両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-208">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="a9664-209">(通話プランのチームクライアントは、Microsoft 365 または Office 365 の利用場所に基づいて、国の緊急電話番号によって自動的に有効になります)。 詳細については、「[ダイレクトルーティングの緊急通話ルーティングポリシーを管理](manage-emergency-call-routing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-209">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="a9664-210">**緊急通話ポリシー** -通話プランとダイレクトルーティングに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-210">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="a9664-211">このポリシーは、緊急通話が行われたときのセキュリティデスクの通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="a9664-211">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="a9664-212">通知する相手と通知方法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a9664-212">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="a9664-213">たとえば、組織のセキュリティデスクに通知を自動的に送信し、そのユーザーが緊急通話をリッスンするようにします。</span><span class="sxs-lookup"><span data-stu-id="a9664-213">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="a9664-214">このポリシーは、ユーザーまたはネットワークサイトまたはその両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-214">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="a9664-215">詳細については、「 [Teams の緊急通話ポリシーを管理](manage-emergency-calling-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-215">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="a9664-216">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="a9664-216">Enable users and sites</span></span>

<span data-ttu-id="a9664-217">緊急通話ルーティングポリシーと緊急通話ポリシーは、ユーザーとサイトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a9664-217">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="a9664-218">緊急通話ルーティングポリシーは、直接ルーティングのみに適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-218">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="a9664-219">(このポリシーは、通話プランのユーザーに割り当てることもできますが、ポリシーは影響を与えません)。</span><span class="sxs-lookup"><span data-stu-id="a9664-219">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="a9664-220">ポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9664-220">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="a9664-221">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9664-221">To learn more, see:</span></span>

- [<span data-ttu-id="a9664-222">ダイレクトルーティングの緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-222">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="a9664-223">Teams で緊急通話のポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-223">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="a9664-224">いくつかの PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9664-224">Here's some PowerShell examples.</span></span>

<span data-ttu-id="a9664-225">セキュリティデスクの通知に特定のユーザーを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9664-225">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="a9664-226">"Contoso 緊急通話ポリシー 1" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9664-226">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="a9664-227">緊急通話のために特定の直接ルーティングユーザーを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9664-227">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="a9664-228">"Contoso New 都エマージェンシールーティング" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9664-228">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="a9664-229">緊急通話のポリシーをネットワークサイトとユーザーに割り当て、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a9664-229">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="a9664-230">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="a9664-230">Test emergency calling</span></span>

<span data-ttu-id="a9664-231">米国の一部の緊急ルーティングサービスプロバイダー (ERSPs) では、緊急対応のテストボットが提供されています。</span><span class="sxs-lookup"><span data-stu-id="a9664-231">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="a9664-232">**米国の通話プランユーザー**は、事前に定義されたテスト緊急電話番号933を使って、緊急通話の構成を検証できます。</span><span class="sxs-lookup"><span data-stu-id="a9664-232">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="a9664-233">この番号はボットにルーティングされます。これは、発信者番号 (発信者の電話番号)、緊急対応の住所、場所、通話が自動的に PSAP にルーティングされるか、最初に表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a9664-233">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="a9664-234">**米国のダイレクトルーティングのお客様**は、テストサービスの ersp と連携する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9664-234">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="a9664-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9664-235">Related topics</span></span>

- [<span data-ttu-id="a9664-236">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-236">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a9664-237">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-237">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="a9664-238">緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-238">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="a9664-239">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a9664-239">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="a9664-240">ユーザーの緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="a9664-240">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="a9664-241">クラウド ボイス機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="a9664-241">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="a9664-242">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="a9664-242">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
