---
title: "組織用のモバイルのポリシーを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: "ビジネスのアプリを行い、勤務先の電話番号を使用して、携帯電話番号の連ではなく、携帯電話で通話を受信できるようにする機能などのモバイル デバイスでの Skype を使用するのには、Skype for Business Online ユーザーの接続を設定できます。mber します。移動ポリシーは、Wi-fi 接続されたとき、または通話の発着信を要求するも使用できます。"
ms.openlocfilehash: 904da369a4218b0b41112c97a1fed9de03c47c3b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="823b0-104">組織用のモバイルのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="823b0-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="823b0-p102">ビジネスのアプリを行い、勤務先の電話番号を使用して、携帯電話番号の連ではなく、携帯電話で通話を受信できるようにする機能などのモバイル デバイスでの Skype を使用するのには、Skype for Business Online ユーザーの接続を設定できます。mber します。移動ポリシーは、Wi-fi 接続されたとき、または通話の発着信を要求するも使用できます。</span><span class="sxs-lookup"><span data-stu-id="823b0-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="823b0-107">ポリシーを作成すると、時にモバイル ポリシーの設定を構成することができますか、既存のポリシーの設定を変更する**設定 CsMobilityPolicy**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="823b0-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="823b0-108">モバイルのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="823b0-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="823b0-109">すべてのモバイル ポリシーの設定で Skype for Business Online の Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="823b0-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="823b0-110">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="823b0-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="823b0-111">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="823b0-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="823b0-112">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="823b0-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="823b0-113">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="823b0-p103">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="823b0-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="823b0-p104">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="823b0-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="823b0-120">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="823b0-121">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="823b0-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="823b0-122">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="823b0-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="823b0-123">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="823b0-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="823b0-124">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="823b0-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="823b0-125">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="823b0-126">ユーザーのビデオの WiFi 接続が必要</span><span class="sxs-lookup"><span data-stu-id="823b0-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="823b0-127">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="823b0-128">[新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="823b0-129">組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="823b0-130">[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="823b0-131">既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="823b0-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="823b0-132">ユーザーが、Skype を for Business アプリを使用するを防ぐ</span><span class="sxs-lookup"><span data-stu-id="823b0-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="823b0-133">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="823b0-134">[新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="823b0-135">作成した新しいポリシーを Amos 大理石に付与するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="823b0-136">[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="823b0-137">既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="823b0-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="823b0-138">ユーザーがモバイル デバイスを使って IP 電話で音声を作成するを防ぐ</span><span class="sxs-lookup"><span data-stu-id="823b0-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="823b0-139">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="823b0-140">[新規 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="823b0-141">組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="823b0-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="823b0-142">[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="823b0-143">既にポリシーを作成している場合は、[セット CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに設定を適用する[許可を付与する CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="823b0-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="823b0-144">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="823b0-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="823b0-p105">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b0-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="823b0-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="823b0-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="823b0-149">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="823b0-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="823b0-p106">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="823b0-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="823b0-152">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="823b0-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="823b0-153">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="823b0-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="823b0-154">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="823b0-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="823b0-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="823b0-155">Related topics</span></span>
[<span data-ttu-id="823b0-156">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="823b0-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="823b0-157">ブロック ポイント間接ファイル転送</span><span class="sxs-lookup"><span data-stu-id="823b0-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="823b0-158">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="823b0-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="823b0-159">組織内の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="823b0-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

