---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 米国政府規制の対象となるデータを処理するエンティティで Office 365 の展開を推進する IT 担当者向けガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: baeb60f00602052d28a85337387cb0024979360e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237671"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="616c8-103">Microsoft 365 Government-GCC 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="616c8-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="616c8-104">このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人向けの Office 365 の展開を推進している IT プロフェッショナル、または Microsoft の使用時に政府機関の規制と要件の対象となるデータを処理するその他のエンティティを対象としています。365 Government-GCC はこれらの要件を満たすのに適しています。</span><span class="sxs-lookup"><span data-stu-id="616c8-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="616c8-105">組織が既に Microsoft 365 Government-GCC の資格要件を満たし、プログラムに受け入れられている場合は、手順1と2をスキップして、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="616c8-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="616c8-106">手順1</span><span class="sxs-lookup"><span data-stu-id="616c8-106">Step 1.</span></span> <span data-ttu-id="616c8-107">組織に Microsoft 365 Government-GCC が必要かどうか、および資格要件を満たしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="616c8-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="616c8-108">Microsoft 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="616c8-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="616c8-109">Office 365 の機能を活用できるだけでなく、Microsoft 365 Government-GCC に固有の次の機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="616c8-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="616c8-110">組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="616c8-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="616c8-111">組織の顧客コンテンツは、米国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="616c8-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="616c8-112">組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="616c8-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="616c8-113">Microsoft 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="616c8-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="616c8-114">米国政府機関向け Microsoft 365 政府向けの GCC 製品の詳細については、「[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="616c8-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="616c8-115">[Office 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="616c8-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="616c8-116">サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織\*\*\*\*のニーズに応じ**て2つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="616c8-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="616c8-117">次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="616c8-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="616c8-119">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="616c8-119">Decision points</span></span>|<ul><li><span data-ttu-id="616c8-120">組織に対して Microsoft 365 Government-GCC が適切であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="616c8-120">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="616c8-121">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="616c8-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="616c8-122">Microsoft 365 Government-GCC は米国でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="616c8-122">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="616c8-123">米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="616c8-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="616c8-124">手順2</span><span class="sxs-lookup"><span data-stu-id="616c8-124">Step 2.</span></span> <span data-ttu-id="616c8-125">Microsoft 365 Government-GCC に適用する</span><span class="sxs-lookup"><span data-stu-id="616c8-125">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="616c8-126">このサービスが組織に適していると判断された場合は、[ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="616c8-126">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="616c8-127">手順3</span><span class="sxs-lookup"><span data-stu-id="616c8-127">Step 3.</span></span> <span data-ttu-id="616c8-128">Microsoft 365 Government-GCC の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="616c8-128">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="616c8-129">[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="616c8-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="616c8-131">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="616c8-131">Decision point</span></span>|<ul><li><span data-ttu-id="616c8-132">Microsoft 365 Government の既定のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="616c8-132">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="616c8-133">手順4。</span><span class="sxs-lookup"><span data-stu-id="616c8-133">Step 4.</span></span> <span data-ttu-id="616c8-134">現在、どの機能が既定で利用できないか、無効になっているかを理解する。</span><span class="sxs-lookup"><span data-stu-id="616c8-134">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="616c8-135">政府機関向けクラウドのお客様の要件に対応するため、Microsoft 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="616c8-135">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="616c8-136">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="616c8-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="616c8-137">機能</span><span class="sxs-lookup"><span data-stu-id="616c8-137">Feature</span></span>                     | <span data-ttu-id="616c8-138">GCC</span><span class="sxs-lookup"><span data-stu-id="616c8-138">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="616c8-139">技術</span><span class="sxs-lookup"><span data-stu-id="616c8-139">Base</span></span> | <span data-ttu-id="616c8-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="616c8-140">Login</span></span> | <span data-ttu-id="616c8-141">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-141">Available</span></span> |
| | <span data-ttu-id="616c8-142">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="616c8-142">Presence</span></span> | <span data-ttu-id="616c8-143">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-143">Available</span></span> |
| | <span data-ttu-id="616c8-144">統合されたプレゼンス (Skype for Business および Teams 統合)</span><span class="sxs-lookup"><span data-stu-id="616c8-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="616c8-145">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-145">Available</span></span> |
| <span data-ttu-id="616c8-146">処理</span><span class="sxs-lookup"><span data-stu-id="616c8-146">Activity</span></span> | <span data-ttu-id="616c8-147">クロス</span><span class="sxs-lookup"><span data-stu-id="616c8-147">Feed</span></span> | <span data-ttu-id="616c8-148">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-148">Available</span></span> |
|  | <span data-ttu-id="616c8-149">マイアクティビティ</span><span class="sxs-lookup"><span data-stu-id="616c8-149">My Activity</span></span> | <span data-ttu-id="616c8-150">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-150">Available</span></span> |
| <span data-ttu-id="616c8-151">チャット</span><span class="sxs-lookup"><span data-stu-id="616c8-151">Chat</span></span> | <span data-ttu-id="616c8-152">チャット</span><span class="sxs-lookup"><span data-stu-id="616c8-152">Conversation</span></span> | <span data-ttu-id="616c8-153">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-153">Available</span></span> |
| | <span data-ttu-id="616c8-154">ファイル</span><span class="sxs-lookup"><span data-stu-id="616c8-154">Files</span></span> | <span data-ttu-id="616c8-155">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-155">Available</span></span> |
| | <span data-ttu-id="616c8-156">組織図</span><span class="sxs-lookup"><span data-stu-id="616c8-156">Org chart</span></span> | <span data-ttu-id="616c8-157">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-157">Available</span></span> |
| | <span data-ttu-id="616c8-158">処理</span><span class="sxs-lookup"><span data-stu-id="616c8-158">Activity</span></span> | <span data-ttu-id="616c8-159">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-159">Available</span></span> |
| | <span data-ttu-id="616c8-160">相互運用 (1:1 チーム-Skype for Business チャット)</span><span class="sxs-lookup"><span data-stu-id="616c8-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="616c8-161">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-161">Available</span></span> |
| <span data-ttu-id="616c8-162">Teams</span><span class="sxs-lookup"><span data-stu-id="616c8-162">Teams</span></span> | <span data-ttu-id="616c8-163">チャネルメッセージ</span><span class="sxs-lookup"><span data-stu-id="616c8-163">Channel message</span></span> | <span data-ttu-id="616c8-164">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-164">Available</span></span> |
| | <span data-ttu-id="616c8-165">チャネルファイル</span><span class="sxs-lookup"><span data-stu-id="616c8-165">Channel files</span></span> | <span data-ttu-id="616c8-166">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-166">Available</span></span> |
| | <span data-ttu-id="616c8-167">OneNote タブ</span><span class="sxs-lookup"><span data-stu-id="616c8-167">OneNote tab</span></span> | <span data-ttu-id="616c8-168">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="616c8-168">On the Government backlog</span></span> |
| | <span data-ttu-id="616c8-169">チャネルをメールで送信する</span><span class="sxs-lookup"><span data-stu-id="616c8-169">Email a channel</span></span> | <span data-ttu-id="616c8-170">該当なし</span><span class="sxs-lookup"><span data-stu-id="616c8-170">Not available</span></span> |
| | <span data-ttu-id="616c8-171">メンバーの追加</span><span class="sxs-lookup"><span data-stu-id="616c8-171">Add member</span></span> | <span data-ttu-id="616c8-172">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-172">Available</span></span> |
| | <span data-ttu-id="616c8-173">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="616c8-173">Guest access</span></span> | <span data-ttu-id="616c8-174">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-174">Available</span></span> |
| <span data-ttu-id="616c8-175">会議</span><span class="sxs-lookup"><span data-stu-id="616c8-175">Meetings</span></span> | <span data-ttu-id="616c8-176">会議の予約</span><span class="sxs-lookup"><span data-stu-id="616c8-176">Schedule meeting</span></span> | <span data-ttu-id="616c8-177">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-177">Available</span></span> |
| | <span data-ttu-id="616c8-178">会議に参加する</span><span class="sxs-lookup"><span data-stu-id="616c8-178">Join meeting</span></span> | <span data-ttu-id="616c8-179">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-179">Available</span></span> |
| | <span data-ttu-id="616c8-180">VoIP 会議</span><span class="sxs-lookup"><span data-stu-id="616c8-180">VoIP meeting</span></span> | <span data-ttu-id="616c8-181">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-181">Available</span></span> |
| | <span data-ttu-id="616c8-182">デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="616c8-182">Desktop sharing</span></span> | <span data-ttu-id="616c8-183">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-183">Available</span></span> |
| | <span data-ttu-id="616c8-184">共有の制御を行う</span><span class="sxs-lookup"><span data-stu-id="616c8-184">Give and take control in sharing</span></span> | <span data-ttu-id="616c8-185">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-185">Available</span></span> |
| | <span data-ttu-id="616c8-186">会議室から接続する</span><span class="sxs-lookup"><span data-stu-id="616c8-186">Connect from a conference room</span></span> | <span data-ttu-id="616c8-187">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-187">Available</span></span> |
| | <span data-ttu-id="616c8-188">匿名での参加</span><span class="sxs-lookup"><span data-stu-id="616c8-188">Anonymous join</span></span> | <span data-ttu-id="616c8-189">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-189">Available</span></span> |
| | <span data-ttu-id="616c8-190">クラウドの記録</span><span class="sxs-lookup"><span data-stu-id="616c8-190">Cloud recording</span></span> | <span data-ttu-id="616c8-191">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="616c8-191">On the Government backlog</span></span> |
| | <span data-ttu-id="616c8-192">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="616c8-192">Meeting notes</span></span> | <span data-ttu-id="616c8-193">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-193">Available</span></span> |
| | <span data-ttu-id="616c8-194">ブロードキャスト会議</span><span class="sxs-lookup"><span data-stu-id="616c8-194">Broadcast meetings</span></span> | <span data-ttu-id="616c8-195">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="616c8-195">On the Government backlog</span></span> |
| | <span data-ttu-id="616c8-196">フェデレーション会議</span><span class="sxs-lookup"><span data-stu-id="616c8-196">Federated meetings</span></span> | <span data-ttu-id="616c8-197">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-197">Available</span></span> |
| | <span data-ttu-id="616c8-198">Surface Hub のサポート</span><span class="sxs-lookup"><span data-stu-id="616c8-198">Surface Hub support</span></span> | <span data-ttu-id="616c8-199">該当なし</span><span class="sxs-lookup"><span data-stu-id="616c8-199">Not available</span></span> |
| <span data-ttu-id="616c8-200">通話</span><span class="sxs-lookup"><span data-stu-id="616c8-200">Calls</span></span> | <span data-ttu-id="616c8-201">連絡先</span><span class="sxs-lookup"><span data-stu-id="616c8-201">Contacts</span></span> | <span data-ttu-id="616c8-202">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-202">Available</span></span> |
| | <span data-ttu-id="616c8-203">履歴</span><span class="sxs-lookup"><span data-stu-id="616c8-203">History</span></span> | <span data-ttu-id="616c8-204">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-204">Available</span></span> |
| | <span data-ttu-id="616c8-205">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="616c8-205">Voicemail</span></span> | <span data-ttu-id="616c8-206">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-206">Available</span></span> |
| | <span data-ttu-id="616c8-207">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="616c8-207">VoIP call</span></span> | <span data-ttu-id="616c8-208">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-208">Available</span></span> |
| | <span data-ttu-id="616c8-209">Skype for ビジネス-チーム通話</span><span class="sxs-lookup"><span data-stu-id="616c8-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="616c8-210">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-210">Available</span></span> |
| | <span data-ttu-id="616c8-211">通話プラン</span><span class="sxs-lookup"><span data-stu-id="616c8-211">Calling Plans</span></span> | <span data-ttu-id="616c8-212">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-212">Available</span></span> |
| | <span data-ttu-id="616c8-213">電話会議 (会議の参加者に PSTN 経由での参加を許可する)</span><span class="sxs-lookup"><span data-stu-id="616c8-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="616c8-214">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-214">Available</span></span> |
| | <span data-ttu-id="616c8-215">Microsoft Phone システムのダイレクトルーティング</span><span class="sxs-lookup"><span data-stu-id="616c8-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="616c8-216">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-216">Available</span></span> |
| | <span data-ttu-id="616c8-217">PSTN 発信者のロビー</span><span class="sxs-lookup"><span data-stu-id="616c8-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="616c8-218">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-218">Available</span></span> |
| | <span data-ttu-id="616c8-219">通話キュー</span><span class="sxs-lookup"><span data-stu-id="616c8-219">Call queue</span></span> | <span data-ttu-id="616c8-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-220">Available</span></span> |
| | <span data-ttu-id="616c8-221">上司と代理人のサポート</span><span class="sxs-lookup"><span data-stu-id="616c8-221">Boss and delegate support</span></span> | <span data-ttu-id="616c8-222">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-222">Available</span></span> |
| | <span data-ttu-id="616c8-223">提案と安全な移行</span><span class="sxs-lookup"><span data-stu-id="616c8-223">Consultative and safe transfer</span></span> | <span data-ttu-id="616c8-224">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-224">Available</span></span> |
| | <span data-ttu-id="616c8-225">飛躍的に応答不可</span><span class="sxs-lookup"><span data-stu-id="616c8-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="616c8-226">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-226">Available</span></span> |
| | <span data-ttu-id="616c8-227">ディスティンクティブリング</span><span class="sxs-lookup"><span data-stu-id="616c8-227">Distinctive ring</span></span> | <span data-ttu-id="616c8-228">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-228">Available</span></span> |
| | <span data-ttu-id="616c8-229">1:1 を使用して、チーム、Skype for Business、PSTN 参加者とのグループ通話エスカレーション</span><span class="sxs-lookup"><span data-stu-id="616c8-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="616c8-230">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-230">Available</span></span> |
| | <span data-ttu-id="616c8-231">グループに転送</span><span class="sxs-lookup"><span data-stu-id="616c8-231">Forward to group</span></span> | <span data-ttu-id="616c8-232">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-232">Available</span></span> |
| | <span data-ttu-id="616c8-233">PSTN 通話に転送</span><span class="sxs-lookup"><span data-stu-id="616c8-233">Transfer to PSTN call</span></span> | <span data-ttu-id="616c8-234">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-234">Available</span></span> |
| | <span data-ttu-id="616c8-235">緊急通話-通話プラン</span><span class="sxs-lookup"><span data-stu-id="616c8-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="616c8-236">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-236">Available</span></span> |
| | <span data-ttu-id="616c8-237">既存の認定 SIP 電話のサポート</span><span class="sxs-lookup"><span data-stu-id="616c8-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="616c8-238">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-238">Available</span></span> |
| | <span data-ttu-id="616c8-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="616c8-239">USB HID</span></span> | <span data-ttu-id="616c8-240">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-240">Available</span></span> |
| | <span data-ttu-id="616c8-241">通話と会議の両方の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="616c8-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="616c8-242">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-242">Available</span></span> |
| | <span data-ttu-id="616c8-243">組織の自動応答</span><span class="sxs-lookup"><span data-stu-id="616c8-243">Organization auto attendant</span></span> | <span data-ttu-id="616c8-244">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-244">Available</span></span> |
| | <span data-ttu-id="616c8-245">Skype コンシューマー-チーム通話サポート</span><span class="sxs-lookup"><span data-stu-id="616c8-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="616c8-246">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-246">Available</span></span> |
| <span data-ttu-id="616c8-247">ファイル</span><span class="sxs-lookup"><span data-stu-id="616c8-247">Files</span></span> | <span data-ttu-id="616c8-248">行っ</span><span class="sxs-lookup"><span data-stu-id="616c8-248">Recent</span></span> | <span data-ttu-id="616c8-249">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-249">Available</span></span> |
| | <span data-ttu-id="616c8-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="616c8-250">Microsoft Teams</span></span> | <span data-ttu-id="616c8-251">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-251">Available</span></span> |
| <span data-ttu-id="616c8-252">ストア</span><span class="sxs-lookup"><span data-stu-id="616c8-252">Store</span></span> | <span data-ttu-id="616c8-253">App Store</span><span class="sxs-lookup"><span data-stu-id="616c8-253">App Store</span></span> | <span data-ttu-id="616c8-254">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="616c8-254">On the Government backlog</span></span> |
| <span data-ttu-id="616c8-255">検索</span><span class="sxs-lookup"><span data-stu-id="616c8-255">Search</span></span> | <span data-ttu-id="616c8-256">メッセージ</span><span class="sxs-lookup"><span data-stu-id="616c8-256">Messages</span></span> | <span data-ttu-id="616c8-257">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-257">Available</span></span> |
| | <span data-ttu-id="616c8-258">ユーザー</span><span class="sxs-lookup"><span data-stu-id="616c8-258">People</span></span> | <span data-ttu-id="616c8-259">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-259">Available</span></span> |
| | <span data-ttu-id="616c8-260">ファイル</span><span class="sxs-lookup"><span data-stu-id="616c8-260">Files</span></span> | <span data-ttu-id="616c8-261">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-261">Available</span></span> |
| | <span data-ttu-id="616c8-262">スラッシュコマンド</span><span class="sxs-lookup"><span data-stu-id="616c8-262">Slash commands</span></span> | <span data-ttu-id="616c8-263">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-263">Available</span></span> |
| <span data-ttu-id="616c8-264">コン</span><span class="sxs-lookup"><span data-stu-id="616c8-264">Compliance</span></span> | <span data-ttu-id="616c8-265">コンプライアンスコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="616c8-265">Compliance content search</span></span> | <span data-ttu-id="616c8-266">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-266">Available</span></span> |
| | <span data-ttu-id="616c8-267">保持</span><span class="sxs-lookup"><span data-stu-id="616c8-267">Retention</span></span> | <span data-ttu-id="616c8-268">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-268">Available</span></span> |
| | <span data-ttu-id="616c8-269">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="616c8-269">Audit log search</span></span> | <span data-ttu-id="616c8-270">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-270">Available</span></span> |
| | <span data-ttu-id="616c8-271">法的保持</span><span class="sxs-lookup"><span data-stu-id="616c8-271">Legal hold</span></span> | <span data-ttu-id="616c8-272">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-272">Available</span></span> |
| | <span data-ttu-id="616c8-273">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="616c8-273">eDiscovery</span></span> | <span data-ttu-id="616c8-274">利用可能</span><span class="sxs-lookup"><span data-stu-id="616c8-274">Available</span></span> |

> [!Note]

> <span data-ttu-id="616c8-275">GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="616c8-275">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="616c8-277">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="616c8-277">Decision point</span></span>|<ul><li><span data-ttu-id="616c8-278">Teams 機能セットが組織のニーズを満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="616c8-278">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="616c8-279">手順5</span><span class="sxs-lookup"><span data-stu-id="616c8-279">Step 5.</span></span> <span data-ttu-id="616c8-280">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="616c8-280">Plan for governance</span></span>

<span data-ttu-id="616c8-281">ガバナンスの要件と、それらをどのように満たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="616c8-281">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="616c8-282">詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="616c8-282">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを示すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="616c8-284">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="616c8-284">Decision point</span></span>|<ul><li><span data-ttu-id="616c8-285">[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</span><span class="sxs-lookup"><span data-stu-id="616c8-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="616c8-286">手順6</span><span class="sxs-lookup"><span data-stu-id="616c8-286">Step 6.</span></span> <span data-ttu-id="616c8-287">チームをコラボレーションのために展開する</span><span class="sxs-lookup"><span data-stu-id="616c8-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="616c8-288">Microsoft 365 Government-GCC に onboarded された後は、 [Fasttrack](https://www.microsoft.com/fasttrack)を使用する標準的な展開方法と、お客様が選んだパートナーを対象に、サービスにオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="616c8-288">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="616c8-289">準備ができたら、チームを展開し[て、チームとチャネルを通じて組織内での共同作業を可能](teams-overview.md)にします。</span><span class="sxs-lookup"><span data-stu-id="616c8-289">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="616c8-290">導入と変更管理チームまたは Teams のエキスパートに相談してください。</span><span class="sxs-lookup"><span data-stu-id="616c8-290">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="616c8-291">手順7</span><span class="sxs-lookup"><span data-stu-id="616c8-291">Step 7.</span></span> <span data-ttu-id="616c8-292">会議と音声のチームを展開する</span><span class="sxs-lookup"><span data-stu-id="616c8-292">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="616c8-293">これは、より幅広いステークホルダーグループで Teams を使用して、会議や[クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。</span><span class="sxs-lookup"><span data-stu-id="616c8-293">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

