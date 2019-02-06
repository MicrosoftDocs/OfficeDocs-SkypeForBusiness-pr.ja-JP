---
title: Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Microsoft Teams での PIN や既定の電話番号などの設定が変更されたときに、Skype でユーザーにメールを送信することを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 5f0573a0dec22791bd49eeeb6be6235ae2838c70
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754138"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="9b0b5-103">Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9b0b5-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="9b0b5-104">ユーザーが電話会議で有効になっている場合、ユーザーにはメールで自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="9b0b5-105">しかしながら、Microsoft Teams ユーザーに送信されるメールの数を削減する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="9b0b5-106">そのような場合に、メールの送信を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="9b0b5-107">メールの送信を無効にすると、ユーザーが電話会議で有効または無効になったとき、ユーザーの PIN がリセットされたとき、会議 ID および既定の電話会議の電話番号が変更されたときなどに、電話会議のメールがユーザーに送信されなくなります。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="9b0b5-108">次に示しているのは、電話会議が有効になっているユーザーに送信されるメールの例です。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![電話会議のメール](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="9b0b5-110">ユーザーにメールが送信されるとき</span><span class="sxs-lookup"><span data-stu-id="9b0b5-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="9b0b5-111">組織内のユーザーが電話会議で有効になった後に、それらのユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="9b0b5-112">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="9b0b5-113">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="9b0b5-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="9b0b5-115">**電話会議**ライセンスがユーザーから解除された場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="9b0b5-116">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダー、または [**なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="9b0b5-117">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="9b0b5-118">ユーザーに送信されているメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9b0b5-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="9b0b5-119">Microsoft Teams または Windows PowerShell を使用してメールがユーザーに送信されるのを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="9b0b5-120">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="9b0b5-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9b0b5-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9b0b5-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9b0b5-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9b0b5-124">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="9b0b5-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="9b0b5-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="9b0b5-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9b0b5-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="9b0b5-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9b0b5-p102">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9b0b5-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9b0b5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9b0b5-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9b0b5-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9b0b5-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b0b5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="9b0b5-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9b0b5-134">Related topics</span></span>

[<span data-ttu-id="9b0b5-135">電話会議の設定が変更されたときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="9b0b5-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="9b0b5-136">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="9b0b5-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


