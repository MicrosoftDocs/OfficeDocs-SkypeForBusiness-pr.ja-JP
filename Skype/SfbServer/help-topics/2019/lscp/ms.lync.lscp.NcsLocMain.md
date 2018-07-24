---
title: 場所のポリシー
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。
ms.openlocfilehash: 9299b3b909e36a0f0cbfb28b20cc989fe7e09bbd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985263"
---
# <a name="location-policy"></a><span data-ttu-id="0169d-103">場所のポリシー</span><span class="sxs-lookup"><span data-stu-id="0169d-103">Location Policy</span></span>
 
<span data-ttu-id="0169d-104">場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="0169d-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="0169d-105">場所ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト ポリシーおよびユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0169d-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="0169d-106">**グローバル ポリシー:** グローバル ポリシーが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="0169d-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="0169d-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="0169d-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="0169d-108">グローバル ポリシーを削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0169d-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="0169d-109">**サイトのポリシー (オプション):** ポリシーを作成できます 1 つまたは複数サイトの場所、特定のサイトにそれぞれ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0169d-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="0169d-110">サイト ポリシーは、グローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0169d-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="0169d-111">**ユーザーのポリシー (オプション):** ポリシーを作成できます 1 つまたは複数ユーザーの場所、特定のユーザーまたはユーザーのグループにそれぞれ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0169d-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="0169d-112">ユーザー ポリシーは、グローバル ポリシーおよびサイト ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="0169d-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0169d-113">場所ポリシーは、サブネットのグループであるネットワーク サイトに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0169d-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="0169d-114">ネットワーク サイトに割り当てられた場所ポリシーは、他のすべてのユーザー ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="0169d-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="0169d-115">コマンドレットを使用して、場所のポリシーをネットワーク サイトに割り当てる方法については、 [Skype のビジネス サーバー内のネットワーク サイトに場所のポリシーの追加](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0169d-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="0169d-116">詳細についてビジネス サーバーのコントロール パネルの Skype を使用して、場所のポリシーをネットワーク サイトに割り当てるには、[ネットワーク サイトの構成](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0169d-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="0169d-117">[**場所ポリシー**] ページには、組織で定義されているすべての場所ポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0169d-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="0169d-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="0169d-118">Tasks you can perform</span></span>

<span data-ttu-id="0169d-119">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0169d-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="0169d-120">新しいサイトの場所ポリシーまたはユーザーの場所ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0169d-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="0169d-121">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0169d-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="0169d-122">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0169d-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="0169d-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="0169d-123">UI Reference</span></span>

<span data-ttu-id="0169d-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="0169d-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="0169d-125">**新しい**新しいサイトの場所のポリシーまたはユーザーの場所のポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="0169d-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="0169d-126">**編集**編集するために選択した場所のポリシーを開きます、一覧で、すべての場所のポリシーを選択または選択したサイト ポリシーまたはユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0169d-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0169d-127">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0169d-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="0169d-128">**更新**場所のポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="0169d-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="0169d-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="0169d-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="0169d-130">**名**場所のポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="0169d-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="0169d-131">**スコープ**場所ポリシーのスコープを識別します。 グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="0169d-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="0169d-132">**~ 9-1-1**~ 9-1-1 のこの場所のポリシーが割り当てられているユーザーが有効なかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0169d-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="0169d-133">**場所**ユーザーが場合は、場所情報を入力することがなく、プロンプトを閉じ、免責事項が表示するかどうかと、クライアントが、新しい場所にあるサーバーをビジネスの Skype で登録する場合は、場所情報を入力するように求められますかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0169d-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="0169d-134">**PSTN の使用法**このプロファイルを使用してクライアントからの緊急電話をルーティングするために使用するボイス ルートを決定するために使用される公衆交換電話網 (PSTN) 使用法を指定します。</span><span class="sxs-lookup"><span data-stu-id="0169d-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="0169d-135">**~ 9-1-1 の数**緊急サービスに到達するためにダイヤルする番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0169d-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="0169d-136">**~ 9-1-1 マスク**緊急ダイヤル番号に変換し、ユーザーにダイヤルする数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="0169d-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="0169d-137">エンタープライズ VoIP の緊急サービスの特徴と機能についての詳細は、計画ドキュメントの[概要の ~ 9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0169d-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0169d-138">場所のポリシーの使用についての詳細は、操作マニュアルを参照の[場所のポリシーを構成する](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0169d-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

