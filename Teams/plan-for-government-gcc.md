---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 米国政府規制の対象となるデータを処理するエンティティで Office 365 の展開を推進する IT 担当者向けガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 025a1f22552fa8c196e9eeb4bee6b7e6e19eebdf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902456"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="60aad-103">Microsoft 365 Government-GCC 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="60aad-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="60aad-104">このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人向けの Office 365 の展開を推進している IT プロフェッショナル、または Microsoft の使用時に政府機関の規制と要件の対象となるデータを処理するその他のエンティティを対象としています。365 Government-GCC はこれらの要件を満たすのに適しています。</span><span class="sxs-lookup"><span data-stu-id="60aad-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="60aad-105">組織が既に Microsoft 365 Government-GCC の資格要件を満たし、プログラムに受け入れられている場合は、手順1と2をスキップして、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="60aad-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="60aad-106">手順1</span><span class="sxs-lookup"><span data-stu-id="60aad-106">Step 1.</span></span> <span data-ttu-id="60aad-107">組織に Microsoft 365 Government-GCC が必要かどうか、および資格要件を満たしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="60aad-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="60aad-108">Microsoft 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="60aad-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="60aad-109">Office 365 の機能を活用できるだけでなく、Microsoft 365 Government-GCC に固有の次の機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="60aad-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="60aad-110">組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="60aad-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="60aad-111">組織の顧客コンテンツは、米国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="60aad-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="60aad-112">組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="60aad-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="60aad-113">Microsoft 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="60aad-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="60aad-114">米国政府機関向け Microsoft 365 政府向けの GCC 製品の詳細については、「[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60aad-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="60aad-115">[Office 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="60aad-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="60aad-116">サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織\*\*\*\*のニーズに応じ**て2つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="60aad-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="60aad-117">次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60aad-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60aad-118">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="60aad-118">Decision points</span></span>|<ul><li><span data-ttu-id="60aad-119">組織に対して Microsoft 365 Government-GCC が適切であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="60aad-119">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="60aad-120">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60aad-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="60aad-121">Microsoft 365 Government-GCC は米国でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="60aad-121">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="60aad-122">米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="60aad-122">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="60aad-123">手順2</span><span class="sxs-lookup"><span data-stu-id="60aad-123">Step 2.</span></span> <span data-ttu-id="60aad-124">Microsoft 365 Government-GCC に適用する</span><span class="sxs-lookup"><span data-stu-id="60aad-124">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="60aad-125">このサービスが組織に適していると判断された場合は、[ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="60aad-125">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="60aad-126">手順3</span><span class="sxs-lookup"><span data-stu-id="60aad-126">Step 3.</span></span> <span data-ttu-id="60aad-127">Microsoft 365 Government-GCC の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="60aad-127">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="60aad-128">[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="60aad-128">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60aad-129">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="60aad-129">Decision point</span></span>|<ul><li><span data-ttu-id="60aad-130">Microsoft 365 Government の既定のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60aad-130">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="60aad-131">手順4。</span><span class="sxs-lookup"><span data-stu-id="60aad-131">Step 4.</span></span> <span data-ttu-id="60aad-132">現在、どの機能が既定で利用できないか、無効になっているかを理解する。</span><span class="sxs-lookup"><span data-stu-id="60aad-132">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="60aad-133">政府機関向けクラウドのお客様の要件に対応するため、Microsoft 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="60aad-133">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="60aad-134">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60aad-134">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="60aad-135">機能</span><span class="sxs-lookup"><span data-stu-id="60aad-135">Feature</span></span>                     | <span data-ttu-id="60aad-136">GCC</span><span class="sxs-lookup"><span data-stu-id="60aad-136">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="60aad-137">技術</span><span class="sxs-lookup"><span data-stu-id="60aad-137">Base</span></span> | <span data-ttu-id="60aad-138">ログイン</span><span class="sxs-lookup"><span data-stu-id="60aad-138">Login</span></span> | <span data-ttu-id="60aad-139">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-139">Available</span></span> |
| | <span data-ttu-id="60aad-140">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="60aad-140">Presence</span></span> | <span data-ttu-id="60aad-141">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-141">Available</span></span> |
| | <span data-ttu-id="60aad-142">統合されたプレゼンス (Skype for Business および Teams 統合)</span><span class="sxs-lookup"><span data-stu-id="60aad-142">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="60aad-143">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-143">Available</span></span> |
| <span data-ttu-id="60aad-144">処理</span><span class="sxs-lookup"><span data-stu-id="60aad-144">Activity</span></span> | <span data-ttu-id="60aad-145">クロス</span><span class="sxs-lookup"><span data-stu-id="60aad-145">Feed</span></span> | <span data-ttu-id="60aad-146">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-146">Available</span></span> |
|  | <span data-ttu-id="60aad-147">マイアクティビティ</span><span class="sxs-lookup"><span data-stu-id="60aad-147">My Activity</span></span> | <span data-ttu-id="60aad-148">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-148">Available</span></span> |
| <span data-ttu-id="60aad-149">チャット</span><span class="sxs-lookup"><span data-stu-id="60aad-149">Chat</span></span> | <span data-ttu-id="60aad-150">チャット</span><span class="sxs-lookup"><span data-stu-id="60aad-150">Conversation</span></span> | <span data-ttu-id="60aad-151">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-151">Available</span></span> |
| | <span data-ttu-id="60aad-152">ファイル</span><span class="sxs-lookup"><span data-stu-id="60aad-152">Files</span></span> | <span data-ttu-id="60aad-153">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-153">Available</span></span> |
| | <span data-ttu-id="60aad-154">組織図</span><span class="sxs-lookup"><span data-stu-id="60aad-154">Org chart</span></span> | <span data-ttu-id="60aad-155">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-155">Available</span></span> |
| | <span data-ttu-id="60aad-156">処理</span><span class="sxs-lookup"><span data-stu-id="60aad-156">Activity</span></span> | <span data-ttu-id="60aad-157">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-157">Available</span></span> |
| | <span data-ttu-id="60aad-158">相互運用 (1:1 チーム-Skype for Business チャット)</span><span class="sxs-lookup"><span data-stu-id="60aad-158">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="60aad-159">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-159">Available</span></span> |
| <span data-ttu-id="60aad-160">Teams</span><span class="sxs-lookup"><span data-stu-id="60aad-160">Teams</span></span> | <span data-ttu-id="60aad-161">チャネルメッセージ</span><span class="sxs-lookup"><span data-stu-id="60aad-161">Channel message</span></span> | <span data-ttu-id="60aad-162">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-162">Available</span></span> |
| | <span data-ttu-id="60aad-163">チャネルファイル</span><span class="sxs-lookup"><span data-stu-id="60aad-163">Channel files</span></span> | <span data-ttu-id="60aad-164">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-164">Available</span></span> |
| | <span data-ttu-id="60aad-165">OneNote タブ</span><span class="sxs-lookup"><span data-stu-id="60aad-165">OneNote tab</span></span> | <span data-ttu-id="60aad-166">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="60aad-166">On the Government backlog</span></span> |
| | <span data-ttu-id="60aad-167">チャネルをメールで送信する</span><span class="sxs-lookup"><span data-stu-id="60aad-167">Email a channel</span></span> | <span data-ttu-id="60aad-168">該当なし</span><span class="sxs-lookup"><span data-stu-id="60aad-168">Not available</span></span> |
| | <span data-ttu-id="60aad-169">メンバーの追加</span><span class="sxs-lookup"><span data-stu-id="60aad-169">Add member</span></span> | <span data-ttu-id="60aad-170">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-170">Available</span></span> |
| | <span data-ttu-id="60aad-171">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="60aad-171">Guest access</span></span> | <span data-ttu-id="60aad-172">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-172">Available</span></span> |
| <span data-ttu-id="60aad-173">会議</span><span class="sxs-lookup"><span data-stu-id="60aad-173">Meetings</span></span> | <span data-ttu-id="60aad-174">会議の予約</span><span class="sxs-lookup"><span data-stu-id="60aad-174">Schedule meeting</span></span> | <span data-ttu-id="60aad-175">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-175">Available</span></span> |
| | <span data-ttu-id="60aad-176">会議に参加する</span><span class="sxs-lookup"><span data-stu-id="60aad-176">Join meeting</span></span> | <span data-ttu-id="60aad-177">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-177">Available</span></span> |
| | <span data-ttu-id="60aad-178">VoIP 会議</span><span class="sxs-lookup"><span data-stu-id="60aad-178">VoIP meeting</span></span> | <span data-ttu-id="60aad-179">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-179">Available</span></span> |
| | <span data-ttu-id="60aad-180">デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="60aad-180">Desktop sharing</span></span> | <span data-ttu-id="60aad-181">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-181">Available</span></span> |
| | <span data-ttu-id="60aad-182">共有の制御を行う</span><span class="sxs-lookup"><span data-stu-id="60aad-182">Give and take control in sharing</span></span> | <span data-ttu-id="60aad-183">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-183">Available</span></span> |
| | <span data-ttu-id="60aad-184">会議室から接続する</span><span class="sxs-lookup"><span data-stu-id="60aad-184">Connect from a conference room</span></span> | <span data-ttu-id="60aad-185">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-185">Available</span></span> |
| | <span data-ttu-id="60aad-186">匿名での参加</span><span class="sxs-lookup"><span data-stu-id="60aad-186">Anonymous join</span></span> | <span data-ttu-id="60aad-187">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-187">Available</span></span> |
| | <span data-ttu-id="60aad-188">クラウドの記録</span><span class="sxs-lookup"><span data-stu-id="60aad-188">Cloud recording</span></span> | <span data-ttu-id="60aad-189">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="60aad-189">On the Government backlog</span></span> |
| | <span data-ttu-id="60aad-190">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="60aad-190">Meeting notes</span></span> | <span data-ttu-id="60aad-191">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-191">Available</span></span> |
| | <span data-ttu-id="60aad-192">ブロードキャスト会議</span><span class="sxs-lookup"><span data-stu-id="60aad-192">Broadcast meetings</span></span> | <span data-ttu-id="60aad-193">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="60aad-193">On the Government backlog</span></span> |
| | <span data-ttu-id="60aad-194">フェデレーション会議</span><span class="sxs-lookup"><span data-stu-id="60aad-194">Federated meetings</span></span> | <span data-ttu-id="60aad-195">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-195">Available</span></span> |
| | <span data-ttu-id="60aad-196">Surface Hub のサポート (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="60aad-196">Surface Hub support (preview)</span></span> | <span data-ttu-id="60aad-197">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="60aad-197">On the Government backlog</span></span> |
| <span data-ttu-id="60aad-198">通話</span><span class="sxs-lookup"><span data-stu-id="60aad-198">Calls</span></span> | <span data-ttu-id="60aad-199">連絡先</span><span class="sxs-lookup"><span data-stu-id="60aad-199">Contacts</span></span> | <span data-ttu-id="60aad-200">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-200">Available</span></span> |
| | <span data-ttu-id="60aad-201">履歴</span><span class="sxs-lookup"><span data-stu-id="60aad-201">History</span></span> | <span data-ttu-id="60aad-202">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-202">Available</span></span> |
| | <span data-ttu-id="60aad-203">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="60aad-203">Voicemail</span></span> | <span data-ttu-id="60aad-204">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-204">Available</span></span> |
| | <span data-ttu-id="60aad-205">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="60aad-205">VoIP call</span></span> | <span data-ttu-id="60aad-206">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-206">Available</span></span> |
| | <span data-ttu-id="60aad-207">Skype for ビジネス-チーム通話</span><span class="sxs-lookup"><span data-stu-id="60aad-207">Skype for Business - Teams calling</span></span> | <span data-ttu-id="60aad-208">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-208">Available</span></span> |
| | <span data-ttu-id="60aad-209">通話プラン</span><span class="sxs-lookup"><span data-stu-id="60aad-209">Calling Plans</span></span> | <span data-ttu-id="60aad-210">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-210">Available</span></span> |
| | <span data-ttu-id="60aad-211">電話会議 (会議の参加者に PSTN 経由での参加を許可する)</span><span class="sxs-lookup"><span data-stu-id="60aad-211">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="60aad-212">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-212">Available</span></span> |
| | <span data-ttu-id="60aad-213">Microsoft Phone システムのダイレクトルーティング</span><span class="sxs-lookup"><span data-stu-id="60aad-213">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="60aad-214">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-214">Available</span></span> |
| | <span data-ttu-id="60aad-215">PSTN 発信者のロビー</span><span class="sxs-lookup"><span data-stu-id="60aad-215">Lobby for PSTN callers</span></span> | <span data-ttu-id="60aad-216">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-216">Available</span></span> |
| | <span data-ttu-id="60aad-217">通話キュー</span><span class="sxs-lookup"><span data-stu-id="60aad-217">Call queue</span></span> | <span data-ttu-id="60aad-218">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-218">Available</span></span> |
| | <span data-ttu-id="60aad-219">上司と代理人のサポート</span><span class="sxs-lookup"><span data-stu-id="60aad-219">Boss and delegate support</span></span> | <span data-ttu-id="60aad-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-220">Available</span></span> |
| | <span data-ttu-id="60aad-221">提案と安全な移行</span><span class="sxs-lookup"><span data-stu-id="60aad-221">Consultative and safe transfer</span></span> | <span data-ttu-id="60aad-222">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-222">Available</span></span> |
| | <span data-ttu-id="60aad-223">飛躍的に応答不可</span><span class="sxs-lookup"><span data-stu-id="60aad-223">Do not disturb breakthrough</span></span> | <span data-ttu-id="60aad-224">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-224">Available</span></span> |
| | <span data-ttu-id="60aad-225">ディスティンクティブリング</span><span class="sxs-lookup"><span data-stu-id="60aad-225">Distinctive ring</span></span> | <span data-ttu-id="60aad-226">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-226">Available</span></span> |
| | <span data-ttu-id="60aad-227">1:1 を使用して、チーム、Skype for Business、PSTN 参加者とのグループ通話エスカレーション</span><span class="sxs-lookup"><span data-stu-id="60aad-227">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="60aad-228">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-228">Available</span></span> |
| | <span data-ttu-id="60aad-229">グループに転送</span><span class="sxs-lookup"><span data-stu-id="60aad-229">Forward to group</span></span> | <span data-ttu-id="60aad-230">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-230">Available</span></span> |
| | <span data-ttu-id="60aad-231">PSTN 通話に転送</span><span class="sxs-lookup"><span data-stu-id="60aad-231">Transfer to PSTN call</span></span> | <span data-ttu-id="60aad-232">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-232">Available</span></span> |
| | <span data-ttu-id="60aad-233">緊急通話-通話プラン</span><span class="sxs-lookup"><span data-stu-id="60aad-233">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="60aad-234">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-234">Available</span></span> |
| | <span data-ttu-id="60aad-235">既存の認定 SIP 電話のサポート</span><span class="sxs-lookup"><span data-stu-id="60aad-235">Support for existing certified SIP phones</span></span> | <span data-ttu-id="60aad-236">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-236">Available</span></span> |
| | <span data-ttu-id="60aad-237">USB HID</span><span class="sxs-lookup"><span data-stu-id="60aad-237">USB HID</span></span> | <span data-ttu-id="60aad-238">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-238">Available</span></span> |
| | <span data-ttu-id="60aad-239">通話と会議の両方の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="60aad-239">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="60aad-240">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-240">Available</span></span> |
| | <span data-ttu-id="60aad-241">組織の自動応答</span><span class="sxs-lookup"><span data-stu-id="60aad-241">Organization auto attendant</span></span> | <span data-ttu-id="60aad-242">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-242">Available</span></span> |
| | <span data-ttu-id="60aad-243">Skype コンシューマー-チーム通話サポート</span><span class="sxs-lookup"><span data-stu-id="60aad-243">Skype consumer - Teams call support</span></span> | <span data-ttu-id="60aad-244">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-244">Available</span></span> |
| <span data-ttu-id="60aad-245">ファイル</span><span class="sxs-lookup"><span data-stu-id="60aad-245">Files</span></span> | <span data-ttu-id="60aad-246">行っ</span><span class="sxs-lookup"><span data-stu-id="60aad-246">Recent</span></span> | <span data-ttu-id="60aad-247">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-247">Available</span></span> |
| | <span data-ttu-id="60aad-248">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60aad-248">Microsoft Teams</span></span> | <span data-ttu-id="60aad-249">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-249">Available</span></span> |
| <span data-ttu-id="60aad-250">ストア</span><span class="sxs-lookup"><span data-stu-id="60aad-250">Store</span></span> | <span data-ttu-id="60aad-251">App Store</span><span class="sxs-lookup"><span data-stu-id="60aad-251">App Store</span></span> | <span data-ttu-id="60aad-252">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="60aad-252">On the Government backlog</span></span> |
| <span data-ttu-id="60aad-253">検索</span><span class="sxs-lookup"><span data-stu-id="60aad-253">Search</span></span> | <span data-ttu-id="60aad-254">メッセージ</span><span class="sxs-lookup"><span data-stu-id="60aad-254">Messages</span></span> | <span data-ttu-id="60aad-255">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-255">Available</span></span> |
| | <span data-ttu-id="60aad-256">ユーザー</span><span class="sxs-lookup"><span data-stu-id="60aad-256">People</span></span> | <span data-ttu-id="60aad-257">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-257">Available</span></span> |
| | <span data-ttu-id="60aad-258">ファイル</span><span class="sxs-lookup"><span data-stu-id="60aad-258">Files</span></span> | <span data-ttu-id="60aad-259">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-259">Available</span></span> |
| | <span data-ttu-id="60aad-260">スラッシュコマンド</span><span class="sxs-lookup"><span data-stu-id="60aad-260">Slash commands</span></span> | <span data-ttu-id="60aad-261">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-261">Available</span></span> |
| <span data-ttu-id="60aad-262">コン</span><span class="sxs-lookup"><span data-stu-id="60aad-262">Compliance</span></span> | <span data-ttu-id="60aad-263">コンプライアンスコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="60aad-263">Compliance content search</span></span> | <span data-ttu-id="60aad-264">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-264">Available</span></span> |
| | <span data-ttu-id="60aad-265">保持</span><span class="sxs-lookup"><span data-stu-id="60aad-265">Retention</span></span> | <span data-ttu-id="60aad-266">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-266">Available</span></span> |
| | <span data-ttu-id="60aad-267">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="60aad-267">Audit log search</span></span> | <span data-ttu-id="60aad-268">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-268">Available</span></span> |
| | <span data-ttu-id="60aad-269">法的保持</span><span class="sxs-lookup"><span data-stu-id="60aad-269">Legal hold</span></span> | <span data-ttu-id="60aad-270">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-270">Available</span></span> |
| | <span data-ttu-id="60aad-271">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="60aad-271">eDiscovery</span></span> | <span data-ttu-id="60aad-272">利用可能</span><span class="sxs-lookup"><span data-stu-id="60aad-272">Available</span></span> |

> [!Note]

> <span data-ttu-id="60aad-273">GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="60aad-273">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60aad-274">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="60aad-274">Decision point</span></span>|<ul><li><span data-ttu-id="60aad-275">Teams 機能セットが組織のニーズを満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="60aad-275">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="60aad-276">手順5</span><span class="sxs-lookup"><span data-stu-id="60aad-276">Step 5.</span></span> <span data-ttu-id="60aad-277">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="60aad-277">Plan for governance</span></span>

<span data-ttu-id="60aad-278">ガバナンスの要件と、それらをどのように満たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="60aad-278">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="60aad-279">詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60aad-279">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="60aad-280">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="60aad-280">Decision point</span></span>|<ul><li><span data-ttu-id="60aad-281">[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</span><span class="sxs-lookup"><span data-stu-id="60aad-281">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="60aad-282">手順6</span><span class="sxs-lookup"><span data-stu-id="60aad-282">Step 6.</span></span> <span data-ttu-id="60aad-283">チームをコラボレーションのために展開する</span><span class="sxs-lookup"><span data-stu-id="60aad-283">Deploy Teams for collaboration</span></span>

<span data-ttu-id="60aad-284">Microsoft 365 Government-GCC に onboarded された後は、 [Fasttrack](https://www.microsoft.com/fasttrack)を使用する標準的な展開方法と、お客様が選んだパートナーを対象に、サービスにオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="60aad-284">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="60aad-285">準備ができたら、チームを展開し[て、チームとチャネルを通じて組織内での共同作業を可能](teams-overview.md)にします。</span><span class="sxs-lookup"><span data-stu-id="60aad-285">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="60aad-286">導入と変更管理チームまたは Teams のエキスパートに相談してください。</span><span class="sxs-lookup"><span data-stu-id="60aad-286">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="60aad-287">手順7</span><span class="sxs-lookup"><span data-stu-id="60aad-287">Step 7.</span></span> <span data-ttu-id="60aad-288">会議と音声のチームを展開する</span><span class="sxs-lookup"><span data-stu-id="60aad-288">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="60aad-289">これは、より幅広いステークホルダーグループで Teams を使用して、会議や[クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。</span><span class="sxs-lookup"><span data-stu-id="60aad-289">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

