---
title: "組織のクライアントのポリシーを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: "クライアント ポリシーを決める、機能の Skype for Business Online のユーザーに利用可能になっています。たとえば、可能性があります権限を与えること一部のユーザー、他のユーザーにこの権限を拒否するときにファイルを転送します。"
ms.openlocfilehash: 82fa2c828af9aed01652870ea5d3db02ca8248c3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="d8be5-103">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-103">Set up client policies for your organization</span></span>

<span data-ttu-id="d8be5-104">クライアント ポリシーを決める、機能の Skype for Business Online のユーザーに利用可能になっています。たとえば、可能性があります権限を与えること一部のユーザー、他のユーザーにこの権限を拒否するときにファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="d8be5-105">ポリシーを作成すると、時に、クライアント ポリシーを設定することもできます。 または、既存のポリシーの設定を変更する**設定 CsClientPolicy**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d8be5-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="d8be5-106">顧客のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="d8be5-107">クライアント ポリシー設定の Skype for Business Online のすべての Windows PowerShell と**使用できない** **Skype for Business 管理センター**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8be5-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d8be5-108">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="d8be5-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d8be5-109">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="d8be5-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="d8be5-110">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d8be5-111">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d8be5-p101">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d8be5-p102">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="d8be5-118">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d8be5-119">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="d8be5-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="d8be5-120">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d8be5-121">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8be5-122">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="d8be5-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="d8be5-123">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="d8be5-124">絵文字とプレゼンスの通知を無効にして、ように Im の保存</span><span class="sxs-lookup"><span data-stu-id="d8be5-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="d8be5-125">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="d8be5-126">[新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d8be5-127">組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="d8be5-128">[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d8be5-129">既にポリシーを作成している場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="d8be5-130">Url または Im で可能にハイパーリンクを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d8be5-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="d8be5-131">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="d8be5-132">[新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d8be5-133">組織内のすべてのユーザーを作成した新しいポリシーを与える、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="d8be5-134">[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d8be5-135">既にポリシーを作成している場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="d8be5-136">最近使用した連絡先が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d8be5-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="d8be5-137">これらの設定の新しいポリシーを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="d8be5-138">[新規 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="d8be5-139">作成した新しいポリシーを Amos 大理石に付与するには、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="d8be5-140">[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="d8be5-141">既にポリシーを作成している場合は、[セット CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)コマンドレットを使用して、既存のポリシーを変更してをユーザーに、設定を適用する[許可を付与する CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d8be5-142">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="d8be5-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d8be5-p103">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8be5-p103">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d8be5-146">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="d8be5-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d8be5-147">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="d8be5-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d8be5-p104">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d8be5-150">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="d8be5-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d8be5-151">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="d8be5-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d8be5-152">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="d8be5-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d8be5-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d8be5-153">Related topics</span></span>
[<span data-ttu-id="d8be5-154">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d8be5-155">ブロック ポイント間接ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d8be5-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d8be5-156">組織内の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8be5-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
