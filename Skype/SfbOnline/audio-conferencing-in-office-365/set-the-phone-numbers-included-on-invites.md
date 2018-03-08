---
title: "携帯電話への招待に含まれる数値を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business Online の会議に参加する発信者の既定の電話番号を作成する手順を取得します。 "
ms.openlocfilehash: 8baf3d79b360a5d95da4b9ead6bae12cd488712c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="27354-103">携帯電話への招待に含まれる数値を設定します。</span><span class="sxs-lookup"><span data-stu-id="27354-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="27354-p101">Office 365 で音声会議 Business および Microsoft チームの会議に Skype を作成し、電話を使用して、その会議にダイヤルインするように、組織のユーザーを有効にします。Office 365 で、Microsoft の電話会議ブリッジまたは承認されている電話会議プロバイダー (ACP) でホストされているサードパーティ電話会議ブリッジを使用するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="27354-p101">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="27354-p102">電話会議のすべてのダイヤルイン番号の一覧を含むリソースはありません。ないか確認ダイヤルイン電話番号利用可能な領域または国/地域を検索する場合は、 **Skype for Business 管理センター**を使って > **音声** > **電話番号**をクリックし、**追加****新しいサービス番号**.**国/地域**、**状態/地域のリストを使用して**と検索をフィルター処理するのには、**市区町村**> も、有料の無料サービス番号、探している場合は**フリー ダイヤル**から、**状態/地域を選びます**] ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="27354-p102">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="27354-p103">会議ブリッジによって、組織のダイヤルイン電話番号のセットができます。会議の開催者が作成した会議に参加するすべての使われていることができますが、会議の出席依頼に含めるものを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="27354-p103">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27354-111">最大の 1 つの有料電話番号との会議の開催者、会議の出席依頼のフリー ダイヤル電話番号を 1 つがありますも会議に参加するのに使用できるすべてのダイヤルイン電話番号の完全な一覧を開いている各会議出席依頼の下部にあるリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="27354-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="27354-112">会議の開催者の既定のダイヤルイン電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="27354-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="27354-113">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="27354-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="27354-114">**管理センター**] を選びます > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="27354-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="27354-115">**ユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-115">Choose **Users**.</span></span>
    
    ![Skype for Business 管理センターでユーザーを選択して表示します。](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="27354-117">編集するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="27354-118">1 人のユーザーを選択するには、ユーザーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="27354-119">ページ上のすべてのユーザーを選択するには、リストの上部にある**表示名**の横のボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="27354-120">複数のユーザーを選択するには、各ユーザーの名前の横のボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="27354-121">右のパネルで [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="27354-121">In the right panel, choose **Edit**.</span></span>
    
    ![[編集] アイコンを選択します。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="27354-123">**電話会議**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="27354-p104">**プロパティ**ページで、[**プロバイダー名**] ボックスの一覧で、ユーザーのプロバイダーを選択します。プロバイダーによっては、次のボックスを実行します。</span><span class="sxs-lookup"><span data-stu-id="27354-p104">On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="27354-126">**Microsoft はプロバイダー**:**有料電話番号が既定値**を使用し、ユーザーの既定の番号を選択する**既定のフリー ダイヤル番号**が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="27354-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="27354-p105">1 つ以上のフリー ダイヤル番号は、前に、ユーザーの既定のフリー ダイヤル番号に設定することができます、会議ブリッジを割り当てる必要があります。フリー ダイヤルの番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27354-p105">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="27354-129">**サード パーティがプロバイダー**:**有料電話番号**と**フリー ダイヤル番号**フィールドを使用して、ユーザーの数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="27354-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="27354-130">電話会議の電話番号を再設定します。</span><span class="sxs-lookup"><span data-stu-id="27354-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="27354-131">**Skype for Business 管理センター**では、**電話会議**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27354-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="27354-132">ページの上部で、[**ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="27354-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="27354-133">、リセットするユーザーを選択し、[アクション] ウィンドウで、[**クリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27354-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="27354-p106">既定では、ユーザーの会議の設定を変更する場合は、メールは、ユーザーに送信します。これを変更するには、[有効にするか音声会議の設定を変更するときに、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27354-p106">By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="27354-136">ユーザーの電話会議の設定を変更すると、定期的な予定と将来の Skype for Business や Microsoft チームの会議が更新され、出席者に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27354-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="27354-137">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="27354-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="27354-138">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="27354-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="27354-139">既定の有料またはフリー ダイヤルの番号を特定のユーザーを変更するのにには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27354-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="27354-140">ユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="27354-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="27354-141">既定の有料またはフリー ダイヤルの元の既定の番号またはその場所に基づくユーザー数を変更するのには、**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27354-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="27354-142">[BridgeID を検索するには、 **Get CsOnlineDialInConferencingBridge**を使用します。</span><span class="sxs-lookup"><span data-stu-id="27354-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="27354-143">既定のフリー ダイヤル番号を設定するには、1 +18005551234 せずにすべてのユーザーに実行します。</span><span class="sxs-lookup"><span data-stu-id="27354-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="27354-144">+18005551239 に、既定のフリー ダイヤル番号として +18005551234 を持つすべてのユーザーの既定のフリー ダイヤル番号を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="27354-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="27354-145">+18005551234 米国内にあるすべてのユーザーの既定のフリー ダイヤル番号を設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="27354-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="27354-146">Windows PowerShell の詳細を確認したい場合</span><span class="sxs-lookup"><span data-stu-id="27354-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="27354-p107">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27354-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="27354-150">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="27354-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="27354-151">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="27354-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="27354-p108">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="27354-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="27354-154">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="27354-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="27354-155">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="27354-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="27354-156">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="27354-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="27354-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="27354-157">Related topics</span></span>

[<span data-ttu-id="27354-158">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="27354-158">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

