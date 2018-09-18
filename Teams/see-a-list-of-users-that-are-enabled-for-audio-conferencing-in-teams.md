---
title: Microsoft Teams で電話会議用に有効になっているユーザーのリストを表示する
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams から、ダイヤルイン会議で有効になっている組織のユーザーのリストを表示する方法を説明します。 '
ms.openlocfilehash: 9bbdd5fd8536554c942db19c8c9f5ac41789c461
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884448"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="12543-103">Microsoft Teams で電話会議用に有効になっているユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="12543-103">See a list of users that are enabled for Audio Conferencing</span></span>

<span data-ttu-id="12543-104">自分の組織内の Microsoft Teams ユーザーを電話会議で有効にした後、それらの有効になっているユーザーのリストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="12543-104">After you have enabled Microsoft Teams users in your organization for Audio Conferencing, you can view the list of those users who have been enabled.</span></span> <span data-ttu-id="12543-105">リストを調べると、リスト内の各ユーザーが使用している電話会議プロバイダーの種類、既定のダイヤルイン電話番号、および組織が動的な会議 ID を有効にしていない場合は、それらのユーザーが開催する電話会議用の静的な会議 ID も表示されています。</span><span class="sxs-lookup"><span data-stu-id="12543-105">When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a><span data-ttu-id="12543-106">ユーザーのリストの表示</span><span class="sxs-lookup"><span data-stu-id="12543-106">Viewing a list of users</span></span>

- <span data-ttu-id="12543-107">左側のナビゲーションで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12543-107">In the left navigation bar, click **Users**.</span></span>


## <a name="what-else-should-i-know"></a><span data-ttu-id="12543-108">その他の情報</span><span class="sxs-lookup"><span data-stu-id="12543-108">What else should I know?</span></span>

- <span data-ttu-id="12543-109">有効になっているユーザーのリストを表示すると、そのリストからユーザーを選択して、そのユーザーについての電話会議設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="12543-109">When you view the list of users that are enabled, you can select a user from the list to edit the audio conferencing settings for that user.</span></span>
    
- <span data-ttu-id="12543-110">Microsoft を電話会議プロバイダーとして使用するよう構成されている 1 人のユーザーを選択すると、既定の電話番号と、組織が動的な会議 ID に対して有効になっているかどうかを表示したり、そのユーザーが開催する会議の会議 ID をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="12543-110">When you select a single user that is configured to use Microsoft as the audio conferencing provider, you can view the default phone number and whether your organization is enabled for dynamic conference IDs, and you can reset the conference ID for meetings that the user organizes.</span></span>
    
- <span data-ttu-id="12543-111">サードパーティの電話会議プロバイダーを使用するよう構成されている 1 人のユーザーを選択すると、その電話会議プロバイダーの名前、有料電話番号、無料電話番号 (セットアップしている場合) を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="12543-111">When you select a single user who is configured to use a third-party audio conferencing provider, you can view the name of the audio conferencing provider, the toll phone number, and the toll-free phone number (if they are set up).</span></span>
    
   
- <span data-ttu-id="12543-112">検索ボタンを使用して、リスト内の個別のユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="12543-112">You can use the search button to search for an individual user in the list.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="12543-113">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="12543-113">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="12543-p102">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12543-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12543-117">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="12543-117">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="12543-118">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="12543-118">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="12543-119">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12543-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="12543-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="12543-120">Related topics</span></span>

[<span data-ttu-id="12543-121">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="12543-121">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
