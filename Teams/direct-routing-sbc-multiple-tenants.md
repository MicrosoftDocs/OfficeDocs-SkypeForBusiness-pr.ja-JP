---
title: 複数のテナントのセッション ボーダー コント ローラーを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 複数のテナントを処理する 1 つのセッション ボーダー コント ローラー (SBC) を構成する方法について説明します。
ms.openlocfilehash: 292a3e675455d112fdade04018e670b9a5f9c38f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295745"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="d85aa-103">複数のテナントのセッション ボーダー コント ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="d85aa-104">直接ルーティングでは、構成する 1 つセッション ボーダー コント ローラー (SBC) 複数のテナントを処理するをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="d85aa-105">マイクロソフト パートナーまたは PSTN 通信事業者、このドキュメントの後半には、通信事業者と呼ばれるは、このシナリオは設計されています。</span><span class="sxs-lookup"><span data-stu-id="d85aa-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="d85aa-106">キャリアは、お客様に、マイクロソフトのチームに配信されるテレフォニー サービスを販売しています。</span><span class="sxs-lookup"><span data-stu-id="d85aa-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="d85aa-107">キャリア。</span><span class="sxs-lookup"><span data-stu-id="d85aa-107">A carrier:</span></span>
- <span data-ttu-id="d85aa-108">SBC のデータ センターでの管理を展開し、(お客様が、SBC を実装する必要はありませんし、チームのクライアントでのキャリアからテレフォニー サービスを受信する)。</span><span class="sxs-lookup"><span data-stu-id="d85aa-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="d85aa-109">複数のテナントに SBC を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="d85aa-110">PSTN サービスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="d85aa-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="d85aa-111">エンド ツー エンドの通話品質を管理します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="d85aa-112">PSTN サービスに対して個別に請求します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="d85aa-113">マイクロソフトでは、通信事業者は管理されません。</span><span class="sxs-lookup"><span data-stu-id="d85aa-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="d85aa-114">マイクロソフトは、PBX (マイクロソフトの電話システム) とチームのクライアントを提供しています、電話かを確認して、SBCs マイクロソフトの電話システムで使用できるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="d85aa-115">配送業者を選択するには、前にある選択認定 SBC があり、エンド ツー エンドの音声品質を管理することができますを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="d85aa-116">シナリオを構成するのには技術的な実装手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="d85aa-117">**キャリアのみ。**</span><span class="sxs-lookup"><span data-stu-id="d85aa-117">**Carrier only:**</span></span>
1. <span data-ttu-id="d85aa-118">SBC を配置し、[認定の SBC ベンダーの指示](#deploy-and-configure-the-sbc)に従って、ホストのシナリオ用に構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="d85aa-119">キャリア テナントでベースのドメイン名を登録し、ワイルドカード証明書を要求します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="d85aa-120">ベースのドメインの一部であるすべてのお客様のサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="d85aa-121">**キャリアでは、お客様のグローバル管理者:**</span><span class="sxs-lookup"><span data-stu-id="d85aa-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="d85aa-122">お客様のテナントには、サブドメイン名を追加します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="d85aa-123">サブドメイン名を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="d85aa-124">お客様のテナントとプロビジョニングのユーザーに、キャリアからトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="d85aa-125">*DNS の基礎と Office 365 でドメイン名を管理する方法を理解することを確認してください。進む前に[Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を確認してください。*</span><span class="sxs-lookup"><span data-stu-id="d85aa-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="d85aa-126">展開し、SBC を構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="d85aa-127">展開し、SBC ホスティング シナリオでは、半角を構成する方法の詳細な手順については、SBC の製造元のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="d85aa-128">**は:**[直接ルーティングの構成に関する注意事項](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)」の接続は SBC マイクロソフト チーム直接ルーティングのホスティング モデル構成メモにします」で説明したシナリオをホストしている SBC の構成</span><span class="sxs-lookup"><span data-stu-id="d85aa-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="d85aa-129">**通信のリボン:** リボンの中核となる一連の SBCs を構成する方法に関するドキュメントは、[リボン通信 SBC コア Microsoft チーム構成ガイド](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)をこのページの[リボン最適なベスト ・ プラクティスの通信事業者を構成するマイクロソフト チームの直接のルーティングのためを参照してください。SBC エッジ](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="d85aa-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="d85aa-130">「連絡先」ヘッダーを構成する方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="d85aa-131">Contact ヘッダーを使用して、招待の受信メッセージにお客様のテナントを検索します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="d85aa-132">基本ドメインとサブドメインを登録します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="d85aa-133">ホスティングのシナリオでは、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="d85aa-134">配送業者が所有する 1 つのベースのドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="d85aa-135">サブドメインで顧客のすべてのテナント ベースのドメイン名の一部であります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="d85aa-136">次の例ではします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-136">In the following example:</span></span>
- <span data-ttu-id="d85aa-137">Adatum は、インターネットおよびテレフォニー サービスを提供することで複数の顧客サービスを提供するキャリアです。</span><span class="sxs-lookup"><span data-stu-id="d85aa-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="d85aa-138">Woodgrove Bank、contoso 社では、Adventure Works は、Office 365 のドメインが存在するが、Adatum からテレフォニー サービスを受信する 3 つの顧客です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="d85aa-139">サブドメインに**する必要があります**では、Office 365 に招待状を送信するときに、顧客および取引先担当者のヘッダー内の FQDN を構成するトランクの FQDN 名と一致します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="d85aa-140">Office 365 の直接のルーティング インターフェイスでの呼び出しが到着すると、インタ フェースは、テナントのユーザーを検索する必要がありますを検索するのに連絡先ヘッダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="d85aa-141">直接ルーティングの使用しない電話番号をルックアップへの招待は、一部のお客様がない必要がありますように番号がいくつかのテナントが重複することにしました。</span><span class="sxs-lookup"><span data-stu-id="d85aa-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="d85aa-142">したがって、電話番号で、特定のユーザーを検索するのには正確なテナントは Contact ヘッダー内の FQDN 名が必要です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="d85aa-143">*Office 365 テナントにドメイン名を作成する方法の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="d85aa-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="d85aa-144">次の図は、基本ドメイン、サブドメインでは、連絡先のヘッダーの要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d85aa-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![ベースのドメイン、サブドメインでは、連絡先のヘッダーの要件](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="d85aa-146">SBC には、接続の認証に証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="d85aa-147">キャリアは SBC のホスティング シナリオでは、san 証明書を要求する必要があります*\*.base_domain (たとえば、 \*customers.adatum.biz)*。</span><span class="sxs-lookup"><span data-stu-id="d85aa-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="d85aa-148">この証明書は、複数のテナントが 1 つの SBC からへの接続を認証するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d85aa-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="d85aa-149">次の表は、1 つの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="d85aa-150">新しいドメイン名</span><span class="sxs-lookup"><span data-stu-id="d85aa-150">New domain name</span></span> |<span data-ttu-id="d85aa-151">種類</span><span class="sxs-lookup"><span data-stu-id="d85aa-151">Type</span></span>|<span data-ttu-id="d85aa-152">登録</span><span class="sxs-lookup"><span data-stu-id="d85aa-152">Registered</span></span>  |<span data-ttu-id="d85aa-153">SBC の SAN 証明書</span><span class="sxs-lookup"><span data-stu-id="d85aa-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="d85aa-154">テナントの既定のドメインの例</span><span class="sxs-lookup"><span data-stu-id="d85aa-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="d85aa-155">ユーザーへの呼び出しを送信するとき、連絡先のヘッダーに SBC が提示しなければならない FQDN 名</span><span class="sxs-lookup"><span data-stu-id="d85aa-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="d85aa-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-156">customers.adatum.biz</span></span>|    <span data-ttu-id="d85aa-157">ベース</span><span class="sxs-lookup"><span data-stu-id="d85aa-157">Base</span></span>     |     <span data-ttu-id="d85aa-158">キャリアのテナントで</span><span class="sxs-lookup"><span data-stu-id="d85aa-158">In carrier tenant</span></span>  |    <span data-ttu-id="d85aa-159">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="d85aa-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-160">adatum.biz</span></span>      |<span data-ttu-id="d85aa-161">「Na」と、これは、サービス テナント ユーザーは存在しません</span><span class="sxs-lookup"><span data-stu-id="d85aa-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="d85aa-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="d85aa-163">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="d85aa-163">Subdomain</span></span>  |    <span data-ttu-id="d85aa-164">お客様のテナントで</span><span class="sxs-lookup"><span data-stu-id="d85aa-164">In a customer tenant</span></span>  |    <span data-ttu-id="d85aa-165">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="d85aa-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="d85aa-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="d85aa-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="d85aa-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="d85aa-169">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="d85aa-169">Subdomain</span></span> | <span data-ttu-id="d85aa-170">お客様のテナントで</span><span class="sxs-lookup"><span data-stu-id="d85aa-170">In a customer tenant</span></span>   |   <span data-ttu-id="d85aa-171">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="d85aa-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d85aa-172">contoso.com</span></span>   |<span data-ttu-id="d85aa-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="d85aa-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="d85aa-175">サブドメイン</span><span class="sxs-lookup"><span data-stu-id="d85aa-175">Subdomain</span></span> | <span data-ttu-id="d85aa-176">お客様のテナントで</span><span class="sxs-lookup"><span data-stu-id="d85aa-176">In a customer tenant</span></span> |   <span data-ttu-id="d85aa-177">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="d85aa-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="d85aa-178">adventureworks.com</span></span> | <span data-ttu-id="d85aa-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="d85aa-180">ベースおよびサブドメインを構成するには、以下に示す手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="d85aa-181">例では、ベースのドメイン名 (customers.adatum.biz) と 1 つの顧客 (sbc1.customers.adatum.biz では、Woodgrove Bank のテナント) 用のサブドメイン構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="d85aa-182">キャリア テナントでベースのドメイン名を登録します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="d85aa-183">**キャリアのテナントでは、これらのアクションが実行されます。**</span><span class="sxs-lookup"><span data-stu-id="d85aa-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="d85aa-184">キャリア テナント内の適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="d85aa-185">大域管理者として Office 365 管理センターにサインインする場合にのみ、新しいドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d85aa-185">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="d85aa-186">ある役割を検証するにサインインしてください Microsoft 365 の管理センター (https://portal.office.com)**ユーザー**には、 > **アクティブなユーザー**、グローバル管理者ロールがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="d85aa-187">管理者の役割と Office 365 のロールを割り当てる方法の詳細については、 [Office 365 の管理者の役割](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="d85aa-188">テナント ベースのドメインを追加し、そのことを確認</span><span class="sxs-lookup"><span data-stu-id="d85aa-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="d85aa-189">Microsoft 365 管理センターでは、**セットアップ**に移動 > **ドメイン** > **ドメインを追加**します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="d85aa-190">**自分が所有するドメインを入力してください**] ボックスで、ベースのドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="d85aa-191">次の例では、ベースのドメインとは、 *customers.adatum.biz*です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![ベースのドメインを追加します。](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="d85aa-193">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-193">Click **Next**.</span></span>
4. <span data-ttu-id="d85aa-194">例では、テナントは既に検証済みのドメイン名として adatum.biz を持っています。</span><span class="sxs-lookup"><span data-stu-id="d85aa-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="d85aa-195">ウィザードは要求されません追加の検証 customers.adatum.biz が既に登録されている名前のサブドメインであるためです。</span><span class="sxs-lookup"><span data-stu-id="d85aa-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="d85aa-196">ただし、前に確認されていませんが、FQDN を追加する場合は、検証のプロセスを経由する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="d85aa-197">検証のプロセスでは、[以下に説明](#add-a-subdomain-to-the-customer-tenant-and-verify-it)します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![確認ドメイン名の確認](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="d85aa-199">[**次へ**] をクリックし、[ **DNS の設定の更新**] ページで、 **DNS レコードを自分で追加します**を選択して [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="d85aa-200">[次へ] ページですべての値をオフに場合を除き、ビジネスの交換方法、SharePoint、またはチームと Skype のドメイン名を使用するには)、[**次へ**] をクリックし、 **[完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="d85aa-201">セットアップの完了状態では、新しいドメインを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![ドメインの完全なセットアップのステータスを表示](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="d85aa-203">ドメイン名を有効化します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-203">Activate the domain name</span></span>

<span data-ttu-id="d85aa-204">ドメイン名を登録した後、少なくとも 1 人のユーザーを追加することによってアクティブ化し、作成した基本ドメインと一致する SIP アドレスの FQDN の部分での SIP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-204">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="d85aa-205">*Office 365 テナントのユーザーの追加の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="d85aa-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="d85aa-206">例: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-206">For example: test@customers.adatum.biz</span></span>

![基本ドメインのアクティブ化ページ](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="d85aa-208">お客様のテナントにサブドメイン名を登録します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="d85aa-209">すべてのお客様の固有のサブドメイン名を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="d85aa-210">この例では、既定のドメイン名 woodgrovebank.us のテナントにサブドメインの sbc1.customers.adatum.biz を作成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="d85aa-211">**お客様のテナントには、以下のすべてのアクションです。**</span><span class="sxs-lookup"><span data-stu-id="d85aa-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="d85aa-212">お客様のテナント内の適切な権限があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="d85aa-213">大域管理者として Office 365 管理センターにサインインする場合にのみ、新しいドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d85aa-213">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="d85aa-214">ある役割を検証するにサインインしてください Microsoft 365 の管理センター (https://portal.office.com)**ユーザー**には、 > **アクティブなユーザー**、グローバル管理者ロールがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="d85aa-215">管理者の役割と Office 365 のロールを割り当てる方法の詳細については、 [Office 365 の管理者の役割](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="d85aa-216">お客様のテナントにサブドメインを追加して、そのことを確認</span><span class="sxs-lookup"><span data-stu-id="d85aa-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="d85aa-217">Microsoft 365 管理センターでは、**セットアップ**に移動 > **ドメイン** > **ドメインを追加**します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="d85aa-218">**自分が所有するドメインを入力してください**] ボックスには、このテナントのサブドメインの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="d85aa-219">次の例では、サブドメインとは、sbc1.customers.adatum.biz です。</span><span class="sxs-lookup"><span data-stu-id="d85aa-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![お客様のサブドメインを追加します。](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="d85aa-221">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-221">Click **Next**.</span></span>
4. <span data-ttu-id="d85aa-222">テナントの FQDN が登録されたことはありません。</span><span class="sxs-lookup"><span data-stu-id="d85aa-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="d85aa-223">次の手順でドメインを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="d85aa-224">**代わりに TXT レコードを追加する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-224">Select **Add a TXT record instead**.</span></span> 

    ![[ドメインの確認] ページのオプション](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="d85aa-226">[**次へ**] をクリックし、ドメイン名を確認するのには生成されたテキスト値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![[ドメインの確認] ページのテキスト レコード](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="d85aa-228">配送業者の DNS ホスティング プロバイダーの前の手順からの値は、TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![配送業者の DNS ホスティング プロバイダーで TXT レコードを作成します。](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="d85aa-230">詳細については、 [Office 365 のすべての DNS ホスティング プロバイダーを作成する DNS レコード](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="d85aa-231">お客様の Microsoft 365 管理センターに戻るし、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="d85aa-232">[次へ] ページでは、 **DNS レコードを自分で追加します**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![DNS の更新の設定] ページのオプション](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="d85aa-234">**オンライン サービスの選択**] ページで、[すべてのオプションをオフにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![オンライン サービス ページの選択]](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="d85aa-236">**DNS の更新の設定**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![DNS の更新の設定] ページ](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="d85aa-238">状態で**セットアップを完了**を確認します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![完全なセットアップのステータスを表示するページ](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="d85aa-240">サブドメイン名をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="d85aa-240">Activate the subdomain name</span></span>

<span data-ttu-id="d85aa-241">ドメイン名を登録した後には、少なくとも 1 人のユーザーを追加することによってアクティブ化し、お客様のテナントで作成したサブドメインに一致する SIP アドレスの FQDN の部分での SIP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85aa-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="d85aa-242">*Office 365 テナントのユーザーの追加の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="d85aa-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="d85aa-243">例: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d85aa-243">For example: test@sbc1.customers.adatum.biz</span></span>

![サブドメインのページのアクティブ化](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="d85aa-245">トランクとプロビジョニングのユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="d85aa-246">技術の採用プログラムで受信したフィードバックに基づき、マイクロソフトは、プロセスを簡素化するお客様のテナントのトランクを作成するプロセスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="d85aa-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="d85aa-247">このページのドキュメントの更新を監視し、次の詳細についてはマイクロソフト テクニカル コミュニティ ブログしてください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="d85aa-248">新しい CSonlinePSTNGateway コマンドを使用して顧客のドメインには、トランクを作成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="d85aa-249">トランクの FQDN が**必要**では、顧客用に作成されたサブドメインと一致します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="d85aa-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-250">For example:</span></span>

<span data-ttu-id="d85aa-251">*新しい-CSOnlinePSTNGateway-FQDN sbc1.customers.adatum.biz SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="d85aa-251">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="d85aa-252">電話番号を持つユーザーをプロビジョニングし、音声のルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-252">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="d85aa-253">新規の CSOnlinePSTNGateway の詳細については、ユーザーのプロビジョニングと、音声のルーティングを構成するを参照してください[直接ルーティングを構成](direct-routing-configure.md)します。</span><span class="sxs-lookup"><span data-stu-id="d85aa-253">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="d85aa-254">サブドメインの FQDN 名を送信する連絡先のヘッダーに設定する方法についての[SBC の製造元の指示](#deploy-and-configure-the-sbc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85aa-254">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

