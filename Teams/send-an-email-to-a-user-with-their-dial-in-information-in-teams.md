---
title: ユーザーに電話会議情報を電子メールで送信する
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
description: Microsoft Teams で音声会議情報を記載したメールをユーザーに送信する方法について説明します。
ms.openlocfilehash: 13c566884c5bc3e8d5de873696541c4b88fcb271
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004199"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="20eac-103">Microsoft Teams の電話会議情報が含まれたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="20eac-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="20eac-104">ユーザー Microsoft Teams電話会議情報を送信する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="20eac-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="20eac-105">これを行うには、ユーザーのプロパティの **下** にある [電子メールで電話会議情報を送信する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20eac-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="20eac-106">このメールを送信すると、次を含むすべての電話会議情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="20eac-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="20eac-107">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="20eac-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="20eac-108">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="20eac-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="20eac-109">送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20eac-109">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議の電子メール メッセージの例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="20eac-111">電話会議情報を含むメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="20eac-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](media/teams-logo-30x30.png) <span data-ttu-id="20eac-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="20eac-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="20eac-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="20eac-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="20eac-115">ページの上部にある [編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20eac-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="20eac-116">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20eac-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="20eac-117">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="20eac-117">What else should you know about this email?</span></span>

- <span data-ttu-id="20eac-118">電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="20eac-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="20eac-119">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="20eac-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="20eac-120">ユーザーの電話会議 PIN を手動でリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="20eac-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="20eac-121">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="20eac-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="20eac-122">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="20eac-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="20eac-123">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。</span><span class="sxs-lookup"><span data-stu-id="20eac-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="20eac-124">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="20eac-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="20eac-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20eac-125">Related topics</span></span>

[<span data-ttu-id="20eac-126">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="20eac-126">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
