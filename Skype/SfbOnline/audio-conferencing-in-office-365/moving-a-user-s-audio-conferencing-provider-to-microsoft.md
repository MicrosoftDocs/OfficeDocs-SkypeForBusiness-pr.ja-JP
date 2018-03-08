---
title: "ユーザーの電話会議プロバイダーを Microsoft に移動します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Microsoft ダイヤルイン会議プロバイダーをサードパーティ電話会議プロバイダー (ACP) から、Skype for Business ユーザーを変更します。 "
ms.openlocfilehash: 8df53a27f3dc0934411284c373206fc4b6dcf41a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="f1439-103">ユーザーの電話会議プロバイダーを Microsoft に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1439-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="f1439-p101">電話会議で使う Skype での Office 365 Business および Microsoft チーム、Microsoft する組織が必要となる**電話会議**ライセンスを取得して、自分の電話会議プロバイダーに割り当てられているユーザーに設定する必要があります。ライセンスとコストはどの程度の詳細については、 [Office 365 で音声会議を購入するか](try-or-purchase-audio-conferencing-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1439-p101">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft. See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="f1439-106">ユーザーの電話会議プロバイダーを Microsoft に移動するには</span><span class="sxs-lookup"><span data-stu-id="f1439-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="f1439-p102">ユーザーが電話会議プロバイダーに**電話会議**のライセンスが割り当てられると、ユーザーのプロバイダーに Microsoft に自動的に設定され、それ以外のものを実行する必要はありません。場合は、ユーザーが既に電話会議プロバイダーを使用して、**電話会議**のライセンスの割り当て後に Microsoft に、ユーザーのプロバイダーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1439-p102">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else. If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="f1439-109">**電話会議**ライセンスがあるユーザーの電話会議プロバイダーが割り当てられてくださいが、別の電話会議プロバイダーを使用して、Microsoft を設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f1439-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="f1439-110">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1439-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f1439-111">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="f1439-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f1439-112">**Skype for Business 管理センター**では、**電話会議**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1439-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="f1439-p103">バナーが表示される場合、**電話会議**を持つユーザーがあることを通知するライセンス割り当てがないは Microsoft まだ、電話会議プロバイダーとして設定すると、**ここをクリックすると、それらを移動する**] をクリックします。] バナーが表示されない場合は、 **Skype for Business 管理センター**で**ユーザー**] をクリックし、[**ユーザーの電話会議に移動する準備ができて**フィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1439-p103">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**. If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="f1439-115">移動するユーザーを選択し、[アクション] ウィンドウで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1439-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="f1439-116">[**プロバイダー名**] リストには、 **Microsoft**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1439-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1439-p104">ユーザーの電話会議プロバイダーが Microsoft に変更されると、ユーザーの電話会議の情報が変更されます。この情報を維持する必要がある場合を記録してください、任意の場所にすべてのユーザーのプロバイダーを変更する前にします。</span><span class="sxs-lookup"><span data-stu-id="f1439-p104">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change. If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="f1439-119">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="f1439-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="f1439-120">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="f1439-120">What else should I know?</span></span>

- <span data-ttu-id="f1439-p105">一覧で、ユーザーを選択する場合は、ユーザーの既定の電話会議の情報を表示することができますが、電話会議の PIN を表示することはできません。電話会議のユーザーの PIN をリセットする**をリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1439-p105">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN. You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="f1439-123">ユーザーの電話会議の設定を変更する場合は、ことができます、リストからユーザーを選択し**編集**] をクリックし、[**プロパティ**] ページで変更を行います。</span><span class="sxs-lookup"><span data-stu-id="f1439-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="f1439-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f1439-124">Related topics</span></span>

[<span data-ttu-id="f1439-125">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="f1439-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

