---
title: "マイクロソフトにユーザーの電話会議プロバイダーに移動"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ビジネス ユーザー向けに、Skype をサード ・ パーティ製の音声会議プロバイダー (ACP) からマイクロソフトでは、ダイヤルイン会議プロバイダーに変更します。 "
ms.openlocfilehash: 79697299ce2c3e3fa398150cd300e305ef0c672a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="36c74-103">マイクロソフトにユーザーの電話会議プロバイダーに移動</span><span class="sxs-lookup"><span data-stu-id="36c74-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="36c74-104">ビジネスおよびマイクロソフトのチームに、Skype で Office 365 の音声会議を使用するには、マイクロソフトに組織が必要となると、オーディオ会議プロバイダーに割り当てられた**電話会議**のライセンスを取得してユーザーを設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="36c74-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="36c74-105">ライセンスと、必要なコストの詳細については、 [Office 365 に電話会議を購入するか](try-or-purchase-audio-conferencing-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c74-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="36c74-106">マイクロソフトにユーザーの電話会議プロバイダーに移動するには</span><span class="sxs-lookup"><span data-stu-id="36c74-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="36c74-107">**オーディオ会議**のライセンスが、オーディオ会議プロバイダーをインストールしていないユーザーに割り当てられている場合、ユーザーのプロバイダーをマイクロソフトに自動的に設定され、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36c74-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="36c74-108">場合は、ユーザーが既に、オーディオ会議プロバイダーを使用して、**オーディオ会議**のライセンスを割り当てることの後を Microsoft にユーザーのプロバイダーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36c74-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="36c74-109">**オーディオ会議**のライセンスを持つユーザーの電話会議プロバイダーを割り当てられますが、別のオーディオ会議プロバイダーを使用するように Microsoft を設定するには、これの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="36c74-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="36c74-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="36c74-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="36c74-111">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="36c74-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="36c74-112">**ビジネス管理センターの Skype**では、**オーディオ会議**に移動します。</span><span class="sxs-lookup"><span data-stu-id="36c74-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="36c74-113">バナーが表示される場合が、**音声会議**をしているユーザーがあることを通知するライセンスは割り当てるが、マイクロソフトは、オーディオ会議プロバイダーとして設定いない場合、 **[**ここをクリックして移動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36c74-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="36c74-114">バナーが表示されない場合、**ビジネス管理センターの Skype**で**ユーザー**] をクリックし、し、フィルターを選択、**ユーザーが電話会議に移動する準備ができて**。</span><span class="sxs-lookup"><span data-stu-id="36c74-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="36c74-115">、移動するユーザーを選択し、[アクション] ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36c74-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="36c74-116">**プロバイダー名**] ボックスの一覧で**Microsoft**を選択します。</span><span class="sxs-lookup"><span data-stu-id="36c74-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36c74-117">マイクロソフトにユーザーの電話会議プロバイダーが変更されると、ユーザーの電話会議の情報が変更されます。</span><span class="sxs-lookup"><span data-stu-id="36c74-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="36c74-118">場合はこの情報を記録してください、ユーザーのいずれかのプロバイダーを変更する前にどこかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36c74-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="36c74-119">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36c74-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="36c74-120">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="36c74-120">What else should I know?</span></span>

- <span data-ttu-id="36c74-121">場合は、ボックスの一覧でユーザーを選択すると、ユーザーの既定の音声会議情報を表示することができますが、オーディオ会議の暗証番号 (pin) を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="36c74-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="36c74-122">オーディオ会議のユーザーの暗証番号 (pin) をリセットするには、**リセット**をクリックするとします。</span><span class="sxs-lookup"><span data-stu-id="36c74-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="36c74-123">ユーザーの電話会議の設定を変更する場合は、リストからユーザーを選択し、[**編集**] をクリックし、[**プロパティ**] ページで必要な設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="36c74-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="36c74-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="36c74-124">Related topics</span></span>

[<span data-ttu-id="36c74-125">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="36c74-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

