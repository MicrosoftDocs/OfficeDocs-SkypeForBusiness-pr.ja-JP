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
description: Skype for Business Online では、既存の会議ポリシー設定の一部として、ポイント対ポイント (P2P) ファイル転送を制御できます。 ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関わり、ユーザーのファイル転送が許可またはブロックされます。 以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569103"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="55da5-105">ポイント ツー ポイントのファイル転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="55da5-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="55da5-106">Skype for Business Online では、既存の会議ポリシー設定の一部として、ポイント対ポイント (P2P) ファイル転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="55da5-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="55da5-107">ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関わり、ユーザーのファイル転送が許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="55da5-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="55da5-108">以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="55da5-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="55da5-109">非常に一般的なシナリオは、内部ユーザーに P2P ファイル転送の使用を許可し、フェデレーション パートナーとのファイル転送をブロックする場合です。</span><span class="sxs-lookup"><span data-stu-id="55da5-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="55da5-110">このシナリオでは、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="55da5-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="55da5-111">P2P ファイル転送が有効になっている会議ポリシー _(EnableP2PFileTransfer_ を _True_ に設定) を組織内のユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="55da5-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="55da5-112">外部 P2P ファイル転送 _(EnableP2PFileTransfer_ を _False_ に設定) をブロックするグローバル外部ユーザー通信ポリシー セットを作成し、組織内のユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="55da5-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="55da5-113">これらの設定に関する詳細は、 [ここ](https://technet.microsoft.com/library/mt228132.aspx)からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="55da5-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="55da5-114">組織外のフェデレーション ユーザーが、ポリシーが適用されているユーザーにファイルを送信しようとすると、転送失敗エラー **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="55da5-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="55da5-115">ユーザーがファイルを送信しようとすると、ファイル転送が無効になっているエラー **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="55da5-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="55da5-116">この作業を行う場合、ユーザーは 2016 年のサポートされるバージョンを使用して、クイック実行 Skype for Business アプリを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="55da5-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="55da5-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="55da5-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="55da5-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="55da5-118">**Type**</span></span>|<span data-ttu-id="55da5-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="55da5-119">**Release date**</span></span>|<span data-ttu-id="55da5-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="55da5-120">**Version**</span></span>|<span data-ttu-id="55da5-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="55da5-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55da5-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="55da5-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="55da5-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="55da5-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="55da5-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="55da5-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="55da5-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="55da5-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="55da5-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="55da5-126">Current Channel</span></span>  <br/> |<span data-ttu-id="55da5-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="55da5-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="55da5-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="55da5-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="55da5-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="55da5-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="55da5-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="55da5-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="55da5-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="55da5-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="55da5-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="55da5-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="55da5-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="55da5-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="55da5-134">以前のバージョンの Skype for Business Windows アプリまたは Mac クライアントを使用しているユーザーは、引き続きファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="55da5-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="55da5-135">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55da5-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="55da5-136">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="55da5-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="55da5-137">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="55da5-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="55da5-138">Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="55da5-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="55da5-139">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55da5-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="55da5-140">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55da5-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="55da5-141">組織の P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="55da5-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="55da5-142">既定では _、EnableP2PFileTransfer は_ 組織のグローバル ポリシーで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="55da5-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="55da5-143">作成されると、ユーザーに _BposSAllModality ポリシーが割り当_ てされました。</span><span class="sxs-lookup"><span data-stu-id="55da5-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="55da5-144">組織内での P2P 転送を許可し、別の組織への外部ファイル転送をブロックするには、グローバル レベルで変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55da5-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="55da5-145">これを行うには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="55da5-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="55da5-146">ユーザーの P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="55da5-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="55da5-147">新しいポリシーを作成し、そのユーザーに付与することで、このポリシーをユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="55da5-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="55da5-148">これを行うには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="55da5-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="55da5-149">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="55da5-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="55da5-150">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="55da5-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="55da5-151">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="55da5-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="55da5-152">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55da5-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="55da5-153">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="55da5-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="55da5-154">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="55da5-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="55da5-155">Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="55da5-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="55da5-156">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="55da5-156">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="55da5-157">Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55da5-157">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="55da5-158">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="55da5-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="55da5-159">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="55da5-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="55da5-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="55da5-160">Related topics</span></span>
[<span data-ttu-id="55da5-161">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="55da5-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="55da5-162">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="55da5-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="55da5-163">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="55da5-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
