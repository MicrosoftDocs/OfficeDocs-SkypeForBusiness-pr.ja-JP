---
title: 組織の電話会議ポリシーをセットアップする
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
description: 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。
ms.openlocfilehash: 6005789d4be479ea4fd39f74fb950600c640bbb5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="ffdc0-103">組織の電話会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ffdc0-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="ffdc0-104">[] 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="ffdc0-p101">電話会議および電話会議の設定を制御できる状態を維持することが重要です。場合によって、セキュリティに関する問題があるかもしれません。既定では、未認証のユーザーを含むあらゆるユーザーが会議に参加でき、その会議中に配布されたスライドや資料を保存することができます。さらに、時には法的な問題が発生することもあります。たとえば、既定では会議の参加者は共有コンテンツに注釈を付けることができますが、それらの注釈は会議がアーカイブされるときに保存されません。所属する組織ですべての電子的な通信の記録を保持する必要がある場合は、注釈を無効にする方が良い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="ffdc0-p102">Skype for Business Online では、電話会議は電話会議ポリシーを使用して管理されます。電話会議ポリシーにより、電話会議に IP オーディオまたはビデオを含めることができるかということから、会議に出席できるユーザーの最大数についてまで、あらゆる点を含む電話会議で使用できる機能が決まります。電話会議ポリシーは全体的な範囲またはユーザーごとの範囲で構成できます。これにより、管理者は、どの機能をどのユーザーが利用できるようにするかを決めるときに、最大の柔軟性を発揮できます。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="ffdc0-114">ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsConferencingPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="ffdc0-115">電話会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="ffdc0-116">Skype for Business Online のすべての電話会議ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ffdc0-117">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ffdc0-118">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="ffdc0-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ffdc0-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ffdc0-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ffdc0-120">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ffdc0-p103">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ffdc0-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ffdc0-127">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ffdc0-128">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="ffdc0-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ffdc0-129">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ffdc0-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ffdc0-130">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ffdc0-131">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="ffdc0-132">Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="ffdc0-133">会議中のファイル転送およびデスクトップ共有を禁止する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="ffdc0-134">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-134">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  <span data-ttu-id="ffdc0-135">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ffdc0-136">作成した新しいポリシーを組織内のすべてのユーザーに付与します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-136">To grant the new policy you created to all users in your organization, run:</span></span>
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  <span data-ttu-id="ffdc0-137">[許可 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="ffdc0-138">ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="ffdc0-139">電話会議のレコーディングを禁止し、匿名ユーザーの会議参加者を防止する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="ffdc0-140">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-140">To create a new policy for these settings, run:</span></span> 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
<span data-ttu-id="ffdc0-141">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ffdc0-142">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-142">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
<span data-ttu-id="ffdc0-143">[許可 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ffdc0-144">ポリシーを既に作成した場合は、[セット CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx)コマンドレットを使用して既存のポリシーに変更を加えるし、[与える CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットを使用してユーザー設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="ffdc0-145">匿名ユーザーの参加者による会議のレコーディングと、追加ユーザーによる会議の内容の保存を禁止する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="ffdc0-146">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-146">To create a new policy for these settings, run:</span></span>  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
<span data-ttu-id="ffdc0-147">[新規 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ffdc0-148">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

<span data-ttu-id="ffdc0-149">[許可 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ffdc0-150">ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ffdc0-151">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="ffdc0-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ffdc0-p105">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ffdc0-155">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ffdc0-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ffdc0-156">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="ffdc0-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ffdc0-p106">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffdc0-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ffdc0-159">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ffdc0-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ffdc0-160">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ffdc0-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ffdc0-161">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ffdc0-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="ffdc0-162">See also</span><span class="sxs-lookup"><span data-stu-id="ffdc0-162">Related topics</span></span>
[<span data-ttu-id="ffdc0-163">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ffdc0-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="ffdc0-164">ブロック ポイント ツー ポイントのファイルの転送</span><span class="sxs-lookup"><span data-stu-id="ffdc0-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ffdc0-165">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ffdc0-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 