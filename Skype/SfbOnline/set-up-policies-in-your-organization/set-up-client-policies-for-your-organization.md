---
title: 組織のクライアント ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 4c3434a1649c7bce01557ab97c6c6d9f977c0ab4
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887906"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="a639f-103">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="a639f-103">Set up client policies for your organization</span></span>

<span data-ttu-id="a639f-104">[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="a639f-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="a639f-105">クライアントポリシー設定はポリシーが作成されるときに構成することができます。また、 **Set-CsClientPolicy**コマンドレットを使用して、既存のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a639f-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="a639f-106">クライアント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a639f-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="a639f-107">Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="a639f-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="a639f-108">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="a639f-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="a639f-109">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="a639f-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="a639f-110">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="a639f-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="a639f-111">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="a639f-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="a639f-112">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a639f-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="a639f-113">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="a639f-114">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a639f-114">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="a639f-p102">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a639f-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="a639f-118">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="a639f-119">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="a639f-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="a639f-120">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a639f-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="a639f-121">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="a639f-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="a639f-122">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="a639f-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```powershell
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```
<span data-ttu-id="a639f-123">Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="a639f-124">絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する</span><span class="sxs-lookup"><span data-stu-id="a639f-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="a639f-125">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-125">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="a639f-126">詳細については、「[新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="a639f-127">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="a639f-128">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="a639f-129">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加え、[[権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx)コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a639f-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="a639f-130">URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする</span><span class="sxs-lookup"><span data-stu-id="a639f-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="a639f-131">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-131">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="a639f-132">詳細については、「[新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="a639f-133">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="a639f-134">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="a639f-135">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加え、[[権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx)コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a639f-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="a639f-136">最近の連絡先を表示しないようにする</span><span class="sxs-lookup"><span data-stu-id="a639f-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="a639f-137">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-137">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="a639f-138">詳細については、「[新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="a639f-139">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a639f-139">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="a639f-140">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx)コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="a639f-141">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx)コマンドレットを使用して既存のポリシーに変更を加え、[[権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx)コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a639f-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a639f-142">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="a639f-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="a639f-143">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="a639f-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a639f-144">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="a639f-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a639f-145">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a639f-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a639f-146">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a639f-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a639f-147">Windows PowerShell を使用して Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="a639f-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a639f-148">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a639f-148">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a639f-149">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="a639f-149">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a639f-150">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="a639f-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a639f-151">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="a639f-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a639f-152">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="a639f-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a639f-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a639f-153">Related topics</span></span>
[<span data-ttu-id="a639f-154">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a639f-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="a639f-155">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="a639f-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="a639f-156">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="a639f-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
