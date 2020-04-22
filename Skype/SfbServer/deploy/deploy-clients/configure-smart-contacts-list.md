---
title: Skype for Business クライアントでのスマート連絡先リストの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776692"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="4c651-103">Skype for Business クライアントでのスマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="4c651-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="4c651-104">**概要:** Skype for Business クライアントでスマート連絡先リスト機能を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c651-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="4c651-105">スマート連絡先リスト機能を使用すると、エンドユーザーに対して連絡先リストを自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c651-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="4c651-106">最初に Skype for Business を使用すると、ユーザーは自分のチームの上司とその他の人を自動的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c651-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="4c651-107">この機能は、Microsoft 365 および Office 365 ユーザーに対しては既定で有効になっていますが、クライアントポリシー設定を構成して、オンプレミスユーザーに対してこの機能を明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c651-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="4c651-108">この機能を構成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4c651-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="4c651-109">最大13人のユーザーが自動的にスマート連絡先リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4c651-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="4c651-110">Manager</span><span class="sxs-lookup"><span data-stu-id="4c651-110">Manager</span></span>

  2. <span data-ttu-id="4c651-111">アルファベット順での指示</span><span class="sxs-lookup"><span data-stu-id="4c651-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="4c651-112">ピア (アルファベット順)</span><span class="sxs-lookup"><span data-stu-id="4c651-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="4c651-113">ユーザーが最初にログインしたときに、"My Group" という名前の新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4c651-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="4c651-114">このグループには、[管理者] フィールドに設定されたユーザーエイリアスに基づいて、ユーザーの AD グループの関係にあるユーザーが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c651-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="4c651-115">AD グループのメンバーシップに対する変更では、最初に設定された後に、グループの更新が発生しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4c651-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="4c651-116">ユーザーが連絡先またはグループを削除した場合、連絡先またはグループは再作成されません。</span><span class="sxs-lookup"><span data-stu-id="4c651-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="4c651-117">自動タグ付けが有効になっている場合は、リスト内の連絡先にプレゼンスの変更がタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="4c651-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="4c651-118">自動タグ付けは既定で有効になっていますが、オフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4c651-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="4c651-119">グループ内のすべての新しいユーザーに、連絡先リストに追加されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="4c651-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="4c651-120">ユーザーは、自分のグループまたはその他のグループに新しいメンバーを手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4c651-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="4c651-121">この機能は、初めてサインインしているユーザーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4c651-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="4c651-122">ユーザーが、モバイルデバイスや Mac などのすべてのデバイスから以前にサインインしていた場合は、そのユーザーに対して機能が有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c651-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="4c651-123">スマート連絡先リストの構成</span><span class="sxs-lookup"><span data-stu-id="4c651-123">Configure Smart contacts list</span></span>

<span data-ttu-id="4c651-124">ユーザーに対してスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c651-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="4c651-125">新しい CsClientPolicy エントリを作成し、それをグローバルクライアントポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c651-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="4c651-126">アドレス帳検索が Web 検索専用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c651-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="4c651-127">スマート連絡先リストを有効にするポリシーエントリを作成する</span><span class="sxs-lookup"><span data-stu-id="4c651-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="4c651-128">スマート連絡先リスト機能を有効にするポリシーエントリを作成するには、次のように EnableClientAutoPopulateWithTeam オプションを指定して、[新しい-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c651-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="4c651-129">次に、次のように、 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットを使用して、グローバルポリシーに対する変更を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4c651-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="4c651-130">オプションで、自動タグ付けをオフにするポリシーを次のように作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c651-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="4c651-131">また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4c651-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="4c651-132">詳細については、「 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c651-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="4c651-133">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4c651-133">Troubleshoot</span></span>

<span data-ttu-id="4c651-134">スマート連絡先リストが期待どおりに機能しない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c651-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="4c651-135">構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="4c651-135">Validate the configuration.</span></span> 

- <span data-ttu-id="4c651-136">AD 組織の情報が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c651-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="4c651-137">詳細な分析を行うために、新しいユーザーの Skype for Business クライアントログを収集します。</span><span class="sxs-lookup"><span data-stu-id="4c651-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="4c651-138">Skype for Business クライアントの UI に、アドレス帳に接続できないことを示すメッセージが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c651-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="4c651-139">アドレス帳の接続を確認するには、Skype for Business クライアント検索バーでユーザーの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="4c651-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="4c651-140">ユーザーが Skype for Business に初めてサインインすると、AD DS のレプリケーションの問題によって連絡先が未解決になることがあります。</span><span class="sxs-lookup"><span data-stu-id="4c651-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


