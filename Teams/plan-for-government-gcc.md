---
title: Microsoft 365Government - GCC デプロイ
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT のプロが、米国政府規制Microsoft 365データを処理するエンティティでのデプロイを支援するガイダンス
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117835"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="d4534-103">Microsoft 365 Government の計画 - GCCデプロイ</span><span class="sxs-lookup"><span data-stu-id="d4534-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="d4534-104">このガイダンスは、Microsoft 365 Government - GCC の使用がこれらの要件を満たすために適切である、政府の規制と要件の対象となるデータを処理する米国連邦政府、州、地方、部族、または地域政府のエンティティ、または他のエンティティへの Microsoft 365 の展開を推進している IT プロを対象とします。</span><span class="sxs-lookup"><span data-stu-id="d4534-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="d4534-105">新しい 2020 年 3 月 26 日: ダウンロード可能なクイック スタート ガイドをお見逃[GCC。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d4534-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4534-106">Microsoft Teamsウイルス (COVID-19) パンデミックにより、オンライン通話や音声/ビデオ会議が急増しています。</span><span class="sxs-lookup"><span data-stu-id="d4534-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="d4534-107">これまでにない呼び出しの増加に対応し、継続性と可用性を確保するために、Microsoft は、Microsoft Teams GCC オーディオ/ビデオ サーバーが商用データセンターと政府機関のデータセンターの処理能力を活用できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="d4534-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="d4534-108">これらのオーディオ/ビデオ サーバーは、米国の Microsoft Azure FedRAMP High 認定境界サーバー内に存在し、顧客コンテンツを格納しません。</span><span class="sxs-lookup"><span data-stu-id="d4534-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="d4534-109">ただし、これらのサーバーは通話や会議の音声とビデオを処理し、この中間期間中は業務スタッフの下で動作しています。</span><span class="sxs-lookup"><span data-stu-id="d4534-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="d4534-110">有資格の審査担当者は、これらのサーバーへの対話型ログオンを確認することで、顧客データへの潜在的なアクセスをこれらのサーバーで監視しています。</span><span class="sxs-lookup"><span data-stu-id="d4534-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="d4534-111">資格のある担当者は、GCCコンテンツにアクセスするために必要な要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="d4534-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="d4534-112">スクリーニング要件の詳細については、「サービスの説明[」GCC参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)。</span><span class="sxs-lookup"><span data-stu-id="d4534-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="d4534-113">これらの特別な時間にサービスを確実に利用し、信頼性を維持するための手順を実行して、サポートに感謝します。</span><span class="sxs-lookup"><span data-stu-id="d4534-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="d4534-114">組織が既に Microsoft 365 Government - GCC の資格要件を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。</span><span class="sxs-lookup"><span data-stu-id="d4534-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="d4534-115">手順 1.</span><span class="sxs-lookup"><span data-stu-id="d4534-115">Step 1.</span></span> <span data-ttu-id="d4534-116">組織が Government を使用する必要Microsoft 365、GCC要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4534-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="d4534-117">Microsoft 365 Government - GCC 環境は、FedRAMP Moderate などのクラウド サービスに関する米国政府の要件、および刑事判事および連邦税情報システム (CJI および FTI データ型) の要件に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="d4534-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="d4534-118">組織は、Microsoft 365 の機能を利用できるだけでなく、Microsoft 365 Government - GCC に固有の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d4534-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="d4534-119">組織の顧客コンテンツは、Microsoft の商用サービスの顧客コンテンツMicrosoft 365分離されます。</span><span class="sxs-lookup"><span data-stu-id="d4534-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="d4534-120">組織の顧客コンテンツは米国内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d4534-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="d4534-121">組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。</span><span class="sxs-lookup"><span data-stu-id="d4534-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="d4534-122">Microsoft 365Government - GCC、米国の公的機関のお客様に必要な認定と認定に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="d4534-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="d4534-123">米国政府のお客様向け Microsoft 365 Government - GCC オファリングの詳細については[、Microsoft 365 Government](https://products.office.com/government/compare-office-365-government-plans)プランに関するページを参照してください。資格要件を[含む](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements))。</span><span class="sxs-lookup"><span data-stu-id="d4534-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="d4534-124">米国[政府Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)の説明では、米国内のコンプライアンス要件を満たしていることを中心にしたプラットフォームの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4534-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="d4534-125">サービスの説明の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます。組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たします。</span><span class="sxs-lookup"><span data-stu-id="d4534-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="d4534-126">その後、この一覧を同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="d4534-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d4534-128">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d4534-128">Decision points</span></span>|<ul><li><span data-ttu-id="d4534-129">組織に適Microsoft 365 Government - GCCを決定します。</span><span class="sxs-lookup"><span data-stu-id="d4534-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="d4534-130">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4534-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="d4534-131">Microsoft 365Government - GCCは米国でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4534-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="d4534-132">米国政府以外のお客様は、複数の政府機関向[けプランMicrosoft 365選択できます](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="d4534-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="d4534-133">手順 2.</span><span class="sxs-lookup"><span data-stu-id="d4534-133">Step 2.</span></span> <span data-ttu-id="d4534-134">Microsoft 365 Government - GCC に申し込む</span><span class="sxs-lookup"><span data-stu-id="d4534-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="d4534-135">このサービスが組織に正しいと決定した後、このサービスに適用するプロセスをここから [開始します](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="d4534-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="d4534-136">手順 3.</span><span class="sxs-lookup"><span data-stu-id="d4534-136">Step 3.</span></span> <span data-ttu-id="d4534-137">Government のMicrosoft 365 - 既定GCC設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4534-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="d4534-138">管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定に変更を加える前にコンプライアンスへの影響を考慮することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4534-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d4534-140">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d4534-140">Decision point</span></span>|<ul><li><span data-ttu-id="d4534-141">既定の Microsoft 365 Government - GCC セキュリティ設定を変更するかどうかを決定し、変更の影響を最初に把握します。</span><span class="sxs-lookup"><span data-stu-id="d4534-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="d4534-142">手順 4.</span><span class="sxs-lookup"><span data-stu-id="d4534-142">Step 4.</span></span> <span data-ttu-id="d4534-143">どの機能が現在使用できないか、既定で無効になっているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4534-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="d4534-144">政府機関向けクラウドのお客様の要件に対応するために、Government - Microsoft 365 プランと GCCプランEnterpriseがあります。</span><span class="sxs-lookup"><span data-stu-id="d4534-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="d4534-145">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4534-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="d4534-146">Microsoft Teamsの説明</span><span class="sxs-lookup"><span data-stu-id="d4534-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="d4534-147">GCC クラウドで他のワークロードを完全に利用できると、追加の統合作業が完了すると、Teams で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4534-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d4534-149">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d4534-149">Decision point</span></span>|<ul><li><span data-ttu-id="d4534-150">組織のニーズTeams機能セットを満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d4534-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="d4534-151">手順 5.</span><span class="sxs-lookup"><span data-stu-id="d4534-151">Step 5.</span></span> <span data-ttu-id="d4534-152">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="d4534-152">Plan for governance</span></span>

<span data-ttu-id="d4534-153">ガバナンスの要件とそれらを満たす方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="d4534-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="d4534-154">詳細については[、「Teams ガバナンスの](plan-teams-governance.md)計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4534-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d4534-156">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d4534-156">Decision point</span></span>|<ul><li><span data-ttu-id="d4534-157">ガバナンスの要件を決定し、文書化します。このガイドラインは、「Teams でのガバナンスの計画」[のガイドラインに従Teams。](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="d4534-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="d4534-158">手順 6.</span><span class="sxs-lookup"><span data-stu-id="d4534-158">Step 6.</span></span> <span data-ttu-id="d4534-159">コラボレーションTeamsをデプロイする</span><span class="sxs-lookup"><span data-stu-id="d4534-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="d4534-160">Microsoft 365 Government – GCC にオンボードした後は、「Microsoft Teams をロールアウトする方法」で説明されている推奨されるデプロイ パス[に従Microsoft Teams。](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4534-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="d4534-161">必ず、導入および変更管理チームと新しいTeamsしてください。</span><span class="sxs-lookup"><span data-stu-id="d4534-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="d4534-162">[また、FastTrack または選択したパートナーと](https://www.microsoft.com/fasttrack)一緒にサービスをオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="d4534-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="d4534-163">手順 7.</span><span class="sxs-lookup"><span data-stu-id="d4534-163">Step 7.</span></span> <span data-ttu-id="d4534-164">会議Teams音声用のビデオを展開する</span><span class="sxs-lookup"><span data-stu-id="d4534-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="d4534-165">また、幅広い関係者グループとTeamsを使用して、会議やクラウド音声機能の展開計画[を開始する場合にも最適な時間です](./cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="d4534-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>