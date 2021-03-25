---
title: Skype for Business Onlineの招待状に含まれる電話番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113223"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="09ac2-103">Skype for Business Onlineの招待状に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="09ac2-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="09ac2-104">Microsoft Teamsの会議招待状の電話番号についての詳細は、「 [Microsoft Teamsの招待状に含める電話番号を設定](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)」を参照してください。.</span><span class="sxs-lookup"><span data-stu-id="09ac2-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="09ac2-105">Microsoft 365 または Office 365 の電話会議を使用すると、組織内のユーザーは Skype for Business 会議を作成し、ユーザーが電話を使ってそれらの会議にダイヤルインできます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="09ac2-106">Microsoft 365 および Office 365 では、承認済みの電話会議プロバイダー (ACP) によってホストされる Microsoft 電話会議ブリッジまたはサードパーティの電話会議ブリッジを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="09ac2-107">電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。</span><span class="sxs-lookup"><span data-stu-id="09ac2-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="09ac2-108">お客様の地域または国/地域で利用できるダイヤルイン電話番号が見当たっている場合は **、Skype for Business** 管理センターの [音声電話番号] を使用して、[追加] をクリックし、[新しいサービス番号] をクリックします。  >    >    </span><span class="sxs-lookup"><span data-stu-id="09ac2-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="09ac2-109">[ **国/地域**]、[**州/地域**] および [**市区町村**]のリストを使って検索を絞り込みます。> また、無料電話番号サービスを探している場合には、[**無料電話番号**] を [**州/地域**] リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="09ac2-p103">会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09ac2-112">会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。</span><span class="sxs-lookup"><span data-stu-id="09ac2-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="09ac2-113">会議開催者の既定のダイヤルイン電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="09ac2-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="09ac2-114">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="09ac2-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="09ac2-115">[**管理センター**]  >  [**Skype for Business**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="09ac2-116">[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-116">Choose **Users**.</span></span>
    
    ![Skype for Business 管理センターで、ユーザーの選択を表示](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="09ac2-118">編集するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="09ac2-119">1 人のユーザーを選択するには、ユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="09ac2-120">ページ上のすべてのユーザーを選択するには、リストの上部にある [表示名] **の横にある** ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="09ac2-121">複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="09ac2-122">右側のウィンドウで、[ **編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="09ac2-124"> **電話会議** を選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="09ac2-125">[プロパティ **] ページ** の [プロバイダー名 **]** ボックスの一覧で、ユーザーのプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="09ac2-126">プロバイダーに応じて、次のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="09ac2-127">**Microsoft はプロバイダーです。** 既定の **有料電話番号** と既定の無料電話番号リストを使用して、ユーザーの既定の番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="09ac2-128">ユーザーの既定の無料電話番号として設定できるようになるには、少なくとも 1 つの無料電話番号が会議ブリッジに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ac2-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="09ac2-129">無料電話番号を取得するには、「Skype for Business のサービス電話番号を取得する [」を参照してください](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="09ac2-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="09ac2-130">**サードパーティはプロバイダーです。** ユーザーの番号を入力するには、有料電話番号と無料電話番号のフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="09ac2-131">電話会議の電話番号をリセットする</span><span class="sxs-lookup"><span data-stu-id="09ac2-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="09ac2-132">[ **Skype for Business 管理センター**] で、[ **電話会議**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="09ac2-133">ページの上部で、[ **ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="09ac2-134">リセットするユーザーを選択し、操作ウィンドウで [**クリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09ac2-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="09ac2-135">既定では、ユーザーの会議の設定を変更すると、ユーザーに電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="09ac2-136">これを変更する場合は、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09ac2-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="09ac2-137">ユーザーの電話会議の設定を変更する場合は、定期的な会議と今後の Skype for Business 会議を更新して出席者に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09ac2-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="09ac2-138">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="09ac2-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="09ac2-139">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="09ac2-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="09ac2-140">特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-140">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="09ac2-141">ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="09ac2-142">ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09ac2-143">BridgeID を見つけるには **、Get-CsOnlineDialInConferencingBridge コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="09ac2-144">既定の無料電話番号がないユーザー全員の無料電話番号を既定で +18005551234 に設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="09ac2-145">既定の無料電話番号が +18005551234 のユーザー全員の無料電話番号を既定で +18005551239 に変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="09ac2-146">所在地が米国内のユーザー全員の既定の無料電話番号を +18005551234 に設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="09ac2-147">詳細については、次のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="09ac2-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="09ac2-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09ac2-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="09ac2-151">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="09ac2-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="09ac2-152">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="09ac2-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="09ac2-153">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="09ac2-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="09ac2-154">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="09ac2-154">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="09ac2-155">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="09ac2-155">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="09ac2-156">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="09ac2-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="09ac2-157">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="09ac2-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="09ac2-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="09ac2-158">Related topics</span></span>

[<span data-ttu-id="09ac2-159">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="09ac2-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)