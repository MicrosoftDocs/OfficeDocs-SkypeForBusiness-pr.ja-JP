---
title: Skype for Business Online でユーザーの会議 ID をリセットする
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でユーザーの会議 ID をリセットする手順を学び、会議を更新するためのリンクと移行ツールへのリンクを取得します。 '
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850063"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="ec905-103">Skype for Business Online でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="ec905-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="ec905-104">Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec905-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="ec905-105">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec905-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="ec905-106">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="ec905-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec905-107">会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ec905-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="ec905-108">残念ながら、Skype for Business 管理センターで会議 ID を変更できる機能、または Windows Powershell を使用して動的会議 ID を静的会議 ID に変更する機能は、現在サポートされていないため、ありません。</span><span class="sxs-lookup"><span data-stu-id="ec905-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="ec905-109">会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ec905-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="ec905-110">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="ec905-110">Resetting the meeting conference ID for a user</span></span>
   
1. <span data-ttu-id="ec905-111">**Skype for Business 管理センター**で、**[電話会議]** > **[ユーザー]** をクリックして、[操作] ウィンドウの下の**会議 ID** で **[リセット]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec905-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
2. <span data-ttu-id="ec905-112">[**会議 ID をリセットしますか?**] ウインドウで、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec905-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="ec905-113">会議 ID が自動的に生成されて、ユーザーに新しい会議 ID を含む電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="ec905-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="ec905-114">デフォルトで、電子メールがユーザーに送信されますが、この設定をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec905-114">By default, emails are sent to users, but it can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec905-p104">会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。</span><span class="sxs-lookup"><span data-stu-id="ec905-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="ec905-118">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="ec905-118">What else should I know?</span></span>

- <span data-ttu-id="ec905-119">[操作] ウィンドウでユーザーのために [**電話会議情報をメールで送信**] をクリックすると、会議 ID とダイヤルイン電話番号など、会議に必要なすべての情報をメールに記載して、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="ec905-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="ec905-120">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="ec905-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="ec905-121">会議 ID には 7 桁の情報が含まれます。Skype for Business 管理センターで、または Windows PowerShell を使用して、この長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec905-121">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="ec905-122">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec905-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="ec905-123">ユーザーが電話会議に使用する会議 ID は、[ **ユーザー**] ページでユーザーを選ぶと、[ **電話会議**] の [操作] ウィンドウの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec905-123">The conference ID for a user for dial-in conferencing can be viewed at the bottom of the Action pane under **Dial-in conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="ec905-124">新しい会議 ID が作成された後、呼び出し元は古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="ec905-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="ec905-125">新しい会議 ID が招待状に追加されたことを確認するには、既存の会議招待を再スケジュールするのにユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec905-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="ec905-126">ユーザーは Skype for Business Meeting Tool を使って、既存の会議を更新できます。</span><span class="sxs-lookup"><span data-stu-id="ec905-126">The users can use Skype for Business Meeting Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="ec905-127">Skype for Business Meeting Update Tool をダウンロード、インストール、実行する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec905-127">To see how to download, install and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="ec905-128">Skype for Business Meeting Update Tool と Lync Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="ec905-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="ec905-129">Skype for Business Online、会議移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="ec905-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="ec905-130">Skype for Business Online、会議移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="ec905-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ec905-131">Windows PowerShell を管理する方法を知る必要がありますか？</span><span class="sxs-lookup"><span data-stu-id="ec905-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ec905-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec905-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ec905-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ec905-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ec905-136">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ec905-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ec905-p108">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec905-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ec905-139">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ec905-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ec905-140">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ec905-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ec905-141">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ec905-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ec905-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ec905-142">Related topics</span></span>

<span data-ttu-id="ec905-143">[電話会議の暗証番号 (PIN) をリセットする](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="ec905-143">[](reset-the-audio-conferencing-pin.md)Reset the Audio Conferencing PIN for a user</span></span>
