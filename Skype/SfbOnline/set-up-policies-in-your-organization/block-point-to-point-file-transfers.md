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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: ビジネス オンラインの Skype は、既存の会議ポリシー設定の一部として、ポイント ツー ポイント (P2P) ファイルの転送を制御する機能があります。 ただし、これにより、またはファイルかどうかは、ファイルを転送するユーザーは、同じ組織内に、または別の組織からのフェデレーション ユーザーにユーザーの転送をブロックします。 次の手順では、次のまたはパートナーのフェデレーション組織との P2P のファイル転送をブロックできます。
ms.openlocfilehash: 9b7d229c7f0ea0565dc3174286b4117984a2b606
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237540"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="21558-105">ポイント ツー ポイントのファイル転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="21558-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="21558-106">ビジネス オンラインの Skype は、既存の会議ポリシー設定の一部として、ポイント ツー ポイント (P2P) ファイルの転送を制御する機能があります。</span><span class="sxs-lookup"><span data-stu-id="21558-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="21558-107">ただし、これにより、またはファイルかどうかは、ファイルを転送するユーザーは、同じ組織内に、または別の組織からのフェデレーション ユーザーにユーザーの転送をブロックします。</span><span class="sxs-lookup"><span data-stu-id="21558-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="21558-108">次の手順では、次のまたはパートナーのフェデレーション組織との P2P のファイル転送をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="21558-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="21558-109">非常に一般的なシナリオは、内部ユーザーが P2P を使用してファイル転送がフェデレーション パートナーとファイル転送をブロックできるようにする場合です。</span><span class="sxs-lookup"><span data-stu-id="21558-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="21558-110">このシナリオでは、実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21558-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="21558-111">P2P ファイル転送が有効になっている (_EnableP2PFileTransfer_を_True_に設定) で、組織内のユーザーに会議ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="21558-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="21558-112">外部の P2P ファイル転送 (_EnableP2PFileTransfer_は_False_に設定) をブロックし、組織内のユーザーに割り当てることに設定した外部ユーザーのグローバル通信ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="21558-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="21558-113">これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/en-us/library/mt228132.aspx)からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="21558-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="21558-114">組織外のフェデレーション ユーザーは、ポリシーが適用されているユーザーにファイルを送信しようとすると、**転送に失敗しました**エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21558-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="21558-115">ユーザーがファイルを送信しようとすると場合、エラーが表示されます、**ファイルの転送がオフになっています**。</span><span class="sxs-lookup"><span data-stu-id="21558-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="21558-116">この作業をするためには、ユーザーする必要があります使用している 2016年クイック実行の Skype のサポートされているバージョンでサポートされているビジネス アプリケーションの。</span><span class="sxs-lookup"><span data-stu-id="21558-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="21558-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="21558-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="21558-118">**型**</span><span class="sxs-lookup"><span data-stu-id="21558-118">**Type**</span></span>|<span data-ttu-id="21558-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="21558-119">**Release date**</span></span>|<span data-ttu-id="21558-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="21558-120">**Version**</span></span>|<span data-ttu-id="21558-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="21558-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21558-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="21558-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="21558-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="21558-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="21558-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="21558-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="21558-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="21558-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="21558-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="21558-126">Current Channel</span></span>  <br/> |<span data-ttu-id="21558-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="21558-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="21558-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="21558-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="21558-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="21558-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="21558-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="21558-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="21558-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="21558-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="21558-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="21558-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="21558-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="21558-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="21558-134">ビジネス Windows アプリケーションまたは Mac クライアントの以前のバージョンの Skype を使用しているユーザーはファイルを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="21558-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="21558-135">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="21558-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="21558-136">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="21558-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="21558-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="21558-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="21558-138">**Windows PowerShell**ウィンドウで_ホストの取得_を入力してバージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="21558-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="21558-p106">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="21558-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="21558-p107">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="21558-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="21558-145">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21558-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="21558-146">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="21558-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="21558-147">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="21558-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="21558-148">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="21558-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="21558-149">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="21558-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="21558-150">Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell には、コンピューターの設定](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21558-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="21558-151">組織の P2P のファイル転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="21558-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="21558-152">組織のグローバル ポリシーでは既定では、 _EnableP2PFileTransfer_が有効にします。</span><span class="sxs-lookup"><span data-stu-id="21558-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="21558-153">それが作成されたとき、 _BposSAllModality_ポリシーがユーザーに割り当てられました。</span><span class="sxs-lookup"><span data-stu-id="21558-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="21558-154">組織はブロック外部ファイルの転送に別の組織内の P2P の転送を許可するには、だけで、グローバル レベルで変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21558-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="21558-155">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="21558-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="21558-156">ユーザーの P2P のファイル転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="21558-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="21558-157">ユーザーに新しいポリシーを作成して、そのユーザーに付与することによって適用することができます。</span><span class="sxs-lookup"><span data-stu-id="21558-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="21558-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="21558-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="21558-159">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="21558-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="21558-160">Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。</span><span class="sxs-lookup"><span data-stu-id="21558-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="21558-161">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="21558-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="21558-162">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21558-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="21558-163">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="21558-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="21558-164">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="21558-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="21558-p112">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="21558-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="21558-167">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="21558-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="21558-168">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="21558-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="21558-169">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="21558-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="21558-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="21558-170">Related topics</span></span>
[<span data-ttu-id="21558-171">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="21558-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="21558-172">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="21558-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="21558-173">組織内の会議ポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="21558-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
