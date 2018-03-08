---
title: "ユーザー設定の外部アクセス ポリシーを作成します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: "Skype for Business Online では、その他の外部アクセス ポリシーを作成することができます。ある複数の組み合わせ、クライアントまたは会議のポリシーとは異なり、ほとんどのシナリオを扱うことができる次の 3 つの定義済みの外部アクセス ポリシーがあります。"
ms.openlocfilehash: 7a5e347f3f9629f603544ad9ab06e11d4b649868
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="04ffc-104">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-104">Create custom external access policies</span></span>

<span data-ttu-id="04ffc-p102">Skype for Business Online では、その他の外部アクセス ポリシーを作成することができます。ある複数の組み合わせ、クライアントまたは会議のポリシーとは異なり、ほとんどのシナリオを扱うことができる次の 3 つの定義済みの外部アクセス ポリシーがあります。これらは：</span><span class="sxs-lookup"><span data-stu-id="04ffc-p102">Skype for Business Online allows you to create additional external access policies. Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios. These are:</span></span>
  
- <span data-ttu-id="04ffc-108">フェデレーションなしまたは Skype のコンシューマー アクセス (_タグ: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="04ffc-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="04ffc-109">フェデレーションのアクセスのみ (_タグ: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="04ffc-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="04ffc-110">フェデレーションし、コンシューマー (_FederationAndPICDefault_) にアクセス</span><span class="sxs-lookup"><span data-stu-id="04ffc-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="04ffc-p103">外部のユーザー設定のポリシーを使用するポリシーいないが重なって見えなく上記の設定を作成します。ポリシーを作成すると、必要なすべてのパラメーターを設定する必要があり、後で変更できませんでした。新しいカスタム ポリシーを作成する、Skype のコンシューマー アクセスなどのコントロールの機能を使用するや公開を無効にするポリシーをクラウド音声/ビデオ] のされませんでした定義済みの設定が重なって見えなくなっているものがあります。ユーザー設定の外部アクセス ポリシーでは、クライアント、移動、および会議ポリシー同様の構文に従います。これらの設定の詳細を確認したことが[次のとおり](https://technet.microsoft.com/en-us/library/mt228132.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p103">Custom external policies allow you to create additional polices that aren't covered by the settings above. When the policy was created, you would be required to set all required parameters and you couldn't alter them later. Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings. Custom external access policies follow the same syntax as client, mobility, and conferencing policies. You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="04ffc-p104">この作業を行うには、ユーザーする必要があります使用サポートされているバージョンの 2016年のクイック実行の Skype for Business アプリをサポートしています。次最小のバージョンの Skype for Business の 2016年クイック実行をクライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p104">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="04ffc-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="04ffc-118">**Type**</span></span>|<span data-ttu-id="04ffc-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="04ffc-119">**Release date**</span></span>|<span data-ttu-id="04ffc-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="04ffc-120">**Version**</span></span>|<span data-ttu-id="04ffc-121">**作成します。**</span><span class="sxs-lookup"><span data-stu-id="04ffc-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04ffc-122">現在のチャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="04ffc-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="04ffc-123">2016/11/17</span><span class="sxs-lookup"><span data-stu-id="04ffc-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="04ffc-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="04ffc-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="04ffc-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="04ffc-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="04ffc-126">現在のチャネル</span><span class="sxs-lookup"><span data-stu-id="04ffc-126">Current Channel</span></span>  <br/> |<span data-ttu-id="04ffc-127">2016/12/6</span><span class="sxs-lookup"><span data-stu-id="04ffc-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="04ffc-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="04ffc-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="04ffc-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="04ffc-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="04ffc-130">チャンネルの遅延</span><span class="sxs-lookup"><span data-stu-id="04ffc-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="04ffc-131">2017/2/22</span><span class="sxs-lookup"><span data-stu-id="04ffc-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="04ffc-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="04ffc-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="04ffc-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="04ffc-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="04ffc-134">以前のバージョンの Skype for Business の Windows アプリまたは Mac クライアントを使用しているユーザーはファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="04ffc-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="04ffc-135">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="04ffc-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="04ffc-136">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="04ffc-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="04ffc-137">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="04ffc-138">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="04ffc-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="04ffc-p105">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="04ffc-p106">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="04ffc-145">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04ffc-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="04ffc-146">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="04ffc-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="04ffc-147">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="04ffc-148">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="04ffc-149">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="04ffc-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="04ffc-150">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04ffc-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="04ffc-151">ユーザーのユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="04ffc-152">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="04ffc-153">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="04ffc-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="04ffc-p107">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="04ffc-157">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="04ffc-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="04ffc-158">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="04ffc-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="04ffc-p108">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="04ffc-161">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="04ffc-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="04ffc-162">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="04ffc-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="04ffc-163">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="04ffc-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="04ffc-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="04ffc-164">Related topics</span></span>
[<span data-ttu-id="04ffc-165">ブロック ポイント間接ファイル転送</span><span class="sxs-lookup"><span data-stu-id="04ffc-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="04ffc-166">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="04ffc-167">組織内の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="04ffc-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
