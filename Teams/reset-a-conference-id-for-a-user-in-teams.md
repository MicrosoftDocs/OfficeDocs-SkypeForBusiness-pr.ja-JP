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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新および移行のツールへのリンクを取得する手順を説明します。 '
ms.openlocfilehash: f5926d838d61d38eb5b8e9f840cd9d7a4694253f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206587"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="0b9f5-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="0b9f5-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="0b9f5-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="0b9f5-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b9f5-106">お使いの電話会議プロバイダーが Microsoft の場合、ユーザーの会議 ID は既定で動的のみに設定されます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="0b9f5-107">これを変更して静的にすることは、現在サポート対象外のため、できません。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="0b9f5-108">会議 ID は、電話会議で有効になっている Microsoft Teams ユーザーに対してのみ、自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="0b9f5-109">ユーザーのために会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="0b9f5-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="0b9f5-110">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="0b9f5-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0b9f5-111">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0b9f5-112">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-112">Click **Edit**.</span></span>

3. <span data-ttu-id="0b9f5-113">**オーディオ会議**の下には、**会議 ID のリセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="0b9f5-114">**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="0b9f5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="0b9f5-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="0b9f5-116">既定では、ユーザーに電子メールが送信されますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="0b9f5-117">会議 ID をリセットした後は、新しい会議 ID を持つ電子メールをユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="0b9f5-118">この送信されます、プライマリ電子メール アドレスに、多くの場合、Office 365 メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="0b9f5-119">電子メールには、新しい会議 ID、既定のダイヤルに電話番号と既存のミーティングを更新するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="0b9f5-120">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="0b9f5-120">What else should I know?</span></span>

- <span data-ttu-id="0b9f5-121">**オーディオ会議**セクション内のユーザーの [**電子メールで会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="0b9f5-122">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="0b9f5-123">会議 ID が 7 桁の数字を含めるし、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="0b9f5-124">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="0b9f5-125">新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0b9f5-126">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0b9f5-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="0b9f5-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0b9f5-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0b9f5-131">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="0b9f5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0b9f5-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0b9f5-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0b9f5-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b9f5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0b9f5-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0b9f5-134">Related topics</span></span>

[<span data-ttu-id="0b9f5-135">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="0b9f5-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
