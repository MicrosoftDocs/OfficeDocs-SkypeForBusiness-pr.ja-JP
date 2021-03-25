---
title: Microsoft Teams でのパブリック プレビュー
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams のパブリック プレビューについて説明します。新機能を試して、フィードバックを送信してください。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: cc3dca351924daa368658a8f0c110099768e9986
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117705"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="930cf-104">Microsoft Teams パブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="930cf-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="930cf-p102">プレビューに含まれている機能は完全でないため、一般公開前に変更される場合があります。これらは、評価と調査のみを目的としています。Office 365 Government Community Cloud (GCC) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="930cf-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="930cf-p103">Microsoft Teams のパブリック プレビューを使用すると、Teams の未公開機能にいち早くアクセスできます。プレビューでは、今後加えられる機能を探したり、テストしたりできます。パブリック プレビューのあらゆる機能に関するフィードバックをお待ちしております。パブリック プレビューは、それぞれのチーム ユーザーごとに有効になっているので、組織全体への影響を心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="930cf-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="930cf-112">Teams のパブリック プレビューで利用可能な機能の一覧については、「[Release Notes for Office Current Channel (Preview) (Office 最新チャネル (プレビュー版) のリリース ノート)](/officeupdates/current-channel-preview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="930cf-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="930cf-113">更新ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="930cf-113">Set the Update policy</span></span>

<span data-ttu-id="930cf-114">パブリック プレビューは、ユーザー単位で有効になっています。また、パブリック プレビューを有効にするオプションは管理者ポリシーで制御されます。</span><span class="sxs-lookup"><span data-stu-id="930cf-114">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="930cf-115">更新ポリシーは、Teams アプリのプレリリースやプレビュー機能を表示する Teams や Office のプレビュー ユーザーを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="930cf-115">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="930cf-116">グローバル (組織全体の既定) ポリシーを使用してカスタマイズすることも、ユーザー用に 1 つまたは複数のカスタム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="930cf-116">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="930cf-117">このポリシーは、グローバルポリシーを上書きしないため、特定のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="930cf-117">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="930cf-118">管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="930cf-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="930cf-119">**[Teams**>**更新ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="930cf-119">Select **Teams**>**Update policies**.</span></span>

   ![[更新ポリシー オプション] を選択します。](media/updatePolicies.png)

3. <span data-ttu-id="930cf-121">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="930cf-121">Select **Add**.</span></span>
4. <span data-ttu-id="930cf-122">更新ポリシーに名前を付け、説明を追加し **[プレビュー機能の表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="930cf-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="930cf-123">`CsTeamsUpdateManagementPolicy` コマンドレットを使用しながら、PowerShell を使用してポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="930cf-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="930cf-124">パブリック プレビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="930cf-124">Enable public preview</span></span>

<span data-ttu-id="930cf-125">デスクトップまたは Web クライアントでパブリック プレビューを有効にするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="930cf-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="930cf-126">プロファイルを選び、[Teams] メニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="930cf-126">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="930cf-127">**[情報]** → **[パブリック プレビュー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="930cf-127">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="930cf-128">**[パブリック プレビューに切り替える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="930cf-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="930cf-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="930cf-129">Related topics</span></span>

[<span data-ttu-id="930cf-130">開発者向けパブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="930cf-130">Public developer preview</span></span>](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)