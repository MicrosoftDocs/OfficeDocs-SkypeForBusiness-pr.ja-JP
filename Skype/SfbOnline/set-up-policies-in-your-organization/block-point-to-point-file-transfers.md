---
title: "ブロックのポイントツー ポイント ファイル転送"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: "Skype for Business Online で、既存の会議のポリシー設定の一部としてポイントツー ポイント (P2P) ファイルの転送を制御する機能があります。ただし、これにより、またはブロック ファイルまたは別の組織のフェデレーションされたユーザーに同じ組織内であるユーザーにファイルを転送がかどうかをユーザーに転送します。次の手順では、次のフェデレーションの組織やパートナーと P2P ファイル転送をブロックすることができます。"
ms.openlocfilehash: 288bec32d55d9784690d84b8daa205dd33568847
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="56246-105">ブロックのポイントツー ポイント ファイル転送</span><span class="sxs-lookup"><span data-stu-id="56246-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="56246-p102">Skype for Business Online で、既存の会議のポリシー設定の一部としてポイントツー ポイント (P2P) ファイルの転送を制御する機能があります。ただし、これにより、またはブロック ファイルまたは別の組織のフェデレーションされたユーザーに同じ組織内であるユーザーにファイルを転送がかどうかをユーザーに転送します。次の手順では、次のフェデレーションの組織やパートナーと P2P ファイル転送をブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="56246-p102">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings. However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization. Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="56246-p103">一般的なシナリオは、内部ユーザーが使用 P2P ファイル転送がフェデレーション パートナーとファイル転送のブロックを入力できるようにする場合です。このシナリオでは、操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56246-p103">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners. For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="56246-111">組織のユーザーには、P2P ファイル転送が有効になっている (_EnableP2PFileTransfer_を_True_に設定) を会議ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="56246-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="56246-112">外部 P2P ファイル転送 (を_False_に設定されている_EnableP2PFileTransfer_ ) をブロックして、組織内のユーザーに割り当てるに設定グローバルに外部ユーザーの通信ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="56246-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="56246-113">これらの設定の詳細を確認したことが[次のとおり](https://technet.microsoft.com/en-us/library/mt228132.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="56246-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="56246-p104">組織外のフェデレーションされたユーザーは、ポリシーが適用されたユーザーにファイルを送信しようとすると、それら**移行に失敗しました。**エラーが表示されます。**ファイル転送がオフになっている**エラーが表示されますが、ユーザーがファイルを送信しようとすると場合、。</span><span class="sxs-lookup"><span data-stu-id="56246-p104">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error. And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="56246-p105">この作業をするためには、ユーザーする必要がありますに使用する 2016年クイック実行 Skype のサポートされているバージョンでサポートされているビジネス アプリ。次最小のバージョンの Skype for Business の 2016年クイック実行をクライアントが必要です。</span><span class="sxs-lookup"><span data-stu-id="56246-p105">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it. The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="56246-118">**種類**</span><span class="sxs-lookup"><span data-stu-id="56246-118">**Type**</span></span>|<span data-ttu-id="56246-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="56246-119">**Release date**</span></span>|<span data-ttu-id="56246-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="56246-120">**Version**</span></span>|<span data-ttu-id="56246-121">**作成します。**</span><span class="sxs-lookup"><span data-stu-id="56246-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56246-122">現在のチャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="56246-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="56246-123">2016/11/17</span><span class="sxs-lookup"><span data-stu-id="56246-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="56246-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="56246-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="56246-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="56246-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="56246-126">現在のチャネル</span><span class="sxs-lookup"><span data-stu-id="56246-126">Current Channel</span></span>  <br/> |<span data-ttu-id="56246-127">2016/12/6</span><span class="sxs-lookup"><span data-stu-id="56246-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="56246-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="56246-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="56246-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="56246-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="56246-130">チャンネルの遅延</span><span class="sxs-lookup"><span data-stu-id="56246-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="56246-131">2017/2/22</span><span class="sxs-lookup"><span data-stu-id="56246-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="56246-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="56246-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="56246-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="56246-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="56246-134">以前のバージョンの Skype for Business の Windows アプリまたは Mac クライアントを使用しているユーザーはファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="56246-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="56246-135">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="56246-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="56246-136">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="56246-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="56246-137">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="56246-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="56246-138">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="56246-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="56246-p106">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="56246-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="56246-p107">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="56246-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="56246-145">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56246-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="56246-146">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="56246-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="56246-147">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="56246-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="56246-148">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="56246-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56246-149">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="56246-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="56246-150">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56246-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="56246-151">組織の P2P ファイル転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="56246-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="56246-p108">組織のグローバル ポリシーでは既定では、 _EnableP2PFileTransfer_が有効にします。作成したときに、ユーザーは_BposSAllModality_ポリシーに割り当てられたします。</span><span class="sxs-lookup"><span data-stu-id="56246-p108">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy. When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="56246-p109">組織がブロック外部ファイルの転送に別の組織内の P2P 転送ができるように、だけグローバル レベルで変更する必要があります。そのため、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56246-p109">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level. To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="56246-156">ユーザーの P2P ファイル転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="56246-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="56246-p110">ユーザーに新しいポリシーを作成して、そのユーザーに許可して適用することができます。そのため、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56246-p110">You can apply this to a user by creating a new policy and granting it to that user. To do that, run:</span></span> 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="56246-159">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="56246-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="56246-p111">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56246-p111">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="56246-163">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="56246-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="56246-164">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="56246-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="56246-p112">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="56246-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="56246-167">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="56246-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="56246-168">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="56246-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="56246-169">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="56246-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="56246-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="56246-170">Related topics</span></span>
[<span data-ttu-id="56246-171">ユーザー設定の外部アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="56246-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="56246-172">組織のクライアントのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="56246-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="56246-173">組織内の会議のポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="56246-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

