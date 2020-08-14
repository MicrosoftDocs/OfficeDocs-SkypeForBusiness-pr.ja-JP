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
description: Microsoft Teams でユーザーの会議 ID をリセットし、会議の更新と移行ツールへのリンクを取得する手順について説明します。
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662127"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="5d0ca-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="5d0ca-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="5d0ca-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="5d0ca-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d0ca-106">会議 Id は自動的に生成され、7-9 桁の数字と、ユーザーの電話会議を有効にしたときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="5d0ca-107">**静的な会議 Id はサポートされません。**</span><span class="sxs-lookup"><span data-stu-id="5d0ca-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="5d0ca-108">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="5d0ca-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="5d0ca-109">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="5d0ca-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5d0ca-110">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5d0ca-111">[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-111">Click **Edit**.</span></span>

3. <span data-ttu-id="5d0ca-112">[電話 **会議** ] の [ **会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="5d0ca-113">[ **電話会議 ID のリセット** ] ウィンドウで、[ **リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="5d0ca-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="5d0ca-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="5d0ca-115">既定では、メールはユーザーに送信されますが、無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="5d0ca-116">会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="5d0ca-117">このメールは、プライマリメールアドレス (多くの場合、Microsoft 365 または Office 365 メールボックス) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="5d0ca-118">このメールには、新しい会議 ID、既定のダイヤルイン電話番号、および既存の会議を更新するための手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="5d0ca-119">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="5d0ca-119">What else should I know?</span></span>

- <span data-ttu-id="5d0ca-120">電話会議**のセクションで**、[電話会議情報を**メールで送信**する] をクリックすると、会議 ID、ダイヤルイン電話番号など、会議のすべての情報をメールでユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="5d0ca-121">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="5d0ca-122">7-9 桁の会議 ID は、Teams サービスによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="5d0ca-123">この長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-123">You can't change its length.</span></span>
    
- <span data-ttu-id="5d0ca-124">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="5d0ca-125">新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5d0ca-126">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5d0ca-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="5d0ca-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5d0ca-128">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5d0ca-129">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5d0ca-130">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d0ca-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="5d0ca-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5d0ca-132">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="5d0ca-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5d0ca-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5d0ca-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5d0ca-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5d0ca-134">Related topics</span></span>

[<span data-ttu-id="5d0ca-135">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="5d0ca-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
