---
title: Microsoft Teams でユーザーの会議 ID をリセットする
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新および移行のツールへのリンクを取得する手順を説明します。 '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887853"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="81a45-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="81a45-103">For information about resetting conference ID in Microsoft Teams, see Reset a conference ID for a user in Microsoft Teams.</span></span>

<span data-ttu-id="81a45-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="81a45-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="81a45-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="81a45-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81a45-106">お使いの電話会議プロバイダーが Microsoft の場合、ユーザーの会議 ID は既定で動的のみに設定されます。</span><span class="sxs-lookup"><span data-stu-id="81a45-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="81a45-107">これを変更して静的にすることは、現在サポート対象外のため、できません。</span><span class="sxs-lookup"><span data-stu-id="81a45-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="81a45-108">会議 ID は、電話会議で有効になっている Microsoft Teams ユーザーに対してのみ、自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="81a45-108">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="81a45-109">ユーザーのために会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="81a45-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="81a45-110">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="81a45-110">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="81a45-111">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a45-111">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="81a45-112">[**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a45-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="81a45-113">[**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81a45-113">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="81a45-114">会議 ID は自動的に作成され、新しい会議 ID が記載されたメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="81a45-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="81a45-115">既定では、メールはユーザーに送信されます。ただし、この動作はオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="81a45-115">By default, emails are sent to users, but it can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="81a45-116">会議 ID をリセットした後、新しい会議 ID が記載されたメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="81a45-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="81a45-117">このメールはプライマリ メール アドレスに送信され、多くの場合は、Office 365 のメールボックスに送られます。</span><span class="sxs-lookup"><span data-stu-id="81a45-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="81a45-118">メールには、新しい会議 ID、既定のダイヤルイン電話番号、既存の会議を更新するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81a45-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="81a45-119">その他の情報</span><span class="sxs-lookup"><span data-stu-id="81a45-119">What else should I know?</span></span>

- <span data-ttu-id="81a45-120">[**電話会議**] セクションのユーザーについて [**電話会議情報をメールで送信**] をクリックすると、会議 ID とダイヤルイン電話番号を含んでいるメールで、会議に必要なすべての情報をユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="81a45-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="81a45-121">このメールでは PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="81a45-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="81a45-122">会議 ID は 7 桁の値です。この長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="81a45-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="81a45-123">会議 ID をリセットすると、新しい会議 ID が [**会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="81a45-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="81a45-124">新しい会議 ID が作成されると、発信者は以前の会議 ID を使用することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="81a45-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="81a45-125">ユーザーに対して、新しい会議 ID が招待状に追加されるようにするために、既存の会議の招待をスケジュールし直すことを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81a45-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="81a45-126">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="81a45-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="81a45-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81a45-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="81a45-130">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="81a45-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="81a45-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="81a45-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="81a45-132">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81a45-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="81a45-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="81a45-133">Related topics</span></span>

<span data-ttu-id="81a45-134">[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="81a45-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
