---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f03c4cdd13ea63dfee6470843fea5e2dafeab7c
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837447"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="92ead-103">Microsoft 365 Government-GCC 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="92ead-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="92ead-104">このガイダンスは、米国連邦、州、地方、tribal、または territorial 政府機関の法人向けの Office 365 の展開を推進している IT プロフェッショナル、または Microsoft の使用時に政府機関の規制と要件の対象となるデータを処理するその他のエンティティを対象としています。365 Government-GCC はこれらの要件を満たすのに適しています。</span><span class="sxs-lookup"><span data-stu-id="92ead-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="92ead-105">組織が既に Microsoft 365 Government-GCC の資格要件を満たし、プログラムに受け入れられている場合は、手順1と2をスキップして、手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="92ead-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="92ead-106">手順1</span><span class="sxs-lookup"><span data-stu-id="92ead-106">Step 1.</span></span> <span data-ttu-id="92ead-107">組織に Microsoft 365 Government-GCC が必要かどうか、および資格要件を満たしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="92ead-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="92ead-108">Microsoft 365 Government-GCC 環境は、お客さまのクラウドサービスに関する米国政府の要件に準拠します。これには、FedRAMP の低品質、刑事司法および連邦税情報システム (CJI と FTI のデータ型) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92ead-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="92ead-109">Office 365 の機能を活用できるだけでなく、Microsoft 365 Government-GCC に固有の次の機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="92ead-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="92ead-110">組織の顧客のコンテンツは、Microsoft の一般法人向け Office 365 サービスの顧客のコンテンツから論理的に分離されます。</span><span class="sxs-lookup"><span data-stu-id="92ead-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="92ead-111">組織の顧客コンテンツは、米国内に保存されています。</span><span class="sxs-lookup"><span data-stu-id="92ead-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="92ead-112">組織のお客様のコンテンツへのアクセスは、Microsoft のユーザーに制限されています。</span><span class="sxs-lookup"><span data-stu-id="92ead-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="92ead-113">Microsoft 365 Government-GCC は、米国公的機関のお客様に必要な認定および accreditations に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="92ead-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="92ead-114">米国政府機関向け Microsoft 365 政府向けの GCC 製品の詳細については、「[資格要件](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)を含む[Office 365 政府](https://products.office.com/government/compare-office-365-government-plans)機関向けプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ead-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="92ead-115">[Office 365 US Government service の説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点について説明します。これは、米国内でのコンプライアンス要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="92ead-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="92ead-116">サービスの説明に記載されている情報の表を Excel ブックに転送して、**組織\*\*\*\*のニーズに応じ**て2つの列を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="92ead-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="92ead-117">次に、このリストを同僚と確認して、このサービスが組織のニーズを満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92ead-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="92ead-119">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="92ead-119">Decision points</span></span>|<ul><li><span data-ttu-id="92ead-120">組織に対して Microsoft 365 Government-GCC が適切であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="92ead-120">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="92ead-121">組織が資格要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92ead-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="92ead-122">Microsoft 365 Government-GCC は米国でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="92ead-122">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="92ead-123">米国政府以外のお客様は、多数の[Office 365 Government プラン](https://products.office.com/en/government/compare-office-365-government-plans)から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="92ead-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="92ead-124">手順2</span><span class="sxs-lookup"><span data-stu-id="92ead-124">Step 2.</span></span> <span data-ttu-id="92ead-125">Microsoft 365 Government-GCC に適用する</span><span class="sxs-lookup"><span data-stu-id="92ead-125">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="92ead-126">このサービスが組織に適していると判断された場合は、[ここでこのサービスの適用](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="92ead-126">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="92ead-127">手順3</span><span class="sxs-lookup"><span data-stu-id="92ead-127">Step 3.</span></span> <span data-ttu-id="92ead-128">Microsoft 365 Government-GCC の既定のセキュリティ設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="92ead-128">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="92ead-129">[管理とセキュリティの設定](enable-features-office-365.md)を変更する前に慎重に確認し、コンプライアンスへの影響を考慮して、既定のセキュリティ設定を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92ead-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="92ead-131">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="92ead-131">Decision point</span></span>|<ul><li><span data-ttu-id="92ead-132">Microsoft 365 Government の既定のセキュリティ設定を変更するかどうかを決定します。解決するには、変更の影響を最初に理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92ead-132">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="92ead-133">手順4。</span><span class="sxs-lookup"><span data-stu-id="92ead-133">Step 4.</span></span> <span data-ttu-id="92ead-134">現在、どの機能が既定で利用できないか、無効になっているかを理解する。</span><span class="sxs-lookup"><span data-stu-id="92ead-134">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="92ead-135">政府機関向けクラウドのお客様の要件に対応するため、Microsoft 365 Government-GCC とエンタープライズのプランにはいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="92ead-135">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="92ead-136">使用できる機能については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ead-136">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="92ead-137">機能</span><span class="sxs-lookup"><span data-stu-id="92ead-137">Feature</span></span>                     | <span data-ttu-id="92ead-138">GCC</span><span class="sxs-lookup"><span data-stu-id="92ead-138">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="92ead-139">技術</span><span class="sxs-lookup"><span data-stu-id="92ead-139">Base</span></span> | <span data-ttu-id="92ead-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="92ead-140">Login</span></span> | <span data-ttu-id="92ead-141">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-141">Available</span></span> |
| | <span data-ttu-id="92ead-142">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="92ead-142">Presence</span></span> | <span data-ttu-id="92ead-143">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-143">Available</span></span> |
| | <span data-ttu-id="92ead-144">統合されたプレゼンス (Skype for Business および Teams 統合)</span><span class="sxs-lookup"><span data-stu-id="92ead-144">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="92ead-145">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-145">Available</span></span> |
| <span data-ttu-id="92ead-146">処理</span><span class="sxs-lookup"><span data-stu-id="92ead-146">Activity</span></span> | <span data-ttu-id="92ead-147">クロス</span><span class="sxs-lookup"><span data-stu-id="92ead-147">Feed</span></span> | <span data-ttu-id="92ead-148">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-148">Available</span></span> |
|  | <span data-ttu-id="92ead-149">マイアクティビティ</span><span class="sxs-lookup"><span data-stu-id="92ead-149">My Activity</span></span> | <span data-ttu-id="92ead-150">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-150">Available</span></span> |
| <span data-ttu-id="92ead-151">チャット</span><span class="sxs-lookup"><span data-stu-id="92ead-151">Chat</span></span> | <span data-ttu-id="92ead-152">チャット</span><span class="sxs-lookup"><span data-stu-id="92ead-152">Conversation</span></span> | <span data-ttu-id="92ead-153">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-153">Available</span></span> |
| | <span data-ttu-id="92ead-154">ファイル</span><span class="sxs-lookup"><span data-stu-id="92ead-154">Files</span></span> | <span data-ttu-id="92ead-155">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-155">Available</span></span> |
| | <span data-ttu-id="92ead-156">組織図</span><span class="sxs-lookup"><span data-stu-id="92ead-156">Org chart</span></span> | <span data-ttu-id="92ead-157">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-157">Available</span></span> |
| | <span data-ttu-id="92ead-158">処理</span><span class="sxs-lookup"><span data-stu-id="92ead-158">Activity</span></span> | <span data-ttu-id="92ead-159">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-159">Available</span></span> |
| | <span data-ttu-id="92ead-160">相互運用 (1:1 チーム-Skype for Business チャット)</span><span class="sxs-lookup"><span data-stu-id="92ead-160">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="92ead-161">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-161">Available</span></span> |
| <span data-ttu-id="92ead-162">Teams</span><span class="sxs-lookup"><span data-stu-id="92ead-162">Teams</span></span> | <span data-ttu-id="92ead-163">チャネルメッセージ</span><span class="sxs-lookup"><span data-stu-id="92ead-163">Channel message</span></span> | <span data-ttu-id="92ead-164">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-164">Available</span></span> |
| | <span data-ttu-id="92ead-165">チャネルファイル</span><span class="sxs-lookup"><span data-stu-id="92ead-165">Channel files</span></span> | <span data-ttu-id="92ead-166">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-166">Available</span></span> |
| | <span data-ttu-id="92ead-167">OneNote タブ</span><span class="sxs-lookup"><span data-stu-id="92ead-167">OneNote tab</span></span> | <span data-ttu-id="92ead-168">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="92ead-168">On the Government backlog</span></span> |
| | <span data-ttu-id="92ead-169">チャネルをメールで送信する</span><span class="sxs-lookup"><span data-stu-id="92ead-169">Email a channel</span></span> | <span data-ttu-id="92ead-170">該当なし</span><span class="sxs-lookup"><span data-stu-id="92ead-170">Not available</span></span> |
| | <span data-ttu-id="92ead-171">メンバーの追加</span><span class="sxs-lookup"><span data-stu-id="92ead-171">Add member</span></span> | <span data-ttu-id="92ead-172">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-172">Available</span></span> |
| | <span data-ttu-id="92ead-173">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="92ead-173">Guest access</span></span> | <span data-ttu-id="92ead-174">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-174">Available</span></span> |
| <span data-ttu-id="92ead-175">会議</span><span class="sxs-lookup"><span data-stu-id="92ead-175">Meetings</span></span> | <span data-ttu-id="92ead-176">会議の予約</span><span class="sxs-lookup"><span data-stu-id="92ead-176">Schedule meeting</span></span> | <span data-ttu-id="92ead-177">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-177">Available</span></span> |
| | <span data-ttu-id="92ead-178">会議に参加する</span><span class="sxs-lookup"><span data-stu-id="92ead-178">Join meeting</span></span> | <span data-ttu-id="92ead-179">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-179">Available</span></span> |
| | <span data-ttu-id="92ead-180">VoIP 会議</span><span class="sxs-lookup"><span data-stu-id="92ead-180">VoIP meeting</span></span> | <span data-ttu-id="92ead-181">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-181">Available</span></span> |
| | <span data-ttu-id="92ead-182">デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="92ead-182">Desktop sharing</span></span> | <span data-ttu-id="92ead-183">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-183">Available</span></span> |
| | <span data-ttu-id="92ead-184">共有の制御を行う</span><span class="sxs-lookup"><span data-stu-id="92ead-184">Give and take control in sharing</span></span> | <span data-ttu-id="92ead-185">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-185">Available</span></span> |
| | <span data-ttu-id="92ead-186">会議室から接続する</span><span class="sxs-lookup"><span data-stu-id="92ead-186">Connect from a conference room</span></span> | <span data-ttu-id="92ead-187">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-187">Available</span></span> |
| | <span data-ttu-id="92ead-188">匿名での参加</span><span class="sxs-lookup"><span data-stu-id="92ead-188">Anonymous join</span></span> | <span data-ttu-id="92ead-189">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-189">Available</span></span> |
| | <span data-ttu-id="92ead-190">クラウドの記録</span><span class="sxs-lookup"><span data-stu-id="92ead-190">Cloud recording</span></span> | <span data-ttu-id="92ead-191">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-191">Available</span></span> |
| | <span data-ttu-id="92ead-192">会議のメモ</span><span class="sxs-lookup"><span data-stu-id="92ead-192">Meeting notes</span></span> | <span data-ttu-id="92ead-193">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-193">Available</span></span> |
| | <span data-ttu-id="92ead-194">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="92ead-194">Live Events</span></span> | <span data-ttu-id="92ead-195">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-195">Available</span></span> |
| | <span data-ttu-id="92ead-196">フェデレーション会議</span><span class="sxs-lookup"><span data-stu-id="92ead-196">Federated meetings</span></span> | <span data-ttu-id="92ead-197">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-197">Available</span></span> |
| | <span data-ttu-id="92ead-198">Surface Hub のサポート</span><span class="sxs-lookup"><span data-stu-id="92ead-198">Surface Hub support</span></span> | <span data-ttu-id="92ead-199">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-199">Available</span></span> |
| <span data-ttu-id="92ead-200">通話</span><span class="sxs-lookup"><span data-stu-id="92ead-200">Calls</span></span> | <span data-ttu-id="92ead-201">連絡先</span><span class="sxs-lookup"><span data-stu-id="92ead-201">Contacts</span></span> | <span data-ttu-id="92ead-202">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-202">Available</span></span> |
| | <span data-ttu-id="92ead-203">履歴</span><span class="sxs-lookup"><span data-stu-id="92ead-203">History</span></span> | <span data-ttu-id="92ead-204">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-204">Available</span></span> |
| | <span data-ttu-id="92ead-205">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="92ead-205">Voicemail</span></span> | <span data-ttu-id="92ead-206">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-206">Available</span></span> |
| | <span data-ttu-id="92ead-207">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="92ead-207">VoIP call</span></span> | <span data-ttu-id="92ead-208">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-208">Available</span></span> |
| | <span data-ttu-id="92ead-209">Skype for ビジネス-チーム通話</span><span class="sxs-lookup"><span data-stu-id="92ead-209">Skype for Business - Teams calling</span></span> | <span data-ttu-id="92ead-210">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-210">Available</span></span> |
| | <span data-ttu-id="92ead-211">通話プラン</span><span class="sxs-lookup"><span data-stu-id="92ead-211">Calling Plans</span></span> | <span data-ttu-id="92ead-212">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-212">Available</span></span> |
| | <span data-ttu-id="92ead-213">電話会議 (会議の参加者に PSTN 経由での参加を許可する)</span><span class="sxs-lookup"><span data-stu-id="92ead-213">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="92ead-214">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-214">Available</span></span> |
| | <span data-ttu-id="92ead-215">Microsoft Phone システムのダイレクトルーティング</span><span class="sxs-lookup"><span data-stu-id="92ead-215">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="92ead-216">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-216">Available</span></span> |
| | <span data-ttu-id="92ead-217">PSTN 発信者のロビー</span><span class="sxs-lookup"><span data-stu-id="92ead-217">Lobby for PSTN callers</span></span> | <span data-ttu-id="92ead-218">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-218">Available</span></span> |
| | <span data-ttu-id="92ead-219">通話キュー</span><span class="sxs-lookup"><span data-stu-id="92ead-219">Call queue</span></span> | <span data-ttu-id="92ead-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-220">Available</span></span> |
| | <span data-ttu-id="92ead-221">上司と代理人のサポート</span><span class="sxs-lookup"><span data-stu-id="92ead-221">Boss and delegate support</span></span> | <span data-ttu-id="92ead-222">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-222">Available</span></span> |
| | <span data-ttu-id="92ead-223">提案と安全な移行</span><span class="sxs-lookup"><span data-stu-id="92ead-223">Consultative and safe transfer</span></span> | <span data-ttu-id="92ead-224">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-224">Available</span></span> |
| | <span data-ttu-id="92ead-225">飛躍的に応答不可</span><span class="sxs-lookup"><span data-stu-id="92ead-225">Do not disturb breakthrough</span></span> | <span data-ttu-id="92ead-226">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-226">Available</span></span> |
| | <span data-ttu-id="92ead-227">ディスティンクティブリング</span><span class="sxs-lookup"><span data-stu-id="92ead-227">Distinctive ring</span></span> | <span data-ttu-id="92ead-228">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-228">Available</span></span> |
| | <span data-ttu-id="92ead-229">1:1 を使用して、チーム、Skype for Business、PSTN 参加者とのグループ通話エスカレーション</span><span class="sxs-lookup"><span data-stu-id="92ead-229">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="92ead-230">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-230">Available</span></span> |
| | <span data-ttu-id="92ead-231">グループに転送</span><span class="sxs-lookup"><span data-stu-id="92ead-231">Forward to group</span></span> | <span data-ttu-id="92ead-232">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-232">Available</span></span> |
| | <span data-ttu-id="92ead-233">PSTN 通話に転送</span><span class="sxs-lookup"><span data-stu-id="92ead-233">Transfer to PSTN call</span></span> | <span data-ttu-id="92ead-234">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-234">Available</span></span> |
| | <span data-ttu-id="92ead-235">緊急通話-通話プラン</span><span class="sxs-lookup"><span data-stu-id="92ead-235">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="92ead-236">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-236">Available</span></span> |
| | <span data-ttu-id="92ead-237">既存の認定 SIP 電話のサポート</span><span class="sxs-lookup"><span data-stu-id="92ead-237">Support for existing certified SIP phones</span></span> | <span data-ttu-id="92ead-238">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-238">Available</span></span> |
| | <span data-ttu-id="92ead-239">USB HID</span><span class="sxs-lookup"><span data-stu-id="92ead-239">USB HID</span></span> | <span data-ttu-id="92ead-240">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-240">Available</span></span> |
| | <span data-ttu-id="92ead-241">通話と会議の両方の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="92ead-241">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="92ead-242">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-242">Available</span></span> |
| | <span data-ttu-id="92ead-243">組織の自動応答</span><span class="sxs-lookup"><span data-stu-id="92ead-243">Organization auto attendant</span></span> | <span data-ttu-id="92ead-244">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-244">Available</span></span> |
| | <span data-ttu-id="92ead-245">Skype コンシューマー-チーム通話サポート</span><span class="sxs-lookup"><span data-stu-id="92ead-245">Skype consumer - Teams call support</span></span> | <span data-ttu-id="92ead-246">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-246">Available</span></span> |
| <span data-ttu-id="92ead-247">ファイル</span><span class="sxs-lookup"><span data-stu-id="92ead-247">Files</span></span> | <span data-ttu-id="92ead-248">行っ</span><span class="sxs-lookup"><span data-stu-id="92ead-248">Recent</span></span> | <span data-ttu-id="92ead-249">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-249">Available</span></span> |
| | <span data-ttu-id="92ead-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92ead-250">Microsoft Teams</span></span> | <span data-ttu-id="92ead-251">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-251">Available</span></span> |
| <span data-ttu-id="92ead-252">ストア</span><span class="sxs-lookup"><span data-stu-id="92ead-252">Store</span></span> | <span data-ttu-id="92ead-253">App Store</span><span class="sxs-lookup"><span data-stu-id="92ead-253">App Store</span></span> | <span data-ttu-id="92ead-254">政府バックログの場合</span><span class="sxs-lookup"><span data-stu-id="92ead-254">On the Government backlog</span></span> |
| <span data-ttu-id="92ead-255">検索</span><span class="sxs-lookup"><span data-stu-id="92ead-255">Search</span></span> | <span data-ttu-id="92ead-256">メッセージ</span><span class="sxs-lookup"><span data-stu-id="92ead-256">Messages</span></span> | <span data-ttu-id="92ead-257">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-257">Available</span></span> |
| | <span data-ttu-id="92ead-258">ユーザー</span><span class="sxs-lookup"><span data-stu-id="92ead-258">People</span></span> | <span data-ttu-id="92ead-259">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-259">Available</span></span> |
| | <span data-ttu-id="92ead-260">ファイル</span><span class="sxs-lookup"><span data-stu-id="92ead-260">Files</span></span> | <span data-ttu-id="92ead-261">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-261">Available</span></span> |
| | <span data-ttu-id="92ead-262">スラッシュコマンド</span><span class="sxs-lookup"><span data-stu-id="92ead-262">Slash commands</span></span> | <span data-ttu-id="92ead-263">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-263">Available</span></span> |
| <span data-ttu-id="92ead-264">コン</span><span class="sxs-lookup"><span data-stu-id="92ead-264">Compliance</span></span> | <span data-ttu-id="92ead-265">コンプライアンスコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="92ead-265">Compliance content search</span></span> | <span data-ttu-id="92ead-266">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-266">Available</span></span> |
| | <span data-ttu-id="92ead-267">保持</span><span class="sxs-lookup"><span data-stu-id="92ead-267">Retention</span></span> | <span data-ttu-id="92ead-268">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-268">Available</span></span> |
| | <span data-ttu-id="92ead-269">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="92ead-269">Audit log search</span></span> | <span data-ttu-id="92ead-270">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-270">Available</span></span> |
| | <span data-ttu-id="92ead-271">法的保持</span><span class="sxs-lookup"><span data-stu-id="92ead-271">Legal hold</span></span> | <span data-ttu-id="92ead-272">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-272">Available</span></span> |
| | <span data-ttu-id="92ead-273">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="92ead-273">eDiscovery</span></span> | <span data-ttu-id="92ead-274">利用可能</span><span class="sxs-lookup"><span data-stu-id="92ead-274">Available</span></span> |

> [!Note]

> <span data-ttu-id="92ead-275">GCC クラウドで他の作業負荷が完全に利用できるようになると、その他の統合作業が完了したときにチームで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="92ead-275">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="92ead-277">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="92ead-277">Decision point</span></span>|<ul><li><span data-ttu-id="92ead-278">Teams 機能セットが組織のニーズを満たすかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="92ead-278">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="92ead-279">手順5</span><span class="sxs-lookup"><span data-stu-id="92ead-279">Step 5.</span></span> <span data-ttu-id="92ead-280">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="92ead-280">Plan for governance</span></span>

<span data-ttu-id="92ead-281">ガバナンスの要件と、それらをどのように満たすかを決定します。</span><span class="sxs-lookup"><span data-stu-id="92ead-281">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="92ead-282">詳細については、「 [Teams のガバナンスの計画」](plan-teams-governance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ead-282">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="92ead-284">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="92ead-284">Decision point</span></span>|<ul><li><span data-ttu-id="92ead-285">[チームのガバナンス計画](plan-teams-governance.md)のガイドラインに従って、ガバナンス要件を特定して文書化します。</span><span class="sxs-lookup"><span data-stu-id="92ead-285">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="92ead-286">手順6</span><span class="sxs-lookup"><span data-stu-id="92ead-286">Step 6.</span></span> <span data-ttu-id="92ead-287">チームをコラボレーションのために展開する</span><span class="sxs-lookup"><span data-stu-id="92ead-287">Deploy Teams for collaboration</span></span>

<span data-ttu-id="92ead-288">Microsoft 365 Government – GCC に onboarded したら、「 [Microsoft Teams をロールアウトする方法](How-to-roll-out-teams.md)」に記載されている展開の推奨パスに従います。</span><span class="sxs-lookup"><span data-stu-id="92ead-288">After you’ve been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="92ead-289">お客様の導入と変更管理チームやチームのチャンピオンに協力してください。</span><span class="sxs-lookup"><span data-stu-id="92ead-289">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="92ead-290">また、 [Fasttrack](https://www.microsoft.com/fasttrack)または選択したパートナーと連携してサービスを稼働させることもできます。</span><span class="sxs-lookup"><span data-stu-id="92ead-290">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="92ead-291">手順7</span><span class="sxs-lookup"><span data-stu-id="92ead-291">Step 7.</span></span> <span data-ttu-id="92ead-292">会議と音声のチームを展開する</span><span class="sxs-lookup"><span data-stu-id="92ead-292">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="92ead-293">これは、より幅広いステークホルダーグループで Teams を使用して、会議や[クラウド音声機能](cloud-voice-deployment.md)のロールアウトの計画を開始するのに非常に時間がかかることです。</span><span class="sxs-lookup"><span data-stu-id="92ead-293">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

