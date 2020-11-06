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
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams のパブリックプレビューについて説明します。 新機能を試して、フィードバックを送信してください。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: a2b06c58396db0e8fdb976037696b7a782d581cd
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852188"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="17edc-104">Microsoft Teams パブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="17edc-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="17edc-105">プレビューに含まれている機能は完全でないため、一般公開前に変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="17edc-105">Features included in preview might not be complete, and might undergo changes before becoming available in the public release.</span></span> <span data-ttu-id="17edc-106">これらは、評価と調査のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="17edc-106">They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="17edc-107">Microsoft Teams のパブリック プレビューを使用すると、Teams の未公開機能にいち早くアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="17edc-107">Public Preview for Microsoft Teams provides early access to unreleased features in Teams.</span></span> <span data-ttu-id="17edc-108">プレビューでは、今後加えられる機能を探したり、テストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="17edc-108">Previews allow you to explore and test upcoming features.</span></span> <span data-ttu-id="17edc-109">パブリック プレビューのあらゆる機能に関するフィードバックをお待ちしております。。</span><span class="sxs-lookup"><span data-stu-id="17edc-109">We also welcome feedback on any feature in public previews.</span></span> <span data-ttu-id="17edc-110">パブリック プレビューは、各Teams ユーザーごとに有効になっているので、組織全体への影響を心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17edc-110">Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="17edc-111">更新ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="17edc-111">Set the Update policy</span></span>

 <span data-ttu-id="17edc-112">パブリック プレビューは、ユーザーごとに有効になっています。また、パブリックプレビューを有効にするオプションは管理者ポリシーで制御されます。</span><span class="sxs-lookup"><span data-stu-id="17edc-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="17edc-113">更新ポリシーは、Teams アプリのプレリリースやプレビュー機能を表示する Teams や Office のプレビュー ユーザーを管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="17edc-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="17edc-114">グローバル (組織全体の既定) ポリシーを使用してカスタマイズすることも、ユーザー用に 1 つまたは複数のカスタム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="17edc-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span>

1. <span data-ttu-id="17edc-115">管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="17edc-115">Sign in to the admin center.</span></span>
2. <span data-ttu-id="17edc-116">**[Teams**>**更新ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17edc-116">Select **Teams**>**Update policies**.</span></span>

   ![[更新ポリシー オプション] を選択します。](media/updatePolicies.png)

3. <span data-ttu-id="17edc-118">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17edc-118">Select **Add**.</span></span>
4. <span data-ttu-id="17edc-119">更新ポリシーに名前を付け、説明を追加し **[プレビュー機能の表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="17edc-119">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="17edc-120">パブリック プレビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="17edc-120">Enable public preview</span></span>

<span data-ttu-id="17edc-121">デスクトップまたは Web クライアントでパブリック プレビューを有効にするには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17edc-121">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="17edc-122">プロファイルを選び、[Teams] メニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="17edc-122">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="17edc-123">**[情報]** → **[開発者向けプレビュー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17edc-123">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="17edc-124">**[パブリック プレビューに切り替える]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17edc-124">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="17edc-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="17edc-125">Related topics</span></span>

[<span data-ttu-id="17edc-126">開発者向けパブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="17edc-126">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)