---
title: セッション ボーダー コントローラーの構成 - 複数のテナント
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
description: 1 つのセッション ボーダー コントローラー (SBC) を構成して、Microsoft パートナーや PSTN 通信事業者に複数のテナントを提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 742b02709585e9a25b170bc99aab3d1939d63f10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096533"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="8d177-103">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="8d177-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="8d177-104">ダイレクト ルーティングでは、複数のテナントにサービスを提供する 1 つのセッション ボーダー コントローラー (SBC) の構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8d177-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="8d177-105">このシナリオは、このドキュメントの後半で「通信事業者」と呼ばれる Microsoft パートナーや PSTN 通信事業者向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="8d177-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="8d177-106">運送業者は、顧客に提供されるテレフォニー Microsoft Teamsを販売します。</span><span class="sxs-lookup"><span data-stu-id="8d177-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="8d177-107">運送業者:</span><span class="sxs-lookup"><span data-stu-id="8d177-107">A carrier:</span></span>
- <span data-ttu-id="8d177-108">データセンターに SBC をデプロイして管理します (お客様は SBC を実装する必要が生じず、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="8d177-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="8d177-109">SBC を複数のテナントに相互接続します。</span><span class="sxs-lookup"><span data-stu-id="8d177-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="8d177-110">PSTN サービスを顧客に提供します。</span><span class="sxs-lookup"><span data-stu-id="8d177-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="8d177-111">通話品質のエンド エンド を管理します。</span><span class="sxs-lookup"><span data-stu-id="8d177-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="8d177-112">PSTN サービスに対して個別に料金が発生します。</span><span class="sxs-lookup"><span data-stu-id="8d177-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="8d177-113">Microsoft は通信事業者を管理していない。</span><span class="sxs-lookup"><span data-stu-id="8d177-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="8d177-114">Microsoft では、PBX (Microsoft 電話 システム) とクラウド クライアントTeamsしています。</span><span class="sxs-lookup"><span data-stu-id="8d177-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="8d177-115">また、Microsoft は携帯電話を認定し、マイクロソフトのシステムで使用できる SBC Microsoft 電話します。</span><span class="sxs-lookup"><span data-stu-id="8d177-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="8d177-116">通信事業者を選択する前に、選択した SBC が認定され、音声品質をエンド エンド で管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="8d177-117">シナリオを構成するための技術的な実装手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d177-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="8d177-118">**運送業者のみ:**</span><span class="sxs-lookup"><span data-stu-id="8d177-118">**Carrier only:**</span></span>
1. <span data-ttu-id="8d177-119">SBC をデプロイし、認定された SBC ベンダーからの指示に従ってホスティング [シナリオ用に構成します](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="8d177-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="8d177-120">キャリア テナントにベース ドメイン名を登録し、ワイルドカード証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="8d177-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="8d177-121">ベース ドメインの一部であるすべての顧客にサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="8d177-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="8d177-122">**顧客グローバル管理者を持つ運送業者:**</span><span class="sxs-lookup"><span data-stu-id="8d177-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="8d177-123">サブドメイン名を顧客テナントに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d177-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="8d177-124">サブドメイン名をアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="8d177-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="8d177-125">運送業者から顧客テナントへのトランクを構成し、ユーザーをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="8d177-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="8d177-126">*DNS の基本とドメイン名の管理方法については、Microsoft 365 または Office 365。さらに [進む前に、「Microsoft 365またはOffice 365ヘルプを表示する」](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="8d177-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="8d177-127">SBC のデプロイと構成</span><span class="sxs-lookup"><span data-stu-id="8d177-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="8d177-128">SBC ホスティング シナリオ用に SBC をデプロイおよび構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="8d177-129">**AudioCodes:** [ダイレクト ルーティング](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)構成に関するメモ 。「Direct Routing Hosting Model Configuration Note への AudioCodes SBC の接続Microsoft Teams SBC ホスティング シナリオの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="8d177-130">**Oracle:** [ダイレクト ルーティング構成に関する注意](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)。 SBC ホスティング シナリオの構成については、「Microsoft」セクションで説明しています。</span><span class="sxs-lookup"><span data-stu-id="8d177-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="8d177-131">**リボンコミュニケーション:** リボン コア シリーズの SBC を構成する方法に関するドキュメントについては、リボン通信 [SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)構成ガイドを参照してください。リボンのベスト プラクティス - Microsoft Teams Direct Routing [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)の通信事業者の構成に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="8d177-132">**TE-Systems (anynode):** 複数のテナントに anynode SBC を構成する方法に関するドキュメントと例については [、TE-Systems](https://community.te-systems.de/) Community ページに登録してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="8d177-133">**Metaswitch:** 複数のテナントに [対](https://manuals.metaswitch.com/MAN39555)して Perimeta SBC を有効にする方法に関するドキュメントについては、Metaswitch Community ページに登録してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="8d177-134">"Contact" ヘッダーを構成する方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="8d177-135">Contact ヘッダーは、受信した招待メッセージで顧客テナントを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="8d177-136">ベース ドメインとサブドメインを登録する</span><span class="sxs-lookup"><span data-stu-id="8d177-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="8d177-137">ホスティング シナリオでは、次を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="8d177-138">通信事業者が所有する 1 つのベース ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="8d177-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="8d177-139">すべての顧客テナントのベース ドメイン名の一部であるサブドメイン。</span><span class="sxs-lookup"><span data-stu-id="8d177-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="8d177-140">次の例では、</span><span class="sxs-lookup"><span data-stu-id="8d177-140">In the following example:</span></span>
- <span data-ttu-id="8d177-141">Adatum は、インターネットおよびテレフォニー サービスを提供することで、複数の顧客にサービスを提供する通信事業者です。</span><span class="sxs-lookup"><span data-stu-id="8d177-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="8d177-142">Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 または Office 365 ドメインを持ち、Adatum からテレフォニー サービスを受け取る 3 人のお客様です。</span><span class="sxs-lookup"><span data-stu-id="8d177-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="8d177-143">サブドメインは、顧客に対して構成されるトランクの FQDN 名と、Microsoft 365 または Office 365 への招待を送信するときに連絡先ヘッダーの FQDN と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="8d177-144">Microsoft 365 または Office 365 ダイレクト ルーティング インターフェイスに呼び出しが到着すると、インターフェイスは Contact ヘッダーを使用して、ユーザーを検索する必要があるテナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="8d177-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="8d177-145">ダイレクト ルーティングでは、複数のテナントで重複する可能性がある DID 以外の番号を持つお客様もいます。招待では電話番号の参照は使用しません。</span><span class="sxs-lookup"><span data-stu-id="8d177-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="8d177-146">そのため、電話番号でユーザーを検索する正確なテナントを識別するには、Contact ヘッダーの FQDN 名が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d177-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="8d177-147">*組織で [ドメイン名を作成する方法Office 365ドメイン](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)に関するヘルプを参照Microsoft 365参照Office 365してください。*</span><span class="sxs-lookup"><span data-stu-id="8d177-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8d177-148">次の図は、ベース ドメイン、サブドメイン、および Contact ヘッダーの要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="8d177-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="8d177-150">SBC では、接続を認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d177-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="8d177-151">SBC ホスティング シナリオの場合、通信事業者は CN または .base_domain SAN 証明書 (例: *\* \* .customers.adatum.biz)* で証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="8d177-152">この証明書を使用して、1 つの SBC から提供される複数のテナントへの接続を認証できます。</span><span class="sxs-lookup"><span data-stu-id="8d177-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="8d177-153">次の表は、1 つの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="8d177-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="8d177-154">新しいドメイン名</span><span class="sxs-lookup"><span data-stu-id="8d177-154">New domain name</span></span> |<span data-ttu-id="8d177-155">種類</span><span class="sxs-lookup"><span data-stu-id="8d177-155">Type</span></span>|<span data-ttu-id="8d177-156">登録済み</span><span class="sxs-lookup"><span data-stu-id="8d177-156">Registered</span></span>  |<span data-ttu-id="8d177-157">SBC の証明書 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="8d177-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="8d177-158">この例のテナントの既定のドメイン</span><span class="sxs-lookup"><span data-stu-id="8d177-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="8d177-159">ユーザーに呼び出しを送信するときに、SBC が Contact ヘッダーに表示する必要があります FQDN 名</span><span class="sxs-lookup"><span data-stu-id="8d177-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="8d177-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-160">customers.adatum.biz</span></span>|    <span data-ttu-id="8d177-161">Base</span><span class="sxs-lookup"><span data-stu-id="8d177-161">Base</span></span>     |     <span data-ttu-id="8d177-162">運送業者テナント内</span><span class="sxs-lookup"><span data-stu-id="8d177-162">In carrier tenant</span></span>  |    <span data-ttu-id="8d177-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="8d177-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-164">adatum.biz</span></span>      |<span data-ttu-id="8d177-165">NA、これはサービス テナント、ユーザーなし</span><span class="sxs-lookup"><span data-stu-id="8d177-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="8d177-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="8d177-167">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="8d177-167">Subdomain</span></span>  |    <span data-ttu-id="8d177-168">顧客テナント内</span><span class="sxs-lookup"><span data-stu-id="8d177-168">In a customer tenant</span></span>  |    <span data-ttu-id="8d177-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="8d177-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="8d177-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="8d177-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="8d177-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="8d177-173">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="8d177-173">Subdomain</span></span> | <span data-ttu-id="8d177-174">顧客テナント内</span><span class="sxs-lookup"><span data-stu-id="8d177-174">In a customer tenant</span></span>   |   <span data-ttu-id="8d177-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="8d177-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d177-176">contoso.com</span></span>   |<span data-ttu-id="8d177-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="8d177-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="8d177-179">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="8d177-179">Subdomain</span></span> | <span data-ttu-id="8d177-180">顧客テナント内</span><span class="sxs-lookup"><span data-stu-id="8d177-180">In a customer tenant</span></span> |   <span data-ttu-id="8d177-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="8d177-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="8d177-182">adventureworks.com</span></span> | <span data-ttu-id="8d177-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="8d177-184">ベースドメインとサブドメインを構成するには、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8d177-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="8d177-185">この例では、1 人の顧客 (Woodgrove Bank テナント内の sbc1.customers.adatum.biz) のベース ドメイン名 (customers.adatum.biz) とサブドメインを構成します。</span><span class="sxs-lookup"><span data-stu-id="8d177-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="8d177-186">[sbcX.customers.adatum.biz を使用して、通信事業者のテナントで音声を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d177-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="8d177-187">sbcX には、任意の一意の有効な英数字ホスト名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8d177-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="8d177-188">キャリア テナントにベース ドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="8d177-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="8d177-189">**これらのアクションは、通信事業者テナントで実行されます。**</span><span class="sxs-lookup"><span data-stu-id="8d177-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="8d177-190">通信事業者のテナントで適切な権限を持っている必要があります</span><span class="sxs-lookup"><span data-stu-id="8d177-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="8d177-191">新しいドメインは、グローバル管理者として Microsoft 365にサインインした場合にのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="8d177-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="8d177-192">ロールを検証するには、Microsoft 365 管理センター ( にサインインし、[ユーザーのアクティブなユーザー] に移動し、グローバル管理者ロールが割り当て済みである https://portal.office.com)   >  必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="8d177-193">管理者ロールの詳細と、管理者ロールまたは管理者ロールでロールを割り当てるMicrosoft 365をOffice 365管理者ロールについてを[参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="8d177-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="8d177-194">テナントにベース ドメインを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="8d177-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="8d177-195">管理センター Microsoft 365、[ドメインの追加]**の**  >  **設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="8d177-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="8d177-196">[所有 **するドメインを入力してください] ボックス** に、ベース ドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d177-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="8d177-197">次の例では、ベース ドメインは *customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="8d177-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="8d177-199">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d177-199">Click **Next**.</span></span>
4. <span data-ttu-id="8d177-200">この例では、テナントは既に adatum.biz ドメイン名として使用されています。</span><span class="sxs-lookup"><span data-stu-id="8d177-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="8d177-201">既に登録されている名前のサブドメイン customers.adatum.biz、追加の確認は求めされません。</span><span class="sxs-lookup"><span data-stu-id="8d177-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="8d177-202">ただし、以前に確認されていない FQDN を追加する場合は、検証のプロセスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="8d177-203">検証のプロセスについては、以下 [で説明します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="8d177-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![確認済みのドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="8d177-205">[**次へ**] をクリックし設定 DNS レコードの更新] ページで **、[** 自分で **DNS** レコードを追加する] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d177-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="8d177-206">次のページで、(Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用しない限り) すべての値をクリアし、[次へ] をクリックし、[完了] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8d177-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="8d177-207">新しいドメインがセットアップの完了状態にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="8d177-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![セットアップが完了した状態のドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="8d177-209">ドメイン名をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="8d177-209">Activate the domain name</span></span>

<span data-ttu-id="8d177-210">ドメイン名を登録したら、電話システム ライセンスを持つ少なくとも 1 人のユーザーを追加し、作成したベース ドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当て、ドメイン名をアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-210">After you have registered a domain name, you need to activate it by adding at least one user with Phone System license and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="8d177-211">ライセンスは、ドメインのライセンス認証後に取り消されます (最大 24 時間かかる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="8d177-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="8d177-212">Carrier テナントは、テナントに割り当電話システム少なくとも 1 つのライセンスを保持して、構成の削除を回避Skype for Businessがあります。</span><span class="sxs-lookup"><span data-stu-id="8d177-212">The Carrier tenant must keep at least one Phone System license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="8d177-213">*組織での [ユーザーの追加の詳細については](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)、「Microsoft 365 または Office 365 ドメインに関するヘルプを参照Microsoft 365参照Office 365してください。*</span><span class="sxs-lookup"><span data-stu-id="8d177-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8d177-214">例: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-214">For example: test@customers.adatum.biz</span></span>

![ベース ドメインのアクティブ化ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="8d177-216">顧客テナントにサブドメイン名を登録する</span><span class="sxs-lookup"><span data-stu-id="8d177-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="8d177-217">顧客ごとに一意のサブドメイン名を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="8d177-218">この例では、既定のドメイン名を持つ sbc1.customers.adatum.biz にサブドメイン ドメインを作成 woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="8d177-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="8d177-219">**以下のすべてのアクションは、顧客テナントに含めます。**</span><span class="sxs-lookup"><span data-stu-id="8d177-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="8d177-220">顧客テナントで適切な権限を持っている</span><span class="sxs-lookup"><span data-stu-id="8d177-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="8d177-221">新しいドメインは、グローバル管理者として Microsoft 365にサインインした場合にのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="8d177-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="8d177-222">ロールを検証するには、Microsoft 365 管理センター ( にサインインし、[ユーザーのアクティブなユーザー] に移動し、グローバル管理者ロールが割り当て済みである https://portal.office.com)   >  必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="8d177-223">管理者ロールの詳細と、管理者ロールまたは管理者ロールでロールを割り当てるMicrosoft 365をOffice 365管理者ロールについてを[参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="8d177-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="8d177-224">顧客テナントにサブドメインを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="8d177-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="8d177-225">管理センター Microsoft 365、[ドメインの追加]**の**  >  **設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="8d177-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="8d177-226">[所有 **するドメインを入力してください** ] ボックスに、このテナントのサブドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d177-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="8d177-227">次の例では、サブドメインが sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="8d177-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="8d177-229">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d177-229">Click **Next**.</span></span>
4. <span data-ttu-id="8d177-230">FQDN がテナントに登録されたことがない。</span><span class="sxs-lookup"><span data-stu-id="8d177-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="8d177-231">次の手順では、ドメインを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="8d177-232">[代 **わりに TXT レコードを追加する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d177-232">Select **Add a TXT record instead**.</span></span> 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="8d177-234">[次 **へ]** をクリックし、生成された TXT 値をメモしてドメイン名を確認します。</span><span class="sxs-lookup"><span data-stu-id="8d177-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="8d177-236">通信事業者の DNS ホスティング プロバイダーで、前の手順の値を使用して TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d177-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="8d177-238">詳細については、「任意の DNS ホスティング プロバイダー [で DNS レコードを作成する」を参照してください](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="8d177-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="8d177-239">顧客の管理センターに戻り、[確認Microsoft 365をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8d177-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="8d177-240">次のページで、[自分で DNS レコードを追加する] **を選択し** 、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d177-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    ![[DNS 設定の更新] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="8d177-242">[オンライン **サービスの選択] ページで、** すべてのオプションをオフにし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d177-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![[オンライン サービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="8d177-244">[DNS **設定の** 更新 **] ページで [完了] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8d177-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="8d177-246">状態が [セットアップ完了] **です**。</span><span class="sxs-lookup"><span data-stu-id="8d177-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="8d177-248">ダイレクト ルート トランクを追加するには、個々のクライアントのベース URL とサブドメインが同じテナント上に _必要_ です。</span><span class="sxs-lookup"><span data-stu-id="8d177-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="8d177-249">サブドメイン名をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="8d177-249">Activate the subdomain name</span></span>

<span data-ttu-id="8d177-250">ドメイン名を登録したら、少なくとも 1 人のユーザーを追加してアクティブ化し、顧客テナントで作成されたサブドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="8d177-251">ライセンスは、サブドメインのアクティブ化後にユーザーから取り消されます (最大 24 時間かかる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="8d177-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="8d177-252">*組織での [ユーザーの追加の詳細については](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)、「Microsoft 365 または Office 365 ドメインに関するヘルプを参照Microsoft 365参照Office 365してください。*</span><span class="sxs-lookup"><span data-stu-id="8d177-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="8d177-253">例: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="8d177-253">For example: test@sbc1.customers.adatum.biz</span></span>

![[サブドメインのアクティブ化] ページのスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="8d177-255">トランクを作成してユーザーをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="8d177-255">Create a trunk and provision users</span></span>

<span data-ttu-id="8d177-256">ダイレクト ルーティングの最初のリリースでは、Microsoft は New-CSOnlinePSTNGateway を使用して、提供される各テナント (顧客テナント) にトランクを追加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="8d177-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="8d177-257">ただし、これは次の 2 つの理由で最適であることが証明されません。</span><span class="sxs-lookup"><span data-stu-id="8d177-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="8d177-258">**オーバーヘッド管理**。</span><span class="sxs-lookup"><span data-stu-id="8d177-258">**Overhead management**.</span></span> <span data-ttu-id="8d177-259">たとえば、SBC をオフロードまたはドレインすると、メディア バイパスの有効化や無効化など、いくつかのパラメーターが変更されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="8d177-260">ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC です。</span><span class="sxs-lookup"><span data-stu-id="8d177-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="8d177-261">**オーバーヘッド処理**。</span><span class="sxs-lookup"><span data-stu-id="8d177-261">**Overhead processing**.</span></span> <span data-ttu-id="8d177-262">トランク正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションは、ルーティング データの処理を遅くします。</span><span class="sxs-lookup"><span data-stu-id="8d177-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="8d177-263">このフィードバックに基づいて、Microsoft は顧客テナントのトランクをプロビジョニングする新しいロジックを取り入れしています。</span><span class="sxs-lookup"><span data-stu-id="8d177-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="8d177-264">2 つの新しいエンティティが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8d177-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="8d177-265">New-CSOnlinePSTNGateway コマンド (例: New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true) を使用して、キャリア テナントに登録されたキャリア トランク。</span><span class="sxs-lookup"><span data-stu-id="8d177-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="8d177-266">登録を必要としない派生トランク。</span><span class="sxs-lookup"><span data-stu-id="8d177-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="8d177-267">これは、単に、キャリア トランクから追加された目的のホスト名です。</span><span class="sxs-lookup"><span data-stu-id="8d177-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="8d177-268">このパラメーターは、すべての構成パラメーターをキャリア トランクから派生します。</span><span class="sxs-lookup"><span data-stu-id="8d177-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="8d177-269">派生トランクは PowerShell で作成する必要は一方で、キャリア トランクとの関連付けは FQDN 名に基づいて行います (詳細については、以下を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8d177-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="8d177-270">**プロビジョニング ロジックと例**</span><span class="sxs-lookup"><span data-stu-id="8d177-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="8d177-271">運送業者は、次のコマンドを使用して、単一のトランク (キャリア ドメイン内のキャリア トランク) を設定Set-CSOnlinePSTNGateway必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="8d177-272">上記の例では、次 adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="8d177-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="8d177-273">顧客テナントでは、運送業者は、派生トランク FQDN をユーザーの音声ルーティング ポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="8d177-274">トランクに対してNew-CSOnlinePSTNGatewayする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d177-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="8d177-275">名前が示すように、派生トランクは、すべての構成パラメーターをキャリア トランクから継承または派生します。</span><span class="sxs-lookup"><span data-stu-id="8d177-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="8d177-276">例:</span><span class="sxs-lookup"><span data-stu-id="8d177-276">Examples:</span></span>
-    <span data-ttu-id="8d177-277">Customers.adatum.biz – 運送業者テナントに作成する必要がある運送業者のトランク。</span><span class="sxs-lookup"><span data-stu-id="8d177-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="8d177-278">Sbc1.customers.adatum.biz – PowerShell で作成する必要はない、顧客テナント内の派生トランク。</span><span class="sxs-lookup"><span data-stu-id="8d177-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="8d177-279">顧客テナントの派生トランクの名前は、オンライン音声ルーティング ポリシーで作成せずに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8d177-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="8d177-280">運送業者は、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="8d177-281">(キャリア テナント上の) 運送業者のトランクに加えた変更は、派生トランクに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="8d177-282">たとえば、運送業者は、運送業者のトランクで SIP ポートを変更できます。この変更は、すべての派生トランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="8d177-283">トランクを構成する新しいロジックは、すべてのテナントに移動してすべてのトランクでパラメーターを変更する必要がなさらないので、管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="8d177-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="8d177-284">オプションは、通信事業者のトランク FQDN にのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="8d177-285">キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d177-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="8d177-286">ダイレクト ルーティング オプションの [詳細については、 を参照してください](./direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="8d177-286">Find out more about [Direct Routing options](./direct-routing-monitor-and-troubleshoot.md).</span></span>
-    <span data-ttu-id="8d177-287">キャリアは、キャリアトランクをドレインできます。また、派生したトランクもすべてドレインされます。</span><span class="sxs-lookup"><span data-stu-id="8d177-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="8d177-288">**前のモデルからキャリア トランクへの移行**</span><span class="sxs-lookup"><span data-stu-id="8d177-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="8d177-289">運送業者がホストするモデルの現在の実装から新しいモデルに移行するには、運送業者が顧客テナントのトランクを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="8d177-290">(運送業者のテナントにトランクを残す) Remove-CSOnlinePSTNGatewayを使用して、顧客のテナントからトランクを削除します。</span><span class="sxs-lookup"><span data-stu-id="8d177-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="8d177-291">運送業者と派生トランク モデルを使用して監視とプロビジョニングを強化する予定で、できるだけ早く新しいソリューションに移行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d177-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="8d177-292">Contact ヘッダーで [サブドメインの](#deploy-and-configure-the-sbc) FQDN 名を送信する構成については、SBC ベンダーの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d177-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="8d177-293">マルチテナント フェールオーバーの設定に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="8d177-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="8d177-294">マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d177-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="8d177-295">テナントごとに、2 つの異なる SBC の FQDN を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d177-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="8d177-296">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8d177-296">For example:</span></span>

   <span data-ttu-id="8d177-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d177-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="8d177-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d177-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="8d177-299">ユーザーのオンライン音声ルーティング ポリシーで、両方の SBC を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d177-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="8d177-300">1 つの SBC が失敗した場合、ルーティング ポリシーは 2 つ目の SBC に呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8d177-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="8d177-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d177-301">See also</span></span>

[<span data-ttu-id="8d177-302">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="8d177-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8d177-303">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="8d177-303">Configure Direct Routing</span></span>](direct-routing-configure.md)