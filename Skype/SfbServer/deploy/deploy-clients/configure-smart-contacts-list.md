---
title: ビジネス クライアント用の Skype でスマート アドレス帳を構成します。
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '概要: ビジネス クライアント用の Skype でスマートの連絡先リストの機能を有効にする方法を説明します。'
ms.openlocfilehash: 52de1eb889b1373dc6928c90a9e0e298f467d3fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896659"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="aa9fb-103">ビジネス クライアント用の Skype でスマート アドレス帳を構成します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="aa9fb-104">**の概要:** ビジネス クライアント用の Skype でスマートの連絡先リストの機能を有効にする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="aa9fb-105">スマート連絡先リスト機能を使用すると、エンド ユーザーの連絡先リストを自動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="aa9fb-106">最初に、ユーザーは、ビジネスの Skype を使用すると、自動的に参照してくださいそのマネージャーと他の人の中で。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="aa9fb-107">Office 365 ユーザーは、既定でこの機能が有効になっているが、クライアントのポリシー設定を構成することにより、オンプレミス ユーザーのこの機能を有効する必要があります明示的にします。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="aa9fb-108">この機能を構成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="aa9fb-109">13、最大のユーザーは、次の順序で、スマート アドレス帳に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="aa9fb-110">上司</span><span class="sxs-lookup"><span data-stu-id="aa9fb-110">Manager</span></span>

  2. <span data-ttu-id="aa9fb-111">直属の上司 (アルファベット順)</span><span class="sxs-lookup"><span data-stu-id="aa9fb-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="aa9fb-112">同僚 (アルファベット順)</span><span class="sxs-lookup"><span data-stu-id="aa9fb-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="aa9fb-113">ユーザーの最初のログイン時に、[マイ グループ] という名前の新しいグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="aa9fb-114">グループは、[管理者] フィールドに入力するユーザーのエイリアスに基づいてユーザーの AD グループの関係の人が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="aa9fb-115">AD グループ メンバーシップを変更しても、最初に設定された [マイ グループ] は更新されません。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="aa9fb-116">連絡先やグループを削除すると、その連絡先やグループが再作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="aa9fb-117">自動タグ付けが有効の場合、リスト内の連絡先がプレゼンスの変更に応じてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="aa9fb-118">自動タグ付けは既定で有効ですが、無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="aa9fb-119">グループ内のすべての新規ユーザーに対して、自分が連絡先リストに追加されたことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="aa9fb-120">ユーザーは新しいメンバーを、[マイ グループ] や任意の他のグループに手動で追加できます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="aa9fb-121">この機能はユーザーの初回ログイン時にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="aa9fb-122">他のデバイス (モバイル デバイスや Mac など) から以前にログインしたことがあるユーザーに対しては、この機能は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="aa9fb-123">スマート連絡先リストを構成する</span><span class="sxs-lookup"><span data-stu-id="aa9fb-123">Configure Smart contacts list</span></span>

<span data-ttu-id="aa9fb-124">ユーザーのスマート連絡先リスト機能を有効にするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="aa9fb-125">CsClientPolicy の新しいエントリを作成し、グローバル クライアント ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="aa9fb-126">[アドレス帳の検索] が [Web 検索] のみに構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="aa9fb-127">ポリシー エントリを作成してスマート連絡先リストを有効にする</span><span class="sxs-lookup"><span data-stu-id="aa9fb-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="aa9fb-128">スマート連絡先リスト機能を有効にするには、次のように EnableClientAutoPopulateWithTeam オプションを使用して[新規 CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps)コマンドレットを使用してポリシー エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="aa9fb-129">次に、次のように、グローバル ポリシーに変更を記述するのに[セット CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="aa9fb-130">必要に応じて、次のように自動タグ付けをオフにするポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="aa9fb-131">また、対応するポリシーの AddressBookAvailability パラメーターを WebSearchOnly に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="aa9fb-132">詳細については、[一連の CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="aa9fb-133">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa9fb-133">Troubleshoot</span></span>

<span data-ttu-id="aa9fb-134">スマート連絡先リストが正しく機能しない場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="aa9fb-135">構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-135">Validate the configuration.</span></span> 

- <span data-ttu-id="aa9fb-136">AD 組織情報が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="aa9fb-137">ビジネス クライアントのログの詳細な分析の新しいユーザーの Skype を収集します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="aa9fb-138">ビジネス クライアント UI の Skype では、アドレス帳に接続できないというメッセージが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="aa9fb-139">接続のアドレス帳を削除するには、ビジネスのクライアントの検索バーの Skype のユーザーの検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="aa9fb-140">AD DS レプリケーションの問題には、連絡先とユーザー最初にサインインしているビジネスの Skype が解決されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa9fb-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


