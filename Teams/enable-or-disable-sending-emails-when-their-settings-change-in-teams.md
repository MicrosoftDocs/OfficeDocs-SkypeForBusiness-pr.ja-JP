---
title: 有効にするか、マイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '有効にするか、暗証番号 (pin) などの設定が変更されたときにユーザー、またはマイクロソフトのチームで既定の会議番号の変更に電子メールを送信することから Skype を無効にする方法を説明します。 '
ms.openlocfilehash: 5d18d039c379bb56a861ba6f6a36d23f301150b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861892"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="32a81-103">有効にするか、マイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="32a81-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="32a81-104">ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="32a81-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="32a81-105">場合があります、ただし、マイクロソフトのチームのユーザーに送信される電子メールの数を減らしたいとします。</span><span class="sxs-lookup"><span data-stu-id="32a81-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="32a81-106">このような場合は、電子メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="32a81-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="32a81-107">オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.</span><span class="sxs-lookup"><span data-stu-id="32a81-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="32a81-108">電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="32a81-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![オーディオ会議の電子メール](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="32a81-110">メール ユーザーに送信するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="32a81-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="32a81-111">送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。</span><span class="sxs-lookup"><span data-stu-id="32a81-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="32a81-112">ときに、**オーディオ会議**のライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="32a81-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="32a81-113">リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。</span><span class="sxs-lookup"><span data-stu-id="32a81-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="32a81-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="32a81-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="32a81-115">**電話会議**のライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="32a81-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="32a81-116">オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。</span><span class="sxs-lookup"><span data-stu-id="32a81-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="32a81-117">マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="32a81-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="32a81-118">有効にするか、ユーザーに送信される電子メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="32a81-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="32a81-119">有効にするか、ユーザーに送信される電子メールを無効にするのには、マイクロソフトのチームまたは Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32a81-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="32a81-120">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="32a81-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="32a81-121">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="32a81-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="32a81-122">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a81-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="32a81-123">**ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="32a81-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="32a81-124">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32a81-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="32a81-125">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="32a81-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="32a81-126">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32a81-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="32a81-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="32a81-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="32a81-p102">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32a81-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="32a81-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="32a81-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="32a81-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="32a81-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="32a81-133">Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32a81-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="32a81-134">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="32a81-134">Related topics</span></span>

[<span data-ttu-id="32a81-135">オーディオ会議設定を変更するときにユーザーに送信される電子メール</span><span class="sxs-lookup"><span data-stu-id="32a81-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="32a81-136">ユーザーに電話会議情報が含まれたメールを送信する</span><span class="sxs-lookup"><span data-stu-id="32a81-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


