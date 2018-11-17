---
title: カスタム外部アクセス ポリシーを作成する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.
ms.openlocfilehash: a822e09875bbef1fcd1472ac988a32cadfaf5850
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561698"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="6e556-104">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6e556-104">Create custom external access policies</span></span>

<span data-ttu-id="6e556-p102">Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios. These are:</span><span class="sxs-lookup"><span data-stu-id="6e556-p102">Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios. These are:</span></span>
  
- <span data-ttu-id="6e556-108">フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="6e556-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="6e556-109">フェデレーション アクセスのみ (_タグ: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="6e556-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="6e556-110">フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="6e556-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="6e556-p103">Custom external policies allow you to create additional polices that aren't covered by the settings above. When the policy was created, you would be required to set all required parameters and you couldn't alter them later. Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings. Custom external access policies follow the same syntax as client, mobility, and conferencing policies. You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="6e556-p103">Custom external policies allow you to create additional polices that aren't covered by the settings above. When the policy was created, you would be required to set all required parameters and you couldn't alter them later. Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings. Custom external access policies follow the same syntax as client, mobility, and conferencing policies. You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="6e556-p104">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span><span class="sxs-lookup"><span data-stu-id="6e556-p104">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="6e556-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="6e556-118">**Type**</span></span>|<span data-ttu-id="6e556-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="6e556-119">**Release date**</span></span>|<span data-ttu-id="6e556-120">**Version**</span><span class="sxs-lookup"><span data-stu-id="6e556-120">**Version**</span></span>|<span data-ttu-id="6e556-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="6e556-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e556-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="6e556-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="6e556-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="6e556-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="6e556-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="6e556-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="6e556-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="6e556-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="6e556-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="6e556-126">Current Channel</span></span>  <br/> |<span data-ttu-id="6e556-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="6e556-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="6e556-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="6e556-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="6e556-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="6e556-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="6e556-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="6e556-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="6e556-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="6e556-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="6e556-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="6e556-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="6e556-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="6e556-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="6e556-134">Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="6e556-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6e556-135">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="6e556-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6e556-136">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="6e556-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6e556-137">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="6e556-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6e556-138">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e556-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6e556-p105">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e556-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6e556-p106">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6e556-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="6e556-145">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e556-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6e556-146">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="6e556-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6e556-147"> *\*[スタート] メニュー*\*の [ > *\*Windows PowerShell*\*]。</span><span class="sxs-lookup"><span data-stu-id="6e556-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6e556-148">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="6e556-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e556-149">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="6e556-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="6e556-150">Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell には、コンピューターの設定](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e556-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="6e556-151">ユーザー独自の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e556-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="6e556-152">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e556-152">To do this, run:</span></span>
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6e556-153">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="6e556-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6e556-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="6e556-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6e556-157">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="6e556-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6e556-158">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6e556-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6e556-p108">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e556-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6e556-161">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6e556-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6e556-162">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="6e556-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6e556-163">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="6e556-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6e556-164">See also</span><span class="sxs-lookup"><span data-stu-id="6e556-164">Related topics</span></span>
[<span data-ttu-id="6e556-165">ブロック ポイント ツー ポイントのファイルの転送</span><span class="sxs-lookup"><span data-stu-id="6e556-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6e556-166">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6e556-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6e556-167">組織内の会議ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="6e556-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 