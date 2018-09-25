---
title: Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 9ebd650e487b4ef3108d50ecce31eea0a936b176
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012322"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="e2d23-103">Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="e2d23-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="e2d23-104">マイクロソフトのチームのユーザーの電話会議の情報を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2d23-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="e2d23-105">[ユーザーのプロパティ] で**電子メールを使用して会議情報を送信**をクリックしてこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2d23-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="e2d23-106">この電子メールを送信するとき、すべてが含まれますのオーディオ会議の情報を含みます。</span><span class="sxs-lookup"><span data-stu-id="e2d23-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="e2d23-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="e2d23-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="e2d23-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="e2d23-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="e2d23-109">ユーザーに送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2d23-109">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議のメール](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="e2d23-111">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="e2d23-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="e2d23-112">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d23-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e2d23-113">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d23-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e2d23-114">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d23-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="e2d23-115">このメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="e2d23-115">What else should you know about this email?</span></span>

- <span data-ttu-id="e2d23-116">組織内のユーザーが電話会議で有効になった後に、それらのユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="e2d23-116">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="e2d23-117">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e2d23-118">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-118">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="e2d23-119">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e2d23-120">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e2d23-121">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダー、または [**なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-121">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e2d23-122">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="e2d23-122">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="e2d23-123">既定では、電子メールの送信者が、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e2d23-123">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell.</span></span> <span data-ttu-id="e2d23-124">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d23-124">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e2d23-125">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="e2d23-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e2d23-p103">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d23-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2d23-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2d23-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e2d23-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2d23-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e2d23-131">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2d23-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="e2d23-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e2d23-132">Related topics</span></span>

[<span data-ttu-id="e2d23-133">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="e2d23-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
