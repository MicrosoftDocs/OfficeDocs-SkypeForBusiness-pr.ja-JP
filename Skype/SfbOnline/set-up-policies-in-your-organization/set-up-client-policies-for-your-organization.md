---
title: 組織のクライアント ポリシーをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 93dcef25119527bce25c1155dc7c8c05ac6fe78d
ms.sourcegitcommit: dbef8028cb7f8c6366e0fdb34f5f2e2a30d8c32a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "19500637"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="64111-103">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="64111-103">Set up client policies for your organization</span></span>

<span data-ttu-id="64111-104">[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="64111-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="64111-105">クライアント ポリシー設定はポリシーが作成されるときに構成できます。また、**Set-CsClientPolicy **コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="64111-105">Client policy settings can be configured at the time a policy is created, or you can use the Set-CsClientPolicy cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="64111-106">クライアント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="64111-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="64111-107">Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="64111-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="64111-108">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="64111-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="64111-109">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="64111-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="64111-110">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="64111-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="64111-111">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="64111-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="64111-p101">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="64111-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="64111-p102">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="64111-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="64111-118">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64111-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="64111-119">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="64111-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="64111-120">[**スタート メニュー**]  >  [**Windows PowerShell**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="64111-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="64111-121">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="64111-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64111-122">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="64111-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="64111-123">Windows PowerShell の起動方法の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Skype for Business への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64111-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="64111-124">絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する</span><span class="sxs-lookup"><span data-stu-id="64111-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="64111-125">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="64111-126">詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-126">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64111-127">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="64111-128">詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-128">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="64111-129">ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="64111-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="64111-130">URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする</span><span class="sxs-lookup"><span data-stu-id="64111-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="64111-131">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="64111-132">詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-132">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64111-133">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="64111-134">詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="64111-135">ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="64111-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="64111-136">最近の連絡先を表示しないようにする</span><span class="sxs-lookup"><span data-stu-id="64111-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="64111-137">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="64111-138">詳細については、 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-138">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64111-139">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="64111-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="64111-140">詳細については、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64111-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="64111-141">ポリシーを作成済みの場合は、[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに対する変更を行ってから、[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="64111-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="64111-142">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="64111-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="64111-143">Windows PowerShell では、ユーザーの管理と、ユーザーに許可すること、禁止することをすべて操作できます。</span><span class="sxs-lookup"><span data-stu-id="64111-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="64111-144">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="64111-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="64111-145">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64111-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="64111-146">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="64111-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="64111-147">Office 365 PowerShell を使用する必要がある理由 </span><span class="sxs-lookup"><span data-stu-id="64111-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="64111-p104">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="64111-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="64111-150">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="64111-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="64111-151">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="64111-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="64111-152">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="64111-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="64111-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="64111-153">Related topics</span></span>
[<span data-ttu-id="64111-154">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="64111-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="64111-155">ポイント ツー ポイントのファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="64111-155">Block Point-to-Point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="64111-156">組織の電話会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="64111-156">Set up conferencing policies for your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 