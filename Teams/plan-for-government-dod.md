---
title: Office 365 Government - DoD 展開
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: IT のプロが、米国政府の DoD 規制Officeデータを処理するエンティティでの 365 の展開を支援するガイダンスです。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 954eb24cd0d6c79ab3fd30e22521660d2afeb08e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909161"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="ffb35-103">Office 365 Government の計画 - DoD 展開</span><span class="sxs-lookup"><span data-stu-id="ffb35-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="ffb35-104">このガイダンスは、Office 365 Government – DoD の使用がこれらの要件を満たすために適切である、政府の規制と要件の対象となるデータを扱う、米国連邦政府機関のエンティティまたは他のエンティティで Office 365 の展開を推進している IT プロを対象とします。</span><span class="sxs-lookup"><span data-stu-id="ffb35-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb35-105">組織が既に Office 365 Government – DoD の利用資格要件を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="ffb35-106">手順 1.</span><span class="sxs-lookup"><span data-stu-id="ffb35-106">Step 1.</span></span> <span data-ttu-id="ffb35-107">組織が 365 Government - DoD Office必要であり、資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="ffb35-108">Office 365 Government - DoD 環境は、クラウド サービスに関する米国政府の要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="ffb35-109">Office 365 の機能を利用できるだけでなく、組織は Office 365 Government – DoD 固有の次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="ffb35-110">組織の顧客コンテンツは、企業や 365 サービスの顧客コンテンツから論理的に分離され、Office 365 サービスから分離されます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="ffb35-111">組織の顧客コンテンツは米国内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="ffb35-112">組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="ffb35-113">Office 365 Government – DoD は、米国の公共機関のお客様に必要な認定と認定に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ffb35-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="ffb35-114">Office 365 Government – DoD プランの詳細については、Office [365 Government](https://products.office.com/government/compare-office-365-government-plans)プラン (利用資格要件を含む) を [参照](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)してください。</span><span class="sxs-lookup"><span data-stu-id="ffb35-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="ffb35-115">Office [365 US Government](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) サービスの説明では、米国内のコンプライアンス要件を満たしていることを中心にしたプラットフォームの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="ffb35-116">サービスの説明の情報テーブルを Excel ブックに転送し、組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たすという 2 つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="ffb35-117">その後、このリストを同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ffb35-119">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="ffb35-119">Decision points</span></span>|<ul><li><span data-ttu-id="ffb35-120">365 Office - DoD が組織に適したかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="ffb35-121">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="ffb35-122">Office 365 Government - DoD は米国でのみご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="ffb35-123">米国政府機関以外のお客様は [、365 政府機関向けプランOffice選択できます](https://products.office.com/en/government/compare-office-365-government-plans)。</span><span class="sxs-lookup"><span data-stu-id="ffb35-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="ffb35-124">手順 2.</span><span class="sxs-lookup"><span data-stu-id="ffb35-124">Step 2.</span></span> <span data-ttu-id="ffb35-125">Office 365 Government に申請する - DoD</span><span class="sxs-lookup"><span data-stu-id="ffb35-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="ffb35-126">このサービスが組織に合っている場合は、このサービスを申請する [プロセスを開始します](https://products.office.com/government/eligibility-validation)。</span><span class="sxs-lookup"><span data-stu-id="ffb35-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="ffb35-127">手順 3.</span><span class="sxs-lookup"><span data-stu-id="ffb35-127">Step 3.</span></span> <span data-ttu-id="ffb35-128">365 Office - DoD の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="ffb35-129">管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定を変更する前にコンプライアンスへの影響を考慮することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffb35-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="ffb35-131">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="ffb35-131">Decision point</span></span>|<ul><li><span data-ttu-id="ffb35-132">既定の Office 365 Government - DoD セキュリティ設定を変更する必要があるかどうかを決定し、最初に変更の影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="ffb35-133">手順 4.</span><span class="sxs-lookup"><span data-stu-id="ffb35-133">Step 4.</span></span> <span data-ttu-id="ffb35-134">Office 365 Government - DoD で使用できる Teams の機能を理解する</span><span class="sxs-lookup"><span data-stu-id="ffb35-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="ffb35-135">政府機関向けクラウド のお客様の要件に対応するために、エンタープライズ プランの Office 365 Government - DoD と Teams の Teams にはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="ffb35-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="ffb35-136">使用できる機能を確認するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffb35-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="ffb35-137">Microsoft Teams サービスの説明</span><span class="sxs-lookup"><span data-stu-id="ffb35-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="ffb35-138">手順 5.</span><span class="sxs-lookup"><span data-stu-id="ffb35-138">Step 5.</span></span> <span data-ttu-id="ffb35-139">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="ffb35-139">Plan for governance</span></span>

<span data-ttu-id="ffb35-140">ガバナンスの要件と、ガバナンスを満たす方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="ffb35-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="ffb35-141">詳細については [、「Teams のガバナンスの計画」](plan-teams-governance.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffb35-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="ffb35-142">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="ffb35-142">Decision point</span></span> |<ul><li><span data-ttu-id="ffb35-143">Teams のガバナンス計画のガイドラインに従って、ガバナンス要件を [決定して文書化します](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb35-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="ffb35-144">手順 6.</span><span class="sxs-lookup"><span data-stu-id="ffb35-144">Step 6.</span></span> <span data-ttu-id="ffb35-145">共同作業のために Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="ffb35-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="ffb35-146">Office 365 Government – DoD にオンボードされた後は、「Microsoft Teams を展開する方法」で説明されている推奨される展開パス [に従います](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb35-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="ffb35-147">導入および変更管理チームと Teams のチャンピオンと必ず関与してください。</span><span class="sxs-lookup"><span data-stu-id="ffb35-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="ffb35-148">また、FastTrack または選択 [したパートナー](https://www.microsoft.com/fasttrack) と一緒にサービスをオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="ffb35-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="ffb35-149">DOD 環境向け Mac Teams クライアントはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ffb35-149">The Mac Teams client for DOD environments is not yet supported.</span></span>
