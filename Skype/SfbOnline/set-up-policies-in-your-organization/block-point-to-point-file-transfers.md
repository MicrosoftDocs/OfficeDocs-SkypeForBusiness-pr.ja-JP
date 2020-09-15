---
title: ポイント ツー ポイントのファイル転送を禁止する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: Skype for Business Online では、既存の会議ポリシー設定の一部としてポイントツーポイント (P2P) ファイル転送を制御できます。 ただし、この方法では、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーションユーザーにファイルを転送しているかどうかに関係なく、ファイルの転送が許可またはブロックされます。 以下の手順に従うと、フェデレーションされた組織またはパートナーとの P2P のファイル転送をブロックできます。
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814636"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="bb5d3-105">ポイント ツー ポイントのファイル転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="bb5d3-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="bb5d3-106">Skype for Business Online では、既存の会議ポリシー設定の一部としてポイントツーポイント (P2P) ファイル転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="bb5d3-107">ただし、この方法では、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーションユーザーにファイルを転送しているかどうかに関係なく、ファイルの転送が許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="bb5d3-108">以下の手順に従うと、フェデレーションされた組織またはパートナーとの P2P のファイル転送をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="bb5d3-109">一般的なシナリオとしては、内部ユーザーが P2P ファイル転送を使用できるようにして、フェデレーションパートナーとのファイル送信をブロックすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="bb5d3-110">このシナリオでは、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="bb5d3-111">P2P のファイル転送が有効になっている会議ポリシー (_EnableP2PFileTransfer_ を _True_に設定) を組織のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="bb5d3-112">外部の P2P ファイル転送 (_EnableP2PFileTransfer_ が _False_に設定されている) をブロックして組織内のユーザーに割り当てる、グローバルな外部ユーザー通信ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="bb5d3-113">これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="bb5d3-114">組織外のフェデレーションユーザーが、ポリシーが適用されているユーザーにファイルを送信しようとした場合、 **転送失敗** エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="bb5d3-115">また、ユーザーがファイルを送信しようとすると、 **ファイル転送が有効になっ** ていないことを示すエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="bb5d3-116">この動作を実現するには、サポートされているバージョンの2016のクイック実行 Skype for Business アプリを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="bb5d3-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="bb5d3-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-118">**Type**</span></span>|<span data-ttu-id="bb5d3-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-119">**Release date**</span></span>|<span data-ttu-id="bb5d3-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-120">**Version**</span></span>|<span data-ttu-id="bb5d3-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb5d3-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="bb5d3-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="bb5d3-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="bb5d3-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="bb5d3-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="bb5d3-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="bb5d3-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="bb5d3-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="bb5d3-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="bb5d3-126">Current Channel</span></span>  <br/> |<span data-ttu-id="bb5d3-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="bb5d3-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="bb5d3-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="bb5d3-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="bb5d3-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="bb5d3-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="bb5d3-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="bb5d3-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="bb5d3-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="bb5d3-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="bb5d3-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="bb5d3-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="bb5d3-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="bb5d3-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="bb5d3-134">以前のバージョンの Skype for Business Windows アプリまたは Mac クライアントを使っているユーザーは、引き続きファイルを転送することができます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="bb5d3-135">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="bb5d3-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="bb5d3-136">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="bb5d3-137">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="bb5d3-138">[ **Windows PowerShell** ] ウィンドウで、「 _Get Host_ 」と入力してバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="bb5d3-139">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="bb5d3-140">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="bb5d3-141">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="bb5d3-142">また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="bb5d3-143">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="bb5d3-144">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="bb5d3-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="bb5d3-145">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="bb5d3-146">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="bb5d3-147">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="bb5d3-148">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="bb5d3-149">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="bb5d3-150">組織の P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="bb5d3-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="bb5d3-151">既定では、組織のグローバルポリシーで _EnableP2PFileTransfer_ が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="bb5d3-152">作成されたユーザーには、 _Bpossallmodality_ ポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="bb5d3-153">組織内の P2P 転送を許可するが、外部ファイル転送を別の組織にブロックするには、それをグローバルレベルで変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="bb5d3-154">そのためには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="bb5d3-155">ユーザーに対して P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="bb5d3-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="bb5d3-156">新しいポリシーを作成し、そのポリシーをそのユーザーに付与することで、ユーザーに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="bb5d3-157">そのためには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bb5d3-158">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="bb5d3-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bb5d3-159">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bb5d3-160">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bb5d3-161">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bb5d3-162">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="bb5d3-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bb5d3-163">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="bb5d3-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bb5d3-164">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bb5d3-165">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5d3-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bb5d3-166">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="bb5d3-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bb5d3-167">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="bb5d3-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bb5d3-168">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="bb5d3-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bb5d3-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb5d3-169">Related topics</span></span>
[<span data-ttu-id="bb5d3-170">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="bb5d3-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="bb5d3-171">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bb5d3-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="bb5d3-172">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bb5d3-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
