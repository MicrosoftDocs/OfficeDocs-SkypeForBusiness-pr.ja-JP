---
title: 組織のモバイル ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240069"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="790df-104">組織のモバイル ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="790df-104">Set up mobile policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="790df-p102">[] モバイル デバイス上の Skype for Business アプリで、携帯電話番号ではなく勤務先の電話番号を使用して携帯電話上で通話を発信および受信できるようにする機能などにより、ユーザーが Skype for Business Online に接続する方法を設定することができます。モバイル機能ポリシーを使用して、通話の発着信時に Wi-Fi 接続を要求するようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="790df-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="790df-107">モバイル機能ポリシー設定はポリシーが作成されるときに構成できます。また、 **Set-CsMobilityPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="790df-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="790df-108">モバイル機能ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="790df-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="790df-109">Skype for Business Online のすべてのモバイル機能ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="790df-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="790df-110">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="790df-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="790df-111">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="790df-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="790df-112">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="790df-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="790df-113">[PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="790df-113">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="790df-114">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="790df-115">Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="790df-116">ユーザーに対してビデオ使用時に WiFi 接続を要求する</span><span class="sxs-lookup"><span data-stu-id="790df-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="790df-117">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="790df-118">[New-CsMobilityPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-118">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="790df-119">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="790df-120">[詳細については、Grant-CsMobilityPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-120">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="790df-121">ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) を使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="790df-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="790df-122">ユーザーが Skype for Business アプリを使用できないようにする</span><span class="sxs-lookup"><span data-stu-id="790df-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="790df-123">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="790df-124">[New-CsMobilityPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-124">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="790df-125">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="790df-126">[詳細については、Grant-CsMobilityPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-126">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="790df-127">ポリシーを既に作成している場合は [、Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="790df-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="790df-128">ユーザーがモバイル デバイスを使用してボイス オーバー IP 通話を行えないようにする</span><span class="sxs-lookup"><span data-stu-id="790df-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="790df-129">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="790df-130">[New-CsMobilityPolicy コマンドレットの詳細を参照](/powershell/module/skype/New-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-130">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="790df-131">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="790df-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="790df-132">[詳細については、Grant-CsMobilityPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsMobilityPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="790df-132">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
<span data-ttu-id="790df-133">ポリシーを作成済みの場合は、[Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットを使用して、既存のポリシーに対する変更を行います。次に、[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) を使用して設定をユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="790df-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="790df-134">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="790df-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="790df-135">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="790df-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="790df-136">Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="790df-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="790df-137">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="790df-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="790df-138">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="790df-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="790df-139">アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365</span><span class="sxs-lookup"><span data-stu-id="790df-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="790df-140">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="790df-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="790df-141">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="790df-141">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="790df-142">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="790df-142">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="790df-143">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="790df-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="790df-144">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="790df-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="790df-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="790df-145">Related topics</span></span>
[<span data-ttu-id="790df-146">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="790df-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="790df-147">ポイント対ポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="790df-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="790df-148">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="790df-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="790df-149">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="790df-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
