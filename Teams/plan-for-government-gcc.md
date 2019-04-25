---
title: Microsoft 365 米国政府向けクラウド (GCC) の展開の計画 - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: 米国政府の規制の対象となるデータを処理するエンティティでドライブ Office 365 の展開を IT プロフェッショナルのためのガイダンス
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45c3f16645755a2f459bd136aa439b2a68382f1e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32247054"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="3e965-103">Microsoft 365 政府の GCC の展開の計画</span><span class="sxs-lookup"><span data-stu-id="3e965-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="3e965-104">このガイダンスは米国連邦政府、状態、航空写真や民族のお、ローカル政府機関や政府の規制や要件の対象となるデータを処理する他のエンティティで、Office 365 の導入を促進する IT プロフェッショナルには、Microsoft の使用365 政府の GCC は、これらの要件を満たすために適しています。</span><span class="sxs-lookup"><span data-stu-id="3e965-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="3e965-105">組織が既に Microsoft 365 政府の GCC の適格性の要件が満たされるの適用やプログラムに受け入れられた場合は、1 と 2 の手順をスキップし、ステップ 3 に進みます。</span><span class="sxs-lookup"><span data-stu-id="3e965-105">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="3e965-106">手順 1 です。</span><span class="sxs-lookup"><span data-stu-id="3e965-106">Step 1.</span></span> <span data-ttu-id="3e965-107">組織が Microsoft 365 政府の GCC を必要があるし、適格性の要件を満たしているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3e965-107">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="3e965-108">Microsoft 365 政府の GCC 環境を提供米国への準拠 FedRAMP 中、刑事裁判および連邦の税情報システム (CJI と FTI のデータ型) の要件など、クラウド サービスの政府の要件。</span><span class="sxs-lookup"><span data-stu-id="3e965-108">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="3e965-109">Office 365 の機能を楽しむだけでなくは、組織はマイクロソフト 365 政府の GCC に固有の以下の機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="3e965-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="3e965-110">組織の顧客のコンテンツが Microsoft の商用の Office 365 サービスでお客様のコンテンツ論理的に分離します。</span><span class="sxs-lookup"><span data-stu-id="3e965-110">Your organization’s customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="3e965-111">組織の顧客のコンテンツは、米国内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3e965-111">Your organization’s customer content is stored within the United States.</span></span>
-   <span data-ttu-id="3e965-112">組織の顧客のコンテンツへのアクセスは、スクリーンの Microsoft の担当者に限定されます。</span><span class="sxs-lookup"><span data-stu-id="3e965-112">Access to your organization’s customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="3e965-113">Microsoft 365 政府の GCC は、証明書および米国の公的機関のお客様に必要な認定に準拠します。</span><span class="sxs-lookup"><span data-stu-id="3e965-113">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="3e965-114">Microsoft 365 政府 - 米国政府の[Office 365 の政府の計画](https://products.office.com/government/compare-office-365-government-plans)などの[特典を受ける](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)お客様は、提供する GCC の詳細についてを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3e965-114">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="3e965-115">[Office 365 の米国政府のサービスの説明](https://technet.microsoft.com/library/mt774581.aspx)では、プラットフォームの利点は、米国内でのコンプライアンス要件を満たすことの中心は、について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e965-115">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform’s benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="3e965-116">サービスの説明内の情報のテーブルを Excel ブックに転送し、2 つの列を追加することができます:**はい/いいえ、組織内での関連性**と**Y か N は、自分の組織のニーズに対応**します。</span><span class="sxs-lookup"><span data-stu-id="3e965-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="3e965-117">このサービスが組織のニーズを満たしていることを確認するのには、同僚と、この一覧を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e965-117">Then you can review this list with your colleagues to confirm that this service meets your organization’s needs.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="3e965-118">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="3e965-118">Decision points</span></span>|<ul><li><span data-ttu-id="3e965-119">Microsoft 365 政府の GCC は、組織の適切なかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3e965-119">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="3e965-120">組織が適格性の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e965-120">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="3e965-121">Microsoft 365 政府の GCC をアメリカ合衆国ではできるだけです。</span><span class="sxs-lookup"><span data-stu-id="3e965-121">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="3e965-122">-米国以外の政府機関のお客様は、いくつかの[Office 365 の政府の計画](https://products.office.com/en/government/compare-office-365-government-plans)から選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e965-122">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="3e965-123">手順 2 です。</span><span class="sxs-lookup"><span data-stu-id="3e965-123">Step 2.</span></span> <span data-ttu-id="3e965-124">Microsoft 365 政府の GCC を適用します。</span><span class="sxs-lookup"><span data-stu-id="3e965-124">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="3e965-125">持つことに、このサービスがお客様の組織は、[このサービスは、ここに適用する](https://products.office.com/government/eligibility-validation)プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e965-125">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="3e965-126">ステップ 3 です。</span><span class="sxs-lookup"><span data-stu-id="3e965-126">Step 3.</span></span> <span data-ttu-id="3e965-127">Microsoft 365 政府の GCC のデフォルトのセキュリティ設定を理解します。</span><span class="sxs-lookup"><span data-stu-id="3e965-127">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="3e965-128">[管理とセキュリティの設定](enable-features-office-365.md)を見直し、それらを変更し、既定のセキュリティ設定を変更する前に、コンプライアンスへの影響を検討する前に時間がかかることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e965-128">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="3e965-129">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3e965-129">Decision point</span></span>|<ul><li><span data-ttu-id="3e965-130">Microsoft 365 政府の GCC のセキュリティ設定を既定値のいずれかを変更するかどうか最初の変更の影響を理解するのには解決を加えたことを決定します。</span><span class="sxs-lookup"><span data-stu-id="3e965-130">Decide whether you’ll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="3e965-131">手順 4 します。</span><span class="sxs-lookup"><span data-stu-id="3e965-131">Step 4.</span></span> <span data-ttu-id="3e965-132">機能は、現在利用できないか、既定で無効になっているを理解します。</span><span class="sxs-lookup"><span data-stu-id="3e965-132">Understand which capabilities are currently unavailable or disabled by default.</span></span> 

<span data-ttu-id="3e965-133">Microsoft 365 政府の GCC をいくつかの相違がある、政府のクラウドのお客様の要件に合わせて、およびエンタープライズのプランです。</span><span class="sxs-lookup"><span data-stu-id="3e965-133">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="3e965-134">どの機能が使用できるかを確認するのには次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e965-134">Refer to the following table to see which features are available.</span></span>

|                             | <span data-ttu-id="3e965-135">機能</span><span class="sxs-lookup"><span data-stu-id="3e965-135">Feature</span></span>                     | <span data-ttu-id="3e965-136">GCC</span><span class="sxs-lookup"><span data-stu-id="3e965-136">GCC</span></span>            |
|-----------------------------|-----------------------------|----------------|
| <span data-ttu-id="3e965-137">ベース</span><span class="sxs-lookup"><span data-stu-id="3e965-137">Base</span></span> | <span data-ttu-id="3e965-138">ログイン</span><span class="sxs-lookup"><span data-stu-id="3e965-138">Login</span></span> | <span data-ttu-id="3e965-139">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-139">Available</span></span> |
| | <span data-ttu-id="3e965-140">プレゼンス</span><span class="sxs-lookup"><span data-stu-id="3e965-140">Presence</span></span> | <span data-ttu-id="3e965-141">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-141">Available</span></span> |
| | <span data-ttu-id="3e965-142">統合されたプレゼンス (Skype のビジネスと統合チーム)</span><span class="sxs-lookup"><span data-stu-id="3e965-142">Unified presence (Skype for Business and Teams unified)</span></span> | <span data-ttu-id="3e965-143">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-143">Available</span></span> |
| <span data-ttu-id="3e965-144">活動</span><span class="sxs-lookup"><span data-stu-id="3e965-144">Activity</span></span> | <span data-ttu-id="3e965-145">フィード</span><span class="sxs-lookup"><span data-stu-id="3e965-145">Feed</span></span> | <span data-ttu-id="3e965-146">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-146">Available</span></span> |
|  | <span data-ttu-id="3e965-147">マイ アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3e965-147">My Activity</span></span> | <span data-ttu-id="3e965-148">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-148">Available</span></span> |
| <span data-ttu-id="3e965-149">チャット</span><span class="sxs-lookup"><span data-stu-id="3e965-149">Chat</span></span> | <span data-ttu-id="3e965-150">会話</span><span class="sxs-lookup"><span data-stu-id="3e965-150">Conversation</span></span> | <span data-ttu-id="3e965-151">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-151">Available</span></span> |
| | <span data-ttu-id="3e965-152">ファイル</span><span class="sxs-lookup"><span data-stu-id="3e965-152">Files</span></span> | <span data-ttu-id="3e965-153">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-153">Available</span></span> |
| | <span data-ttu-id="3e965-154">組織図</span><span class="sxs-lookup"><span data-stu-id="3e965-154">Org chart</span></span> | <span data-ttu-id="3e965-155">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-155">Available</span></span> |
| | <span data-ttu-id="3e965-156">活動</span><span class="sxs-lookup"><span data-stu-id="3e965-156">Activity</span></span> | <span data-ttu-id="3e965-157">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-157">Available</span></span> |
| | <span data-ttu-id="3e965-158">相互運用機能 (1:1 チームの Skype ビジネス チャット用)</span><span class="sxs-lookup"><span data-stu-id="3e965-158">InterOp (1:1 Teams-Skype for Business chat)</span></span> | <span data-ttu-id="3e965-159">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-159">Available</span></span> |
| <span data-ttu-id="3e965-160">Teams</span><span class="sxs-lookup"><span data-stu-id="3e965-160">Teams</span></span> | <span data-ttu-id="3e965-161">チャンネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="3e965-161">Channel message</span></span> | <span data-ttu-id="3e965-162">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-162">Available</span></span> |
| | <span data-ttu-id="3e965-163">チャンネル ファイル</span><span class="sxs-lookup"><span data-stu-id="3e965-163">Channel files</span></span> | <span data-ttu-id="3e965-164">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-164">Available</span></span> |
| | <span data-ttu-id="3e965-165">OneNote] タブ</span><span class="sxs-lookup"><span data-stu-id="3e965-165">OneNote tab</span></span> | <span data-ttu-id="3e965-166">政府のバックログに</span><span class="sxs-lookup"><span data-stu-id="3e965-166">On the Government backlog</span></span> |
| | <span data-ttu-id="3e965-167">チャネルを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="3e965-167">Email a channel</span></span> | <span data-ttu-id="3e965-168">該当なし</span><span class="sxs-lookup"><span data-stu-id="3e965-168">Not available</span></span> |
| | <span data-ttu-id="3e965-169">メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e965-169">Add member</span></span> | <span data-ttu-id="3e965-170">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-170">Available</span></span> |
| | <span data-ttu-id="3e965-171">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="3e965-171">Guest access</span></span> | <span data-ttu-id="3e965-172">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-172">Available</span></span> |
| <span data-ttu-id="3e965-173">会議</span><span class="sxs-lookup"><span data-stu-id="3e965-173">Meetings</span></span> | <span data-ttu-id="3e965-174">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="3e965-174">Schedule meeting</span></span> | <span data-ttu-id="3e965-175">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-175">Available</span></span> |
| | <span data-ttu-id="3e965-176">ミーティングへの参加します。</span><span class="sxs-lookup"><span data-stu-id="3e965-176">Join meeting</span></span> | <span data-ttu-id="3e965-177">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-177">Available</span></span> |
| | <span data-ttu-id="3e965-178">VoIP 会議</span><span class="sxs-lookup"><span data-stu-id="3e965-178">VoIP meeting</span></span> | <span data-ttu-id="3e965-179">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-179">Available</span></span> |
| | <span data-ttu-id="3e965-180">デスクトップの共有</span><span class="sxs-lookup"><span data-stu-id="3e965-180">Desktop sharing</span></span> | <span data-ttu-id="3e965-181">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-181">Available</span></span> |
| | <span data-ttu-id="3e965-182">やり取りのコントロールの共有</span><span class="sxs-lookup"><span data-stu-id="3e965-182">Give and take control in sharing</span></span> | <span data-ttu-id="3e965-183">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-183">Available</span></span> |
| | <span data-ttu-id="3e965-184">会議室からの接続します。</span><span class="sxs-lookup"><span data-stu-id="3e965-184">Connect from a conference room</span></span> | <span data-ttu-id="3e965-185">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-185">Available</span></span> |
| | <span data-ttu-id="3e965-186">匿名の結合</span><span class="sxs-lookup"><span data-stu-id="3e965-186">Anonymous join</span></span> | <span data-ttu-id="3e965-187">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-187">Available</span></span> |
| | <span data-ttu-id="3e965-188">クラウドの記録</span><span class="sxs-lookup"><span data-stu-id="3e965-188">Cloud recording</span></span> | <span data-ttu-id="3e965-189">政府のバックログに</span><span class="sxs-lookup"><span data-stu-id="3e965-189">On the Government backlog</span></span> |
| | <span data-ttu-id="3e965-190">会議ノート</span><span class="sxs-lookup"><span data-stu-id="3e965-190">Meeting notes</span></span> | <span data-ttu-id="3e965-191">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-191">Available</span></span> |
| | <span data-ttu-id="3e965-192">会議をブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="3e965-192">Broadcast meetings</span></span> | <span data-ttu-id="3e965-193">政府のバックログに</span><span class="sxs-lookup"><span data-stu-id="3e965-193">On the Government backlog</span></span> |
| | <span data-ttu-id="3e965-194">連合の会議</span><span class="sxs-lookup"><span data-stu-id="3e965-194">Federated meetings</span></span> | <span data-ttu-id="3e965-195">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-195">Available</span></span> |
| | <span data-ttu-id="3e965-196">サーフェス ・ ハブのサポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3e965-196">Surface Hub support (preview)</span></span> | <span data-ttu-id="3e965-197">政府のバックログに</span><span class="sxs-lookup"><span data-stu-id="3e965-197">On the Government backlog</span></span> |
| <span data-ttu-id="3e965-198">通話</span><span class="sxs-lookup"><span data-stu-id="3e965-198">Calls</span></span> | <span data-ttu-id="3e965-199">連絡先</span><span class="sxs-lookup"><span data-stu-id="3e965-199">Contacts</span></span> | <span data-ttu-id="3e965-200">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-200">Available</span></span> |
| | <span data-ttu-id="3e965-201">履歴</span><span class="sxs-lookup"><span data-stu-id="3e965-201">History</span></span> | <span data-ttu-id="3e965-202">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-202">Available</span></span> |
| | <span data-ttu-id="3e965-203">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="3e965-203">Voicemail</span></span> | <span data-ttu-id="3e965-204">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-204">Available</span></span> |
| | <span data-ttu-id="3e965-205">VoIP 通話</span><span class="sxs-lookup"><span data-stu-id="3e965-205">VoIP call</span></span> | <span data-ttu-id="3e965-206">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-206">Available</span></span> |
| | <span data-ttu-id="3e965-207">Skype のビジネス ・ チームを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3e965-207">Skype for Business - Teams calling</span></span> | <span data-ttu-id="3e965-208">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-208">Available</span></span> |
| | <span data-ttu-id="3e965-209">通話プラン</span><span class="sxs-lookup"><span data-stu-id="3e965-209">Calling Plans</span></span> | <span data-ttu-id="3e965-210">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-210">Available</span></span> |
| | <span data-ttu-id="3e965-211">(PSTN を使用して参加するミーティングの参加者を許可する) での音声会議</span><span class="sxs-lookup"><span data-stu-id="3e965-211">Audio conferencing (by allowing meeting participants to join via PSTN)</span></span> | <span data-ttu-id="3e965-212">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-212">Available</span></span> |
| | <span data-ttu-id="3e965-213">マイクロソフトの電話システムの直接のルーティング</span><span class="sxs-lookup"><span data-stu-id="3e965-213">Microsoft Phone System direct routing</span></span> | <span data-ttu-id="3e965-214">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-214">Available</span></span> |
| | <span data-ttu-id="3e965-215">PSTN の呼び出し元のロビー</span><span class="sxs-lookup"><span data-stu-id="3e965-215">Lobby for PSTN callers</span></span> | <span data-ttu-id="3e965-216">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-216">Available</span></span> |
| | <span data-ttu-id="3e965-217">呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="3e965-217">Call queue</span></span> | <span data-ttu-id="3e965-218">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-218">Available</span></span> |
| | <span data-ttu-id="3e965-219">上司と代理人のサポート</span><span class="sxs-lookup"><span data-stu-id="3e965-219">Boss and delegate support</span></span> | <span data-ttu-id="3e965-220">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-220">Available</span></span> |
| | <span data-ttu-id="3e965-221">提案型で安全な転送</span><span class="sxs-lookup"><span data-stu-id="3e965-221">Consultative and safe transfer</span></span> | <span data-ttu-id="3e965-222">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-222">Available</span></span> |
| | <span data-ttu-id="3e965-223">画期的なを不可します。</span><span class="sxs-lookup"><span data-stu-id="3e965-223">Do not disturb breakthrough</span></span> | <span data-ttu-id="3e965-224">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-224">Available</span></span> |
| | <span data-ttu-id="3e965-225">「鳴り分け」</span><span class="sxs-lookup"><span data-stu-id="3e965-225">Distinctive ring</span></span> | <span data-ttu-id="3e965-226">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-226">Available</span></span> |
| | <span data-ttu-id="3e965-227">チーム、ビジネス、Skype で通話をグループに 1:1 と PSTN 参加者</span><span class="sxs-lookup"><span data-stu-id="3e965-227">1:1 to group call escalation with Teams, Skype for Business, and PSTN participants</span></span> | <span data-ttu-id="3e965-228">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-228">Available</span></span> |
| | <span data-ttu-id="3e965-229">グループへの転送します。</span><span class="sxs-lookup"><span data-stu-id="3e965-229">Forward to group</span></span> | <span data-ttu-id="3e965-230">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-230">Available</span></span> |
| | <span data-ttu-id="3e965-231">PSTN 通話を転送します。</span><span class="sxs-lookup"><span data-stu-id="3e965-231">Transfer to PSTN call</span></span> | <span data-ttu-id="3e965-232">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-232">Available</span></span> |
| | <span data-ttu-id="3e965-233">緊急通話のプランを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3e965-233">Emergency calling - Calling Plans</span></span> | <span data-ttu-id="3e965-234">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-234">Available</span></span> |
| | <span data-ttu-id="3e965-235">認定済みの既存の SIP 電話のサポート</span><span class="sxs-lookup"><span data-stu-id="3e965-235">Support for existing certified SIP phones</span></span> | <span data-ttu-id="3e965-236">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-236">Available</span></span> |
| | <span data-ttu-id="3e965-237">USB の HID</span><span class="sxs-lookup"><span data-stu-id="3e965-237">USB HID</span></span> | <span data-ttu-id="3e965-238">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-238">Available</span></span> |
| | <span data-ttu-id="3e965-239">通話と会議の両方の電子的証拠開示</span><span class="sxs-lookup"><span data-stu-id="3e965-239">eDiscovery for both calls and meetings</span></span> | <span data-ttu-id="3e965-240">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-240">Available</span></span> |
| | <span data-ttu-id="3e965-241">組織の自動応答</span><span class="sxs-lookup"><span data-stu-id="3e965-241">Organization auto attendant</span></span> | <span data-ttu-id="3e965-242">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-242">Available</span></span> |
| | <span data-ttu-id="3e965-243">Skype 個人向け - チーム呼び出しのサポート</span><span class="sxs-lookup"><span data-stu-id="3e965-243">Skype consumer - Teams call support</span></span> | <span data-ttu-id="3e965-244">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-244">Available</span></span> |
| <span data-ttu-id="3e965-245">ファイル</span><span class="sxs-lookup"><span data-stu-id="3e965-245">Files</span></span> | <span data-ttu-id="3e965-246">最近</span><span class="sxs-lookup"><span data-stu-id="3e965-246">Recent</span></span> | <span data-ttu-id="3e965-247">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-247">Available</span></span> |
| | <span data-ttu-id="3e965-248">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e965-248">Microsoft Teams</span></span> | <span data-ttu-id="3e965-249">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-249">Available</span></span> |
| <span data-ttu-id="3e965-250">ストア</span><span class="sxs-lookup"><span data-stu-id="3e965-250">Store</span></span> | <span data-ttu-id="3e965-251">アプリケーション ストア</span><span class="sxs-lookup"><span data-stu-id="3e965-251">App Store</span></span> | <span data-ttu-id="3e965-252">政府のバックログに</span><span class="sxs-lookup"><span data-stu-id="3e965-252">On the Government backlog</span></span> |
| <span data-ttu-id="3e965-253">検索</span><span class="sxs-lookup"><span data-stu-id="3e965-253">Search</span></span> | <span data-ttu-id="3e965-254">メッセージ</span><span class="sxs-lookup"><span data-stu-id="3e965-254">Messages</span></span> | <span data-ttu-id="3e965-255">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-255">Available</span></span> |
| | <span data-ttu-id="3e965-256">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3e965-256">People</span></span> | <span data-ttu-id="3e965-257">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-257">Available</span></span> |
| | <span data-ttu-id="3e965-258">ファイル</span><span class="sxs-lookup"><span data-stu-id="3e965-258">Files</span></span> | <span data-ttu-id="3e965-259">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-259">Available</span></span> |
| | <span data-ttu-id="3e965-260">スラッシュ コマンド</span><span class="sxs-lookup"><span data-stu-id="3e965-260">Slash commands</span></span> | <span data-ttu-id="3e965-261">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-261">Available</span></span> |
| <span data-ttu-id="3e965-262">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3e965-262">Compliance</span></span> | <span data-ttu-id="3e965-263">コンプライアンス ・ コンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="3e965-263">Compliance content search</span></span> | <span data-ttu-id="3e965-264">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-264">Available</span></span> |
| | <span data-ttu-id="3e965-265">保持</span><span class="sxs-lookup"><span data-stu-id="3e965-265">Retention</span></span> | <span data-ttu-id="3e965-266">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-266">Available</span></span> |
| | <span data-ttu-id="3e965-267">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="3e965-267">Audit log search</span></span> | <span data-ttu-id="3e965-268">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-268">Available</span></span> |
| | <span data-ttu-id="3e965-269">法的保持義務</span><span class="sxs-lookup"><span data-stu-id="3e965-269">Legal hold</span></span> | <span data-ttu-id="3e965-270">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-270">Available</span></span> |
| | <span data-ttu-id="3e965-271">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="3e965-271">eDiscovery</span></span> | <span data-ttu-id="3e965-272">利用可能</span><span class="sxs-lookup"><span data-stu-id="3e965-272">Available</span></span> |

> [!Note]

> <span data-ttu-id="3e965-273">ほかの作業負荷は、GCC の雲の中が完全に利用可能なしなるチームで使用可能なすべての追加の統合作業が完了したとき。</span><span class="sxs-lookup"><span data-stu-id="3e965-273">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="3e965-274">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3e965-274">Decision point</span></span>|<ul><li><span data-ttu-id="3e965-275">チームの機能セットが、組織のニーズを満たしているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="3e965-275">Decide whether the Teams feature set meets your organization’s needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="3e965-276">手順 5 です。</span><span class="sxs-lookup"><span data-stu-id="3e965-276">Step 5.</span></span> <span data-ttu-id="3e965-277">ガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="3e965-277">Plan for governance</span></span>

<span data-ttu-id="3e965-278">コーポレート ・ ガバナンスとどのように満たすことがお客様の要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="3e965-278">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="3e965-279">詳細については、[チームの管理のための計画](plan-teams-governance.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e965-279">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="3e965-280">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="3e965-280">Decision point</span></span>|<ul><li><span data-ttu-id="3e965-281">決定し、[チームの管理のための計画](plan-teams-governance.md)のガイドラインに従って、・ ガバナンスの要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="3e965-281">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="3e965-282">手順 6。</span><span class="sxs-lookup"><span data-stu-id="3e965-282">Step 6.</span></span> <span data-ttu-id="3e965-283">チームの共同作業を展開します。</span><span class="sxs-lookup"><span data-stu-id="3e965-283">Deploy Teams for collaboration</span></span>

<span data-ttu-id="3e965-284">Microsoft 365 政府の GCC では、onboarded をした後[FastTrack](https://www.microsoft.com/fasttrack)と、選択したパートナー サービスにオンボードを使用する標準的な展開方法に従います。</span><span class="sxs-lookup"><span data-stu-id="3e965-284">After you’ve been onboarded to Microsoft 365 Government - GCC, you can follow the standard deployment approach of using [FastTrack](https://www.microsoft.com/fasttrack) and your chosen partner to onboard to the service.</span></span>

<span data-ttu-id="3e965-285">準備ができたら、[チーム、およびチャネルを通じて、組織内でのコラボレーションを有効に](teams-overview.md)するチームを展開します。</span><span class="sxs-lookup"><span data-stu-id="3e965-285">When you’re ready, deploy Teams to [enable collaboration within your organization through teams and channels](teams-overview.md).</span></span> <span data-ttu-id="3e965-286">採用し、変更管理のチームまたはチームのエキスパートと協力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e965-286">Be sure to engage with your Adoption and Change Management team or Teams champions.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="3e965-287">手順 7 です。</span><span class="sxs-lookup"><span data-stu-id="3e965-287">Step 7.</span></span> <span data-ttu-id="3e965-288">会議および音声のチームを配置します。</span><span class="sxs-lookup"><span data-stu-id="3e965-288">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="3e965-289">広く利害関係者グループにチームを使用して、会議や[クラウドのボイス機能](cloud-voice-deployment.md)を展開するための計画を開始する絶好の機会です。</span><span class="sxs-lookup"><span data-stu-id="3e965-289">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

