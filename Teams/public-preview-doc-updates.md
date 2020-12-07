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
ms.openlocfilehash: ab48796f877f6af33b8a3c1b2bc5a3cc56e7bd1e
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530984"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="f92e1-104">Microsoft Teams パブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="f92e1-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="f92e1-p102">プレビューに含まれている機能は完全でないため、一般公開前に変更される場合があります。これらは、評価と調査のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="f92e1-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="f92e1-p103">Microsoft Teams のパブリック プレビューを使用すると、Teams の未公開機能にいち早くアクセスできます。プレビューでは、今後加えられる機能を探したり、テストしたりできます。パブリック プレビューのあらゆる機能に関するフィードバックをお待ちしております。パブリック プレビューは、各Teams ユーザーごとに有効になっているので、組織全体への影響を心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f92e1-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="f92e1-111">更新ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f92e1-111">Set the Update policy</span></span>

 <span data-ttu-id="f92e1-112">パブリック プレビューは、ユーザーごとに有効になっています。また、パブリックプレビューを有効にするオプションは管理者ポリシーで制御されます。</span><span class="sxs-lookup"><span data-stu-id="f92e1-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="f92e1-113">更新ポリシーは、Teams アプリのプレリリースやプレビュー機能を表示する Teams や Office のプレビュー ユーザーを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f92e1-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="f92e1-114">グローバル (組織全体の既定) ポリシーを使用してカスタマイズすることも、ユーザー用に 1 つまたは複数のカスタム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f92e1-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="f92e1-115">このポリシーは、グローバルポリシーを上書きしないため、特定のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f92e1-115">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="f92e1-116">管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f92e1-116">Sign in to the admin center.</span></span>
2. <span data-ttu-id="f92e1-117">**[Teams**>**更新ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f92e1-117">Select **Teams**>**Update policies**.</span></span>

   ![[更新ポリシー オプション] を選択します。](media/updatePolicies.png)

3. <span data-ttu-id="f92e1-119">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f92e1-119">Select **Add**.</span></span>
4. <span data-ttu-id="f92e1-120">更新ポリシーに名前を付け、説明を追加し **[プレビュー機能の表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f92e1-120">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="f92e1-121">`CsTeamsUpdateManagementPolicy` コマンドレットを使用しながら、PowerShell を使用してポリシーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f92e1-121">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="f92e1-122">パブリック プレビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="f92e1-122">Enable public preview</span></span>

<span data-ttu-id="f92e1-123">デスクトップまたは Web クライアントでパブリック プレビューを有効にするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f92e1-123">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="f92e1-124">プロファイルを選び、[Teams] メニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="f92e1-124">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="f92e1-125">**[情報]** → **[パブリック プレビュー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f92e1-125">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="f92e1-126">**[パブリック プレビューに切り替える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f92e1-126">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f92e1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f92e1-127">Related topics</span></span>

[<span data-ttu-id="f92e1-128">開発者向けパブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="f92e1-128">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
