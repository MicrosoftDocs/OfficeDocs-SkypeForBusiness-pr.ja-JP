---
title: Office 365 Government-GCC 展開
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国政府規制の対象となるデータを処理するエンティティで Office 365 の展開を推進する IT 担当者向けガイダンス
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
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581248"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="5c7fc-103">Office 365 Government-GCC 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="5c7fc-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="5c7fc-104">このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人、州、地方、、または行政機関の団体またはその他の法人で、これらの要件を満たすために Office 365 Government-GCC の使用が適している場合に、Office 365 の展開を行う IT プロフェッショナルを対象としています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="5c7fc-105">2020年3月 26[日: GCC 向けのダウンロード可能なクイックスタートガイド](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)をお見逃しなく。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c7fc-106">Microsoft Teams では、coronavirus (COVID-19) pandemic のため、オンライン通話、音声/ビデオ会議に大きなスパイクが発生しています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="5c7fc-107">優れた通話の増加に対応し、継続性と可用性を確保するために、microsoft Teams の音声/ビデオサーバは、microsoft Teams の商用データセンターと行政機関のデータセンターでの処理能力を活用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="5c7fc-108">これらのオーディオ/ビデオサーバーは、米国の Microsoft Azure FedRAMP 高認定境界サーバー内に存在し、お客様のコンテンツは保存しません。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="5c7fc-109">ただし、このようなサーバーは、通話や会議のための音声とビデオを処理しており、この中間的な間、当社の商用スタッフで動作しています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="5c7fc-110">認定された審査担当者は、これらのサーバーの対話的なログ出力を確認して、顧客データにアクセスできる可能性があるサーバーを監視しています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="5c7fc-111">認定担当者は、お客様のコンテンツへのアクセスに必要な GCC の要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="5c7fc-112">審査の要件の詳細については、「 [GCC サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="5c7fc-113">お客さまのサポートにご協力いただき、ありがとうございました。 skype のサービスは、これらの特別なタイミングで利用可能で信頼できることを確認するための措置となります。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="5c7fc-114">組織が既に Office 365 Government-GCC の資格要件を満たし、プログラムに承認された場合は、手順1と2をスキップして、手順3に進んでください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="5c7fc-115">手順1</span><span class="sxs-lookup"><span data-stu-id="5c7fc-115">Step 1.</span></span> <span data-ttu-id="5c7fc-116">組織に Office 365 Government-GCC が必要かどうかを判断し、資格要件を満たしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="5c7fc-117">Office 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="5c7fc-118">Office 365 の機能を活用できるだけでなく、Office 365 Government-GCC に固有の次の機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="5c7fc-119">組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="5c7fc-120">組織の顧客コンテンツは、米国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="5c7fc-121">組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="5c7fc-122">Office 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="5c7fc-123">米国政府機関向けの Office 365 Government-GCC のお客様向けの詳細については、「[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="5c7fc-124">[Office 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="5c7fc-125">サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織\*\*\*\*のニーズに応じ**て2つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="5c7fc-126">次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5c7fc-128">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5c7fc-128">Decision points</span></span>|<ul><li><span data-ttu-id="5c7fc-129">組織に合わせて Office 365 Government と GCC のどちらを使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="5c7fc-130">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="5c7fc-131">Office 365 Government-GCC はアメリカ国内でのみご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="5c7fc-132">米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="5c7fc-133">手順2</span><span class="sxs-lookup"><span data-stu-id="5c7fc-133">Step 2.</span></span> <span data-ttu-id="5c7fc-134">Office 365 Government に適用する-GCC</span><span class="sxs-lookup"><span data-stu-id="5c7fc-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="5c7fc-135">このサービスが組織に適していると判断された場合は、[ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="5c7fc-136">手順3</span><span class="sxs-lookup"><span data-stu-id="5c7fc-136">Step 3.</span></span> <span data-ttu-id="5c7fc-137">Office 365 Government-GCC の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="5c7fc-138">[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5c7fc-140">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5c7fc-140">Decision point</span></span>|<ul><li><span data-ttu-id="5c7fc-141">既定の Office 365 Government-GCC のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="5c7fc-142">手順4。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-142">Step 4.</span></span> <span data-ttu-id="5c7fc-143">現在、どの機能が既定で利用できないか、無効になっているかを理解する。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="5c7fc-144">政府機関のクラウドのお客様の要件に対応するため、Office 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="5c7fc-145">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="5c7fc-146">Microsoft Teams サービスの説明</span><span class="sxs-lookup"><span data-stu-id="5c7fc-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="5c7fc-147">GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5c7fc-149">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5c7fc-149">Decision point</span></span>|<ul><li><span data-ttu-id="5c7fc-150">Teams 機能セットが組織のニーズを満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="5c7fc-151">手順5</span><span class="sxs-lookup"><span data-stu-id="5c7fc-151">Step 5.</span></span> <span data-ttu-id="5c7fc-152">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="5c7fc-152">Plan for governance</span></span>

<span data-ttu-id="5c7fc-153">ガバナンスの要件と、それらをどのように満たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="5c7fc-154">詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5c7fc-156">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5c7fc-156">Decision point</span></span>|<ul><li><span data-ttu-id="5c7fc-157">[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="5c7fc-158">手順6</span><span class="sxs-lookup"><span data-stu-id="5c7fc-158">Step 6.</span></span> <span data-ttu-id="5c7fc-159">チームをコラボレーションのために展開する</span><span class="sxs-lookup"><span data-stu-id="5c7fc-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="5c7fc-160">Office 365 Government – GCC に onboarded したら、「 [Microsoft Teams をロールアウトする方法](How-to-roll-out-teams.md)」に記載されている展開の推奨パスに従います。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5c7fc-161">お客様の導入と変更管理チームやチームのチャンピオンに協力してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="5c7fc-162">また、 [Fasttrack](https://www.microsoft.com/fasttrack)または選択したパートナーと連携してサービスを稼働させることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="5c7fc-163">手順7</span><span class="sxs-lookup"><span data-stu-id="5c7fc-163">Step 7.</span></span> <span data-ttu-id="5c7fc-164">会議と音声のチームを展開する</span><span class="sxs-lookup"><span data-stu-id="5c7fc-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="5c7fc-165">これは、より幅広いステークホルダーグループで Teams を使用して、会議や[クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。</span><span class="sxs-lookup"><span data-stu-id="5c7fc-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

