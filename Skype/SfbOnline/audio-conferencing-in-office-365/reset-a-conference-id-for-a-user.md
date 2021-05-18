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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でユーザーの会議 ID をリセットし、会議の更新および移行ツールへのリンクを取得する手順について説明します。 '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237773"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="4c7ac-103">Skype for Business Online でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="4c7ac-103">Reset a conference ID for a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="4c7ac-104">Microsoft Teams で会議 ID をリセットする方法の詳細については、「 [Microsoft Teams でユーザーの会議 ID をリセットする](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="4c7ac-105">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="4c7ac-106">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c7ac-107">会議プロバイダーが Microsoft の場合、ユーザーの会議 ID は [動的のみ] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="4c7ac-108">これは変更できません。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-108">This cannot be changed.</span></span> <span data-ttu-id="4c7ac-109">会議 ID は、電話会議が有効にされる Skype for Business ユーザーにのみ自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="4c7ac-110">ユーザーの会議 ID のリセット</span><span class="sxs-lookup"><span data-stu-id="4c7ac-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="4c7ac-111">[Skype for Business **センターで、[電話** 会議ユーザー]をクリックし、ユーザーを選択し、[操作] ウィンドウの [会議 ID] で [リセット]  >  を **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="4c7ac-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="4c7ac-112">[会議 **ID のリセット] ウィンドウで、[** はい] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="4c7ac-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4c7ac-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4c7ac-114">既定では、メールはユーザーに送信されますが、オフにできます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4c7ac-115">会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="4c7ac-116">このメールは、プライマリ メール アドレス (多くの場合、ユーザーのメール アドレスまたはMicrosoft 365送信Office 365されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="4c7ac-117">電子メールには、新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business 会議更新ツールを使用して既存の会議を更新する手順が含まれている。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="4c7ac-118">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="4c7ac-118">What else should I know?</span></span>

- <span data-ttu-id="4c7ac-119">[操作] ウィンドウでユーザーの [電子メールで会議情報を送信する] をクリックすると、会議 ID とダイヤルイン電話番号を含むメールですべての会議情報をユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="4c7ac-120">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="4c7ac-121">会議 ID には 7 桁の数字が含まれるので、Skype for Business 管理センターまたは会議の長さを変更Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="4c7ac-122">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="4c7ac-123">電話会議のユーザーの会議 ID は、[ユーザー] ページでユーザーを選択すると、[電話会議] の [操作] ウィンドウの下部に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="4c7ac-124">新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4c7ac-125">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4c7ac-126">ユーザーは、会議ツールSkype for Business既存の会議を更新できます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="4c7ac-127">会議更新ツールをダウンロード、インストール、実行する方法については、Skype for Businessを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="4c7ac-128">Skype for Business Meeting Update Tool と Lync Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="4c7ac-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="4c7ac-129">Skype for Business Online、会議移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="4c7ac-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="4c7ac-130">Skype for Business Online、会議移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="4c7ac-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4c7ac-131">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="4c7ac-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4c7ac-132">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4c7ac-133">Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4c7ac-134">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4c7ac-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="4c7ac-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4c7ac-136">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="4c7ac-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="4c7ac-137">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4c7ac-138">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c7ac-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="4c7ac-139">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4c7ac-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="4c7ac-140">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="4c7ac-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="4c7ac-141">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="4c7ac-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="4c7ac-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c7ac-142">Related topics</span></span>

[<span data-ttu-id="4c7ac-143">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="4c7ac-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
