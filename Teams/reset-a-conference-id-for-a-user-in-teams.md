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
description: Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新ツールと移行ツールへのリンクを取得する手順について説明します。
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117645"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="5ecac-103">Microsoft Teams でユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="5ecac-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="5ecac-104">動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ecac-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="5ecac-105">ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ecac-106">会議 ID は自動的に生成され、7 ~ 9 桁の数字で、ユーザーの電話会議を有効にするときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="5ecac-107">**静的会議の IP アドレスはサポートされません。**</span><span class="sxs-lookup"><span data-stu-id="5ecac-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="5ecac-108">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="5ecac-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="5ecac-109">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="5ecac-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5ecac-110">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ecac-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5ecac-111">[編集 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5ecac-111">Click **Edit**.</span></span>

3. <span data-ttu-id="5ecac-112">[電話 **会議] の [電話** 会議 **ID のリセット] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5ecac-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="5ecac-113">[会議 ID **のリセット] ウィンドウで** 、[リセット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5ecac-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="5ecac-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="5ecac-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="5ecac-115">既定では、メールはユーザーに送信されますが、これはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="5ecac-116">会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="5ecac-117">このメールはプライマリ メール アドレス (多くの場合、Microsoft 365 または Office 365 メールボックス) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="5ecac-118">メールには、新しい会議 ID、既定のダイヤルイン電話番号、既存の会議を更新するための手順が含まれている。</span><span class="sxs-lookup"><span data-stu-id="5ecac-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="5ecac-119">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="5ecac-119">What else should I know?</span></span>

- <span data-ttu-id="5ecac-120">電話会議セクションでユーザーのメールで電話会議情報を送信するをクリックすると、会議 ID とダイヤルイン電話番号を含むメールで、すべての会議情報をユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="5ecac-121">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="5ecac-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="5ecac-122">7 ~ 9 桁の会議 ID は、Teams サービスによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="5ecac-123">長さを変更できない。</span><span class="sxs-lookup"><span data-stu-id="5ecac-123">You can't change its length.</span></span>
    
- <span data-ttu-id="5ecac-124">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="5ecac-125">新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5ecac-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5ecac-126">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="5ecac-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5ecac-127">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="5ecac-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5ecac-128">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="5ecac-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5ecac-129">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="5ecac-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5ecac-130">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ecac-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5ecac-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="5ecac-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="5ecac-132">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5ecac-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="5ecac-133">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ecac-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5ecac-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5ecac-134">Related topics</span></span>

[<span data-ttu-id="5ecac-135">電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="5ecac-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)