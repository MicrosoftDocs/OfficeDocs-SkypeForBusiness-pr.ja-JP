---
title: モバイル クライアントのプッシュ通知の構成
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: マイクロソフト プッシュ通知と Apple のプッシュ通知を構成するには、必要なプッシュ通知の種類を定義するのにはポリシーを作成する必要があります。
ms.openlocfilehash: 4b0da70e5d66f31ed1c912efcdd7a13660c396f7
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371477"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="b39aa-103">モバイル クライアント: プッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="b39aa-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="b39aa-104">**マイクロソフト プッシュ通知**と**Apple のプッシュ通知**を構成するには、必要なプッシュ通知の種類を定義するのにはポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b39aa-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="b39aa-105">メインの構成] 画面で、[**更新**を更新し、ポリシーの一覧を再設定するをクリックできます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="b39aa-106">検索ボックスが表示されているポリシーの一覧を絞り込む際に提供されています。</span><span class="sxs-lookup"><span data-stu-id="b39aa-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="b39aa-107">検索する名前を入力すると自動的にポリシーの一覧を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b39aa-p102">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="b39aa-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="b39aa-111">2 つの選択は、ポリシーの作成および編集するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="b39aa-112">**新規**: 新しいポリシーを作成する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b39aa-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="b39aa-113">ポリシーを適用するためのサイトを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b39aa-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="b39aa-114">プッシュ通知の設定を構成するとします。</span><span class="sxs-lookup"><span data-stu-id="b39aa-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="b39aa-115">**プッシュ通知の構成**では、既に作成したサイトにのみポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="b39aa-116">**編集**: ポリシーを選択し、ドロップダウン ・ リストからアクションを選択して編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b39aa-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="b39aa-117">サイトが既に作成されているまたはグローバル ポリシーを編集することのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="b39aa-118">**... の詳細を表示**: 現在選択されているポリシーに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b39aa-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="b39aa-119">既存のポリシーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="b39aa-120">**すべて選択**: ポリシーの数があるし、すべてのポリシーを選択する必要がある、すべて選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b39aa-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="b39aa-121">**削除**: 選択したポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="b39aa-122">**すべてを選択**し、**削除**を使用すると、すべてのポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b39aa-123">既定の**グローバル**ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b39aa-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="b39aa-124">削除しようとした場合に通知されます、グローバル ポリシーが既定値に返されたこと (つまり、すべての設定がオフになって)、ポリシーを削除することはできませんが。</span><span class="sxs-lookup"><span data-stu-id="b39aa-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="b39aa-125">新しいポリシーを作成または既存のポリシーを編集するには、2 つのアクションに関連付けられているです。</span><span class="sxs-lookup"><span data-stu-id="b39aa-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="b39aa-126">**コミット**コミット ・ アクションを作成、ポリシーの更新や変更を保存</span><span class="sxs-lookup"><span data-stu-id="b39aa-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="b39aa-127">**キャンセル**キャンセル アクションは、最後のコミット操作以降に加えられた変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="b39aa-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="b39aa-128">キャンセルした場合、加えられた変更は失われます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="b39aa-129">2 つの設定は、**プッシュ通知**構成可能です。</span><span class="sxs-lookup"><span data-stu-id="b39aa-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="b39aa-130">設定は、マイクロソフトおよび Apple のプッシュ通知サービスに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="b39aa-131">いずれかのサービスのプッシュ通知を有効にするには、サービスの名前の横のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b39aa-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="b39aa-132">選択をオフにして、チェック ボックスをオフすることができます。</span><span class="sxs-lookup"><span data-stu-id="b39aa-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="b39aa-133">選択内容を変更したするか、コミットまたはキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="b39aa-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="b39aa-134">クリックするとコミットでは、ポリシーに変更が保存します。</span><span class="sxs-lookup"><span data-stu-id="b39aa-134">Clicking commit will save the changes to the policy.</span></span>
  

