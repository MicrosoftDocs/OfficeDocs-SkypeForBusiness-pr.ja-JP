---
title: モバイル クライアントプッシュ通知構成の作成または編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: プッシュ通知とプッシュ通知クリアリング 家 (PNCH) は、モビリティ機能の 2 つの重要な部分です。 プッシュ通知は、メッセージが PNCH に送信されるプロセスです。 メッセージがモバイル クライアントに配信されるか、タイムアウト期間が経過するまで、メッセージはここで保持されます。
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810887"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="bf793-105">モバイル クライアント: プッシュ通知の構成の作成または編集</span><span class="sxs-lookup"><span data-stu-id="bf793-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="bf793-106">プッシュ通知とプッシュ通知クリアリング 家 (PNCH) は、モビリティ機能の 2 つの重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="bf793-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="bf793-107">プッシュ通知は、メッセージが PNCH に送信されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="bf793-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="bf793-108">メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が経過するまで、ここで保持されます。</span><span class="sxs-lookup"><span data-stu-id="bf793-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf793-109">この期間は、プッシュ通知クリアリング 家で設定され、展開のユーザーまたは管理者は構成できません。</span><span class="sxs-lookup"><span data-stu-id="bf793-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="bf793-110">プッシュ通知を有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bf793-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="bf793-111">**スコープ:** このポリシーのスコープをメモします。</span><span class="sxs-lookup"><span data-stu-id="bf793-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="bf793-112">グローバル **(この展開** のすべてのユーザーに適用される) またはサイト (指定したサイト内のホーム サーバーに割り当てられているユーザーのみ) のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bf793-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf793-113">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定をオーバーライドすることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf793-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="bf793-114">ポリシーの優先順位は、ユーザー ポリシー (最も影響を受ける) がサイト ポリシーを上書きし、サイト ポリシーがグローバル ポリシーよりも優先される (最も影響が少ない) という点です。</span><span class="sxs-lookup"><span data-stu-id="bf793-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="bf793-115">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="bf793-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="bf793-116">有効にするプッシュ通知サービスを選択するには、次のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf793-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="bf793-117">**Microsoft プッシュ通知を有効** にして、Skype for Business アプリを使用して Windows Phone 用のクラウドベースの PNCH へのプッシュ通知を有効にする</span><span class="sxs-lookup"><span data-stu-id="bf793-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="bf793-118">**Apple** プッシュ通知を有効にした場合、Apple の iOS を実行しているデバイス (iPhone、iPad など) と Skype for Business アプリの使用に対して Apple PNCH へのプッシュ通知が有効になります。</span><span class="sxs-lookup"><span data-stu-id="bf793-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="bf793-119">ポリシーの編集が完了したら、[確定] をクリックして **変更を** 保存します。</span><span class="sxs-lookup"><span data-stu-id="bf793-119">When you have completed the edits of the policy, click **Commit** to save your changes.</span></span> <span data-ttu-id="bf793-120">加えた変更を削除する必要がある場合は、[キャンセル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="bf793-120">If you need to delete the changes you have made, select **Cancel**.</span></span> <span data-ttu-id="bf793-121">変更はポリシーに保存されません。</span><span class="sxs-lookup"><span data-stu-id="bf793-121">No changes will be saved to the policy.</span></span>
    

