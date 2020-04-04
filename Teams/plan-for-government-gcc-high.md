---
title: Microsoft 365 Government-GCC 高展開
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 米国政府規制の対象となるデータを処理するエンティティの Office 365 展開を推進する IT 担当者向けガイダンス
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
ms.openlocfilehash: 0b5111e61f6c545a7311280fa865c762e8498b86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137817"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="27a0f-103">Microsoft 365 Government の計画-GCC 高展開</span><span class="sxs-lookup"><span data-stu-id="27a0f-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="27a0f-104">このガイダンスは、米国連邦政府機関の法人またはその他の法人に Office 365 の展開を推進している IT プロフェッショナルを対象としています。ここでは、Microsoft 365 Government – GCC 高を使用することで、これらの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="27a0f-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="27a0f-105">組織が既に Microsoft 365 Government – GCC の高品質要件を満たし、プログラムに承認された場合は、手順1と2をスキップして、手順3に進んでください。</span><span class="sxs-lookup"><span data-stu-id="27a0f-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="27a0f-106">手順1</span><span class="sxs-lookup"><span data-stu-id="27a0f-106">Step 1.</span></span> <span data-ttu-id="27a0f-107">組織で Microsoft 365 Government-GCC 高が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="27a0f-108">Microsoft 365 Government-GCC 高環境では、クラウドサービスの米国政府の要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="27a0f-109">Office 365 の機能を活用できるように、組織は、Microsoft 365 Government に固有の次の機能を利用できます。 GCC High:</span><span class="sxs-lookup"><span data-stu-id="27a0f-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="27a0f-110">組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="27a0f-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="27a0f-111">組織の顧客コンテンツは、米国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="27a0f-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="27a0f-112">組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="27a0f-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="27a0f-113">Microsoft 365 Government – GCC High は、公的機関のお客様に必要な認定および accreditations に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="27a0f-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="27a0f-114">Microsoft 365 Government –米国政府のお客様向けの高度な機能については、「[資格の要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a0f-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="27a0f-115">[Office 365 US Government service の説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)では、プラットフォームの利点について説明します。この情報は、米国内での会議のコンプライアンス要件に基づいて中央に配置されています。</span><span class="sxs-lookup"><span data-stu-id="27a0f-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="27a0f-116">サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織\*\*\*\*のニーズに応じ**て2つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="27a0f-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="27a0f-117">次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="27a0f-119">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="27a0f-119">Decision points</span></span>|<ul><li><span data-ttu-id="27a0f-120">組織に対して Microsoft 365 Government-GCC 高が適切であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="27a0f-121">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="27a0f-122">Microsoft 365 Government-GCC 高はアメリカ国内でのみご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="27a0f-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="27a0f-123">米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="27a0f-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="27a0f-124">手順2</span><span class="sxs-lookup"><span data-stu-id="27a0f-124">Step 2.</span></span> <span data-ttu-id="27a0f-125">Microsoft 365 Government に適用する-GCC High</span><span class="sxs-lookup"><span data-stu-id="27a0f-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="27a0f-126">このサービスが組織に適していると判断された場合は、[このサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="27a0f-127">手順3</span><span class="sxs-lookup"><span data-stu-id="27a0f-127">Step 3.</span></span> <span data-ttu-id="27a0f-128">Microsoft 365 Government-GCC 高の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="27a0f-129">[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27a0f-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="27a0f-131">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="27a0f-131">Decision point</span></span>|<ul><li><span data-ttu-id="27a0f-132">既定の Microsoft 365 Government-GCC 高セキュリティ設定を変更する必要があるかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27a0f-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="27a0f-133">手順4。</span><span class="sxs-lookup"><span data-stu-id="27a0f-133">Step 4.</span></span> <span data-ttu-id="27a0f-134">Microsoft 365 Government で現在利用できる Teams 機能を理解する-GCC 高</span><span class="sxs-lookup"><span data-stu-id="27a0f-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="27a0f-135">政府機関向けクラウドのお客様の要件に対応するために、Microsoft 365 Government の Teams には、エンタープライズプランにおける GCC 高と Teams の間にいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="27a0f-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="27a0f-136">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a0f-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="27a0f-137">Microsoft Teams サービスの説明</span><span class="sxs-lookup"><span data-stu-id="27a0f-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="27a0f-138">手順5</span><span class="sxs-lookup"><span data-stu-id="27a0f-138">Step 5.</span></span> <span data-ttu-id="27a0f-139">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="27a0f-139">Plan for governance</span></span>

<span data-ttu-id="27a0f-140">ガバナンスの要件と、それらをどのように満たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="27a0f-141">詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a0f-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="27a0f-142">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="27a0f-142">Decision point</span></span> |<ul><li><span data-ttu-id="27a0f-143">[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</span><span class="sxs-lookup"><span data-stu-id="27a0f-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="27a0f-144">手順6</span><span class="sxs-lookup"><span data-stu-id="27a0f-144">Step 6.</span></span> <span data-ttu-id="27a0f-145">チームをコラボレーションのために展開する</span><span class="sxs-lookup"><span data-stu-id="27a0f-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="27a0f-146">Microsoft 365 Government – GCC High に onboarded したら、 [Microsoft Teams のロールアウト方法](How-to-roll-out-teams.md)に関する推奨される展開パスに従います。</span><span class="sxs-lookup"><span data-stu-id="27a0f-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="27a0f-147">お客様の導入と変更管理チームやチームのチャンピオンに協力してください。</span><span class="sxs-lookup"><span data-stu-id="27a0f-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="27a0f-148">また、 [Fasttrack](https://www.microsoft.com/fasttrack)または選択したパートナーと連携してサービスを稼働させることもできます。</span><span class="sxs-lookup"><span data-stu-id="27a0f-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

