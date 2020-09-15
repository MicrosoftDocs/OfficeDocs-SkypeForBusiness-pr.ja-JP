---
title: 組織の電話会議ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814756"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="4af10-103">組織の電話会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4af10-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="4af10-104">[] 電話会議は Skype for Business Online の重要な部分です。電話会議により、ユーザーのグループがオンラインで一緒にスライドやビデオを表示したり、アプリケーションを共有したり、ファイルをやり取りしたり、連絡を取り合って共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4af10-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="4af10-p101">電話会議および電話会議の設定を制御できる状態を維持することが重要です。場合によって、セキュリティに関する問題があるかもしれません。既定では、未認証のユーザーを含むあらゆるユーザーが会議に参加でき、その会議中に配布されたスライドや資料を保存することができます。さらに、時には法的な問題が発生することもあります。たとえば、既定では会議の参加者は共有コンテンツに注釈を付けることができますが、それらの注釈は会議がアーカイブされるときに保存されません。所属する組織ですべての電子的な通信の記録を保持する必要がある場合は、注釈を無効にする方が良い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4af10-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="4af10-p102">Skype for Business Online では、電話会議は電話会議ポリシーを使用して管理されます。電話会議ポリシーにより、電話会議に IP オーディオまたはビデオを含めることができるかということから、会議に出席できるユーザーの最大数についてまで、あらゆる点を含む電話会議で使用できる機能が決まります。電話会議ポリシーは全体的な範囲またはユーザーごとの範囲で構成できます。これにより、管理者は、どの機能をどのユーザーが利用できるようにするかを決めるときに、最大の柔軟性を発揮できます。</span><span class="sxs-lookup"><span data-stu-id="4af10-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="4af10-114">ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsConferencingPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4af10-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="4af10-115">電話会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="4af10-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="4af10-116">Skype for Business Online のすべての電話会議ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="4af10-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4af10-117">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="4af10-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4af10-118">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="4af10-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="4af10-119">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="4af10-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="4af10-120">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="4af10-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="4af10-121">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af10-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="4af10-122">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="4af10-123">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4af10-123">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="4af10-124">また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af10-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="4af10-125">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4af10-126">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="4af10-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="4af10-127">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4af10-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="4af10-128">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="4af10-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="4af10-129">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4af10-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="4af10-130">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4af10-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="4af10-131">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="4af10-132">会議中のファイル転送およびデスクトップ共有を禁止する</span><span class="sxs-lookup"><span data-stu-id="4af10-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="4af10-133">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="4af10-134">詳細については、「 [set-csconferencingpolicy](https://technet.microsoft.com/library/mt779148.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4af10-135">作成した新しいポリシーを組織内のすべてのユーザーに付与します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="4af10-136">[Set-csconferencingpolicy](https://technet.microsoft.com/library/mt779156.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="4af10-137">ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="4af10-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="4af10-138">電話会議のレコーディングを禁止し、匿名ユーザーの会議参加者を防止する</span><span class="sxs-lookup"><span data-stu-id="4af10-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="4af10-139">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="4af10-140">詳細については、「 [set-csconferencingpolicy](https://technet.microsoft.com/library/mt779148.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4af10-141">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="4af10-142">[Set-csconferencingpolicy](https://technet.microsoft.com/library/mt779156.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="4af10-143">既にポリシーを作成済みの場合は、 [set-csconferencingpolicy](https://technet.microsoft.com/library/mt779157.aspx) コマンドレットを使用して既存のポリシーに変更を加えることができます。次に、 [set-csconferencingpolicy](https://technet.microsoft.com/library/mt779156.aspx) コマンドレットを使用して、ユーザーに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4af10-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="4af10-144">匿名ユーザーの参加者による会議のレコーディングと、追加ユーザーによる会議の内容の保存を禁止する</span><span class="sxs-lookup"><span data-stu-id="4af10-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="4af10-145">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="4af10-146">詳細については、「 [set-csconferencingpolicy](https://technet.microsoft.com/library/mt779148.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="4af10-147">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4af10-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="4af10-148">[Set-csconferencingpolicy](https://technet.microsoft.com/library/mt779156.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="4af10-149">ポリシーを作成済みの場合は、[Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="4af10-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4af10-150">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="4af10-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4af10-151">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4af10-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4af10-152">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4af10-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4af10-153">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af10-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4af10-154">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="4af10-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4af10-155">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="4af10-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4af10-156">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="4af10-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4af10-157">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="4af10-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4af10-158">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="4af10-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4af10-159">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="4af10-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4af10-160">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="4af10-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="4af10-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4af10-161">Related topics</span></span>
[<span data-ttu-id="4af10-162">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4af10-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="4af10-163">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="4af10-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="4af10-164">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4af10-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
