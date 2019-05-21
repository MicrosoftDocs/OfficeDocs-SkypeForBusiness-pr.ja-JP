---
title: 複数のテナントにセッション ボーダー コントローラーを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 1つのセッション境界コントローラー (SBC) を複数のテナントに対応するように構成する方法について説明します。
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290470"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="0171e-103">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="0171e-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="0171e-104">ダイレクトルーティングでは、1つのセッション境界コントローラー (SBC) で複数のテナントに対応するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0171e-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="0171e-105">このシナリオは、このドキュメントで後述する「配送業者」と呼ばれる Microsoft パートナーや PSTN キャリア向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="0171e-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="0171e-106">通信事業者は、Microsoft Teams に配信されたテレフォニーサービスを顧客に販売します。</span><span class="sxs-lookup"><span data-stu-id="0171e-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="0171e-107">電話会社:</span><span class="sxs-lookup"><span data-stu-id="0171e-107">A carrier:</span></span>
- <span data-ttu-id="0171e-108">データセンターで SBC を展開して管理します (顧客は SBC を実装する必要はありません。また、ユーザーは、チームクライアントの電話会社からテレフォニーサービスを受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="0171e-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="0171e-109">SBC と複数のテナントを相互接続します。</span><span class="sxs-lookup"><span data-stu-id="0171e-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="0171e-110">ユーザーに PSTN サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0171e-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="0171e-111">通話品質の終了を管理します。</span><span class="sxs-lookup"><span data-stu-id="0171e-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="0171e-112">PSTN サービスに対して別途料金がかかります。</span><span class="sxs-lookup"><span data-stu-id="0171e-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="0171e-113">Microsoft は、配送業者を管理しません。</span><span class="sxs-lookup"><span data-stu-id="0171e-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="0171e-114">Microsoft は、PBX (Microsoft 電話システム) とチームクライアント、電話の認定、および Microsoft 電話システムで使用できる SBCs の認定を提供しています。</span><span class="sxs-lookup"><span data-stu-id="0171e-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="0171e-115">キャリアを選択する前に、お客様の選択内容が認定された SBC であり、音声品質のエンドツーエンドを管理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="0171e-116">次に、シナリオを構成するための技術的な実装手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0171e-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="0171e-117">**電話会社のみ:**</span><span class="sxs-lookup"><span data-stu-id="0171e-117">**Carrier only:**</span></span>
1. <span data-ttu-id="0171e-118">認定された[sbc ベンダーからの指示](#deploy-and-configure-the-sbc)に従って、sbc を展開してホスティングシナリオ用に構成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="0171e-119">キャリアテナントにベースドメイン名を登録して、ワイルドカード証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="0171e-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="0171e-120">ベースドメインの一部であるすべてのユーザーに対してサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="0171e-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="0171e-121">**顧客のグローバル管理者がいる電話会社:**</span><span class="sxs-lookup"><span data-stu-id="0171e-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="0171e-122">顧客テナントにサブドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="0171e-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="0171e-123">サブドメイン名を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0171e-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="0171e-124">電話会社から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="0171e-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="0171e-125">*DNS の基礎と、Office 365 でのドメイン名の管理について理解していることを確認してください。先に進む前に[、「Office 365 ドメインに関するヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0171e-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="0171e-126">SBC の展開と構成</span><span class="sxs-lookup"><span data-stu-id="0171e-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="0171e-127">SBC ホスティングシナリオでの SBCs の展開と構成の詳細な手順については、SBC ベンダーのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="0171e-128">**Audiocodes:**[ダイレクトルーティング構成のメモ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)「AUDIOCODES の Sbc から Microsoft Teams へのダイレクトルーティングホスティングモデル構成のメモ」で説明されているように、sbc ホスティングシナリオの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="0171e-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="0171e-129">**リボンの通信:** リボンについては、「リボンの主要なシリーズの[概要」](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)および「このページのリボンを構成する」を参照してください。[ベストプラクティス-Microsoft Teams のダイレクトルーティング (sbc) 向けの通信事業を構成するEdge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="0171e-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="0171e-130">「コンタクト」ヘッダーの設定方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="0171e-131">連絡先ヘッダーは、着信招待メッセージで顧客テナントを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0171e-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="0171e-132">ベースドメインとサブドメインを登録する</span><span class="sxs-lookup"><span data-stu-id="0171e-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="0171e-133">ホスティングシナリオでは、次のものを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="0171e-134">通信事業者によって所有される1つのベースドメイン名。</span><span class="sxs-lookup"><span data-stu-id="0171e-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="0171e-135">すべての顧客テナントのベースドメイン名の一部であるサブドメイン。</span><span class="sxs-lookup"><span data-stu-id="0171e-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="0171e-136">次の例では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0171e-136">In the following example:</span></span>
- <span data-ttu-id="0171e-137">Adatum は、インターネットとテレフォニーサービスを提供することによって、複数の顧客に提供する電話会社です。</span><span class="sxs-lookup"><span data-stu-id="0171e-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="0171e-138">Woodgrove Bank、Contoso、Adventure Works は、Office 365 ドメインを所有しているが、Adatum からテレフォニーサービスを受け取る3人のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0171e-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="0171e-139">サブドメインは、ユーザーに対して構成されるトランクの FQDN 名と、招待状を Office 365 に送信するときに連絡先ヘッダー内の FQDN に一致させる**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="0171e-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="0171e-140">電話が Office 365 ダイレクトルーティングインターフェイスに到着すると、インターフェイスは連絡先ヘッダーを使って、ユーザーを検索する必要があるテナントを見つけます。</span><span class="sxs-lookup"><span data-stu-id="0171e-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="0171e-141">直接ルーティングでは、ユーザーによっては、複数のテナントで重複する可能性のある電話番号がない可能性があるため、招待で電話番号の参照は使用されません。</span><span class="sxs-lookup"><span data-stu-id="0171e-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="0171e-142">そのため、連絡先ヘッダーの FQDN 名は、電話番号によってユーザーを検索する正確なテナントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="0171e-143">*Office 365 テナントでのドメイン名の作成について詳しくは、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0171e-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="0171e-144">次の図は、ベースドメイン、サブドメイン、連絡先ヘッダーの要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="0171e-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![ベースドメイン、サブドメイン、連絡先ヘッダーの要件](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="0171e-146">SBC は、接続を認証するために証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0171e-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="0171e-147">SBC ホスティングシナリオでは、通信事業者は\* \*base_domain (customers.adatum.biz \*など)\* で証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="0171e-148">この証明書を使って、1つの SBC から提供されている複数のテナントへの接続を認証することができます。</span><span class="sxs-lookup"><span data-stu-id="0171e-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="0171e-149">次の表は、1つの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="0171e-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="0171e-150">新しいドメイン名</span><span class="sxs-lookup"><span data-stu-id="0171e-150">New domain name</span></span> |<span data-ttu-id="0171e-151">型</span><span class="sxs-lookup"><span data-stu-id="0171e-151">Type</span></span>|<span data-ttu-id="0171e-152">登録</span><span class="sxs-lookup"><span data-stu-id="0171e-152">Registered</span></span>  |<span data-ttu-id="0171e-153">SBC 用証明書 SAN</span><span class="sxs-lookup"><span data-stu-id="0171e-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="0171e-154">テナントの既定のドメインの例</span><span class="sxs-lookup"><span data-stu-id="0171e-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="0171e-155">ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに提示する必要がある FQDN 名</span><span class="sxs-lookup"><span data-stu-id="0171e-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="0171e-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-156">customers.adatum.biz</span></span>|    <span data-ttu-id="0171e-157">技術</span><span class="sxs-lookup"><span data-stu-id="0171e-157">Base</span></span>     |     <span data-ttu-id="0171e-158">運送業者のテナント</span><span class="sxs-lookup"><span data-stu-id="0171e-158">In carrier tenant</span></span>  |    <span data-ttu-id="0171e-159">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="0171e-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-160">adatum.biz</span></span>      |<span data-ttu-id="0171e-161">NA、これはサービステナントであり、ユーザーは存在しません</span><span class="sxs-lookup"><span data-stu-id="0171e-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="0171e-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="0171e-163">プロトコル</span><span class="sxs-lookup"><span data-stu-id="0171e-163">Subdomain</span></span>  |    <span data-ttu-id="0171e-164">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="0171e-164">In a customer tenant</span></span>  |    <span data-ttu-id="0171e-165">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="0171e-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="0171e-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="0171e-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="0171e-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="0171e-169">プロトコル</span><span class="sxs-lookup"><span data-stu-id="0171e-169">Subdomain</span></span> | <span data-ttu-id="0171e-170">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="0171e-170">In a customer tenant</span></span>   |   <span data-ttu-id="0171e-171">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="0171e-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0171e-172">contoso.com</span></span>   |<span data-ttu-id="0171e-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="0171e-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="0171e-175">プロトコル</span><span class="sxs-lookup"><span data-stu-id="0171e-175">Subdomain</span></span> | <span data-ttu-id="0171e-176">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="0171e-176">In a customer tenant</span></span> |   <span data-ttu-id="0171e-177">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="0171e-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="0171e-178">adventureworks.com</span></span> | <span data-ttu-id="0171e-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="0171e-180">基本とサブドメインを構成するには、次に説明する手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="0171e-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="0171e-181">この例では、1つの顧客のベースドメイン名 (customers.adatum.biz) とサブドメイン (Woodgrove Bank テナントの sbc1.customers.adatum.biz) を構成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="0171e-182">会社のテナントにベースドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="0171e-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="0171e-183">**これらの操作は、キャリアテナントで実行されます。**</span><span class="sxs-lookup"><span data-stu-id="0171e-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="0171e-184">電話会社のテナントで適切な権利を持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="0171e-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="0171e-185">新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="0171e-186">所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0171e-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="0171e-187">管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="0171e-188">ベースドメインをテナントに追加して確認する</span><span class="sxs-lookup"><span data-stu-id="0171e-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="0171e-189">Microsoft 365 管理センターで、[**セットアップ** > \*\*\*\* > ドメインの**追加**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0171e-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="0171e-190">[**自分が所有しているドメインを入力して**ください] ボックスに、ベースドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="0171e-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="0171e-191">次の例では、ベースドメインは*customers.adatum.biz*です。</span><span class="sxs-lookup"><span data-stu-id="0171e-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![ベースドメインを追加する](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="0171e-193">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-193">Click **Next**.</span></span>
4. <span data-ttu-id="0171e-194">この例では、テナントは既に確認済みドメイン名として adatum.biz されています。</span><span class="sxs-lookup"><span data-stu-id="0171e-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="0171e-195">Customers.adatum.biz は既に登録されている名前のサブドメインであるため、追加の確認を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="0171e-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="0171e-196">ただし、以前に確認されていない FQDN を追加する場合は、確認プロセスを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="0171e-197">確認プロセスについては、[以下で説明](#add-a-subdomain-to-the-customer-tenant-and-verify-it)します。</span><span class="sxs-lookup"><span data-stu-id="0171e-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![確認済みドメイン名の確認](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="0171e-199">[**次へ**] をクリックし、[ **Dns 設定の更新**] ページで [**自分で dns レコードを追加する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="0171e-200">次のページで、すべての値を削除します (Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用する場合を除く)、[**次へ**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="0171e-201">新しいドメインがセットアップの完了状態になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0171e-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![セットアップ完了の状態を示すドメイン](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="0171e-203">ドメイン名を有効にする</span><span class="sxs-lookup"><span data-stu-id="0171e-203">Activate the domain name</span></span>

<span data-ttu-id="0171e-204">ドメイン名を登録したら、少なくとも1つの E1、E3、または E5 のライセンスを持つユーザーを追加し、作成されたベースドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てることによって、そのドメイン名をアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="0171e-205">*Office 365 テナントでのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0171e-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="0171e-206">例: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-206">For example: test@customers.adatum.biz</span></span>

![ベースドメインのライセンス認証ページ](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="0171e-208">顧客テナントにサブドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="0171e-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="0171e-209">すべてのユーザーに対して一意のサブドメイン名を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="0171e-210">この例では、既定のドメイン名 woodgrovebank.us を使用して、テナントにサブドメイン sbc1.customers.adatum.biz を作成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="0171e-211">**以下のすべてのアクションが顧客のテナントにあります。**</span><span class="sxs-lookup"><span data-stu-id="0171e-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="0171e-212">お客様のテナントに適切な権限があることを確認する</span><span class="sxs-lookup"><span data-stu-id="0171e-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="0171e-213">新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="0171e-214">所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0171e-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="0171e-215">管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="0171e-216">サブドメインを顧客テナントに追加して確認する</span><span class="sxs-lookup"><span data-stu-id="0171e-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="0171e-217">Microsoft 365 管理センターで、[**セットアップ** > \*\*\*\* > ドメインの**追加**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0171e-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="0171e-218">[**自分が所有しているドメインを入力してください**] ボックスに、このテナントのサブドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="0171e-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="0171e-219">次の例では、サブドメインは sbc1.customers.adatum.biz です。</span><span class="sxs-lookup"><span data-stu-id="0171e-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![顧客のサブドメインを追加する](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="0171e-221">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-221">Click **Next**.</span></span>
4. <span data-ttu-id="0171e-222">FQDN がテナントに登録されていない。</span><span class="sxs-lookup"><span data-stu-id="0171e-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="0171e-223">次の手順では、ドメインを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="0171e-224">[**代わりに TXT レコードを追加する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0171e-224">Select **Add a TXT record instead**.</span></span> 

    ![[ドメインの確認] ページのオプション](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="0171e-226">[**次へ**] をクリックして、ドメイン名を確認するために生成された TXT 値を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="0171e-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[ドメインの確認] ページのテキストレコード](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="0171e-228">キャリアの DNS ホスティングプロバイダーで、前の手順の値を使用して TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![キャリアの DNS ホスティングプロバイダーでの TXT レコードの作成](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="0171e-230">詳細については、「 [Office 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="0171e-231">顧客の Microsoft 365 管理センターに戻り、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="0171e-232">次のページで、[**自分で DNS レコードを追加**します] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![[DNS 設定の更新] ページのオプション](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="0171e-234">[**オンラインサービスの選択**] ページで、すべてのオプションをオフにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![[オンラインサービスの選択] ページ](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="0171e-236">[ **DNS 設定の更新**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0171e-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![[DNS 設定の更新] ページ](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="0171e-238">ステータスが [**セットアップ完了完了**しています。</span><span class="sxs-lookup"><span data-stu-id="0171e-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![セットアップ完了の状態を示すページ](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="0171e-240">サブドメイン名を有効にする</span><span class="sxs-lookup"><span data-stu-id="0171e-240">Activate the subdomain name</span></span>

<span data-ttu-id="0171e-241">ドメイン名を登録したら、少なくとも1人のユーザーを追加して、sip アドレスの FQDN 部分を使用して、顧客テナント内で作成されたサブドメインと一致する SIP アドレスを割り当てることで、ライセンス認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="0171e-242">*Office 365 テナントでのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="0171e-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="0171e-243">例: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="0171e-243">For example: test@sbc1.customers.adatum.biz</span></span>

![[サブドメイン] ページのアクティブ化](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="0171e-245">トランクを作成してユーザーをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="0171e-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="0171e-246">技術採用プログラムで受け取ったフィードバックに基づき、Microsoft は顧客テナントでの trunks の作成プロセスを変更して、プロセスを簡素化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0171e-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="0171e-247">詳細については、このページに記載されているドキュメントの更新内容を確認して、Microsoft テクニカルコミュニティのブログをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0171e-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="0171e-248">新しい-CSonlinePSTNGateway コマンドを使用して、顧客のドメインでトランクを作成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="0171e-249">トランク FQDN は、顧客用に作成されたサブドメインと一致**する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="0171e-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="0171e-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0171e-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="0171e-251">トランクの作成時に、次のエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0171e-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="0171e-252">ドメイン登録とライセンス認証が複製されるまでしばらくお待ちください。もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="0171e-253">電話番号を使ってユーザーをプロビジョニングし、音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="0171e-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="0171e-254">CSOnlinePSTNGateway、ユーザーのプロビジョニング、および音声ルーティングの構成の詳細については、「[直接ルーティングを構成](direct-routing-configure.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="0171e-255">連絡先ヘッダーでサブドメインの FQDN 名の送信を構成する方法については、「 [SBC ベンダーの手順](#deploy-and-configure-the-sbc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0171e-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

