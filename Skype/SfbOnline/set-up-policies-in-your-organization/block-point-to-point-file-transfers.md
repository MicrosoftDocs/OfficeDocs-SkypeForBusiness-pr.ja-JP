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
description: Skype for Business Online では、既存の会議ポリシー設定の一部としてポイント対ポイント (P2P) ファイル転送を制御できます。 ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関して、ユーザーのファイル転送が許可またはブロックされます。 以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240176"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="e7052-105">ポイント ツー ポイントのファイル転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="e7052-105">Block Point-to-Point file transfers</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e7052-106">Skype for Business Online では、既存の会議ポリシー設定の一部としてポイント対ポイント (P2P) ファイル転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e7052-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="e7052-107">ただし、これにより、ユーザーが同じ組織内のユーザーまたは別の組織のフェデレーション ユーザーにファイルを転送するかどうかに関して、ユーザーのファイル転送が許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e7052-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="e7052-108">以下の手順に従って、フェデレーション組織またはパートナーとの P2P ファイル転送をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e7052-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="e7052-109">非常に一般的なシナリオは、内部ユーザーに P2P ファイル転送の使用を許可し、フェデレーション パートナーとのファイル転送をブロックする場合です。</span><span class="sxs-lookup"><span data-stu-id="e7052-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="e7052-110">このシナリオでは、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7052-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="e7052-111">P2P ファイル転送が有効な会議ポリシー _(EnableP2PFileTransfer_ を _True_ に設定) を組織内のユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e7052-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="e7052-112">外部 P2P ファイル転送をブロックするグローバル外部ユーザー通信ポリシー セット _(EnableP2PFileTransfer_ を _False_ に設定) を作成し、組織内のユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e7052-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="e7052-113">これらの設定に関する詳細は、 [ここ](/previous-versions//mt228132(v=technet.10))からご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="e7052-113">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="e7052-114">組織外のフェデレーション ユーザーが、ポリシーが適用されているユーザーにファイルを送信しようとすると、転送失敗エラー **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e7052-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="e7052-115">また、ユーザーがファイルを送信しようとすると、ファイル転送が無効になっている **というエラーが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e7052-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="e7052-116">この作業を行う場合、ユーザーは、サポートされている 2016 年 2016 年バージョンのアプリをクイック実行 Skype for Business使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7052-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="e7052-117">Skype for Business 2016 クイック実行クライアントの次の最小バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7052-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="e7052-118">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7052-118">**Type**</span></span>|<span data-ttu-id="e7052-119">**リリース日**</span><span class="sxs-lookup"><span data-stu-id="e7052-119">**Release date**</span></span>|<span data-ttu-id="e7052-120">**バージョン**</span><span class="sxs-lookup"><span data-stu-id="e7052-120">**Version**</span></span>|<span data-ttu-id="e7052-121">**ビルド**</span><span class="sxs-lookup"><span data-stu-id="e7052-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7052-122">最新機能提供チャネルの最初のリリース</span><span class="sxs-lookup"><span data-stu-id="e7052-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="e7052-123">2016 年 11 月 17 日</span><span class="sxs-lookup"><span data-stu-id="e7052-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="e7052-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="e7052-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="e7052-125">バージョン 1611 (ビルド 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="e7052-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="e7052-126">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="e7052-126">Current Channel</span></span>  <br/> |<span data-ttu-id="e7052-127">2016 年 12 月 6 日</span><span class="sxs-lookup"><span data-stu-id="e7052-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="e7052-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="e7052-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="e7052-129">バージョン 1611 (ビルド 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="e7052-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="e7052-130">段階的提供チャネル</span><span class="sxs-lookup"><span data-stu-id="e7052-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="e7052-131">2017 年 2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="e7052-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="e7052-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="e7052-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="e7052-133">バージョン 1609 (ビルド 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="e7052-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="e7052-134">以前のバージョンのアプリまたは Mac Skype for Business Windowsを使用しているユーザーは、引き続きファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="e7052-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="e7052-135">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7052-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="e7052-136">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7052-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="e7052-137">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7052-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="e7052-138">[PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="e7052-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="e7052-139">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7052-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="e7052-140">Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。</span><span class="sxs-lookup"><span data-stu-id="e7052-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="e7052-141">組織の P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="e7052-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="e7052-142">既定では _、EnableP2PFileTransfer は_ 組織のグローバル ポリシーで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e7052-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="e7052-143">作成されると、ユーザーに _BposSAllModality ポリシーが割り当_ てされました。</span><span class="sxs-lookup"><span data-stu-id="e7052-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="e7052-144">組織内での P2P 転送を許可し、外部ファイルの別の組織への転送をブロックするには、グローバル レベルで変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7052-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="e7052-145">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7052-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="e7052-146">ユーザーの P2P ファイル転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="e7052-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="e7052-147">これをユーザーに適用するには、新しいポリシーを作成し、そのユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="e7052-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="e7052-148">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7052-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e7052-149">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="e7052-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="e7052-150">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="e7052-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e7052-151">Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="e7052-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e7052-152">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7052-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e7052-153">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="e7052-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e7052-154">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="e7052-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="e7052-155">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="e7052-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e7052-156">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7052-156">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="e7052-157">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e7052-157">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="e7052-158">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="e7052-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="e7052-159">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e7052-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="e7052-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7052-160">Related topics</span></span>
[<span data-ttu-id="e7052-161">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e7052-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="e7052-162">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e7052-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="e7052-163">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="e7052-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
