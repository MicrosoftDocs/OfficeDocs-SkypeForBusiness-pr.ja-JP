---
title: 組織のクライアント ポリシーをセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。
ms.openlocfilehash: 59bc9ab406d530bc09803b61cfc4341617dc911d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240089"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="ad655-103">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ad655-103">Set up client policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ad655-104">[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="ad655-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="ad655-105">クライアント ポリシーの設定は、ポリシーの作成時に構成するか **、Set-CsClientPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ad655-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="ad655-106">クライアント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ad655-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="ad655-107">Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="ad655-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="ad655-108">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad655-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="ad655-109">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad655-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="ad655-110">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad655-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="ad655-111">[PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="ad655-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="ad655-112">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="ad655-113">Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="ad655-114">絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する</span><span class="sxs-lookup"><span data-stu-id="ad655-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="ad655-115">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="ad655-116">[詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="ad655-117">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="ad655-118">[詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="ad655-119">既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ad655-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="ad655-120">URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする</span><span class="sxs-lookup"><span data-stu-id="ad655-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="ad655-121">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="ad655-122">[詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="ad655-123">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="ad655-124">[詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="ad655-125">既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ad655-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="ad655-126">最近の連絡先を表示しないようにする</span><span class="sxs-lookup"><span data-stu-id="ad655-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="ad655-127">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="ad655-128">[詳細については、New-CsClientPolicy コマンドレットを参照](/powershell/module/skype/New-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="ad655-129">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad655-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="ad655-130">[詳細については、Grant-CsClientPolicy コマンドレットを参照](/powershell/module/skype/Grant-CsClientPolicy)してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="ad655-131">既にポリシーを作成している場合は [、Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="ad655-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ad655-132">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="ad655-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ad655-133">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="ad655-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ad655-134">Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="ad655-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ad655-135">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad655-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ad655-136">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ad655-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="ad655-137">アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365</span><span class="sxs-lookup"><span data-stu-id="ad655-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="ad655-138">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="ad655-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ad655-139">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad655-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="ad655-140">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ad655-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="ad655-141">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ad655-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="ad655-142">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ad655-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="ad655-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad655-143">Related topics</span></span>
[<span data-ttu-id="ad655-144">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad655-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="ad655-145">ポイント対ポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="ad655-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ad655-146">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ad655-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
