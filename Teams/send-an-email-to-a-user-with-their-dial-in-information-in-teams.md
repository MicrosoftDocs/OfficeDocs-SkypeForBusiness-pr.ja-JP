---
title: Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信します。
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892093"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="c1472-103">Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="c1472-103">See Send an email to a user with their Audio Conferencing information.</span></span>

<span data-ttu-id="c1472-104">Microsoft Teams ユーザーに電話会議の情報を送信することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1472-104">Sometimes Skype for Business users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="c1472-105">そのような場合は、ユーザーのプロパティの [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1472-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="c1472-106">送信するメールには、次のようなすべての電話会議の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1472-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="c1472-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="c1472-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="c1472-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="c1472-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="c1472-109">ユーザーに送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c1472-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![ダイヤルイン会議のメール](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c1472-111">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="c1472-111">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="c1472-112">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1472-112">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="c1472-113">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1472-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="c1472-114">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1472-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c1472-115">このメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="c1472-115">What else should you know about this email?</span></span>

- <span data-ttu-id="c1472-116">組織内のユーザーが電話会議で有効になった後に、それらのユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="c1472-116">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="c1472-117">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c1472-118">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="c1472-119">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c1472-120">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c1472-121">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダー、または [**なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c1472-122">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="c1472-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="c1472-123">既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c1472-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="c1472-124">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1472-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c1472-125">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="c1472-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c1472-p103">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1472-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1472-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="c1472-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c1472-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="c1472-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c1472-131">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1472-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="c1472-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c1472-132">Related topics</span></span>

[<span data-ttu-id="c1472-133">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="c1472-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
