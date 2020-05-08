---
title: Skype for Business Online で電話会議用に有効になっているユーザーのリストを表示する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business 管理センターから、ダイヤルイン会議が有効になっている組織内のユーザーのリストを表示する方法について説明します。 '
ms.openlocfilehash: 206bd52d1b2e0cfc1a72bb557c5d5dc4c0162534
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163926"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="3811c-103">Skype for Business Online で電話会議用に有効になっているユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="3811c-103">See a list of users that are enabled for Audio Conferencing in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="3811c-104">Microsoft Teams で有効になっているユーザーについては、「 [Microsoft teams で電話会議用に有効になっているユーザーのリストを表示](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3811c-104">For information about enabled users in Microsoft Teams, see [See a list of users that are enabled for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="3811c-105">電話会議用に組織の Skype for Business ユーザーを有効にした後は、有効になっているユーザーの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3811c-105">After you have enabled Skype for Business users in your organization for Audio Conferencing, you can view the list of those users who have been enabled.</span></span> <span data-ttu-id="3811c-106">リストを見ると、使用している電話会議プロバイダーの種類、ユーザーの既定のダイヤルイン電話番号、組織で動的会議 Id が有効になっていない場合にも、自分が開催した電話会議の静的な会議 Id がリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3811c-106">When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a><span data-ttu-id="3811c-107">ユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="3811c-107">Viewing a list of users</span></span>

   
- <span data-ttu-id="3811c-108">左側のナビゲーションで、[**電話会議** > **ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3811c-108">In the left navigation, go to **Audio conferencing** > **Users**.</span></span>

## <a name="what-else-should-i-know"></a><span data-ttu-id="3811c-109">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="3811c-109">What else should I know?</span></span>

- <span data-ttu-id="3811c-110">有効になっているユーザーのリストを表示すると、一覧からユーザーを選んで、操作ウィンドウを使ってそのユーザーの電話会議の設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="3811c-110">When you view the list of users that are enabled, you can select a user from the list and use the Action pane to edit the audio conferencing settings for that user.</span></span>
    
- <span data-ttu-id="3811c-111">Microsoft を電話会議プロバイダーとして使用するように構成されている1人のユーザーを選ぶと、既定の電話番号と、組織で動的会議 Id が有効になっているかどうかが表示され、ユーザーが開催する会議の会議 ID をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="3811c-111">When you select a single user that is configured to use Microsoft as the audio conferencing provider, you can view the default phone number and whether your organization is enabled for dynamic conference IDs, and you can reset the conference ID for meetings that the user organizes.</span></span>
    
- <span data-ttu-id="3811c-112">サードパーティの電話会議プロバイダーを使用するように構成されている1人のユーザーを選ぶと、電話会議プロバイダーの名前、有料電話番号、フリーダイヤル電話番号 (設定されている場合) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3811c-112">When you select a single user who is configured to use a third-party audio conferencing provider, you can view the name of the audio conferencing provider, the toll phone number, and the toll-free phone number (if they are set up).</span></span>
    
- <span data-ttu-id="3811c-113">フィルターオプションを使って、次のユーザーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3811c-113">You can use the filter options to show users that have:</span></span>
    
  - <span data-ttu-id="3811c-114">**電話会議のオン**</span><span class="sxs-lookup"><span data-stu-id="3811c-114">**Audio conferencing on**</span></span>
    
  - <span data-ttu-id="3811c-115">**電話会議のオフ**</span><span class="sxs-lookup"><span data-stu-id="3811c-115">**Audio conferencing off**</span></span>
    
  - <span data-ttu-id="3811c-116">**会議プロバイダー-Microsoft**</span><span class="sxs-lookup"><span data-stu-id="3811c-116">**Conferencing provider - Microsoft**</span></span>
    
  - <span data-ttu-id="3811c-117">**会議プロバイダー-その他**</span><span class="sxs-lookup"><span data-stu-id="3811c-117">**Conferencing provider - others**</span></span>
    
- <span data-ttu-id="3811c-118">[検索] ボタンを使用して、リスト内の個々のユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="3811c-118">You can use the search button to search for an individual user in the list.</span></span>
    
- <span data-ttu-id="3811c-119">複数のユーザーを選択して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3811c-119">You can select more than one user and do the following:</span></span>
    
  - <span data-ttu-id="3811c-120">これらのユーザーに別の既定の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="3811c-120">Select a different default number for these users.</span></span>
    
  - <span data-ttu-id="3811c-121">プロバイダーを **[なし**] に変更して、ユーザーの電話会議をオフにします。</span><span class="sxs-lookup"><span data-stu-id="3811c-121">Turn off audio conferencing for the user by changing the provider to **None**.</span></span>
    
  - <span data-ttu-id="3811c-122">ユーザーに**電話会議**ライセンスが割り当てられている場合は、電話会議プロバイダーとして Microsoft に切り替える。</span><span class="sxs-lookup"><span data-stu-id="3811c-122">Switch to Microsoft as the audio conferencing provider if the user has been assigned an **Audio Conferencing** license.</span></span>
    
  - <span data-ttu-id="3811c-123">選択したユーザーの電話会議を匿名ユーザーが有効にすることを許可または禁止する。</span><span class="sxs-lookup"><span data-stu-id="3811c-123">Allow/disallow anonymous users to activate the selected users' phone meetings.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3811c-124">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="3811c-124">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3811c-125">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="3811c-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3811c-126">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3811c-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3811c-127">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3811c-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3811c-128">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="3811c-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3811c-129">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="3811c-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3811c-130">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3811c-130">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3811c-131">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="3811c-131">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3811c-132">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="3811c-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3811c-133">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="3811c-133">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3811c-134">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="3811c-134">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3811c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3811c-135">Related topics</span></span>

[<span data-ttu-id="3811c-136">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="3811c-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
