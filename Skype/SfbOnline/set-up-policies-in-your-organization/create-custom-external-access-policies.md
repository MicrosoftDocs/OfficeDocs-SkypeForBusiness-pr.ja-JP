---
title: カスタム外部アクセス ポリシーを作成する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。 複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。
ms.openlocfilehash: 49572dc1aaef3d595bd0de41fd6359d90e8d803a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706662"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="84c1d-104">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="84c1d-104">Create custom external access policies</span></span>

<span data-ttu-id="84c1d-105">Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="84c1d-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="84c1d-106">複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="84c1d-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="84c1d-107">これらは：</span><span class="sxs-lookup"><span data-stu-id="84c1d-107">These are:</span></span>
  
- <span data-ttu-id="84c1d-108">フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="84c1d-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="84c1d-109">フェデレーション アクセスのみ (_タグ: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="84c1d-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="84c1d-110">フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="84c1d-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="84c1d-111">カスタム外部ポリシーを使用すると、上記の設定でカバーされない追加ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="84c1d-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="84c1d-112">ポリシーを作成した時に、すべての必要なパラメーターを設定する必要があり、設定したパラメーターを後で変更することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="84c1d-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="84c1d-113">新しいカスタム ポリシーを作成すると、Skype 消費者アクセスなどの機能やパブリック クラウド オーディオ/ビデオを無効にするポリシーなどを管理できます。これは、定義済みの設定でサポートされていなかったものです。</span><span class="sxs-lookup"><span data-stu-id="84c1d-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="84c1d-114">カスタム外部アクセス ポリシーは、クライアントやモビリティ、会議のポリシーと同じ構文に従います。</span><span class="sxs-lookup"><span data-stu-id="84c1d-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="84c1d-115">これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="84c1d-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="84c1d-116">カスタム外部アクセス ポリシーを機能させるには、ユーザーは、そのポリシーに対応している 2016 クイック実行 Skype for Business アプリケーションのサポートされているバージョンを使用していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="84c1d-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="84c1d-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="84c1d-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="84c1d-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="84c1d-118">**Type**</span></span>|<span data-ttu-id="84c1d-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="84c1d-119">**Release date**</span></span>|<span data-ttu-id="84c1d-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="84c1d-120">**Version**</span></span>|<span data-ttu-id="84c1d-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="84c1d-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84c1d-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="84c1d-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="84c1d-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="84c1d-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="84c1d-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="84c1d-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="84c1d-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="84c1d-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="84c1d-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="84c1d-126">Current Channel</span></span>  <br/> |<span data-ttu-id="84c1d-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="84c1d-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="84c1d-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="84c1d-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="84c1d-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="84c1d-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="84c1d-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="84c1d-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="84c1d-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="84c1d-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="84c1d-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="84c1d-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="84c1d-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="84c1d-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="84c1d-134">Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="84c1d-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="84c1d-135">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="84c1d-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="84c1d-136">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="84c1d-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="84c1d-137">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="84c1d-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="84c1d-138">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="84c1d-139">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84c1d-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="84c1d-140">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84c1d-140">See [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="84c1d-141">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="84c1d-p106">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="84c1d-145">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84c1d-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="84c1d-146">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="84c1d-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="84c1d-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="84c1d-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="84c1d-148">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84c1d-149">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="84c1d-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="84c1d-150">Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84c1d-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="84c1d-151">ユーザー独自の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="84c1d-152">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-152">To do this, run:</span></span>
  
> 
>   ```PowerShell
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```PowerShell
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="84c1d-153">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="84c1d-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="84c1d-154">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="84c1d-155">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="84c1d-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="84c1d-156">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84c1d-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="84c1d-157">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="84c1d-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="84c1d-158">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="84c1d-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="84c1d-159">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="84c1d-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="84c1d-160">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="84c1d-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="84c1d-161">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="84c1d-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="84c1d-162">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="84c1d-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="84c1d-163">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="84c1d-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="84c1d-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="84c1d-164">Related topics</span></span>
[<span data-ttu-id="84c1d-165">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="84c1d-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="84c1d-166">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="84c1d-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="84c1d-167">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="84c1d-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
