---
title: 組織のモバイル ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
ms.openlocfilehash: cfd9232943aebc9e4565b0ebfe1b46872c4bad65
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164846"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="c0f59-104">組織のモバイル ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c0f59-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="c0f59-p102">[] モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c0f59-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="c0f59-107">モバイル機能ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsMobilityPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c0f59-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="c0f59-108">モバイル機能ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c0f59-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="c0f59-109">Skype for Business Online のすべてのモバイル機能ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="c0f59-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="c0f59-110">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="c0f59-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="c0f59-111">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="c0f59-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="c0f59-112">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="c0f59-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="c0f59-113">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="c0f59-114">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f59-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="c0f59-115">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="c0f59-116">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-116">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="c0f59-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="c0f59-120">詳細については、「[単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="c0f59-121">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="c0f59-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="c0f59-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c0f59-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="c0f59-123">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="c0f59-124">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="c0f59-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="c0f59-125">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-125">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="c0f59-126">ユーザーに対してビデオ使用時に WiFi 接続を要求する</span><span class="sxs-lookup"><span data-stu-id="c0f59-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="c0f59-127">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="c0f59-128">詳細については、「 [set-csmobilitypolicy](https://technet.microsoft.com/library/mt779150.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c0f59-129">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="c0f59-130">[Set-csmobilitypolicy](https://technet.microsoft.com/library/mt779149.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="c0f59-131">ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) を使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="c0f59-132">ユーザーが Skype for Business アプリを使用できないようにする</span><span class="sxs-lookup"><span data-stu-id="c0f59-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="c0f59-133">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="c0f59-134">詳細については、「 [set-csmobilitypolicy](https://technet.microsoft.com/library/mt779150.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c0f59-135">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="c0f59-136">[Set-csmobilitypolicy](https://technet.microsoft.com/library/mt779149.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="c0f59-137">既にポリシーを作成済みの場合は、 [set-csmobilitypolicy](https://technet.microsoft.com/library/mt779147.aspx)コマンドレットを使用して既存のポリシーに変更を加えることができます。次に、 [set-csmobilitypolicy](https://technet.microsoft.com/library/mt779149.aspx)コマンドレットを使用して、ユーザーに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="c0f59-138">ユーザーがモバイル デバイスを使用してボイス オーバー IP 通話を行えないようにする</span><span class="sxs-lookup"><span data-stu-id="c0f59-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="c0f59-139">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="c0f59-140">詳細については、「 [set-csmobilitypolicy](https://technet.microsoft.com/library/mt779150.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="c0f59-141">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="c0f59-142">[Set-csmobilitypolicy](https://technet.microsoft.com/library/mt779149.aspx)コマンドレットの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c0f59-143">ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) を使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c0f59-144">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="c0f59-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c0f59-145">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c0f59-146">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c0f59-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c0f59-147">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f59-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c0f59-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="c0f59-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c0f59-149">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="c0f59-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c0f59-150">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="c0f59-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c0f59-151">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0f59-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c0f59-152">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="c0f59-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c0f59-153">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="c0f59-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c0f59-154">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="c0f59-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c0f59-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0f59-155">Related topics</span></span>
[<span data-ttu-id="c0f59-156">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c0f59-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="c0f59-157">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="c0f59-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="c0f59-158">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c0f59-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="c0f59-159">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c0f59-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
