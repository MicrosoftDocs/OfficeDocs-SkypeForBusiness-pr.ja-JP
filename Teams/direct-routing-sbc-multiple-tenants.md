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
ms.openlocfilehash: 33f9c00734ed9e5724c18eb57ceb361bd28df695
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2019
ms.locfileid: "36254022"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="9b4ff-103">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="9b4ff-104">ダイレクトルーティングでは、1つのセッション境界コントローラー (SBC) で複数のテナントに対応するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="9b4ff-105">このシナリオは、このドキュメントで後述する「配送業者」と呼ばれる Microsoft パートナーや PSTN キャリア向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="9b4ff-106">通信事業者は、Microsoft Teams に配信されたテレフォニーサービスを顧客に販売します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="9b4ff-107">電話会社:</span><span class="sxs-lookup"><span data-stu-id="9b4ff-107">A carrier:</span></span>
- <span data-ttu-id="9b4ff-108">データセンターで SBC を展開して管理します (顧客は SBC を実装する必要はありません。また、ユーザーは、チームクライアントの電話会社からテレフォニーサービスを受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="9b4ff-109">SBC と複数のテナントを相互接続します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="9b4ff-110">ユーザーに PSTN サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="9b4ff-111">通話品質の終了を管理します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="9b4ff-112">PSTN サービスに対して別途料金がかかります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="9b4ff-113">Microsoft は、配送業者を管理しません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="9b4ff-114">Microsoft は、PBX (Microsoft 電話システム) とチームクライアント、電話の認定、および Microsoft 電話システムで使用できる SBCs の認定を提供しています。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="9b4ff-115">キャリアを選択する前に、お客様の選択内容が認定された SBC であり、音声品質のエンドツーエンドを管理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="9b4ff-116">次に、シナリオを構成するための技術的な実装手順を示します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="9b4ff-117">**電話会社のみ:**</span><span class="sxs-lookup"><span data-stu-id="9b4ff-117">**Carrier only:**</span></span>
1. <span data-ttu-id="9b4ff-118">認定された[sbc ベンダーからの指示](#deploy-and-configure-the-sbc)に従って、sbc を展開してホスティングシナリオ用に構成します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="9b4ff-119">キャリアテナントにベースドメイン名を登録して、ワイルドカード証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="9b4ff-120">ベースドメインの一部であるすべてのユーザーに対してサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="9b4ff-121">**顧客のグローバル管理者がいる電話会社:**</span><span class="sxs-lookup"><span data-stu-id="9b4ff-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="9b4ff-122">顧客テナントにサブドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="9b4ff-123">サブドメイン名を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="9b4ff-124">電話会社から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="9b4ff-125">*DNS の基礎と、Office 365 でのドメイン名の管理について理解していることを確認してください。先に進む前に[、「Office 365 ドメインに関するヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="9b4ff-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="9b4ff-126">SBC の展開と構成</span><span class="sxs-lookup"><span data-stu-id="9b4ff-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="9b4ff-127">SBC ホスティングシナリオでの SBCs の展開と構成の詳細な手順については、SBC ベンダーのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="9b4ff-128">**Audiocodes:**[ダイレクトルーティング構成のメモ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)「AUDIOCODES の Sbc から Microsoft Teams へのダイレクトルーティングホスティングモデル構成のメモ」で説明されているように、sbc ホスティングシナリオの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="9b4ff-129">**リボンの通信:** リボンについては、「リボンの主要なシリーズの[概要」](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)および「このページのリボンを構成する」を参照してください。[ベストプラクティス-Microsoft Teams のダイレクトルーティング (sbc) 向けの通信事業を構成するEdge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="9b4ff-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>
- <span data-ttu-id="9b4ff-130">**TE システム (anynode):** 複数のテナントに対して、任意のノードの SBC を構成する方法のドキュメントと例については、[ [TE システムのコミュニティ] ページ](https://community.te-systems.de/)で登録してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-130">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="9b4ff-131">「コンタクト」ヘッダーの設定方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-131">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="9b4ff-132">連絡先ヘッダーは、着信招待メッセージで顧客テナントを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-132">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="9b4ff-133">ベースドメインとサブドメインを登録する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-133">Register a base domain and subdomains</span></span>

<span data-ttu-id="9b4ff-134">ホスティングシナリオでは、次のものを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-134">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="9b4ff-135">通信事業者によって所有される1つのベースドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-135">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="9b4ff-136">すべての顧客テナントのベースドメイン名の一部であるサブドメイン。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-136">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="9b4ff-137">次の例では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-137">In the following example:</span></span>
- <span data-ttu-id="9b4ff-138">Adatum は、インターネットとテレフォニーサービスを提供することによって、複数の顧客に提供する電話会社です。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-138">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="9b4ff-139">Woodgrove Bank、Contoso、Adventure Works は、Office 365 ドメインを所有しているが、Adatum からテレフォニーサービスを受け取る3人のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-139">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="9b4ff-140">サブドメインは、ユーザーに対して構成されるトランクの FQDN 名と、招待状を Office 365 に送信するときに連絡先ヘッダー内の FQDN に一致させる**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-140">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="9b4ff-141">電話が Office 365 ダイレクトルーティングインターフェイスに到着すると、インターフェイスは連絡先ヘッダーを使って、ユーザーを検索する必要があるテナントを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-141">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="9b4ff-142">直接ルーティングでは、ユーザーによっては、複数のテナントで重複する可能性のある電話番号がない可能性があるため、招待で電話番号の参照は使用されません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-142">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="9b4ff-143">そのため、連絡先ヘッダーの FQDN 名は、電話番号によってユーザーを検索する正確なテナントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-143">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="9b4ff-144">*Office 365 テナントでのドメイン名の作成について詳しくは、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="9b4ff-144">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="9b4ff-145">次の図は、ベースドメイン、サブドメイン、連絡先ヘッダーの要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-145">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="9b4ff-147">SBC は、接続を認証するために証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-147">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="9b4ff-148">SBC ホスティングシナリオでは、通信事業者は\* \*base_domain (customers.adatum.biz \*など)\* で証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-148">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="9b4ff-149">この証明書を使って、1つの SBC から提供されている複数のテナントへの接続を認証することができます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-149">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="9b4ff-150">次の表は、1つの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-150">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="9b4ff-151">新しいドメイン名</span><span class="sxs-lookup"><span data-stu-id="9b4ff-151">New domain name</span></span> |<span data-ttu-id="9b4ff-152">型</span><span class="sxs-lookup"><span data-stu-id="9b4ff-152">Type</span></span>|<span data-ttu-id="9b4ff-153">登録</span><span class="sxs-lookup"><span data-stu-id="9b4ff-153">Registered</span></span>  |<span data-ttu-id="9b4ff-154">SBC 用証明書 SAN</span><span class="sxs-lookup"><span data-stu-id="9b4ff-154">Certificate SAN for SBC</span></span>  |<span data-ttu-id="9b4ff-155">テナントの既定のドメインの例</span><span class="sxs-lookup"><span data-stu-id="9b4ff-155">Tenant default domain in the example</span></span>  |<span data-ttu-id="9b4ff-156">ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに提示する必要がある FQDN 名</span><span class="sxs-lookup"><span data-stu-id="9b4ff-156">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="9b4ff-157">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-157">customers.adatum.biz</span></span>|    <span data-ttu-id="9b4ff-158">技術</span><span class="sxs-lookup"><span data-stu-id="9b4ff-158">Base</span></span>     |     <span data-ttu-id="9b4ff-159">運送業者のテナント</span><span class="sxs-lookup"><span data-stu-id="9b4ff-159">In carrier tenant</span></span>  |    <span data-ttu-id="9b4ff-160">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-160">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="9b4ff-161">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-161">adatum.biz</span></span>      |<span data-ttu-id="9b4ff-162">NA、これはサービステナントであり、ユーザーは存在しません</span><span class="sxs-lookup"><span data-stu-id="9b4ff-162">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="9b4ff-163">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-163">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="9b4ff-164">プロトコル</span><span class="sxs-lookup"><span data-stu-id="9b4ff-164">Subdomain</span></span>  |    <span data-ttu-id="9b4ff-165">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="9b4ff-165">In a customer tenant</span></span>  |    <span data-ttu-id="9b4ff-166">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-166">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="9b4ff-167">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="9b4ff-167">woodgrovebank.us</span></span>  |  <span data-ttu-id="9b4ff-168">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-168">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="9b4ff-169">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-169">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="9b4ff-170">プロトコル</span><span class="sxs-lookup"><span data-stu-id="9b4ff-170">Subdomain</span></span> | <span data-ttu-id="9b4ff-171">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="9b4ff-171">In a customer tenant</span></span>   |   <span data-ttu-id="9b4ff-172">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-172">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="9b4ff-173">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b4ff-173">contoso.com</span></span>   |<span data-ttu-id="9b4ff-174">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-174">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="9b4ff-175">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-175">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="9b4ff-176">プロトコル</span><span class="sxs-lookup"><span data-stu-id="9b4ff-176">Subdomain</span></span> | <span data-ttu-id="9b4ff-177">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="9b4ff-177">In a customer tenant</span></span> |   <span data-ttu-id="9b4ff-178">\*customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-178">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="9b4ff-179">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="9b4ff-179">adventureworks.com</span></span> | <span data-ttu-id="9b4ff-180">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-180">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="9b4ff-181">基本とサブドメインを構成するには、次に説明する手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-181">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="9b4ff-182">この例では、1つの顧客のベースドメイン名 (customers.adatum.biz) とサブドメイン (Woodgrove Bank テナントの sbc1.customers.adatum.biz) を構成します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-182">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="9b4ff-183">会社のテナントにベースドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-183">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="9b4ff-184">**これらの操作は、キャリアテナントで実行されます。**</span><span class="sxs-lookup"><span data-stu-id="9b4ff-184">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="9b4ff-185">電話会社のテナントで適切な権利を持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-185">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="9b4ff-186">新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-186">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="9b4ff-187">所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-187">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="9b4ff-188">管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-188">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="9b4ff-189">ベースドメインをテナントに追加して確認する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-189">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="9b4ff-190">Microsoft 365 管理センターで、[**セットアップ** > \*\*\*\* > ドメインの**追加**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-190">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="9b4ff-191">[**自分が所有しているドメインを入力して**ください] ボックスに、ベースドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-191">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="9b4ff-192">次の例では、ベースドメインは*customers.adatum.biz*です。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-192">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="9b4ff-194">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-194">Click **Next**.</span></span>
4. <span data-ttu-id="9b4ff-195">この例では、テナントは既に確認済みドメイン名として adatum.biz されています。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-195">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="9b4ff-196">Customers.adatum.biz は既に登録されている名前のサブドメインであるため、追加の確認を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-196">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="9b4ff-197">ただし、以前に確認されていない FQDN を追加する場合は、確認プロセスを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-197">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="9b4ff-198">確認プロセスについては、[以下で説明](#add-a-subdomain-to-the-customer-tenant-and-verify-it)します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-198">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![確認済みドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="9b4ff-200">[**次へ**] をクリックし、[ **Dns 設定の更新**] ページで [**自分で dns レコードを追加する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-200">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="9b4ff-201">次のページで、すべての値を削除します (Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用する場合を除く)、[**次へ**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-201">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="9b4ff-202">新しいドメインがセットアップの完了状態になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-202">Make sure your new domain is in the Setup complete status.</span></span>

    ![セットアップの状態が完了しているドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="9b4ff-204">ドメイン名を有効にする</span><span class="sxs-lookup"><span data-stu-id="9b4ff-204">Activate the domain name</span></span>

<span data-ttu-id="9b4ff-205">ドメイン名を登録したら、少なくとも1つの E1、E3、または E5 のライセンスを持つユーザーを追加し、作成されたベースドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てることによって、そのドメイン名をアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-205">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="9b4ff-206">*Office 365 テナントでのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="9b4ff-206">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="9b4ff-207">例: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-207">For example: test@customers.adatum.biz</span></span>

![[ベースドメインのアクティブ化] ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="9b4ff-209">顧客テナントにサブドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-209">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="9b4ff-210">すべてのユーザーに対して一意のサブドメイン名を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-210">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="9b4ff-211">この例では、既定のドメイン名 woodgrovebank.us を使用して、テナントにサブドメイン sbc1.customers.adatum.biz を作成します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-211">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="9b4ff-212">**以下のすべてのアクションが顧客のテナントにあります。**</span><span class="sxs-lookup"><span data-stu-id="9b4ff-212">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="9b4ff-213">お客様のテナントに適切な権限があることを確認する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-213">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="9b4ff-214">新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-214">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="9b4ff-215">所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-215">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="9b4ff-216">管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-216">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="9b4ff-217">サブドメインを顧客テナントに追加して確認する</span><span class="sxs-lookup"><span data-stu-id="9b4ff-217">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="9b4ff-218">Microsoft 365 管理センターで、[**セットアップ** > \*\*\*\* > ドメインの**追加**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-218">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="9b4ff-219">[**自分が所有しているドメインを入力してください**] ボックスに、このテナントのサブドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-219">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="9b4ff-220">次の例では、サブドメインは sbc1.customers.adatum.biz です。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-220">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="9b4ff-222">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-222">Click **Next**.</span></span>
4. <span data-ttu-id="9b4ff-223">FQDN がテナントに登録されていない。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-223">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="9b4ff-224">次の手順では、ドメインを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-224">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="9b4ff-225">[**代わりに TXT レコードを追加する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-225">Select **Add a TXT record instead**.</span></span> 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="9b4ff-227">[**次へ**] をクリックして、ドメイン名を確認するために生成された TXT 値を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-227">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[ドメインの確認] ページのテキストレコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="9b4ff-229">キャリアの DNS ホスティングプロバイダーで、前の手順の値を使用して TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-229">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="9b4ff-231">詳細については、「 [Office 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-231">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="9b4ff-232">顧客の Microsoft 365 管理センターに戻り、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-232">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="9b4ff-233">次のページで、[**自分で DNS レコードを追加**します] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-233">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![[更新 DNS の設定] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="9b4ff-235">[**オンラインサービスの選択**] ページで、すべてのオプションをオフにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-235">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![[オンラインサービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="9b4ff-237">[ **DNS 設定の更新**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-237">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="9b4ff-239">ステータスが [**セットアップ完了完了**しています。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-239">Ensure that the status is **Setup complete**.</span></span> 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="9b4ff-241">サブドメイン名を有効にする</span><span class="sxs-lookup"><span data-stu-id="9b4ff-241">Activate the subdomain name</span></span>

<span data-ttu-id="9b4ff-242">ドメイン名を登録したら、少なくとも1人のユーザーを追加して、sip アドレスの FQDN 部分を使用して、顧客テナント内で作成されたサブドメインと一致する SIP アドレスを割り当てることで、ライセンス認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-242">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="9b4ff-243">*Office 365 テナントでのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="9b4ff-243">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="9b4ff-244">例: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="9b4ff-244">For example: test@sbc1.customers.adatum.biz</span></span>

![[サブドメイン] ページのアクティブ化のスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="9b4ff-246">トランクを作成してユーザーをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="9b4ff-246">Create a trunk and provision users</span></span>

<span data-ttu-id="9b4ff-247">Microsoft は、直接ルーティングの最初のリリースで、新しい-CSOnlinePSTNGateway を使用して、提供される各テナント (顧客テナント) にトランクを追加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-247">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="9b4ff-248">ただし、これは次の2つの理由により最適とは言えません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-248">However, this has not proved optimal for two reasons:</span></span>
 
<span data-ttu-id="9b4ff-249">•**オーバーヘッド管理**。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-249">• **Overhead management**.</span></span> <span data-ttu-id="9b4ff-250">たとえば、SBC のオフロードまたはドレインは、メディアのバイパスを有効または無効にするなど、いくつかのパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-250">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="9b4ff-251">ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC になります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-251">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> <span data-ttu-id="9b4ff-252">•**オーバーヘッド処理**。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-252">• **Overhead processing**.</span></span> <span data-ttu-id="9b4ff-253">複数の論理 trunks から収集されたトランクの正常性データの収集と監視 (実際には同じ SBC と物理的なトランク) によって、ルーティングデータの処理が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-253">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 

<span data-ttu-id="9b4ff-254">このフィードバックに基づいて、Microsoft は、お客様のテナントのために trunks をプロビジョニングするための新しいロジックを導入しています。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-254">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="9b4ff-255">2つの新しいエンティティが導入されました: • CSOnlinePSTNGateway を使用してキャリアテナントに登録されているキャリアトランク。たとえば、CSOnlinePSTNGateway customers.adatum.biz-SIPSignallingport 5068-ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-255">Two new entities were introduced: •   A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignallingport 5068 -ForwardPAI $true.</span></span>
<span data-ttu-id="9b4ff-256">•登録を必要としない派生トランク。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-256">•   A derived trunk, that does not require registration.</span></span> <span data-ttu-id="9b4ff-257">これは、単に、キャリアトランクから追加された目的のホスト名です。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-257">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="9b4ff-258">これは、すべての構成パラメーターをキャリアトランクから導出します。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-258">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="9b4ff-259">派生した樹幹は、PowerShell で作成する必要はありません。また、carrier トランクとの関連付けは FQDN 名に基づいています (以下の詳細を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-259">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="9b4ff-260">プロビジョニングロジックと例。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-260">Provisioning logic and example.</span></span>

<span data-ttu-id="9b4ff-261">•航空会社は、CSOnlinePSTNGateway コマンドを使用して、1つのトランク (キャリアドメインのキャリアトランク) を設定して管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-261">•   Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="9b4ff-262">上の例では、adatum.biz が使用されています。•お客様のテナントで、キャリアでは、ユーザーのボイスルーティングポリシーに派生トランク FQDN を追加するだけでできます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-262">In the example above it is adatum.biz; •   In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="9b4ff-263">トランクの新規 CSOnlinePSTNGateway を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-263">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
<span data-ttu-id="9b4ff-264">•名前として派生トランクを指定すると、すべての構成パラメーターがキャリアトランクから継承されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-264">•    The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="9b4ff-265">例: • Customers.adatum.biz –キャリアテナントで作成する必要があるキャリアトランク。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-265">Examples: •   Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
<span data-ttu-id="9b4ff-266">• Sbc1.customers.adatum.biz –顧客テナントで、PowerShell で作成する必要がない派生トランク。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-266">•   Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="9b4ff-267">オンラインボイスルーティングポリシーの顧客テナントに派生トランクの名前を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-267">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>

<span data-ttu-id="9b4ff-268">•通信事業者のトランク (キャリアテナント) で行った変更は、派生した trunks に自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-268">•   Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="9b4ff-269">たとえば、運送業者は、電話会社のトランクの SIP ポートを変更することができます。この変更は、すべての派生 trunks に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-269">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="9b4ff-270">Trunks を構成するための新しいロジックにより、すべてのテナントに移動したり、すべてのトランクのパラメーターを変更したりする必要がないため、管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-270">New logic to configure the trunks simplifies the management as you don’t need to go to every tenant and change the parameter on every trunk.</span></span>
<span data-ttu-id="9b4ff-271">•オプションは、キャリアトランク FQDN にのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-271">•   The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="9b4ff-272">キャリアトランクの正常性状態は、すべての派生 trunks に適用され、ルーティング決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-272">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="9b4ff-273">[ダイレクトルーティングオプション](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-273">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
<span data-ttu-id="9b4ff-274">•通信事業者は、電話会社のトランクを放電することができ、派生した trunks もすべてドレインされます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-274">•   The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="9b4ff-275">以前のモデルからキャリアトランクへの移行</span><span class="sxs-lookup"><span data-stu-id="9b4ff-275">Migration from the previous model to the carrier trunk</span></span>
 
<span data-ttu-id="9b4ff-276">キャリアでホストされているモデルの現在の実装から新しいモデルに移行するには、運送業者は trunks を顧客テナント用に再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-276">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="9b4ff-277">Trunks を使用して、ユーザーテナントから CSOnlinePSTNGateway を削除します (電話会社のテナントにトランクを残します)。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-277">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant).</span></span>

<span data-ttu-id="9b4ff-278">新しいソリューションへの移行はできるだけ早くお勧めします。これにより、通信事業者と派生したトランクモデルを使用した監視とプロビジョニングが強化されます。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-278">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="9b4ff-279">連絡先ヘッダーでサブドメインの FQDN 名の送信を構成する方法については、「 [SBC ベンダーの手順](#deploy-and-configure-the-sbc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b4ff-279">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

