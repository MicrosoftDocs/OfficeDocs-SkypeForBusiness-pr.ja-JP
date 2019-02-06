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
ms.openlocfilehash: dc48f427fa0b2013332c5ef34d40bad94cea0a75
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754698"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="fde33-103">Microsoft Teams で電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="fde33-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="fde33-104">Microsoft Teams ユーザーに電話会議の情報を送信することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fde33-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="fde33-105">そのような場合は、ユーザーのプロパティの [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fde33-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="fde33-106">送信するメールには、次のようなすべての電話会議の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fde33-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="fde33-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="fde33-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="fde33-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="fde33-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="fde33-109">ユーザーに送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fde33-109">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議のメール](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="fde33-111">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="fde33-111">Send an email with audio conferencing information to a user</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="fde33-113">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fde33-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fde33-114">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fde33-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fde33-115">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fde33-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="fde33-116">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fde33-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="fde33-117">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="fde33-117">What else should you know about this email?</span></span>

- <span data-ttu-id="fde33-118">送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。</span><span class="sxs-lookup"><span data-stu-id="fde33-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="fde33-119">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="fde33-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="fde33-120">リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。</span><span class="sxs-lookup"><span data-stu-id="fde33-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="fde33-121">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="fde33-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="fde33-122">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="fde33-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="fde33-123">オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。</span><span class="sxs-lookup"><span data-stu-id="fde33-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="fde33-124">マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="fde33-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fde33-125">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="fde33-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="fde33-p102">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fde33-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fde33-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="fde33-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fde33-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="fde33-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="fde33-131">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fde33-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="fde33-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fde33-132">Related topics</span></span>

[<span data-ttu-id="fde33-133">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="fde33-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
