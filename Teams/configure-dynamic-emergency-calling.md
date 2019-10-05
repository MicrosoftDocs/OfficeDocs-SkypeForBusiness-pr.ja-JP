---
title: 動的な緊急通話を設定する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 動的な緊急通話を設定する
appliesto:
- Microsoft Teams
ms.openlocfilehash: 006f131183fe75b8246f0d2fa2d0ae28575e9e1d
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396522"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="6b513-103">プランを呼び出す動的な緊急通話の計画と構成</span><span class="sxs-lookup"><span data-stu-id="6b513-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="6b513-104">Microsoft 通話プランの動的な緊急通話には、Teams クライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6b513-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="6b513-105">適切な公開安全性の応答ポイント (PSAP) に自動的にルーティングするか、またはセキュリティデスクの担当者に通知する機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6b513-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="6b513-106">動的な緊急通話は、現在、米国でのみご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="6b513-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="6b513-107">ただし、セキュリティデスクの通知は、国の境界を超えてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b513-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="6b513-108">**米国内**では、次のように動的な緊急通話のルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6b513-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="6b513-109">チームクライアントがテナントで定義された動的な緊急対応の場所にある場合、そのクライアントからの緊急通話は、その地理的な場所を提供する PSAP に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="6b513-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="6b513-110">チームクライアントがテナントで定義された動的な緊急対応の場所に配置されていない場合、そのクライアントからの緊急通報は、その地理的な場所を提供する PSAP に通話を転送する前に、発信者の場所を特定するために、国のコールセンターによって選別されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="6b513-111">セキュリティデスクの通知は次の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="6b513-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="6b513-112">チームクライアントがテナント定義のネットワークサイトに配置されている場合は、そのサイトに対して構成されたセキュリティグループメンバーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="6b513-113">チームクライアントがテナント定義のネットワークサイトに配置されていない場合は、ユーザーに対して構成されたセキュリティグループメンバーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="6b513-114">**米国外**では、緊急通話は、ユーザーに割り当てられている電話番号にマップされている psap にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="6b513-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="6b513-115">英国やカナダなどの一部の国では、発信者が適切な PSAP に転送される前に、呼び出し元が国内されます。他の国は、ユーザーが現在所在している場所に関係なく、直接 PSAP にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6b513-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="6b513-116">ただし、すべての通話プランのユーザーに対して、動的セキュリティデスクの通知を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6b513-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="6b513-117">サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="6b513-117">Supported clients</span></span>

<span data-ttu-id="6b513-118">現在、次のクライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b513-118">The following clients are currently supported.</span></span>  <span data-ttu-id="6b513-119">このリストの更新を確認するには、もう一度チェックインします。</span><span class="sxs-lookup"><span data-stu-id="6b513-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="6b513-120">Windows 用 Teams デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6b513-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="6b513-121">Mac 用の Teams のデスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="6b513-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="6b513-122">動的な緊急通話を設定する</span><span class="sxs-lookup"><span data-stu-id="6b513-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="6b513-123">動的な緊急通話を構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="6b513-124">緊急対応の住所を設定する</span><span class="sxs-lookup"><span data-stu-id="6b513-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="6b513-125">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="6b513-126">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="6b513-127">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="6b513-128">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="6b513-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="6b513-129">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="6b513-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="6b513-130">緊急対応の住所を設定する</span><span class="sxs-lookup"><span data-stu-id="6b513-130">Configure emergency addresses</span></span>

<span data-ttu-id="6b513-131">米国内での自動ルーティングをサポートするには、ネットワーク識別子に割り当てられている緊急対応の場所の一部であり、関連付けられた geo コードが含まれている都市の住所を完全に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="6b513-132">(Geo コードのない緊急対応の住所を、動的な場所に必要なネットワーク識別子に割り当てることはできません。)</span><span class="sxs-lookup"><span data-stu-id="6b513-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="6b513-133">Microsoft Teams 管理センターを使用して緊急対応の住所を入力した場合、一致するものが見つかると、geo コードが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b513-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="6b513-134">一致が自動的に見つからない場合は、緊急対応の住所を手動で作成する機会があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="6b513-135">つまり、既存の緊急対応の住所が緊急通報用に構成されている場合は、その住所を再作成して geo コードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="6b513-136">2つのアドレスを区別するには、別の説明を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="6b513-137">新しい緊急対応の住所は、古い住所を使用しているユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6b513-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="6b513-138">完全に移行された場合は、古いアドレスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6b513-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="6b513-139">緊急対応の住所の設定の詳細については、「緊急対応の[場所、場所、通話ルーティングとは](what-are-emergency-locations-addresses-and-call-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b513-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="6b513-140">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-140">Configure network settings</span></span>

<span data-ttu-id="6b513-141">緊急通話のルーティングに使用する緊急対応の場所を動的に取得するようにネットワーク設定を構成する必要があります。また、必要に応じて、セキュリティデスク通知の動的構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b513-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="6b513-142">緊急通話のエクスペリエンスでは、どのネットワーク設定を構成する必要があるかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="6b513-143">次の定義を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="6b513-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="6b513-144">信頼できる IP には、企業ネットワークのインターネット外部 Ip のコレクションが含まれており、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="6b513-145">動的な場所は、ユーザーの外部 IP が信頼された IP コレクション内の IP と一致した場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="6b513-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="6b513-146">一致は、IPv4 または IPv6 の IP アドレスに対して行うことができます。また、ネットワーク設定に送信される IP パケットの形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6b513-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="6b513-147">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b513-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="6b513-148">ネットワークサイトは、オフィス、建物のセット、キャンパスなど、組織の物理的な値が含まれている場所を表します。</span><span class="sxs-lookup"><span data-stu-id="6b513-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="6b513-149">これらのサイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="6b513-150">ネットワークサブネットは、特定のネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="6b513-151">クライアントの場所は、ネットワークサブネットと関連付けられたネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="6b513-152">通話プランユーザーの場合:</span><span class="sxs-lookup"><span data-stu-id="6b513-152">For Calling Plan users:</span></span>

- <span data-ttu-id="6b513-153">セキュリティデスク通知の動的構成が必要な場合は、信頼できる IP アドレスとネットワークサイトの両方を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="6b513-154">動的な場所のみが必要な場合は、信頼できる IP アドレスのみを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="6b513-155">どちらも必要ない場合は、ネットワーク設定の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6b513-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="6b513-156">詳細については、「[場所に基づくルーティングのネットワーク設定を構成](location-based-routing-configure-network-settings.md)する」を参照してください。これは、ネットワーク設定の構成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b513-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="6b513-157">(この記事の情報は、通話プランとダイレクトルーティングの両方に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="6b513-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="6b513-158">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-158">Configure Location Information Service</span></span>

<span data-ttu-id="6b513-159">チームクライアントは、さまざまなネットワーク識別子に関連付けられた緊急対応の場所から緊急対応の住所を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b513-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="6b513-160">サブネットとワイヤレスアクセスポイントはどちらもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b513-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="6b513-161">(イーサネットスイッチ/ポートのサポートは保留中です)。</span><span class="sxs-lookup"><span data-stu-id="6b513-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="6b513-162">ネットワーク識別子と緊急対応の場所を使用して位置情報サービス (LIS) を構成するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b513-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="6b513-163">取得、設定、削除-Csonlinのスポーツ</span><span class="sxs-lookup"><span data-stu-id="6b513-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="6b513-164">取得、設定、削除-Csonlinの切り替え</span><span class="sxs-lookup"><span data-stu-id="6b513-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="6b513-165">Get、Set、Remove-Csonlinのサブネット</span><span class="sxs-lookup"><span data-stu-id="6b513-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="6b513-166">Get、Set、Remove-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="6b513-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="6b513-167">サブネットがネットワークサイトの一部として使われている場合は、動的な場所を表示するために、場所情報サービスでサブネットを再定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="6b513-168">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6b513-168">Configure emergency policies</span></span>

<span data-ttu-id="6b513-169">緊急ポリシーは、組織内のユーザーが緊急通話を発信したときの動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b513-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="6b513-170">ユーザーが緊急電話サービスを呼び出したときの通知方法と通知方法を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6b513-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="6b513-171">たとえば、ポリシー設定を構成して、組織のセキュリティデスクに自動的に通知され、緊急電話をリッスンしていることを知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="6b513-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="6b513-172">緊急ポリシーを管理するには、新しい-、CsTeamsEmergencyCalling の各ポリシーコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b513-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="6b513-173">詳細については、「 [Teams の緊急通話ポリシーを管理](manage-emergency-calling-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b513-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="6b513-174">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="6b513-174">Enable users and sites</span></span>

<span data-ttu-id="6b513-175">電話プランを利用しているユーザーは緊急通話に対して自動的に有効になりますが、次の例のように緊急通話ポリシーを構成することによって、セキュリティデスクの通知をユーザーに有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b513-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="6b513-176">次の例に示すように、緊急通話ポリシーをネットワークサイトに割り当てることもできます。これは、"Contoso 緊急通話ポリシー 1" と呼ばれるポリシーをサイト1に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b513-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="6b513-177">緊急通話のポリシーをネットワークサイトとユーザーに割り当て、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6b513-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="6b513-178">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="6b513-178">Test emergency calling</span></span>

<span data-ttu-id="6b513-179">米国で緊急通話をテストするには、事前に定義されたテスト緊急電話番号933を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b513-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="6b513-180">この番号はボットにルーティングされます。これにより、発信者番号 (発信者の電話番号)、緊急対応の住所、場所、通話が自動的に PSAP または表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b513-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  