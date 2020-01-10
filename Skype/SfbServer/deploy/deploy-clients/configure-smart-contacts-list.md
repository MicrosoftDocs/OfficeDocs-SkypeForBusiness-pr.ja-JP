---
title: Skype for Business クライアントでスマート連絡先リストを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。'
ms.openlocfilehash: 4c867232fd07131666033dc48ff9930dcdf6dccb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002687"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="c72e8-103">Skype for Business クライアントでスマート連絡先リストを構成する</span><span class="sxs-lookup"><span data-stu-id="c72e8-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="c72e8-104">**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="c72e8-105">スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストを自動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="c72e8-106">初めて Skype for Business を使用すると、ユーザーは自分の上司と自分のチームメンバーを自動的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="c72e8-107">Office 365 ユーザーの場合、この機能は既定でオンになっていますが、クライアントポリシーの設定を構成することで、オンプレミスのユーザーに対してこの機能を明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c72e8-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="c72e8-108">この機能を構成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c72e8-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="c72e8-109">最大13人のユーザーは、次の順序でスマート連絡先リストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="c72e8-110">上司</span><span class="sxs-lookup"><span data-stu-id="c72e8-110">Manager</span></span>

  2. <span data-ttu-id="c72e8-111">直属の上司 (アルファベット順)</span><span class="sxs-lookup"><span data-stu-id="c72e8-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="c72e8-112">同僚 (アルファベット順)</span><span class="sxs-lookup"><span data-stu-id="c72e8-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="c72e8-113">ユーザーの最初のログイン時に、[マイ グループ] という名前の新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="c72e8-114">このグループには、[管理者] フィールドに入力されたユーザーエイリアスに基づいて、ユーザーの AD グループの関係に含まれるユーザーが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="c72e8-115">AD グループ メンバーシップを変更しても、最初に設定された [マイ グループ] は更新されません。</span><span class="sxs-lookup"><span data-stu-id="c72e8-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="c72e8-116">連絡先やグループを削除すると、その連絡先やグループが再作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="c72e8-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="c72e8-117">自動タグ付けが有効の場合、リスト内の連絡先がプレゼンスの変更に応じてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="c72e8-118">自動タグ付けは既定で有効ですが、無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="c72e8-119">グループ内のすべての新規ユーザーに対して、自分が連絡先リストに追加されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="c72e8-120">ユーザーは新しいメンバーを、[マイ グループ] や任意の他のグループに手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="c72e8-121">この機能はユーザーの初回ログイン時にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="c72e8-122">他のデバイス (モバイル デバイスや Mac など) から以前にログインしたことがあるユーザーに対しては、この機能は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="c72e8-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="c72e8-123">スマート連絡先リストを構成する</span><span class="sxs-lookup"><span data-stu-id="c72e8-123">Configure Smart contacts list</span></span>

<span data-ttu-id="c72e8-124">ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c72e8-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="c72e8-125">新しい CsClientPolicy エントリを作成して、グローバルクライアントポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="c72e8-126">[アドレス帳の検索] が [Web 検索] のみに構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="c72e8-127">ポリシー エントリを作成してスマート連絡先リストを有効にする</span><span class="sxs-lookup"><span data-stu-id="c72e8-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="c72e8-128">スマート連絡先リスト機能を有効にするポリシーエントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを使用して、[新しい-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="c72e8-129">次に、次の[手順でグローバル](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)ポリシーへの変更を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c72e8-130">必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c72e8-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c72e8-131">また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c72e8-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="c72e8-132">詳細については、「 [CsClientPolicy を設定](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c72e8-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="c72e8-133">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c72e8-133">Troubleshoot</span></span>

<span data-ttu-id="c72e8-134">スマート連絡先リストが正しく機能しない場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c72e8-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="c72e8-135">構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-135">Validate the configuration.</span></span> 

- <span data-ttu-id="c72e8-136">AD 組織情報が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="c72e8-137">さらに詳しく分析するには、新しいユーザーに Skype for Business クライアントログを収集します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="c72e8-138">Skype for Business クライアントの UI に、アドレス帳に接続できないことを示すメッセージが表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="c72e8-139">アドレス帳の接続を確認するには、Skype for Business クライアントの検索バーでユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="c72e8-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="c72e8-140">AD DS のレプリケーションの問題により、ユーザーが最初に Skype for Business にサインインしたときに連絡先が未解決になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c72e8-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


