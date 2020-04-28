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
ms.openlocfilehash: 92862eb960722ac2becbe216cdec5281282106b5
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905889"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="bc217-103">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="bc217-104">Microsoft 通話プランや電話システムのダイレクトルーティングの動的な緊急通話では、チームクライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="bc217-105">テナント管理者が定義したネットワークトポロジに基づいて、Teams クライアントは、位置情報サービス (LIS) に対する要求にネットワーク接続情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc217-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span>  <span data-ttu-id="bc217-106">一致するものがある場合、LIS はクライアントに対して場所を返します。</span><span class="sxs-lookup"><span data-stu-id="bc217-106">If there is a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="bc217-107">この位置情報データはクライアントに戻されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="bc217-108">チームクライアントには、緊急通話の一部として位置情報データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc217-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="bc217-109">このデータは、緊急サービスプロバイダーによって、適切な公開安全性の応答ポイント (PSAP) を特定し、その呼び出しをその PSAP にルーティングすることによって、呼び出し元の位置情報を取得できるようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bc217-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="bc217-110">動的な緊急通話の場合は、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="bc217-111">ネットワーク管理者がネットワーク設定と LIS を構成して、ネットワーク/緊急対応の場所マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc217-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="bc217-112">直接ルーティングの場合は、緊急通話をルーティングするために追加の構成が必要になります。また、パートナー接続の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bc217-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="bc217-113">管理者は、緊急ルーティングサービス (管理者) プロバイダーへの接続を構成する**か**(米国)、緊急対応の位置情報識別番号 (ELIN) アプリケーションのセッションボーダーコントローラー (SBC) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="bc217-114">起動時と定期的に定期的に、またはネットワーク接続が変更されると、チームクライアントはネットワーク接続情報が含まれている場所要求をネットワーク設定と LIS に送信します。</span><span class="sxs-lookup"><span data-stu-id="bc217-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="bc217-115">[ネットワーク設定] サイトがある場合は、緊急通話のポリシーがそのサイトから Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-115">If there is a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="bc217-116">(ポリシーの詳細については、「[緊急ポリシーを構成する](#configure-emergency-policies)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bc217-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="bc217-117">LIS の一致がある場合は、Teams クライアントが接続されているネットワーク要素の緊急対応の場所が Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-117">If there is an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="bc217-118">チームクライアントが緊急通報を行うと、緊急対応の場所が PSTN ネットワークに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="bc217-119">直接ルーティングの場合、管理者は、アプリを緊急通報に送信するように SBC を構成するか、SBC ELIN アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="bc217-120">この記事は、次のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc217-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="bc217-121">緊急対応の住所を設定する</span><span class="sxs-lookup"><span data-stu-id="bc217-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="bc217-122">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="bc217-123">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="bc217-124">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="bc217-125">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="bc217-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="bc217-126">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="bc217-126">Test emergency calling</span></span>](#test-emergency-calling)


<span data-ttu-id="bc217-127">適切な公開安全性の応答ポイント (PSAP) に自動的にルーティングする機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bc217-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span> 

<span data-ttu-id="bc217-128">緊急通話の詳細については、緊急対応の住所と緊急通話のルーティングに関する情報、国に固有の情報、ネットワーク設定とネットワークトポロジに関する情報を含む緊急通話の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc217-128">For more information about emergency calling--including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology--see the following:</span></span>

- [<span data-ttu-id="bc217-129">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="bc217-130">クラウド音声機能のネットワーク設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="bc217-131">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)


## <a name="supported-clients"></a><span data-ttu-id="bc217-132">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="bc217-132">Supported clients</span></span>

<span data-ttu-id="bc217-133">現在、次のクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc217-133">The following clients are currently supported.</span></span>  <span data-ttu-id="bc217-134">このリストの更新を確認するには、もう一度チェックインします。</span><span class="sxs-lookup"><span data-stu-id="bc217-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="bc217-135">Microsoft Windows 向けの Teams デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="bc217-135">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="bc217-136">Apple macOS 用の Teams デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="bc217-136">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="bc217-137">Apple iOS クライアントバージョン1.0.92.2019121004 と App Store バージョン1.0.92 以上の Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="bc217-137">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="bc217-138">Android クライアントと Google Play ストアのバージョン 1416/1.0.0.2019121201 以上の Teams モバイルクライアント</span><span class="sxs-lookup"><span data-stu-id="bc217-138">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="bc217-139">Teams 電話バージョン 1449/1.0.94.2019110802 以降</span><span class="sxs-lookup"><span data-stu-id="bc217-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="bc217-140">緊急対応の住所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bc217-140">Assign emergency addresses</span></span>

<span data-ttu-id="bc217-141">緊急対応の住所は、通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-141">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="bc217-142">(Subnet および WiFi AP はサポートされています。イーサネットスイッチ/ポートのサポートは保留中)。</span><span class="sxs-lookup"><span data-stu-id="bc217-142">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="bc217-143">米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に関連する geo コードが含まれていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-143">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="bc217-144">(地理コードのない緊急対応の住所を、動的な場所に必要なネットワーク識別子に割り当てることはできません。)</span><span class="sxs-lookup"><span data-stu-id="bc217-144">(Emergency addresses without geo codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="bc217-145">Azure Maps は、位置ベースのサービスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-145">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="bc217-146">Microsoft Teams 管理センターを使用して緊急対応の住所を入力すると、チームは次のアドレスの Azure Maps を確認します。</span><span class="sxs-lookup"><span data-stu-id="bc217-146">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="bc217-147">一致するものが見つかった場合は、geo コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc217-147">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="bc217-148">一致が見つからなかった場合は、緊急対応の住所を手動で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-148">If a match is not found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="bc217-149">PIN のドロップ機能を使用して、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-149">You can use the PIN drop feature to do this.</span></span>   

<span data-ttu-id="bc217-150">これは、通話プランユーザに割り当てるために作成された既存の緊急対応の場所が、動的な場所を目的としている場合は、その住所を再作成して geo コードを含める必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bc217-150">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="bc217-151">2つの場所を区別するには、別の説明を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-151">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="bc217-152">以前の場所を持っているユーザーに新しい緊急対応の場所を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-152">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="bc217-153">完全に移行された場合、古い場所は削除できます。</span><span class="sxs-lookup"><span data-stu-id="bc217-153">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="bc217-154">緊急対応の住所の設定の詳細については、「[組織の緊急対応の場所を追加](add-change-remove-emergency-location-organization.md)する」および「[緊急対応の場所をユーザーに割り当てる](assign-change-emergency-location-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc217-154">For more information about configuring emergency addresses, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for your user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="bc217-155">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-155">Configure network settings</span></span>

<span data-ttu-id="bc217-156">[ネットワーク設定] は、Teams クライアントの場所を決定するために使用され、緊急通話ポリシーと緊急対応の場所を動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="bc217-156">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="bc217-157">組織で緊急電話が機能する方法に応じて、ネットワーク設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bc217-157">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="bc217-158">ネットワーク設定には、サブネットのコレクションが含まれているサイトが含まれます。これらは、ユーザーへの動的なポリシーの割り当てに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-158">Network settings include sites that include a collection of subnets--these are used exclusively for dynamic policy assignment to users.</span></span>  <span data-ttu-id="bc217-159">たとえば、TeamsEmergencyCalling ポリシーと TeamsEmergencyCallRouting ポリシーは "Redmond site" に割り当てられている可能性があります。これにより、自宅または別の Microsoft の場所からローミングしたユーザーは、緊急電話番号、ルーティング、および、Redmond に固有のセキュリティデスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-159">For example, a TeamsEmergencyCalling Policy and TeamsEmergencyCallRouting Policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="bc217-160">サブネットは、LIS で定義することもできます。また、緊急対応の場所に関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="bc217-160">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="bc217-161">次の定義を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="bc217-161">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="bc217-162">信頼できる IP には、企業ネットワークのインターネット外部 Ip のコレクションが含まれており、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-162">Trusted IP's contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="bc217-163">動的なポリシーまたは場所を取得しようとしても、ユーザーの外部 IP が信頼された IP アドレスの IP アドレスと一致した場合にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="bc217-163">An attempt to obtain a dynamic policy or location will only be made if the user's external IP matches an IP in the Trusted IP address.</span></span> <span data-ttu-id="bc217-164">一致は、IPv4 または IPv6 の IP アドレスに対して行うことができます。また、ネットワーク設定に送信される IP パケットの形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bc217-164">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="bc217-165">(パブリック IP アドレスに IPv4 と IPv6 の両方が含まれている場合は、両方を信頼できる IP アドレスとして追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="bc217-165">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="bc217-166">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc217-166">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="bc217-167">ネットワークサイトは、オフィス、建物のセット、キャンパスなど、組織の物理的な値が含まれている場所を表します。</span><span class="sxs-lookup"><span data-stu-id="bc217-167">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="bc217-168">これらのサイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-168">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="bc217-169">ネットワークサブネットは、特定のネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-169">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="bc217-170">クライアントの場所は、ネットワークサブネットと関連付けられたネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-170">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="bc217-171">詳細については、「[クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」と「[クラウド音声機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc217-171">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md) and [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="bc217-172">ネットワーク設定の変更 (新しいアドレス、ネットワーク識別子など) がチームクライアントに伝達されて利用可能になるまでに少し時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc217-172">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="bc217-173">**通話プランユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="bc217-173">**For Calling Plan users:**</span></span>

- <span data-ttu-id="bc217-174">セキュリティデスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-174">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="bc217-175">動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-175">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="bc217-176">どちらも必要ない場合は、ネットワーク設定の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bc217-176">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="bc217-177">**ダイレクトルーティングユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="bc217-177">**For Direct Routing users:**</span></span>

- <span data-ttu-id="bc217-178">緊急通報またはセキュリティデスクの動的構成の通知が動的に使用されるようにするには、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-178">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="bc217-179">動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-179">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span>

- <span data-ttu-id="bc217-180">どちらも必要ない場合は、ネットワーク設定の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bc217-180">If neither are required, then configuration of network settings is not required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="bc217-181">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-181">Configure Location Information Service</span></span>

<span data-ttu-id="bc217-182">チームクライアントは、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc217-182">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="bc217-183">サブネットとワイヤレスアクセスポイント (Wap) はどちらもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc217-183">Both subnets and Wireless Access Points (WAPs) are supported.</span></span> <span data-ttu-id="bc217-184">(イーサネットスイッチ/ポートのサポートは保留中です)。</span><span class="sxs-lookup"><span data-stu-id="bc217-184">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="bc217-185">クライアントが場所を取得するには、次のコマンドレットを使用して、場所情報サービス (LIS) にネットワーク識別子と緊急対応の場所を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-185">For a client to obtain a location, you must populate the Location Information Service (LIS) with network identifiers and emergency locations by using the following cmdlets:</span></span>  


- <span data-ttu-id="bc217-186">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-csonlinのスポーツ</span><span class="sxs-lookup"><span data-stu-id="bc217-186">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="bc217-187">[取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、[削除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-csonlinの切り替え</span><span class="sxs-lookup"><span data-stu-id="bc217-187">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="bc217-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -csonlinのサブネット</span><span class="sxs-lookup"><span data-stu-id="bc217-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="bc217-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="bc217-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span></span> 


>[!Important] 
><span data-ttu-id="bc217-190">サブネットがネットワークサイトの一部として使われている場合は、動的な場所を表示するために、場所情報サービスでサブネットを再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-190">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


## <a name="configure-emergency-policies"></a><span data-ttu-id="bc217-191">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="bc217-191">Configure emergency policies</span></span>

<span data-ttu-id="bc217-192">緊急通話を構成するには、次のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-192">You use the following policies to configure emergency calling:</span></span>

- <span data-ttu-id="bc217-193">**TeamsEmergencyCallRoutingPolicy** –直接ルーティングにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-193">**TeamsEmergencyCallRoutingPolicy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="bc217-194">このポリシーでは、緊急電話番号、必要に応じて番号のマスク、および電話番号ごとの PSTN ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc217-194">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="bc217-195">このポリシーは、ユーザー、ネットワークサイト、またはその両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-195">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="bc217-196">(通話プランのチームクライアントは、Office 365 の利用場所に基づいて、国の緊急電話番号を使用して、自動的に有効になります。) このポリシーを管理するには、新しい-、CsTeamsEmergencyCallRouting コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-196">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Office 365 usage location.)  You manage this policy by using the New-, Set-, and Grant-CsTeamsEmergencyCallRouting cmdlets.</span></span> 

- <span data-ttu-id="bc217-197">**TeamsEmergencyCallingPolicy** -通話プランとダイレクトルーティングに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-197">**TeamsEmergencyCallingPolicy** - Applies to Calling Plan and Direct Routing.</span></span> <span data-ttu-id="bc217-198">このポリシーは、緊急通話が行われたときのセキュリティデスクの通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="bc217-198">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="bc217-199">通知する相手と通知方法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc217-199">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="bc217-200">たとえば、組織のセキュリティデスクに通知を自動的に送信し、そのユーザーが緊急通話をリッスンするようにします。</span><span class="sxs-lookup"><span data-stu-id="bc217-200">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="bc217-201">このポリシーは、ユーザーまたはネットワークサイトまたはその両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-201">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="bc217-202">このポリシーを管理するには、新しい-、CsTeamsEmergencyCallingPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-202">You manage this policy by using the New-, Set- and Grant-CsTeamsEmergencyCallingPolicy  cmdlets.</span></span> 

<span data-ttu-id="bc217-203">詳細については、「 [Teams で緊急通話のポリシーを管理](manage-emergency-calling-policies.md)する」および「[ダイレクトルーティングの緊急通話ルーティングポリシーを管理する](manage-emergency-call-routing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc217-203">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md) and [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>


## <a name="enable-users-and-sites"></a><span data-ttu-id="bc217-204">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="bc217-204">Enable users and sites</span></span>

<span data-ttu-id="bc217-205">**TeamsEmergencyCalling**と**TeamsEmergencyCallROuting**のポリシーは、ユーザーとサイトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc217-205">You can assign **TeamsEmergencyCalling** and **TeamsEmergencyCallROuting** policies to users and to sites.</span></span>  

<span data-ttu-id="bc217-206">TeamsEmergencyCallRouting ポリシーは、直接ルーティング専用に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-206">The TeamsEmergencyCallRouting policy applies to Direct Routing only.</span></span> <span data-ttu-id="bc217-207">(このポリシーは、通話プランのユーザーに割り当てることもできますが、ポリシーは影響を与えません)。</span><span class="sxs-lookup"><span data-stu-id="bc217-207">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="bc217-208">たとえば、セキュリティデスクの通知に特定のユーザーを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-208">For example, to enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="bc217-209">"Contoso 緊急通話ポリシー 1" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-209">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="bc217-210">緊急通話のために特定の直接ルーティングユーザーを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-210">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="bc217-211">"Contoso New 都エマージェンシールーティング" と呼ばれるポリシーをサイト1に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc217-211">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="bc217-212">緊急通話のポリシーをネットワークサイトとユーザーに割り当て、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="bc217-212">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


## <a name="test-emergency-calling"></a><span data-ttu-id="bc217-213">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="bc217-213">Test emergency calling</span></span>

<span data-ttu-id="bc217-214">米国の一部の緊急ルーティングサービスプロバイダー (ERSPs) では、緊急対応のテストボットが提供されています。</span><span class="sxs-lookup"><span data-stu-id="bc217-214">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="bc217-215">**米国の通話プランユーザー**は、事前に定義されたテスト緊急電話番号933を使って、緊急通話の構成を検証できます。</span><span class="sxs-lookup"><span data-stu-id="bc217-215">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="bc217-216">この番号はボットにルーティングされます。これは、発信者番号 (発信者の電話番号)、緊急対応の住所、場所、通話が自動的に PSAP にルーティングされるか、最初に表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bc217-216">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="bc217-217">**米国のダイレクトルーティングのお客様**は、テストサービスの ersp と連携する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc217-217">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="bc217-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc217-218">Related topics</span></span>

- [<span data-ttu-id="bc217-219">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-219">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="bc217-220">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-220">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="bc217-221">緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-221">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="bc217-222">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="bc217-222">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="bc217-223">ユーザーの緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="bc217-223">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="bc217-224">クラウド ボイス機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="bc217-224">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="bc217-225">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="bc217-225">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
