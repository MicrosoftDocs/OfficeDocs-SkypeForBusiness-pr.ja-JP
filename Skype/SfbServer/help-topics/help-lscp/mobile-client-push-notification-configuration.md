---
title: モバイルクライアントプッシュ通知の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Microsoft プッシュ通知と Apple プッシュ通知を構成するには、必要なプッシュ通知の種類を定義するポリシーを作成する必要があります。
ms.openlocfilehash: 3fde99c3f026f87197492417cd10611d96f7e20e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822660"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="8cede-103">モバイル クライアント: プッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="8cede-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="8cede-104">**Microsoft プッシュ通知**と**Apple プッシュ**通知を構成するには、必要なプッシュ通知の種類を定義するポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cede-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="8cede-105">メイン構成画面で、[**更新**] をクリックして、ポリシーの一覧を更新して再設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8cede-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="8cede-106">表示されるポリシーの一覧を絞り込むための検索ボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8cede-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="8cede-107">検索する名前を入力すると、ポリシーの一覧が自動的に縮小表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cede-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cede-p102">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="8cede-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="8cede-111">ポリシーの作成と編集には、次の2つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="8cede-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="8cede-112">[**新規**]: クリックして新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cede-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="8cede-113">ポリシーを適用するサイトを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cede-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="8cede-114">次に、プッシュ通知の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cede-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="8cede-115">**プッシュ通知の構成**では、作成済みのサイトに対してのみポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8cede-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="8cede-116">[**編集**]: ポリシーを選択し、[編集] をクリックして、ドロップダウンから操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cede-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="8cede-117">編集できるのは、既に作成したサイトまたはグローバルポリシーを編集したサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="8cede-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="8cede-118">[**詳細の表示]**: 現在選択されているポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cede-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="8cede-119">既存のポリシーに変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="8cede-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="8cede-120">**すべて選択**: 多数のポリシーがあり、すべてのポリシーを選択する必要がある場合は、[すべて選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cede-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="8cede-121">[**削除**: 選択したポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="8cede-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="8cede-122">**[すべて選択**して**削除**] を使用すると、すべてのポリシーが削除される</span><span class="sxs-lookup"><span data-stu-id="8cede-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="8cede-123">既定の**グローバル**ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="8cede-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="8cede-124">削除しようとすると、グローバルポリシーが既定値 (つまり、すべての設定がオフ) に戻されたことが通知されますが、ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="8cede-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="8cede-125">新しいポリシーの作成または既存のポリシーの編集は、次の2つの操作に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="8cede-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="8cede-126">**Commit**コミットアクションは、ポリシーを作成または更新し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="8cede-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="8cede-127">**キャンセル**キャンセルアクションは、最後のコミットアクション以降に行われたすべての変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="8cede-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="8cede-128">キャンセルすると、加えた変更はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="8cede-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="8cede-129">**プッシュ通知構成**では、2つの設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8cede-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="8cede-130">設定は、Microsoft および Apple のプッシュ通知サービスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8cede-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="8cede-131">いずれかのサービスのプッシュ通知を有効にするには、サービス名の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cede-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="8cede-132">オフにするには、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cede-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="8cede-133">選択が完了したら、コミットするかキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="8cede-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="8cede-134">[コミット] をクリックすると、ポリシーの変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="8cede-134">Clicking commit will save the changes to the policy.</span></span>
  

