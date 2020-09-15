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
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814196"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="819fd-104">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="819fd-104">Create custom external access policies</span></span>

<span data-ttu-id="819fd-105">Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="819fd-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="819fd-106">複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="819fd-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="819fd-107">これらは：</span><span class="sxs-lookup"><span data-stu-id="819fd-107">These are:</span></span>
  
- <span data-ttu-id="819fd-108">フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="819fd-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="819fd-109">フェデレーション アクセスのみ (_タグ: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="819fd-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="819fd-110">フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="819fd-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="819fd-111">カスタム外部ポリシーを使用すると、上記の設定でカバーされない追加ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="819fd-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="819fd-112">ポリシーを作成した時に、すべての必要なパラメーターを設定する必要があり、設定したパラメーターを後で変更することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="819fd-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="819fd-113">新しいカスタム ポリシーを作成すると、Skype 消費者アクセスなどの機能やパブリック クラウド オーディオ/ビデオを無効にするポリシーなどを管理できます。これは、定義済みの設定でサポートされていなかったものです。</span><span class="sxs-lookup"><span data-stu-id="819fd-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="819fd-114">カスタム外部アクセス ポリシーは、クライアントやモビリティ、会議のポリシーと同じ構文に従います。</span><span class="sxs-lookup"><span data-stu-id="819fd-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="819fd-115">これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="819fd-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="819fd-116">カスタム外部アクセス ポリシーを機能させるには、ユーザーは、そのポリシーに対応している 2016 クイック実行 Skype for Business アプリケーションのサポートされているバージョンを使用していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="819fd-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="819fd-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="819fd-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="819fd-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="819fd-118">**Type**</span></span>|<span data-ttu-id="819fd-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="819fd-119">**Release date**</span></span>|<span data-ttu-id="819fd-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="819fd-120">**Version**</span></span>|<span data-ttu-id="819fd-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="819fd-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="819fd-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="819fd-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="819fd-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="819fd-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="819fd-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="819fd-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="819fd-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="819fd-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="819fd-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="819fd-126">Current Channel</span></span>  <br/> |<span data-ttu-id="819fd-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="819fd-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="819fd-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="819fd-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="819fd-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="819fd-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="819fd-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="819fd-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="819fd-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="819fd-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="819fd-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="819fd-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="819fd-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="819fd-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="819fd-134">Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="819fd-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="819fd-135">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="819fd-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="819fd-136">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="819fd-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="819fd-137">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="819fd-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="819fd-138">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="819fd-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="819fd-139">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="819fd-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="819fd-140">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819fd-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="819fd-141">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="819fd-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="819fd-142">また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="819fd-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="819fd-143">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819fd-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="819fd-144">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="819fd-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="819fd-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="819fd-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="819fd-146">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="819fd-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="819fd-147">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="819fd-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="819fd-148">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="819fd-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="819fd-149">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819fd-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="819fd-150">ユーザー独自の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="819fd-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="819fd-151">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="819fd-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="819fd-152">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="819fd-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="819fd-153">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="819fd-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="819fd-154">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="819fd-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="819fd-155">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="819fd-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="819fd-156">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="819fd-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="819fd-157">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="819fd-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="819fd-158">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="819fd-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="819fd-159">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="819fd-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="819fd-160">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="819fd-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="819fd-161">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="819fd-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="819fd-162">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="819fd-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="819fd-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="819fd-163">Related topics</span></span>
[<span data-ttu-id="819fd-164">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="819fd-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="819fd-165">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="819fd-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="819fd-166">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="819fd-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
