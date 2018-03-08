---
title: "組織の会議のポリシーを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Skype for Business Online の重要な部分は、会議: 会議を有効に統合するユーザーのグループ オンライン スライドやビデオを表示、アプリケーションの共有、ファイルを交換し、それ以外の場合コミュニケーションや共同作業します。"
ms.openlocfilehash: 97102f717fbc8703c6bda456acdfadfcfd71276f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="40c66-103">組織の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="40c66-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="40c66-104">Skype for Business Online の重要な部分は、会議: 会議を有効に統合するユーザーのグループ オンライン スライドやビデオを表示、アプリケーションの共有、ファイルを交換し、それ以外の場合コミュニケーションや共同作業します。</span><span class="sxs-lookup"><span data-stu-id="40c66-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="40c66-p101">会議や電話会議の設定を管理することが重要です。場合によってである可能性がありますセキュリティに関する注意事項: 既定では、会議に参加し、スライドまたは会議中の配布資料のいずれかの保存認証されていないユーザーを含むすべてのユーザーことができます。さらに、臨時の法的な問題がある可能性があります。たとえば、既定では、会議の参加者ができるようにする共有コンテンツに注釈を付けるただし、会議をアーカイブする場合、これらの注釈は保存されません。組織が電子のすべての通信の記録を残すに必要な場合注釈を無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="40c66-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="40c66-p102">Skype for Business Online で、会議は会議のポリシーを使用して管理します。会議のポリシーは、すべての会議で音声とビデオ会議に参加できるユーザーの最大数を IP を含めることができるかどうかなど、電話会議中に使用できる機能を決定します。グローバル スコープ、またはユーザーごとの範囲で、会議のポリシーを構成できます。これは、さまざまな機能が利用できるユーザーを決定する際にする場合です。</span><span class="sxs-lookup"><span data-stu-id="40c66-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="40c66-114">ポリシーを作成すると、時にポリシーの設定を構成することができますか、既存のポリシーの設定を変更する**設定 CsConferencingPolicy**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="40c66-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="40c66-115">自分の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="40c66-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="40c66-116">すべての会議のポリシー設定が skype for Business Online の Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c66-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="40c66-117">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="40c66-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="40c66-118">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="40c66-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="40c66-119">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="40c66-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="40c66-120">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="40c66-p103">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="40c66-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="40c66-p104">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="40c66-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="40c66-127">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="40c66-128">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="40c66-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="40c66-129">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="40c66-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="40c66-130">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="40c66-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40c66-131">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="40c66-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="40c66-132">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="40c66-133">ファイル転送とデスクトップ共有の会議中にブロックします。</span><span class="sxs-lookup"><span data-stu-id="40c66-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="40c66-134">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-134">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  <span data-ttu-id="40c66-135">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40c66-136">組織内のすべてのユーザーに作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-136">To grant the new policy you created to all users in your organization, run:</span></span>
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  <span data-ttu-id="40c66-137">[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="40c66-138">既にポリシーを作成している場合は、[セット CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="40c66-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="40c66-139">会議のレコーディングをブロックして、匿名会議の参加者を防ぐ</span><span class="sxs-lookup"><span data-stu-id="40c66-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="40c66-140">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-140">To create a new policy for these settings, run:</span></span> 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
<span data-ttu-id="40c66-141">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40c66-142">作成した新しいポリシーを Amos 大理石に付与するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-142">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
<span data-ttu-id="40c66-143">[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="40c66-144">既にポリシーを作成している場合は、[セット CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="40c66-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="40c66-145">匿名参加者にレコーディングの会議と会議の内容を保存するから外部ユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="40c66-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="40c66-146">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-146">To create a new policy for these settings, run:</span></span>  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
<span data-ttu-id="40c66-147">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="40c66-148">組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c66-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

<span data-ttu-id="40c66-149">[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="40c66-150">既にポリシーを作成している場合は、[セット CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="40c66-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="40c66-151">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="40c66-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="40c66-p105">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c66-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="40c66-155">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="40c66-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="40c66-156">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="40c66-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="40c66-p106">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="40c66-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="40c66-159">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="40c66-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="40c66-160">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="40c66-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="40c66-161">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="40c66-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="40c66-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="40c66-162">Related topics</span></span>
[<span data-ttu-id="40c66-163">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="40c66-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="40c66-164">ブロック ポイント間接ファイル転送</span><span class="sxs-lookup"><span data-stu-id="40c66-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="40c66-165">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="40c66-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)