---
title: Microsoft Teams でユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新および移行のツールへのリンクを取得する手順を説明します。 '
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019045"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="e4beb-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="e4beb-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="e4beb-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4beb-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="e4beb-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4beb-106">会議プロバイダーが Microsoft の場合、ユーザーの会議 ID がデフォルトで「動的のみ」に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="e4beb-107">残念ながら、これは、静的になるように変更することはありませんサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e4beb-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="e4beb-108">会議 Id は、マイクロソフトのチームのユーザーが電話会議を有効になっているだけ自動的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e4beb-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="e4beb-109">ユーザーのために会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="e4beb-109">Resetting the conference ID for a user</span></span>

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="e4beb-111">ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e4beb-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="e4beb-112">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4beb-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e4beb-113">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4beb-113">Click **Edit**.</span></span>

3. <span data-ttu-id="e4beb-114">**オーディオ会議**の下には、**会議 ID のリセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4beb-114">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="e4beb-115">**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4beb-115">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="e4beb-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="e4beb-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="e4beb-117">既定では、ユーザーに電子メールが送信されますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-117">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="e4beb-118">会議 ID をリセットした後は、新しい会議 ID を持つ電子メールをユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-118">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="e4beb-119">この送信されます、プライマリ電子メール アドレスに、多くの場合、Office 365 メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="e4beb-119">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="e4beb-120">電子メールには、新しい会議 ID、既定のダイヤルに電話番号と既存のミーティングを更新するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4beb-120">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="e4beb-121">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="e4beb-121">What else should I know?</span></span>

- <span data-ttu-id="e4beb-122">**オーディオ会議**セクション内のユーザーの [**電子メールで会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-122">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="e4beb-123">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="e4beb-123">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="e4beb-124">会議 ID が 7 桁の数字を含めるし、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e4beb-124">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="e4beb-125">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4beb-125">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="e4beb-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="e4beb-126">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="e4beb-127">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="e4beb-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e4beb-128">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="e4beb-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e4beb-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4beb-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4beb-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e4beb-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e4beb-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e4beb-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e4beb-134">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e4beb-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e4beb-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e4beb-135">Related topics</span></span>

[<span data-ttu-id="e4beb-136">オーディオ会議の暗証番号 (pin) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="e4beb-136">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
