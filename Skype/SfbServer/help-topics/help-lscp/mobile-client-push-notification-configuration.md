---
title: モバイル クライアント プッシュ通知の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '[Microsoft プッシュ通知] と [Apple Push 通知] を構成するには、どちらの種類のプッシュ通知が必要かを定義するポリシーを作成する必要があります。'
ms.openlocfilehash: 493c8138e7c5dcaeab154ce1a44054cc082d1672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810877"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="d2b09-103">モバイル クライアント: プッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="d2b09-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="d2b09-104">[**Microsoft プッシュ通知**] と [**Apple Push 通知**] を構成するには、どちらの種類のプッシュ通知が必要かを定義するポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2b09-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="d2b09-p101">メインの構成画面で、[**最新の情報に更新**] をクリックしてポリシーの一覧の内容を最新の情報に更新できます。検索ボックスを使用すると、表示されるポリシーの数を絞り込むことができます。検索する名前を入力すると、一覧に表示されるポリシーが自動的に絞り込まれます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d2b09-108">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定をオーバーライドすることがあります。</span><span class="sxs-lookup"><span data-stu-id="d2b09-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d2b09-109">ポリシーの優先順位は、ユーザー ポリシー (最も影響を受ける) がサイト ポリシーを上書きし、サイト ポリシーがグローバル ポリシーよりも優先される (最も影響が少ない) という点です。</span><span class="sxs-lookup"><span data-stu-id="d2b09-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d2b09-110">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="d2b09-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="d2b09-111">ポリシーの作成と編集には、2 つの選択肢を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="d2b09-p103">[**新規**]: クリックして新しいポリシーを作成します。ポリシーを適用するサイトを指定する必要があります。その後で、プッシュ通知の設定を構成します。[**プッシュ通知の構成**] では、既に作成済みのサイトにのみポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="d2b09-p104">[**編集**]: ポリシーを選択し、[編集] をクリックしてドロップダウン リストから操作を選択します。既に作成済みのサイトまたはグローバル ポリシーのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="d2b09-p105">[**詳細の表示**]: 現在選択中のポリシーに関する情報を表示します。既存のポリシーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="d2b09-120">[**すべて選択**]: 多数のポリシーがあり、すべてのポリシーを選択する必要がある場合、[すべて選択] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2b09-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="d2b09-p106">[**削除**]: 選択されているポリシーを削除します。[**すべて選択**] または [**削除**] を使用すると、すべてのポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="d2b09-p107">既定の **グローバル** ポリシーは削除できません。グローバル ポリシーを削除しようとすると、グローバル ポリシーの値が既定値に戻る (すべての設定がリセットされる) だけでポリシーそのものは削除されないことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="d2b09-125">新しいポリシーの作成や既存ポリシーの編集には、次の 2 つの操作が関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="d2b09-126">**Commit** コミット アクションによってポリシーが作成または更新され、変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="d2b09-127">**Cancel** キャンセル アクションは、最後のコミット アクション以降に行われた変更を破棄します。</span><span class="sxs-lookup"><span data-stu-id="d2b09-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="d2b09-128">取り消した場合、加えた変更は失われます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="d2b09-p109">[**プッシュ通知の構成**] では、2 つの設定が可能です。これらの設定は、Microsoft 用または Apple 用のプッシュ通知サービスに関連付けられます。プッシュ通知を有効にするには、どちらかのサービス名の横にあるチェック ボックスをオンにします。オフにするには、チェック ボックスをクリックして選択を解除します。選択した後で、コミットするか取り消すことができます。[コミット] をクリックすると、変更内容がポリシーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d2b09-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

