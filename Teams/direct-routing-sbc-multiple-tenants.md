---
title: セッション ボーダー コントローラーを構成する - 複数のテナント
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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 1 つのセッション ボーダー コントローラー (SBC) を構成して、Microsoft パートナーや PSTN キャリア用に複数のテナントにサービスを提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 742b02709585e9a25b170bc99aab3d1939d63f10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096533"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="32265-103">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="32265-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="32265-104">ダイレクト ルーティングは、複数のテナントにサービスを提供する 1 つのセッション ボーダー コントローラー (SBC) の構成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="32265-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="32265-105">このシナリオは、このドキュメントの後半で通信事業者と呼ばれる、Microsoft パートナーや PSTN 通信事業者向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="32265-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="32265-106">通信事業者は、Microsoft Teams に配信されたテレフォニー サービスを顧客に販売しています。</span><span class="sxs-lookup"><span data-stu-id="32265-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="32265-107">通信事業者:</span><span class="sxs-lookup"><span data-stu-id="32265-107">A carrier:</span></span>
- <span data-ttu-id="32265-108">データセンターに SBC を展開して管理します (お客様は SBC を実装する必要は不要で、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="32265-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="32265-109">SBC を複数のテナントに相互接続します。</span><span class="sxs-lookup"><span data-stu-id="32265-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="32265-110">PSTN サービスをお客様に提供します。</span><span class="sxs-lookup"><span data-stu-id="32265-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="32265-111">通話品質のエンドツーエンドを管理します。</span><span class="sxs-lookup"><span data-stu-id="32265-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="32265-112">PSTN サービスに対する個別の料金。</span><span class="sxs-lookup"><span data-stu-id="32265-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="32265-113">Microsoft は、通信事業者を管理していない。</span><span class="sxs-lookup"><span data-stu-id="32265-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="32265-114">Microsoft は PBX (Microsoft Phone System) と Teams クライアントを提供しています。</span><span class="sxs-lookup"><span data-stu-id="32265-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="32265-115">また、Microsoft は電話を認定し、Microsoft Phone System で使用できる SPC を認定します。</span><span class="sxs-lookup"><span data-stu-id="32265-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="32265-116">通信事業者を選択する前に、お客様の選択に認定済みの SBC が付いていて、音声品質をエンドツーエンドで管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="32265-117">シナリオを構成するための技術的な実装手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32265-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="32265-118">**通信事業者のみ:**</span><span class="sxs-lookup"><span data-stu-id="32265-118">**Carrier only:**</span></span>
1. <span data-ttu-id="32265-119">SBC を展開し、認定された SBC ベンダーからの指示に従ってホスティング [シナリオ用に構成します](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="32265-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="32265-120">キャリア テナントにベース ドメイン名を登録し、ワイルドカード証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="32265-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="32265-121">ベース ドメインの一部であるすべての顧客のサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="32265-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="32265-122">**顧客グローバル管理者による通信事業者:**</span><span class="sxs-lookup"><span data-stu-id="32265-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="32265-123">サブドメイン名を顧客テナントに追加します。</span><span class="sxs-lookup"><span data-stu-id="32265-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="32265-124">サブドメイン名をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="32265-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="32265-125">通信事業者から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="32265-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="32265-126">*DNS の基本と、Microsoft 365 または Office 365 でのドメイン名の管理方法を理解してください。さらに [進む前に、Microsoft 365 または 365 Officeヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="32265-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="32265-127">SBC を展開して構成する</span><span class="sxs-lookup"><span data-stu-id="32265-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="32265-128">SBC ホスティング シナリオ用に SBC を展開および構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32265-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="32265-129">**AudioCodes:** [ダイレクト](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)ルーティング構成のメモ、"AudioCodes SBC を Microsoft Teams ダイレクト ルーティング ホスティング モデル構成メモに接続する" で説明されている SBC ホスティング シナリオの構成。</span><span class="sxs-lookup"><span data-stu-id="32265-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="32265-130">**Oracle:** [ダイレクト ルーティング構成に関する注意事項](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)、SBC ホスティング シナリオの構成については、「Microsoft」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32265-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="32265-131">**リボンのコミュニケーション:** リボン コア シリーズの SBC を構成する方法およびこのページのリボンのベスト プラクティス - Microsoft Teams ダイレクト ルーティング [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)用の携帯電話会社の構成については、リボン通信 [SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) Core Microsoft Teams 構成ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32265-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="32265-132">**TE-Systems (anynode):**  複数のテナントに対して anynode SBC を構成する方法のドキュメントと例については [、TE-Systems コミュニティ](https://community.te-systems.de/) ページに登録してください。</span><span class="sxs-lookup"><span data-stu-id="32265-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="32265-133">**メタスイッチ:**  複数のテナントで Perimeta SBC を有効にする方法のドキュメントについては [、Metaswitch コミュニティ](https://manuals.metaswitch.com/MAN39555) ページに登録してください。</span><span class="sxs-lookup"><span data-stu-id="32265-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="32265-134">"連絡先" ヘッダーの構成方法にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="32265-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="32265-135">連絡先ヘッダーは、受信した招待メッセージで顧客テナントを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="32265-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="32265-136">ベース ドメインとサブドメインを登録する</span><span class="sxs-lookup"><span data-stu-id="32265-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="32265-137">ホスティングシナリオでは、次を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="32265-138">通信事業者が所有する 1 つのベース ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="32265-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="32265-139">すべての顧客テナントのベース ドメイン名の一部であるサブドメイン。</span><span class="sxs-lookup"><span data-stu-id="32265-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="32265-140">次の例では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32265-140">In the following example:</span></span>
- <span data-ttu-id="32265-141">Adatum は、インターネットおよびテレフォニー サービスを提供することで、複数の顧客にサービスを提供する通信事業者です。</span><span class="sxs-lookup"><span data-stu-id="32265-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="32265-142">Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 または Office 365 ドメインを持っているが、Adatum からテレフォニー サービスを受け取る 3 人のお客様です。</span><span class="sxs-lookup"><span data-stu-id="32265-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="32265-143">サブドメインは、Microsoft 365 または Office 365 に招待を送信するときに、顧客用に構成されるトランクの FQDN 名と連絡先ヘッダーの FQDN と一致する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="32265-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="32265-144">呼び出しが Microsoft 365 または Office 365 ダイレクト ルーティング インターフェイスに到着すると、インターフェイスは連絡先ヘッダーを使用して、ユーザーを検索する必要があるテナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="32265-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="32265-145">ダイレクト ルーティングでは、複数のテナントで重複する可能性がある DID 以外の番号を持つお客様もいます。</span><span class="sxs-lookup"><span data-stu-id="32265-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="32265-146">そのため、電話番号でユーザーを検索するテナントを正確に識別するには、連絡先ヘッダーの FQDN 名が必要です。</span><span class="sxs-lookup"><span data-stu-id="32265-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="32265-147">*Microsoft  [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのドメイン名の作成の詳細については、365 のドメインに関するヘルプOffice参照してください。*</span><span class="sxs-lookup"><span data-stu-id="32265-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="32265-148">次の図は、ベース ドメイン、サブドメイン、および連絡先ヘッダーの要件をまとめた図です。</span><span class="sxs-lookup"><span data-stu-id="32265-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="32265-150">SBC では、接続を認証するために証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="32265-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="32265-151">SBC ホスティング シナリオでは、通信事業者は CN または SAN .base_domain *\* \* (.customers.adatum.biz など)* を含む証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="32265-152">この証明書は、1 つの SBC から提供された複数のテナントへの接続を認証するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="32265-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="32265-153">次の表は、1 つの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="32265-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="32265-154">新しいドメイン名</span><span class="sxs-lookup"><span data-stu-id="32265-154">New domain name</span></span> |<span data-ttu-id="32265-155">種類</span><span class="sxs-lookup"><span data-stu-id="32265-155">Type</span></span>|<span data-ttu-id="32265-156">登録済み</span><span class="sxs-lookup"><span data-stu-id="32265-156">Registered</span></span>  |<span data-ttu-id="32265-157">SBC 用証明書 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="32265-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="32265-158">例のテナントの既定のドメイン</span><span class="sxs-lookup"><span data-stu-id="32265-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="32265-159">ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="32265-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-160">customers.adatum.biz</span></span>|    <span data-ttu-id="32265-161">Base</span><span class="sxs-lookup"><span data-stu-id="32265-161">Base</span></span>     |     <span data-ttu-id="32265-162">通信事業者テナントの場合</span><span class="sxs-lookup"><span data-stu-id="32265-162">In carrier tenant</span></span>  |    <span data-ttu-id="32265-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="32265-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-164">adatum.biz</span></span>      |<span data-ttu-id="32265-165">NA、これはサービス テナント、ユーザーなし</span><span class="sxs-lookup"><span data-stu-id="32265-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="32265-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="32265-167">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="32265-167">Subdomain</span></span>  |    <span data-ttu-id="32265-168">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="32265-168">In a customer tenant</span></span>  |    <span data-ttu-id="32265-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="32265-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="32265-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="32265-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="32265-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="32265-173">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="32265-173">Subdomain</span></span> | <span data-ttu-id="32265-174">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="32265-174">In a customer tenant</span></span>   |   <span data-ttu-id="32265-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="32265-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="32265-176">contoso.com</span></span>   |<span data-ttu-id="32265-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="32265-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="32265-179">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="32265-179">Subdomain</span></span> | <span data-ttu-id="32265-180">顧客テナントの場合</span><span class="sxs-lookup"><span data-stu-id="32265-180">In a customer tenant</span></span> |   <span data-ttu-id="32265-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="32265-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="32265-182">adventureworks.com</span></span> | <span data-ttu-id="32265-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="32265-184">ベースとサブドメインを構成するには、次に説明する手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="32265-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="32265-185">この例では、1 人の顧客のベース ドメイン名 (customers.adatum.biz) とサブドメイン (Woodgrove Bank テナントの sbc1.customers.adatum.biz) を構成します。</span><span class="sxs-lookup"><span data-stu-id="32265-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="32265-186">この sbcX.customers.adatum.biz を使用して、キャリア テナントで音声を有効にします。</span><span class="sxs-lookup"><span data-stu-id="32265-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="32265-187">sbcX には、任意の一意の有効な英数字ホスト名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="32265-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="32265-188">キャリア テナントでベース ドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="32265-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="32265-189">**これらのアクションは、通信事業者テナントで実行されます。**</span><span class="sxs-lookup"><span data-stu-id="32265-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="32265-190">通信事業者テナントに適切な権限を持っている必要があります</span><span class="sxs-lookup"><span data-stu-id="32265-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="32265-191">新しいドメインを追加できるのは、グローバル管理者として Microsoft 365 管理センターにサインインしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="32265-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="32265-192">持っている役割を検証するには、Microsoft 365 管理センターにサインインしてください ([アクティブなユーザー] に移動し、グローバル管理者の役割を持っているか https://portal.office.com)   >  確認します)。</span><span class="sxs-lookup"><span data-stu-id="32265-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="32265-193">管理者ロールの詳細と、Microsoft 365 または Office 365 でロールを割り当てる方法については、「管理者ロールについて」を [参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="32265-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="32265-194">テナントにベース ドメインを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="32265-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="32265-195">Microsoft 365 管理センターで、[ドメインの追加の **セットアップ**  >  **] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="32265-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="32265-196">[所有 **するドメインを入力してください] ボックス** に、ベース ドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="32265-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="32265-197">次の例では、ベース ドメインは *customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="32265-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="32265-199">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32265-199">Click **Next**.</span></span>
4. <span data-ttu-id="32265-200">この例では、テナントは既に adatum.biz ドメイン名として使用されています。</span><span class="sxs-lookup"><span data-stu-id="32265-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="32265-201">既に登録されている名前のサブドメイン customers.adatum.biz、追加の確認は求めされません。</span><span class="sxs-lookup"><span data-stu-id="32265-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="32265-202">ただし、以前に確認されていない FQDN を追加する場合は、確認プロセスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="32265-203">確認プロセスについては、以下 [で説明します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="32265-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![確認済みドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="32265-205">[ **次へ]** をクリックし **、[DNS** 設定の更新] ページで **[DNS** レコードを自分で追加する] を選び、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="32265-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="32265-206">次のページで、すべての値をクリアし (Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用しない場合)、[次へ] をクリックし、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32265-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="32265-207">新しいドメインがセットアップ完了ステータスに入った状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="32265-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![セットアップが完了した状態のドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="32265-209">ドメイン名をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="32265-209">Activate the domain name</span></span>

<span data-ttu-id="32265-210">ドメイン名を登録したら、電話システム ライセンスを持つ 1 人のユーザーを少なくとも 1 人追加し、作成されたベース ドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当て、ドメインをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-210">After you have registered a domain name, you need to activate it by adding at least one user with Phone System license and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="32265-211">ライセンスは、ドメインのライセンス認証後に取り消されます (最大 24 時間かかる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="32265-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="32265-212">Skype for Business 構成が削除されるのを避けるために、Carrier テナントでは、テナントに割り当てられている電話システム ライセンスを少なくとも 1 つ保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-212">The Carrier tenant must keep at least one Phone System license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="32265-213">*Microsoft [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのユーザーの追加の詳細については、Microsoft 365 または Office Office 365 ドメインに関するヘルプを参照してください。*</span><span class="sxs-lookup"><span data-stu-id="32265-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="32265-214">例: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-214">For example: test@customers.adatum.biz</span></span>

![ベース ドメインのライセンス認証ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="32265-216">顧客テナントでサブドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="32265-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="32265-217">すべての顧客に一意のサブドメイン名を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="32265-218">この例では、既定のドメイン名が sbc1.customers.adatum.biz を持つサブドメイン ドメインを woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="32265-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="32265-219">**以下のすべてのアクションは、顧客テナントに含されます。**</span><span class="sxs-lookup"><span data-stu-id="32265-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="32265-220">顧客テナントに適切な権限を持っている必要があります</span><span class="sxs-lookup"><span data-stu-id="32265-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="32265-221">新しいドメインを追加できるのは、グローバル管理者として Microsoft 365 管理センターにサインインしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="32265-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="32265-222">持っている役割を検証するには、Microsoft 365 管理センターにサインインしてください ([アクティブなユーザー] に移動し、グローバル管理者の役割を持っているか https://portal.office.com)   >  確認します)。</span><span class="sxs-lookup"><span data-stu-id="32265-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="32265-223">管理者ロールの詳細と、Microsoft 365 または Office 365 でロールを割り当てる方法については、「管理者ロールについて」を [参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="32265-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="32265-224">サブドメインを顧客テナントに追加して確認する</span><span class="sxs-lookup"><span data-stu-id="32265-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="32265-225">Microsoft 365 管理センターで、[ドメインの追加の **セットアップ**  >  **] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="32265-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="32265-226">[所有 **するドメインを入力してください]** ボックスに、このテナントのサブドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="32265-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="32265-227">次の例では、サブドメインは sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="32265-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="32265-229">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32265-229">Click **Next**.</span></span>
4. <span data-ttu-id="32265-230">FQDN がテナントに登録されていません。</span><span class="sxs-lookup"><span data-stu-id="32265-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="32265-231">次の手順では、ドメインを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="32265-232">代 **わりに [TXT レコードの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32265-232">Select **Add a TXT record instead**.</span></span> 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="32265-234">[ **次へ]** をクリックし、ドメイン名を確認するために生成された TXT 値をメモします。</span><span class="sxs-lookup"><span data-stu-id="32265-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="32265-236">通信事業者の DNS ホスティング プロバイダーの前の手順の値を使用して TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="32265-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="32265-238">詳細については、「任意の DNS ホスティング プロバイダー [で DNS レコードを作成する」を参照してください](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="32265-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="32265-239">顧客の Microsoft 365 管理センターに戻り、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="32265-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="32265-240">次のページで **、[DNS** レコードを自分で追加して、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="32265-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![[DNS 設定の更新] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="32265-242">[オンライン **サービスの選択] ページで、** すべてのオプションをオフにし、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="32265-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![[オンライン サービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="32265-244">[DNS **設定** の更新 **] ページで [完了] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="32265-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="32265-246">状態が [セットアップ完了 **] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="32265-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="32265-248">直接ルート トランクを追加するには、個々のクライアントのベース URL とサブドメインが同じテナント上に _設定されている必要_ があります。</span><span class="sxs-lookup"><span data-stu-id="32265-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="32265-249">サブドメイン名をアクティブにする</span><span class="sxs-lookup"><span data-stu-id="32265-249">Activate the subdomain name</span></span>

<span data-ttu-id="32265-250">ドメイン名を登録したら、少なくとも 1 人のユーザーを追加して SIP アドレスを割り当て、顧客テナントで作成されたサブドメインと一致する SIP アドレスの FQDN 部分を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="32265-251">ライセンスは、サブドメインのライセンス認証後にユーザーから取り消されます (最大 24 時間かかる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="32265-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="32265-252">*Microsoft [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのユーザーの追加の詳細については、Microsoft 365 または Office Office 365 ドメインに関するヘルプを参照してください。*</span><span class="sxs-lookup"><span data-stu-id="32265-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="32265-253">例: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="32265-253">For example: test@sbc1.customers.adatum.biz</span></span>

![サブドメイン ページのアクティブ化のスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="32265-255">トランクを作成してユーザーをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="32265-255">Create a trunk and provision users</span></span>

<span data-ttu-id="32265-256">ダイレクト ルーティングの最初のリリースでは、Microsoft は New-CSOnlinePSTNGateway を使用して、提供された各テナント (顧客テナント) にトランクを追加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="32265-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="32265-257">ただし、次の 2 つの理由で、これが最適であることが証明されたわけではありません。</span><span class="sxs-lookup"><span data-stu-id="32265-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="32265-258">**オーバーヘッド管理**。</span><span class="sxs-lookup"><span data-stu-id="32265-258">**Overhead management**.</span></span> <span data-ttu-id="32265-259">たとえば、SBC のオフロードや水切りは、メディア バイパスの有効化や無効化など、一部のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="32265-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="32265-260">ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC です。</span><span class="sxs-lookup"><span data-stu-id="32265-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="32265-261">**オーバーヘッド処理**。</span><span class="sxs-lookup"><span data-stu-id="32265-261">**Overhead processing**.</span></span> <span data-ttu-id="32265-262">トランク正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションは、ルーティング データの処理を遅くします。</span><span class="sxs-lookup"><span data-stu-id="32265-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="32265-263">このフィードバックに基づいて、Microsoft は顧客テナントのトランクをプロビジョニングする新しいロジックを取り入れしています。</span><span class="sxs-lookup"><span data-stu-id="32265-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="32265-264">2 つの新しいエンティティが導入されました。</span><span class="sxs-lookup"><span data-stu-id="32265-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="32265-265">New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true など、コマンド New-CSOnlinePSTNGateway を使用してキャリア テナントに登録されたキャリア トランク。</span><span class="sxs-lookup"><span data-stu-id="32265-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="32265-266">登録を必要としない派生トランク。</span><span class="sxs-lookup"><span data-stu-id="32265-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="32265-267">単に、キャリア トランクから追加された目的のホスト名です。</span><span class="sxs-lookup"><span data-stu-id="32265-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="32265-268">このパラメーターは、すべての構成パラメーターをキャリア トランクから取得します。</span><span class="sxs-lookup"><span data-stu-id="32265-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="32265-269">派生トランクは PowerShell で作成する必要はなかった。また、キャリア トランクとの関連付けは FQDN 名に基づいて行います (詳細については以下を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="32265-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="32265-270">**プロビジョニング ロジックと例**</span><span class="sxs-lookup"><span data-stu-id="32265-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="32265-271">通信事業者は、1 つのトランク (キャリア ドメイン内のキャリア トランク) をセットアップして管理する必要がある場合にのみ、Set-CSOnlinePSTNGatewayします。</span><span class="sxs-lookup"><span data-stu-id="32265-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="32265-272">上の例では、次 adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="32265-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="32265-273">顧客テナントでは、通信事業者は派生トランク FQDN をユーザーの音声ルーティング ポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="32265-274">トランクに対してNew-CSOnlinePSTNGatewayする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="32265-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="32265-275">派生トランクは、名前が示す通り、キャリア トランクからすべての構成パラメーターを継承または派生します。</span><span class="sxs-lookup"><span data-stu-id="32265-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="32265-276">例:</span><span class="sxs-lookup"><span data-stu-id="32265-276">Examples:</span></span>
-    <span data-ttu-id="32265-277">Customers.adatum.biz – キャリア テナントで作成する必要があるキャリア トランク。</span><span class="sxs-lookup"><span data-stu-id="32265-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="32265-278">Sbc1.customers.adatum.biz – PowerShell で作成する必要はない、顧客テナントの派生トランクです。</span><span class="sxs-lookup"><span data-stu-id="32265-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="32265-279">顧客テナントの派生トランクの名前をオンライン音声ルーティング ポリシーに追加するだけで、その名前を作成せずに追加できます。</span><span class="sxs-lookup"><span data-stu-id="32265-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="32265-280">キャリアは、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="32265-281">キャリア トランク (キャリア テナント) に加えた変更は、派生トランクに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="32265-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="32265-282">たとえば、キャリアはキャリア トランク上の SIP ポートを変更できます。この変更は、すべての派生トランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="32265-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="32265-283">トランクを構成する新しいロジックは、すべてのテナントに移動してすべてのトランクのパラメーターを変更する必要がなさたので、管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="32265-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="32265-284">オプションは、キャリア トランク FQDN にのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="32265-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="32265-285">キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="32265-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="32265-286">ダイレクト ルーティング オプションの [詳細については、以下を参照してください](./direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="32265-286">Find out more about [Direct Routing options](./direct-routing-monitor-and-troubleshoot.md).</span></span>
-    <span data-ttu-id="32265-287">キャリアはキャリアのトランクを流し込み、すべての派生トランクも同様に流し込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32265-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="32265-288">**前のモデルからキャリア トランクへの移行**</span><span class="sxs-lookup"><span data-stu-id="32265-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="32265-289">通信事業者がホストするモデルの現在の実装から新しいモデルに移行するには、通信事業者が顧客テナントのトランクを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="32265-290">顧客テナントからトランクを削除するには、Remove-CSOnlinePSTNGatewayを使用します (キャリア テナントのトランクを残します)。</span><span class="sxs-lookup"><span data-stu-id="32265-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="32265-291">通信事業者と派生トランク モデルを使用した監視とプロビジョニングを強化する予定で、できるだけ早く新しいソリューションに移行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32265-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="32265-292">連絡先ヘッダーのサブドメインの FQDN 名の送信を構成する方法については [、SBC](#deploy-and-configure-the-sbc) ベンダーの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32265-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="32265-293">Muti テナントのフェールオーバーをセットアップする場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="32265-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="32265-294">マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="32265-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="32265-295">テナントごとに、2 つの異なる SPC の FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="32265-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="32265-296">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="32265-296">For example:</span></span>

   <span data-ttu-id="32265-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32265-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="32265-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32265-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="32265-299">ユーザーのオンライン音声ルーティング ポリシーで、両方の SPC を指定します。</span><span class="sxs-lookup"><span data-stu-id="32265-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="32265-300">1 つの SBC が失敗した場合、ルーティング ポリシーは 2 つ目の SBC に通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="32265-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="32265-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="32265-301">See also</span></span>

[<span data-ttu-id="32265-302">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="32265-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="32265-303">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="32265-303">Configure Direct Routing</span></span>](direct-routing-configure.md)