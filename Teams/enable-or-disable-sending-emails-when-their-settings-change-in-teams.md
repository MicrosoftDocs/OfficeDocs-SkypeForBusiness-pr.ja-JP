---
title: 電話会議の設定が変更された場合のメール オプション
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ピン留め変更や既定の電話会議番号の変更などの設定Skypeを有効または無効にして、ユーザーにメールを送信する方法について説明Microsoft Teams。 '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092705"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="0f69d-103">Microsoft Teams で電話会議の設定が変更されたときのメールの自動送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0f69d-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="0f69d-104">電話会議が有効になると、ユーザーに電子メールで自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="0f69d-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="0f69d-105">ただし、ユーザーに送信されるメールの数を減らしたい場合Microsoft Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="0f69d-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="0f69d-106">このような場合は、メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0f69d-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="0f69d-107">メールの送信を無効にした場合、電話会議メールはユーザーに送信されません。たとえば、ユーザーが電話会議に対して有効または無効になっているとき、PIN がリセットされた場合、電話会議 ID と既定の会議電話番号が変更された場合のメールも含めて送信されません。</span><span class="sxs-lookup"><span data-stu-id="0f69d-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="0f69d-108">電話会議が有効になっているユーザーに送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f69d-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![電話会議の電子メール メッセージの例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="0f69d-110">メールがユーザーに送信されるのは、いつですか?</span><span class="sxs-lookup"><span data-stu-id="0f69d-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="0f69d-111">電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="0f69d-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="0f69d-112">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="0f69d-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="0f69d-113">ユーザーの電話会議 PIN を手動でリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="0f69d-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="0f69d-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="0f69d-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="0f69d-115">電話会議 **ライセンスが** 削除された場合。</span><span class="sxs-lookup"><span data-stu-id="0f69d-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="0f69d-116">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。</span><span class="sxs-lookup"><span data-stu-id="0f69d-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="0f69d-117">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="0f69d-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="0f69d-118">メールがユーザーに送信されるのを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0f69d-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="0f69d-119">ユーザーに送信Microsoft TeamsまたはWindows PowerShellを使用して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0f69d-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="0f69d-120">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="0f69d-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0f69d-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f69d-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0f69d-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f69d-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0f69d-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="0f69d-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="0f69d-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f69d-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0f69d-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="0f69d-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="0f69d-126">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f69d-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0f69d-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="0f69d-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0f69d-128">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="0f69d-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0f69d-129">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="0f69d-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0f69d-130">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f69d-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0f69d-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0f69d-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="0f69d-132">[Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0f69d-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="0f69d-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f69d-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="0f69d-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0f69d-134">Related topics</span></span>

[<span data-ttu-id="0f69d-135">電話会議の設定が変更された場合にユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="0f69d-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="0f69d-136">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="0f69d-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)