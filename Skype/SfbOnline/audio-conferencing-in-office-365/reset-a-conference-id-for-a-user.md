---
title: ビジネス オンラインの Skype のユーザーの会議 ID をリセットします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーをリセットする手順の Skype での会議 ID のビジネス オンラインでは、会議の会議出席依頼の更新と移行ツールへのリンクを取得するかを説明します。 '
ms.openlocfilehash: 748664ec8e6584adcbcb0630147f1bcd60be9482
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229273"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="119ff-103">ビジネス オンラインの Skype のユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="119ff-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="119ff-104">Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="119ff-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="119ff-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span><span class="sxs-lookup"><span data-stu-id="119ff-p101">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="119ff-107">会議プロバイダーがマイクロソフトの場合は、動的なだけに、ユーザーの会議 Id が設定されています。</span><span class="sxs-lookup"><span data-stu-id="119ff-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="119ff-108">これを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="119ff-108">This cannot be changed.</span></span> <span data-ttu-id="119ff-109">会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="119ff-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="119ff-110">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="119ff-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="119ff-111">**ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119ff-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="119ff-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span><span class="sxs-lookup"><span data-stu-id="119ff-p103">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="119ff-p104">会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。</span><span class="sxs-lookup"><span data-stu-id="119ff-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="119ff-118">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="119ff-118">What else should I know?</span></span>

- <span data-ttu-id="119ff-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span><span class="sxs-lookup"><span data-stu-id="119ff-p105">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="119ff-121">会議 ID が 7 桁の数字を含めるし、ビジネス管理センターまたは Windows PowerShell を使用して、Skype では、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="119ff-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="119ff-122">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="119ff-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="119ff-123">[**ユーザー** ] ページで、ユーザーを選択すると、**オーディオ会議**の下にある操作ウィンドウの下部にあるユーザーが電話会議の会議 ID を表示できます。</span><span class="sxs-lookup"><span data-stu-id="119ff-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="119ff-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span><span class="sxs-lookup"><span data-stu-id="119ff-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="119ff-128">Skype for Business Meeting Update Tool と Lync Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="119ff-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="119ff-129">Skype for Business Online、会議移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="119ff-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="119ff-130">Skype for Business Online、会議移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="119ff-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="119ff-131">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="119ff-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="119ff-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="119ff-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="119ff-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="119ff-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="119ff-136">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="119ff-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="119ff-p108">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="119ff-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="119ff-139">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="119ff-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="119ff-140">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="119ff-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="119ff-141">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="119ff-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="119ff-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="119ff-142">Related topics</span></span>

[<span data-ttu-id="119ff-143">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="119ff-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
