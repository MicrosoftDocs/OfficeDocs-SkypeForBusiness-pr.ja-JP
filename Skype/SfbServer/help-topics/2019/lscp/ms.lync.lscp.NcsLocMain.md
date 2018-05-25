---
title: 場所のポリシー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="location-policy"></a><span data-ttu-id="09b36-103">場所のポリシー</span><span class="sxs-lookup"><span data-stu-id="09b36-103">Location Policy</span></span>
 
<span data-ttu-id="09b36-104">場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="09b36-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="09b36-105">場所ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト ポリシーおよびユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09b36-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="09b36-106">**グローバル ポリシー:** グローバル ポリシーが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="09b36-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="09b36-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="09b36-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="09b36-108">グローバル ポリシーを削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="09b36-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="09b36-109">**サイトのポリシー (オプション):** ポリシーを作成できます 1 つまたは複数サイトの場所、特定のサイトにそれぞれ適用されます。</span><span class="sxs-lookup"><span data-stu-id="09b36-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="09b36-110">サイト ポリシーは、グローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="09b36-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="09b36-111">**ユーザーのポリシー (オプション):** ポリシーを作成できます 1 つまたは複数ユーザーの場所、特定のユーザーまたはユーザーのグループにそれぞれ適用されます。</span><span class="sxs-lookup"><span data-stu-id="09b36-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="09b36-112">ユーザー ポリシーは、グローバル ポリシーおよびサイト ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="09b36-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="09b36-113">場所ポリシーは、サブネットのグループであるネットワーク サイトに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="09b36-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="09b36-114">ネットワーク サイトに割り当てられた場所ポリシーは、他のすべてのユーザー ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="09b36-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="09b36-115">コマンドレットを使用して、場所のポリシーをネットワーク サイトに割り当てる方法については、[追加のビジネス サーバー 2015 Skype 内のネットワーク サイトに場所のポリシー](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b36-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="09b36-116">詳細についてビジネス サーバーのコントロール パネルの Skype を使用して、場所のポリシーをネットワーク サイトに割り当てるには、[ネットワーク サイトの構成](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b36-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="09b36-117">[**場所ポリシー**] ページには、組織で定義されているすべての場所ポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="09b36-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="09b36-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="09b36-118">Tasks you can perform</span></span>

<span data-ttu-id="09b36-119">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="09b36-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="09b36-120">新しいサイトの場所ポリシーまたはユーザーの場所ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="09b36-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="09b36-121">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="09b36-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="09b36-122">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="09b36-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="09b36-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="09b36-123">UI Reference</span></span>

<span data-ttu-id="09b36-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="09b36-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="09b36-125">**新しい**新しいサイトの場所のポリシーまたはユーザーの場所のポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="09b36-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="09b36-126">**編集**編集するために選択した場所のポリシーを開きます、一覧で、すべての場所のポリシーを選択または選択したサイト ポリシーまたはユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="09b36-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09b36-127">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="09b36-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="09b36-128">**更新**場所のポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="09b36-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="09b36-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="09b36-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="09b36-130">**名**場所のポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="09b36-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="09b36-131">**スコープ**場所ポリシーのスコープを識別します。 グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="09b36-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="09b36-132">**~ 9-1-1**~ 9-1-1 のこの場所のポリシーが割り当てられているユーザーが有効なかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="09b36-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="09b36-133">**場所**ユーザーが場合は、場所情報を入力することがなく、プロンプトを閉じ、免責事項が表示するかどうかと、クライアントが、新しい場所にあるサーバーをビジネスの Skype で登録する場合は、場所情報を入力するように求められますかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="09b36-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="09b36-134">**PSTN の使用法**このプロファイルを使用してクライアントからの緊急電話をルーティングするために使用するボイス ルートを決定するために使用される公衆交換電話網 (PSTN) 使用法を指定します。</span><span class="sxs-lookup"><span data-stu-id="09b36-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="09b36-135">**~ 9-1-1 の数**緊急サービスに到達するためにダイヤルする番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="09b36-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="09b36-136">**~ 9-1-1 マスク**緊急ダイヤル番号に変換し、ユーザーにダイヤルする数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="09b36-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="09b36-137">エンタープライズ VoIP の緊急サービスの特徴と機能についての詳細は、計画ドキュメントの[概要の ~ 9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b36-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="09b36-138">場所のポリシーの使用についての詳細は、操作マニュアルを参照の[場所のポリシーを構成する](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b36-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

