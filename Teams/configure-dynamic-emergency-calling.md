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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 通話プランと電話システムダイレクト ルーティングの動的緊急通話機能を構成する方法について説明します。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2531add2b43b7061b81a23676c54fbc557929c0f
ms.sourcegitcommit: 2ce82f301f2d59da57f579a23038b2cab5e31360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51858010"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="6ee28-103">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="6ee28-104">Microsoft 通話プランと電話システムダイレクト ルーティングの動的緊急通話は、Teams クライアントの現在の場所に基づいて緊急通話を構成およびルーティングし、セキュリティ担当者に通知する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="6ee28-105">テナント管理者が定義するネットワーク トポロジに基づいて、Teams クライアントは Location Information Service (LIS) への要求でネットワーク接続情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="6ee28-106">一致する値がある場合、LIS はクライアントに場所を返します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="6ee28-107">この場所のデータは、クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="6ee28-108">Teams クライアントには、緊急通話の一部として場所データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="6ee28-109">このデータは、緊急サービス プロバイダーによって適切なパブリック セーフティ応答ポイント (PSAP) を決定し、その PSAP に通話をルーティングするために使用されます。これにより、PSAP ディスパッチャーは呼び出し元の場所を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="6ee28-110">動的緊急通話の場合は、次の処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="6ee28-111">ネットワーク管理者がネットワーク設定と LIS を構成して、ネットワーク/緊急対応の場所マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="6ee28-112">直接ルーティングの場合、緊急通話をルーティングする場合や、パートナー接続の場合は追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ee28-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="6ee28-113">管理者は、緊急ルーティング サービス (ERS) プロバイダー ( **米国)** への接続を構成するか、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="6ee28-114">起動中および定期的に、またはネットワーク接続が変更された場合、Teams クライアントはネットワーク接続情報を含む場所要求をネットワーク設定と LIS に送信します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="6ee28-115">ネットワーク設定サイトが一致する場合–緊急通話ポリシーは、そのサイトから Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="6ee28-116">(ポリシーの詳細については、「緊急ポリシーを構成する [」を参照してください](#configure-emergency-policies))。</span><span class="sxs-lookup"><span data-stu-id="6ee28-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="6ee28-117">LIS が一致する場合は、Teams クライアントが接続されているネットワーク要素からの緊急対応の場所が Teams クライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="6ee28-118">一致は次の順序で実行され、最初に一致した結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="6ee28-119">(1)</span><span class="sxs-lookup"><span data-stu-id="6ee28-119">WAP</span></span>
       - <span data-ttu-id="6ee28-120">イーサネット スイッチ/ポート</span><span class="sxs-lookup"><span data-stu-id="6ee28-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="6ee28-121">イーサネット スイッチ</span><span class="sxs-lookup"><span data-stu-id="6ee28-121">Ethernet switch</span></span>
       - <span data-ttu-id="6ee28-122">サブネット</span><span class="sxs-lookup"><span data-stu-id="6ee28-122">Subnet</span></span>

3. <span data-ttu-id="6ee28-123">Teams クライアントが緊急通話を行う場合、緊急対応の場所は PSTN ネットワークに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="6ee28-124">直接ルーティングの場合、管理者は緊急通話を ERS プロバイダーに送信するか、SBC ELIN アプリケーションを構成するために SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="6ee28-125">この記事では、次のセクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="6ee28-126">緊急対応の住所を構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="6ee28-127">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="6ee28-128">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="6ee28-129">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="6ee28-130">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="6ee28-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="6ee28-131">緊急通話をテストする</span><span class="sxs-lookup"><span data-stu-id="6ee28-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="6ee28-132">適切なパブリック セーフティ応答ポイント (PSAP) に自動ルーティングを実行する機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="6ee28-133">緊急通話の詳細 (緊急対応の住所と緊急通話ルーティングに関する情報、国固有の情報、ネットワーク設定とネットワーク トポロジに関する情報など) については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ee28-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="6ee28-134">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6ee28-135">クラウド音声機能のネットワーク設定を管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="6ee28-136">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

<span data-ttu-id="6ee28-137">政府機関向けクラウドで利用できる機能の詳細については、この記事の[](#government-support)最後にある政府機関向けサポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ee28-137">For more information about which features are available in the government clouds, see [Government support](#government-support) at the end of this article.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="6ee28-138">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="6ee28-138">Supported clients</span></span>

<span data-ttu-id="6ee28-139">現在、次のクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ee28-139">The following clients are currently supported.</span></span>  <span data-ttu-id="6ee28-140">この一覧の更新プログラムを確認するには、頻繁に確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ee28-140">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="6ee28-141">Microsoft Windows 用 Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="6ee28-141">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="6ee28-142">Apple macOS 用 Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="6ee28-142">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="6ee28-143">Apple iOS クライアント バージョン 1.0.92.2019121004 および App Store バージョン 1.0.92 以上用の Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="6ee28-143">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="6ee28-144">Android クライアントおよび Google Play ストア バージョン 1416/1.0.0.2019121201 以上用の Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="6ee28-144">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="6ee28-145">Teams の電話バージョン 1449/1.0.94.2019110802 以上</span><span class="sxs-lookup"><span data-stu-id="6ee28-145">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="6ee28-146">Teams Rooms バージョン 4.4.25.0 以上</span><span class="sxs-lookup"><span data-stu-id="6ee28-146">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="6ee28-147">セキュリティ デスク通知を含む動的緊急通話は、Teams Web クライアントではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6ee28-147">Dynamic emergency calling including security desk notification isn't supported on the Teams web client.</span></span> <span data-ttu-id="6ee28-148">ユーザーが Teams Web クライアントを使用して PSTN 番号を呼び出すのを防ぐために、Teams 通話ポリシーを設定し、[Web PSTN 通話を許可する] **設定をオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="6ee28-148">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="6ee28-149">詳細については [、「Teams](teams-calling-policy.md) および [Set-CsTeamsCallingPolicy の通話ポリシー」を参照してください](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-149">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="6ee28-150">緊急対応の住所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="6ee28-150">Assign emergency addresses</span></span>

<span data-ttu-id="6ee28-151">通話プランのユーザーと、場所を動的に取得するために必要なネットワーク識別子の両方に緊急対応の住所を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-151">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="6ee28-152">(サブネットと WiFi AP はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ee28-152">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="6ee28-153">イーサネット スイッチ/ポートは、現時点では Windows 8.1 以降でサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-153">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="6ee28-154">米国内での緊急通話の自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所に関連する地域コードが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-154">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="6ee28-155">(地域コードのない緊急対応の住所は、動的な場所に必要なネットワーク識別子に割り当てできません)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-155">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="6ee28-156">Azure Maps は、場所ベースのサービスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-156">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="6ee28-157">Microsoft Teams 管理センターを使用して緊急対応の住所を入力すると、Teams は Azure Maps で住所を確認します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-157">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="6ee28-158">一致が見つかると、地理コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-158">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="6ee28-159">一致が見つからない場合は、緊急対応の住所を手動で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-159">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="6ee28-160">PIN ドロップ機能を使って、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6ee28-160">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="6ee28-161">つまり、通話プランのユーザーに割り当てのために作成された既存の緊急対応の場所が動的な場所を対象としている場合、地域コードを含めるには、同じ住所を再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-161">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="6ee28-162">2 つの場所を区別するには、別の説明を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-162">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="6ee28-163">新しい緊急対応の場所は、古い場所を持つユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-163">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="6ee28-164">完全に移行すると、古い場所を削除できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-164">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="6ee28-165">Microsoft Teams 管理センターで緊急対応の住所を追加して割り当てるには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-165">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="6ee28-166">詳細については、「組織の緊急対応の場所を追加 [する」](add-change-remove-emergency-location-organization.md) および「ユーザーに緊急対応の場所を割り当てる [」を参照してください](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-166">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="6ee28-167">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-167">Configure network settings</span></span>

<span data-ttu-id="6ee28-168">ネットワーク設定は、Teams クライアントの場所を決定し、緊急通話ポリシーと緊急対応の場所を動的に取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-168">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="6ee28-169">組織が緊急通話の機能を求める方法に応じて、ネットワーク設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-169">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="6ee28-170">ネットワーク設定には、サブネットのコレクションを含むサイトが含まれます。これらはユーザーへの動的ポリシー割り当て専用に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-170">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="6ee28-171">たとえば、緊急通話ポリシーと緊急通話ルーティング ポリシーを "レドモンド サイト" に割り当てると、自宅または別の Microsoft の場所からローミングするユーザーが、レドモンド固有の緊急電話番号、ルーティング、セキュリティ デスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-171">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="6ee28-172">また、サブネットは LIS で定義し、緊急対応の場所に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-172">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="6ee28-173">次の定義を念頭に置きます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-173">Keep the following definitions in mind.</span></span> <span data-ttu-id="6ee28-174">詳細については、「クラウド音声機能 [のネットワーク設定」を参照してください](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-174">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="6ee28-175">信頼済み IP アドレスには、エンタープライズ ネットワークのインターネット外部 IP アドレスのコレクションが含まれているので、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-175">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="6ee28-176">動的ポリシーまたは場所の取得は、ユーザーの外部 IP アドレスが信頼済み IP アドレスの IP アドレスと一致する場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="6ee28-176">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="6ee28-177">一致は IPv4 または IPv6 IP アドレスに対して行い、ネットワーク設定に送信される IP パケットの形式に依存します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-177">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="6ee28-178">(パブリック IP アドレスに IPv4 と IPv6 の両方がある場合は、両方を信頼済み IP アドレスとして追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-178">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="6ee28-179">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-179">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="6ee28-180">ネットワーク サイトは、オフィス、建物のセット、キャンパスなど、組織が物理的な価値を持つ場所を表します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-180">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="6ee28-181">これらのサイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-181">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="6ee28-182">ネットワーク サブネットは、特定のネットワーク サイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-182">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="6ee28-183">クライアントの場所は、ネットワーク サブネットと関連するネットワーク サイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-183">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="6ee28-184">Microsoft Teams 管理センターで、または PowerShell を使用してネットワーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-184">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="6ee28-185">詳細については、「クラウド音声 [機能のネットワーク トポロジを管理する」を参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-185">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="6ee28-186">ネットワーク設定の変更 (新しいアドレス、ネットワーク識別子など) が反映され、Teams クライアントで使用可能になるには、時間がかかることがあります (最大で数時間)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-186">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="6ee28-187">**通話プランのユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="6ee28-187">**For Calling Plan users:**</span></span>

- <span data-ttu-id="6ee28-188">セキュリティ デスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワーク サイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-188">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="6ee28-189">動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-189">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="6ee28-190">どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ee28-190">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="6ee28-191">**直接ルーティング ユーザーの場合:**</span><span class="sxs-lookup"><span data-stu-id="6ee28-191">**For Direct Routing users:**</span></span>

- <span data-ttu-id="6ee28-192">緊急通話の動的有効化またはセキュリティ デスク通知の動的構成が必要な場合は、信頼済み IP アドレスとネットワーク サイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-192">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="6ee28-193">動的な場所だけが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-193">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="6ee28-194">どちらも必要ない場合は、ネットワーク設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ee28-194">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="6ee28-195">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-195">Configure Location Information Service</span></span>

<span data-ttu-id="6ee28-196">Teams クライアントは、異なるネットワーク識別子に関連付けられている場所から緊急対応の住所を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-196">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="6ee28-197">サブネットとワイヤレス アクセス ポイント (WAP) の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-197">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="6ee28-198">イーサネット スイッチ/ポートは、現時点では Windows 8.1 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ee28-198">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="6ee28-199">クライアントが場所を取得するには、ネットワーク識別子 (サブネット、WAP、スイッチ、ポート) と緊急対応の場所を LIS に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-199">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="6ee28-200">これは、Microsoft Teams 管理センターまたは PowerShell を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="6ee28-200">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6ee28-201">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="6ee28-201">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6ee28-202">左側のナビゲーションで、[**場所ネットワーク**] に  >  **移動&します**。</span><span class="sxs-lookup"><span data-stu-id="6ee28-202">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="6ee28-203">追加するネットワーク識別子を表すタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ee28-203">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="6ee28-204">たとえば、[サブネット **]、[Wi-Fi アクセス ポイント]、[\*\*\*\*スイッチ]、** または [ポート] を **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="6ee28-204">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="6ee28-205">次に、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ee28-205">Then click **Add**.</span></span>
3. <span data-ttu-id="6ee28-206">フィールドに入力し、緊急対応の場所を追加して、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6ee28-206">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6ee28-207">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="6ee28-207">Using PowerShell</span></span>

<span data-ttu-id="6ee28-208">次のコマンドレットを使用して、ポート、スイッチ、サブネット、WAP を LIS に追加します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-208">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="6ee28-209">[取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="6ee28-209">[Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="6ee28-210">[取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelisport?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="6ee28-210">[Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="6ee28-211">[取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)[削除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps)-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="6ee28-211">[Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="6ee28-212">[取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定、](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)[削除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="6ee28-212">[Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="6ee28-213">サブネットがネットワーク サイトの一部として使用されている場合、動的な場所を表示するには、Location Information Service でサブネットを再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-213">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="6ee28-214">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6ee28-214">Configure emergency policies</span></span>

<span data-ttu-id="6ee28-215">次のポリシーを使用して、緊急通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-215">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="6ee28-216">これらのポリシーは、Microsoft Teams 管理センターまたは PowerShell を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-216">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="6ee28-217">**緊急通話ルーティング ポリシー** – ダイレクト ルーティングにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-217">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="6ee28-218">このポリシーは、緊急電話番号、必要に応じて番号ごとのマスク、番号ごとの PSTN ルートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-218">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="6ee28-219">このポリシーは、ユーザー、ネットワーク サイト、または両方に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-219">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="6ee28-220">(通話プラン Teams クライアントは、Microsoft 365 または Office 365 の使用場所に基づいて、国からの緊急電話番号での緊急通話に対して自動的に有効になります)。 詳細については、「ダイレクト ルーティングの [緊急通話ルーティング ポリシーを管理する」を参照してください](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-220">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="6ee28-221">**緊急通話ポリシー** - 通話プランとダイレクト ルーティングに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-221">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="6ee28-222">このポリシーは、緊急通話が行われた場合のセキュリティ デスク通知エクスペリエンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-222">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="6ee28-223">通知するユーザーと通知方法を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-223">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="6ee28-224">たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通話を聞く場合などです。</span><span class="sxs-lookup"><span data-stu-id="6ee28-224">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="6ee28-225">このポリシーは、ユーザーまたはネットワーク サイト、または両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-225">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="6ee28-226">詳細については、「Teams で緊急 [通話ポリシーを管理する」を参照してください](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-226">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="6ee28-227">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="6ee28-227">Enable users and sites</span></span>

<span data-ttu-id="6ee28-228">緊急通話ルーティング ポリシーと緊急通話ポリシーをユーザーとサイトに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-228">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="6ee28-229">緊急通話ルーティング ポリシーは、ダイレクト ルーティングにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-229">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="6ee28-230">(このポリシーを通話プラン ユーザーに割り当て可能ですが、ポリシーは影響しません)。</span><span class="sxs-lookup"><span data-stu-id="6ee28-230">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="6ee28-231">Microsoft Teams 管理センターで、または PowerShell を使用してポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6ee28-231">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="6ee28-232">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ee28-232">To learn more, see:</span></span>

- [<span data-ttu-id="6ee28-233">ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-233">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="6ee28-234">Teams で緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-234">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="6ee28-235">PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-235">Here's some PowerShell examples.</span></span>

<span data-ttu-id="6ee28-236">特定のユーザーにセキュリティ デスク通知を有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-236">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="6ee28-237">"Contoso 緊急通話ポリシー 1" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-237">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="6ee28-238">特定のダイレクト ルーティング ユーザーによる緊急通話を有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-238">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="6ee28-239">"Contoso New York 緊急通話ルーティング" というポリシーをサイト 1 に割り当てるには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee28-239">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="6ee28-240">ネットワーク サイトとユーザーに緊急通話ポリシーを割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="6ee28-240">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="6ee28-241">緊急通話をテストする</span><span class="sxs-lookup"><span data-stu-id="6ee28-241">Test emergency calling</span></span>

<span data-ttu-id="6ee28-242">米国の一部の緊急ルーティング サービス プロバイダー (ERSP) は、緊急通話テスト ボットを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6ee28-242">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="6ee28-243">**米国の通話プラン ユーザー** は、事前に定義されたテスト緊急電話番号 933 を使用して、緊急通話の構成を検証できます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-243">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="6ee28-244">この番号はボットにルーティングされ、発信者番号 (通話回線 ID)、緊急対応の住所または場所、通話が自動的に PSAP にルーティングされるかどうか、または最初に表示されるかどうかがエコーされます。</span><span class="sxs-lookup"><span data-stu-id="6ee28-244">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="6ee28-245">**米国のダイレクト ルーティングのお客様は、** テスト サービスのために ERSP と調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ee28-245">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

## <a name="government-support"></a><span data-ttu-id="6ee28-246">政府機関のサポート</span><span class="sxs-lookup"><span data-stu-id="6ee28-246">Government support</span></span>

<span data-ttu-id="6ee28-247">次の表は、政府クラウドでの動的緊急通話のサポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="6ee28-247">The following table shows support for dynamic emergency calling in the government clouds:</span></span>

| <span data-ttu-id="6ee28-248">クラウド</span><span class="sxs-lookup"><span data-stu-id="6ee28-248">Cloud</span></span> | <span data-ttu-id="6ee28-249">使用するための条件</span><span class="sxs-lookup"><span data-stu-id="6ee28-249">Availability</span></span> |
| :------------|:-------|
| <span data-ttu-id="6ee28-250">World Wide Multi Tenant</span><span class="sxs-lookup"><span data-stu-id="6ee28-250">World Wide Multi Tenant</span></span> | <span data-ttu-id="6ee28-251">すべての Teams クライアントで利用可能</span><span class="sxs-lookup"><span data-stu-id="6ee28-251">Available on all Teams clients</span></span> |
| <span data-ttu-id="6ee28-252">GCC</span><span class="sxs-lookup"><span data-stu-id="6ee28-252">GCC</span></span> | <span data-ttu-id="6ee28-253">すべての Teams クライアントで利用可能</span><span class="sxs-lookup"><span data-stu-id="6ee28-253">Available on all Teams clients</span></span> |
| <span data-ttu-id="6ee28-254">GCCH</span><span class="sxs-lookup"><span data-stu-id="6ee28-254">GCCH</span></span> | <span data-ttu-id="6ee28-255">Teams デスクトップで利用可能</span><span class="sxs-lookup"><span data-stu-id="6ee28-255">Available on Teams desktop</span></span> |
| <span data-ttu-id="6ee28-256">DoD</span><span class="sxs-lookup"><span data-stu-id="6ee28-256">DoD</span></span> | <span data-ttu-id="6ee28-257">Pending</span><span class="sxs-lookup"><span data-stu-id="6ee28-257">Pending</span></span> |

 ## <a name="related-topics"></a><span data-ttu-id="6ee28-258">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ee28-258">Related topics</span></span>

- [<span data-ttu-id="6ee28-259">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-259">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6ee28-260">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-260">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="6ee28-261">緊急通話ルーティング ポリシーを管理する </span><span class="sxs-lookup"><span data-stu-id="6ee28-261">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="6ee28-262">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="6ee28-262">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="6ee28-263">ユーザーの緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="6ee28-263">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="6ee28-264">クラウド ボイス機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="6ee28-264">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="6ee28-265">クラウド ボイス機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="6ee28-265">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)