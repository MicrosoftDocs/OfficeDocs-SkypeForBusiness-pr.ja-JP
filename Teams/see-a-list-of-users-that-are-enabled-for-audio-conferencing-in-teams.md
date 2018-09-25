---
title: Microsoft Teams で電話会議用に有効になっているユーザーのリストを表示する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams から、ダイヤルイン会議で有効になっている組織のユーザーのリストを表示する方法を説明します。 '
ms.openlocfilehash: e82d0d265e89c5b717ff25ea7c58ec240b38bea0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014036"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="6c229-103">Microsoft Teams で電話会議用に有効になっているユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="6c229-103">See a list of users that are enabled for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="6c229-104">オーディオ会議の組織でマイクロソフトのチームのユーザーを有効にした後は、有効になっているユーザーの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6c229-104">After you have enabled Microsoft Teams users in your organization for Audio Conferencing, you can view the list of those users who have been enabled.</span></span> <span data-ttu-id="6c229-105">オーディオ会議プロバイダーを使用しているユーザーの既定のダイヤルインの電話番号の種類の一覧内の各ユーザーに対しても表示されます、ボックスの一覧を確認する場合と、組織は、動的な会議 Id、静的な会議 Id を有効になっていません。オーディオ会議会議を開催します。</span><span class="sxs-lookup"><span data-stu-id="6c229-105">When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a><span data-ttu-id="6c229-106">ユーザーのリストの表示</span><span class="sxs-lookup"><span data-stu-id="6c229-106">Viewing a list of users</span></span>

- <span data-ttu-id="6c229-107">左側のナビゲーションで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c229-107">In the left navigation, click **Users**.</span></span>


## <a name="what-else-should-i-know"></a><span data-ttu-id="6c229-108">その他の情報</span><span class="sxs-lookup"><span data-stu-id="6c229-108">What else should I know?</span></span>

- <span data-ttu-id="6c229-109">有効になっているユーザーのリストを表示すると、そのリストからユーザーを選択して、そのユーザーについての電話会議設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="6c229-109">When you view the list of users that are enabled, you can select a user from the list to edit the audio conferencing settings for that user.</span></span>
    
- <span data-ttu-id="6c229-110">Microsoft を電話会議プロバイダーとして使用するよう構成されている 1 人のユーザーを選択すると、既定の電話番号と、組織が動的な会議 ID に対して有効になっているかどうかを表示したり、そのユーザーが開催する会議の会議 ID をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c229-110">When you select a single user that is configured to use Microsoft as the audio conferencing provider, you can view the default phone number and whether your organization is enabled for dynamic conference IDs, and you can reset the conference ID for meetings that the user organizes.</span></span>
    
- <span data-ttu-id="6c229-111">サードパーティの電話会議プロバイダーを使用するよう構成されている 1 人のユーザーを選択すると、その電話会議プロバイダーの名前、有料電話番号、無料電話番号 (セットアップしている場合) を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="6c229-111">When you select a single user who is configured to use a third-party audio conferencing provider, you can view the name of the audio conferencing provider, the toll phone number, and the toll-free phone number (if they are set up).</span></span>
    
   
- <span data-ttu-id="6c229-112">検索ボタンを使用して、リスト内の個別のユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="6c229-112">You can use the search button to search for an individual user in the list.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6c229-113">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="6c229-113">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6c229-p102">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c229-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6c229-117">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6c229-117">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6c229-118">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6c229-118">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6c229-119">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c229-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6c229-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6c229-120">Related topics</span></span>

[<span data-ttu-id="6c229-121">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="6c229-121">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
