---
title: Microsoft Teams でユーザーに割り当てられている会議 ID を表示、変更、リセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Microsoft Teams でユーザーに会議 ID を割り当てる方法と、会議 ID のパラメーターを指定する方法について説明します。 '
ms.openlocfilehash: e6b1a1ace9bdbf607fa4e1ef678687f37034a052
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838137"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="d1c21-103">Microsoft Teams でユーザーに割り当てられている会議 ID を表示およびリセットする</span><span class="sxs-lookup"><span data-stu-id="d1c21-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="d1c21-104">会議 ID は、Office 365 で電話会議用にセットアップされ、電話会議プロバイダーとして Microsoft を使用している場合に、Microsoft Teams ユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d1c21-105">会議がスケジュールされると、割り当てられた会議 ID が会議の出席依頼に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="d1c21-106">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="d1c21-107">会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこの機能を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが自分の会議 ID を忘れてしまったり、紛失したりする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d1c21-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="d1c21-108">Microsoft Teams 管理センターまたは Windows PowerShell を使用して、会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="d1c21-109">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="d1c21-110">会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user-in-teams.md)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c21-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="d1c21-111">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="d1c21-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="d1c21-112">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="d1c21-112">To view the conference ID</span></span>

<span data-ttu-id="d1c21-113">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="d1c21-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1c21-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1c21-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d1c21-115">ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c21-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d1c21-116">[電話**会議**] の下の [**電話会議 ID**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="d1c21-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d1c21-117">[メールの電話**会議情報を送信**] リンクをクリックすると、会議 ID と電話番号を含むメールのユーザーにすべての会議情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="d1c21-118">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="d1c21-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d1c21-119">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1c21-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="d1c21-120">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="d1c21-120">To reset the conference ID</span></span>

<span data-ttu-id="d1c21-121">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="d1c21-122">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="d1c21-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d1c21-123">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1c21-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d1c21-124">ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c21-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d1c21-125">[**電話会議**] で [**会議通話 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c21-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="d1c21-126">[**電話会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c21-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="d1c21-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="d1c21-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="d1c21-128">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="d1c21-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d1c21-129">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1c21-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="d1c21-130">その他の情報</span><span class="sxs-lookup"><span data-stu-id="d1c21-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="d1c21-131">新しい会議 ID を作成するか、またはリセットした後は、古い会議 ID を発信者が使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1c21-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d1c21-132">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="d1c21-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="d1c21-133">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c21-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="d1c21-134">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1c21-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d1c21-135">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="d1c21-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d1c21-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1c21-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d1c21-139">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="d1c21-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d1c21-140">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d1c21-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d1c21-141">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1c21-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="d1c21-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d1c21-142">Related topics</span></span>

[<span data-ttu-id="d1c21-143">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="d1c21-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

