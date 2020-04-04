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
- seo-marvel-mar2020
description: Microsoft Teams で電話会議情報を記載したメールをユーザーに送信します。
ms.openlocfilehash: 2a045eaf3a2a79b893ff0d13e25d9b34224fd355
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140930"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="a3c7f-103">Microsoft Teams の電話会議情報が含まれたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="a3c7f-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="a3c7f-104">Microsoft Teams ユーザーは、電話会議情報を送信する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="a3c7f-105">これを行うには、ユーザーのプロパティの下にある [**会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="a3c7f-106">このメールを送信すると、次のようなすべての電話会議情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="a3c7f-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="a3c7f-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="a3c7f-109">送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-109">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議のメールメッセージの例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="a3c7f-111">電話会議の情報が含まれるメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="a3c7f-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) <span data-ttu-id="a3c7f-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a3c7f-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a3c7f-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a3c7f-115">ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a3c7f-116">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="a3c7f-117">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="a3c7f-117">What else should you know about this email?</span></span>

- <span data-ttu-id="a3c7f-118">電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a3c7f-119">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a3c7f-120">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a3c7f-121">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a3c7f-122">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a3c7f-123">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a3c7f-124">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a3c7f-125">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="a3c7f-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a3c7f-p102">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a3c7f-129">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="a3c7f-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a3c7f-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="a3c7f-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a3c7f-131">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3c7f-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="a3c7f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3c7f-132">Related topics</span></span>

[<span data-ttu-id="a3c7f-133">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="a3c7f-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
