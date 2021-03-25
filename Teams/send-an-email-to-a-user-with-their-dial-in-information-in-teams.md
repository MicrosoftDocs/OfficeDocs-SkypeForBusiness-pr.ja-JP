---
title: ユーザーに電話会議情報をメールで送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams の電話会議情報を含むメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: 8cc0e549d502a2c7a8d8052ebe496a82e36b6648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117215"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="7cdfe-103">Microsoft Teams の電話会議情報が含まれたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="7cdfe-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="7cdfe-104">Microsoft Teams ユーザーが電話会議情報を送信する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="7cdfe-105">この操作を行うには、ユーザーのプロパティの下にある [ **電話** 会議情報をメールで送信] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="7cdfe-106">このメールを送信すると、次を含むすべての電話会議情報が含されます。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="7cdfe-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="7cdfe-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="7cdfe-109">送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-109">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議のメール メッセージの例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="7cdfe-111">電話会議情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="7cdfe-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](media/teams-logo-30x30.png) <span data-ttu-id="7cdfe-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="7cdfe-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="7cdfe-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7cdfe-115">ページの上部にある [編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="7cdfe-116">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="7cdfe-117">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="7cdfe-117">What else should you know about this email?</span></span>

- <span data-ttu-id="7cdfe-118">電話会議を有効にすると、組織内のユーザーに送信されるメールが複数あります。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="7cdfe-119">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="7cdfe-120">ユーザーの電話会議の PIN を手動でリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="7cdfe-121">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="7cdfe-122">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="7cdfe-123">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなしに変更 **された場合**。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="7cdfe-124">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7cdfe-125">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="7cdfe-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7cdfe-126">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7cdfe-127">Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7cdfe-128">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7cdfe-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="7cdfe-129">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7cdfe-130">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7cdfe-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="7cdfe-131">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cdfe-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="7cdfe-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7cdfe-132">Related topics</span></span>

[<span data-ttu-id="7cdfe-133">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="7cdfe-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)