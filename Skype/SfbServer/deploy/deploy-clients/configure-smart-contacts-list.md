---
title: Skype for Business クライアントでスマート連絡先リストを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について学習します。'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095801"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="1ad09-103">Skype for Business クライアントでスマート連絡先リストを構成する</span><span class="sxs-lookup"><span data-stu-id="1ad09-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="1ad09-104">**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="1ad09-105">スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストの自動作成が可能です。</span><span class="sxs-lookup"><span data-stu-id="1ad09-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="1ad09-106">最初に Skype for Business を使用すると、ユーザーは自分のマネージャーや他のユーザーをチームに自動的に表示します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="1ad09-107">この機能は、Microsoft 365 および Office 365 ユーザーの場合は既定で有効になっていますが、クライアント ポリシー設定を構成して、オンプレミスユーザーに対してこの機能を明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad09-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="1ad09-108">この機能を構成する場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ad09-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="1ad09-109">最大 13 人のユーザーは、次の順序でスマート連絡先リストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="1ad09-110">Manager</span><span class="sxs-lookup"><span data-stu-id="1ad09-110">Manager</span></span>

  2. <span data-ttu-id="1ad09-111">アルファベット順に指示する</span><span class="sxs-lookup"><span data-stu-id="1ad09-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="1ad09-112">アルファベット順のピア</span><span class="sxs-lookup"><span data-stu-id="1ad09-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="1ad09-113">ユーザーが初めてログインすると、My Group という名前の新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="1ad09-114">グループには、[マネージャー] フィールドに入力されたユーザー エイリアスに基ADユーザーのグループ関係のユーザーが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="1ad09-115">グループ メンバーシップに対する変更AD、最初に設定した後にマイ グループを更新する場合は発生し得ない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ad09-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="1ad09-116">ユーザーが連絡先またはグループを削除した場合、連絡先もグループも再作成されません。</span><span class="sxs-lookup"><span data-stu-id="1ad09-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="1ad09-117">自動タグ付けをオンにすると、リスト内の連絡先にプレゼンスの変更のタグが付けされます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="1ad09-118">自動タグ付けは既定でオンになっていますが、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="1ad09-119">グループ内のすべての新しいユーザーに、連絡先リストに追加されたという通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="1ad09-120">ユーザーは、自分のマイ グループまたは選択した他のグループに新しいメンバーを手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="1ad09-121">この機能は、初めてサインインするユーザーにのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="1ad09-122">ユーザーが以前に任意のデバイスからサインインしている場合 (たとえば、モバイル デバイスや Mac など) は、そのユーザーに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="1ad09-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="1ad09-123">スマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="1ad09-123">Configure Smart contacts list</span></span>

<span data-ttu-id="1ad09-124">ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad09-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="1ad09-125">新しい CsClientPolicy エントリを作成し、グローバル クライアント ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="1ad09-126">アドレス帳検索が Web 検索専用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="1ad09-127">スマート連絡先リストを有効にするポリシー エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="1ad09-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="1ad09-128">スマート連絡先リスト機能を有効にするポリシー エントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを使用して [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="1ad09-129">次に [、Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットを使用して、次のようにグローバル ポリシーに変更を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="1ad09-130">必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1ad09-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="1ad09-131">また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ad09-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="1ad09-132">詳細については [、「Set-CsClientPolicy」を参照してください](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1ad09-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="1ad09-133">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1ad09-133">Troubleshoot</span></span>

<span data-ttu-id="1ad09-134">スマート連絡先リストが期待通り機能していない場合は、次の項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="1ad09-135">構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-135">Validate the configuration.</span></span> 

- <span data-ttu-id="1ad09-136">組織の情報がAD確認します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="1ad09-137">新しいユーザーの Skype for Business クライアント ログを収集して、詳細な分析を行います。</span><span class="sxs-lookup"><span data-stu-id="1ad09-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="1ad09-138">Skype for Business クライアント UI にアドレス帳に接続できないというメッセージが表示されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="1ad09-139">アドレス帳の接続を確認するには、Skype for Business クライアント検索バーでユーザーの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ad09-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="1ad09-140">AD DS レプリケーションの問題により、ユーザーが最初に Skype for Business にサインインすると、連絡先が未解決になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ad09-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>