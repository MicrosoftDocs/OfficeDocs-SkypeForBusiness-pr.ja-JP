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
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100613"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="acb07-104">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="acb07-104">Create custom external access policies</span></span>

<span data-ttu-id="acb07-105">Skype for Business Online を使用すると、その他の外部アクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="acb07-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="acb07-106">複数な組み合わせを作成できるクライアントポリシーや会議ポリシーとは異なり、シナリオのほとんどをカバーできる 3 つの定義済み外部アクセス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="acb07-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="acb07-107">これらは：</span><span class="sxs-lookup"><span data-stu-id="acb07-107">These are:</span></span>
  
- <span data-ttu-id="acb07-108">フェデレーション アクセスまたは Skype 消費者アクセスなし (_タグ: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="acb07-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="acb07-109">フェデレーション アクセスのみ (_タグ: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="acb07-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="acb07-110">フェデレーション アクセスと消費者アクセス (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="acb07-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="acb07-111">カスタム外部ポリシーを使用すると、上記の設定でカバーされない追加ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="acb07-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="acb07-112">ポリシーを作成した時に、すべての必要なパラメーターを設定する必要があり、設定したパラメーターを後で変更することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="acb07-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="acb07-113">新しいカスタム ポリシーを作成すると、Skype 消費者アクセスなどの機能やパブリック クラウド オーディオ/ビデオを無効にするポリシーなどを管理できます。これは、定義済みの設定でサポートされていなかったものです。</span><span class="sxs-lookup"><span data-stu-id="acb07-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="acb07-114">カスタム外部アクセス ポリシーは、クライアントやモビリティ、会議のポリシーと同じ構文に従います。</span><span class="sxs-lookup"><span data-stu-id="acb07-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="acb07-115">これらの設定に関する詳細は、 [ここ](/previous-versions//mt228132(v=technet.10))からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="acb07-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="acb07-116">カスタム外部アクセス ポリシーを機能させるには、ユーザーは、そのポリシーに対応している 2016 クイック実行 Skype for Business アプリケーションのサポートされているバージョンを使用していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="acb07-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="acb07-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="acb07-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="acb07-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="acb07-118">**Type**</span></span>|<span data-ttu-id="acb07-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="acb07-119">**Release date**</span></span>|<span data-ttu-id="acb07-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="acb07-120">**Version**</span></span>|<span data-ttu-id="acb07-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="acb07-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="acb07-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="acb07-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="acb07-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="acb07-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="acb07-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="acb07-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="acb07-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="acb07-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="acb07-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="acb07-126">Current Channel</span></span>  <br/> |<span data-ttu-id="acb07-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="acb07-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="acb07-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="acb07-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="acb07-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="acb07-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="acb07-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="acb07-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="acb07-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="acb07-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="acb07-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="acb07-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="acb07-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="acb07-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="acb07-134">Skype for Business Windows アプリケーションまたは Mac クライアントの以前のバージョンを使用しているユーザーは、ファイルを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="acb07-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="acb07-135">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="acb07-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="acb07-136">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="acb07-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="acb07-137">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="acb07-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="acb07-138">Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="acb07-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="acb07-139">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="acb07-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="acb07-140">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb07-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="acb07-141">ユーザー独自の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="acb07-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="acb07-142">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="acb07-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="acb07-143">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="acb07-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="acb07-144">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="acb07-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="acb07-145">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="acb07-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="acb07-146">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb07-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="acb07-147">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="acb07-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="acb07-148">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="acb07-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="acb07-149">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="acb07-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="acb07-150">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="acb07-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="acb07-151">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="acb07-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="acb07-152">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="acb07-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="acb07-153">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="acb07-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="acb07-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb07-154">Related topics</span></span>
[<span data-ttu-id="acb07-155">ポイント間ファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="acb07-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="acb07-156">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="acb07-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="acb07-157">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="acb07-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
