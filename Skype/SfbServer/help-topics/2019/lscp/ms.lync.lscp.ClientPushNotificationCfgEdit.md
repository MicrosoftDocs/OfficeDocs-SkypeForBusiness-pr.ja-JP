---
title: モバイルクライアントのプッシュ通知の構成の作成または編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の重要な 2 つの構成要素です。プッシュ通知は、メッセージが PNCH に送信されるプロセスです。メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が過ぎるまで、PNCH で保持されます。
ms.openlocfilehash: 803bc61d12263e98efe5e74764f9f60f392af95f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796486"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="9680e-105">モバイル クライアント: プッシュ通知の構成の作成または編集</span><span class="sxs-lookup"><span data-stu-id="9680e-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="9680e-p102">プッシュ通知とプッシュ通知クリアリング ハウス (PNCH) は、モビリティ機能の重要な 2 つの構成要素です。プッシュ通知は、メッセージが PNCH に送信されるプロセスです。メッセージは、モバイル クライアントに配信されるか、タイムアウト期間が過ぎるまで、PNCH で保持されます。</span><span class="sxs-lookup"><span data-stu-id="9680e-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9680e-109">この期間はプッシュ通知クリアリング ハウス側の設定値なので、展開のユーザーまたは管理者は変更できません。</span><span class="sxs-lookup"><span data-stu-id="9680e-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="9680e-110">プッシュ通知を有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9680e-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="9680e-p103">[**範囲**]: このポリシーの範囲を示します。設定値は、展開に含まれるすべてのユーザーにポリシーが適用される [**グローバル**]、または指定されたサイトのホーム サーバーに割り当てられたユーザーにのみポリシーが適用される [**サイト**] のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="9680e-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9680e-p104">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="9680e-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="9680e-116">有効にするプッシュ通知サービスの種類を選択するには、対応するチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9680e-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="9680e-117">**Microsoft プッシュ通知を有効**にすると、Skype for business アプリを使用して、クラウドベースの Pnch For Windows Phone にプッシュ通知を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9680e-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="9680e-118">アップル**プッシュ通知を有効**にすると、APPLE Pnch for IOS (IPhone、iPad など) および Skype for business アプリを使用しているデバイスのプッシュ通知が有効になります。</span><span class="sxs-lookup"><span data-stu-id="9680e-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="9680e-p105">ポリシーの編集が完了したら、[**コミット**] をクリックして変更内容を保存します。変更した設定を削除する必要がある場合は、[**キャンセル**] をクリックします。変更内容はポリシーに保存されません。</span><span class="sxs-lookup"><span data-stu-id="9680e-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

