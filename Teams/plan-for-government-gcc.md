---
title: マイクロソフト チームが Microsoft 365 政府の GCC の展開の計画します。
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: 米国政府の規制の対象となるデータを処理するエンティティでドライブ Office 365 の展開を IT プロフェッショナルのためのガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34c13d9094512a52c334acf2b660b11b6579c886
ms.sourcegitcommit: 63c391ce9144ba5b296050ac189f77f5cea78707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "23973687"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="fbdd0-103">Microsoft 365 政府の GCC の展開の計画</span><span class="sxs-lookup"><span data-stu-id="fbdd0-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="fbdd0-104">このガイダンスは米国連邦政府、状態、航空写真や民族のお、ローカル政府機関や政府の規制や要件の対象となるデータを処理する他のエンティティで、Office 365 の導入を促進する IT プロフェッショナルには、Microsoft の使用365 政府の GCC は、これらの要件を満たすために適しています。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="fbdd0-105">組織が既に Microsoft 365 政府の GCC の適格性の要件が満たされるとに適用され、プログラムに受け入れられた、1 ~ 4 の手順をスキップして、展開を開始するのには 5 の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 through 4 and go directly to step 5 to begin your deployment.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="fbdd0-106">手順 1 です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-106">Step 1.</span></span> <span data-ttu-id="fbdd0-107">組織が Microsoft 365 政府の GCC を必要があるし、適格性の要件を満たしているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="fbdd0-108">Microsoft 365 政府の GCC 環境を提供米国への準拠 FedRAMP 中、刑事裁判および連邦の税情報システム (CJI と FTI のデータ型) の要件など、クラウド サービスの政府の要件。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="fbdd0-109">Office 365 の機能を楽しむだけでなくは、組織はマイクロソフト 365 政府の GCC に固有の以下の機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="fbdd0-110">組織の顧客のコンテンツが Microsoft の商用の Office 365 サービスでお客様のコンテンツ論理的に分離します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="fbdd0-111">組織の顧客のコンテンツは、米国内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="fbdd0-112">組織の顧客のコンテンツへのアクセスは、スクリーンの Microsoft の担当者に限定されます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="fbdd0-113">Microsoft 365 政府の GCC は、証明書および米国の公的機関のお客様に必要な認定に準拠します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="fbdd0-114">Microsoft 365 政府 - 米国政府の[Office 365 の政府の計画](https://products.office.com/government/compare-office-365-government-plans)などの[特典を受ける](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)お客様は、提供する GCC の詳細についてを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="fbdd0-115">[Office 365 の米国政府のサービスの説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点は、米国内でのコンプライアンス要件を満たすことの中心は、について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="fbdd0-116">サービスの説明内の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます:**はい/いいえ、組織内での関連性**と**Y か N は、自分の組織のニーズに対応**します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="fbdd0-117">このサービスが組織のニーズを満たしていることを確認するのには、同僚と、この一覧を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="fbdd0-118">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="fbdd0-118">Decision points</span></span>|<ul><li><span data-ttu-id="fbdd0-119">Microsoft 365 政府の GCC は、組織の適切なかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-119">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="fbdd0-120">組織が適格性の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="fbdd0-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="fbdd0-121">Next step</span></span>|<ul><li><span data-ttu-id="fbdd0-122">Microsoft 365 政府の GCC が提供する機能を理解します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-122">Understand the capabilities provided by Microsoft 365 Government - GCC.</span></span></li></ul>|

> [!Note]
> <span data-ttu-id="fbdd0-123">Microsoft 365 政府の GCC をアメリカ合衆国ではできるだけです。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-123">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="fbdd0-124">-米国以外の政府機関のお客様は、いくつかの[Office 365 の政府の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-124">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="fbdd0-125">手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-125">Step 2.</span></span> <span data-ttu-id="fbdd0-126">機能は、現在利用できないか、既定で無効になっているを理解します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-126">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="fbdd0-127">Microsoft 365 政府の GCC をいくつかの相違がある、政府のクラウドのお客様の要件に合わせて、およびエンタープライズのプランです。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-127">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="fbdd0-128">次の表に記載されている機能はご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-128">The features listed in the following table are unavailable.</span></span>

| <span data-ttu-id="fbdd0-129">機能</span><span class="sxs-lookup"><span data-stu-id="fbdd0-129">Feature</span></span>                     | <span data-ttu-id="fbdd0-130">理由</span><span class="sxs-lookup"><span data-stu-id="fbdd0-130">Reason</span></span>            |
|-----------------------------|-------------------|
| <span data-ttu-id="fbdd0-131">通話とミーティングのレコーディング</span><span class="sxs-lookup"><span data-stu-id="fbdd0-131">Call and Meeting Recording</span></span>  | <span data-ttu-id="fbdd0-132">記録はマイクロソフトのストリームは、将来的に米国政府の計画で使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-132">Recording is dependent on Microsoft Stream, which will be available in US Government plans in the future.</span></span> |
| <span data-ttu-id="fbdd0-133">アプリ</span><span class="sxs-lookup"><span data-stu-id="fbdd0-133">Apps</span></span>       | <span data-ttu-id="fbdd0-134">アプリケーション (コンポーネント、タブ、コネクタなど) は使用できません、最初に、利用できるように、すべてのコンポーネントは、FedRAMP 中コンプライアンス基準を満たしてとすぐに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-134">Apps (such as bots, tabs, and connectors) won’t be available initially, but we’re working to make them available as soon as all their components meet the FedRAMP Moderate compliance bar.</span></span> |
| <span data-ttu-id="fbdd0-135">チャネルを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-135">Email a channel</span></span>             | <span data-ttu-id="fbdd0-136">政府の計画では、現在のアーキテクチャの機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-136">The current feature architecture isn’t supported in government plans.</span></span> |
| <span data-ttu-id="fbdd0-137">プレゼンスの統合</span><span class="sxs-lookup"><span data-stu-id="fbdd0-137">Unified Presence</span></span>            | <span data-ttu-id="fbdd0-138">私たちはこの重要な機能の最初の企業のお客様のための仕上げの作業です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-138">We’re finishing work for our enterprise customers first for this important feature.</span></span> <span data-ttu-id="fbdd0-139">政府の顧客に利用可能な将来的にします。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-139">It will be available to government customers in the future.</span></span> |
| <span data-ttu-id="fbdd0-140">チームとデバイス間の相互運用機能のチャット ユーザー</span><span class="sxs-lookup"><span data-stu-id="fbdd0-140">Interop chat between Teams & SfB users</span></span>            | <span data-ttu-id="fbdd0-141">相互運用機能は、統合プレゼンス サービス (UPS) に依存して、UPS の GCC のチームのテナントを有効にするまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-141">Interop is dependent on Unified Presence Service (UPS) and cannot work until GCC Teams Tenants are enabled for UPS.</span></span> |
| <span data-ttu-id="fbdd0-142">電子メール通知</span><span class="sxs-lookup"><span data-stu-id="fbdd0-142">Email Notifications</span></span>         | <span data-ttu-id="fbdd0-143">米国政府の計画では、現在のアーキテクチャの機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-143">The current feature architecture isn’t supported in the US Government plans.</span></span> <span data-ttu-id="fbdd0-144">作業は、この機能が使用できるように米国政府の計画の顧客、将来的に継続的です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-144">Work is ongoing to make this feature available to US Government plan customers in the future.</span></span> |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="fbdd0-145">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="fbdd0-145">Decision point</span></span>|<ul><li><span data-ttu-id="fbdd0-146">Microsoft 365 政府の GCC の機能セットが、組織のニーズを満たしているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-146">Decide whether the Microsoft 365 Government - GCC feature set meets your organization’s needs.</span></span></li></ul> |
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="fbdd0-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="fbdd0-147">Next step</span></span>|<ul><li><span data-ttu-id="fbdd0-148">既定のセキュリティ設定を理解します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-148">Understand default security settings.</span></span></li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="fbdd0-149">ステップ 3 です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-149">Step 3.</span></span> <span data-ttu-id="fbdd0-150">Microsoft 365 政府の GCC のデフォルトのセキュリティ設定を理解します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-150">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="fbdd0-151">[管理とセキュリティの設定](enable-features-office-365.md)を見直し、それらを変更し、既定のセキュリティ設定を変更する前に、コンプライアンスへの影響を検討する前に時間がかかることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-151">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="fbdd0-152">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="fbdd0-152">Decision point</span></span>|<ul><li><span data-ttu-id="fbdd0-153">Microsoft 365 政府の GCC のセキュリティ設定を既定値のいずれかを変更するかどうかの変更の影響を理解して最初に解決する可能性がありますを行うかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-153">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impacts of any changes you might make.</span></span></li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="fbdd0-154">手順 4 します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-154">Step 4.</span></span> <span data-ttu-id="fbdd0-155">Microsoft 365 政府の GCC を適用します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-155">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="fbdd0-156">持つことに、このサービスがお客様の組織は、[このサービスは、ここに適用する](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-156">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="fbdd0-157">手順 5 です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-157">Step 5.</span></span> <span data-ttu-id="fbdd0-158">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="fbdd0-158">Plan for governance</span></span>

<span data-ttu-id="fbdd0-159">コーポレート ・ ガバナンスとどのように満たすことがお客様の要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-159">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="fbdd0-160">詳細については、[チームの管理のための計画](plan-teams-governance.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-160">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="fbdd0-161">手順 6。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-161">Step 6.</span></span> <span data-ttu-id="fbdd0-162">チームの共同作業を展開します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-162">Deploy Teams for collaboration</span></span>

<span data-ttu-id="fbdd0-163">Microsoft 365 政府の GCC では、onboarded をした後[FastTrack](https://fasttrack.microsoft.com/fasttrack-faq)と、選択したパートナー サービスにオンボードを使用する標準的な展開方法に従います。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-163">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="fbdd0-164">準備ができたら、[チーム、およびチャネルを通じて、組織内でのコラボレーションを有効に](teams-overview.md)するチームを展開します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-164">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="fbdd0-165">採用し、変更管理のチームまたはチームのエキスパートと協力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-165">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="fbdd0-166">手順 7 です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-166">Step 7.</span></span> <span data-ttu-id="fbdd0-167">会議および音声のチームを配置します。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-167">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="fbdd0-168">広く利害関係者グループにチームを使用して、会議や[クラウドのボイス機能](cloud-voice-deployment.md)を展開するための計画を開始する絶好の機会です。</span><span class="sxs-lookup"><span data-stu-id="fbdd0-168">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

