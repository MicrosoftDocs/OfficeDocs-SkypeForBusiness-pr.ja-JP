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
ms.openlocfilehash: 65a346f0f16892d5995b723431fc796e3faa1a3b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569229"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="66dbe-103">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="66dbe-103">Set up client policies for your organization</span></span>

<span data-ttu-id="66dbe-104">[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="66dbe-105">クライアント ポリシー設定は、ポリシーの作成時に構成するか **、Set-CsClientPolicy** コマンドレットを使用して既存のポリシーの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="66dbe-106">クライアント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="66dbe-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="66dbe-107">Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="66dbe-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="66dbe-108">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66dbe-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="66dbe-109">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="66dbe-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="66dbe-110">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66dbe-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="66dbe-111">Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="66dbe-111">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="66dbe-112">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="66dbe-113">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="66dbe-114">絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する</span><span class="sxs-lookup"><span data-stu-id="66dbe-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="66dbe-115">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="66dbe-116">[New-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779155.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-116">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="66dbe-117">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="66dbe-118">[Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779152.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-118">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="66dbe-119">既にポリシーを作成している場合は [、Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-119">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="66dbe-120">URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする</span><span class="sxs-lookup"><span data-stu-id="66dbe-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="66dbe-121">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="66dbe-122">[New-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779155.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-122">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="66dbe-123">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="66dbe-124">[Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779152.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-124">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="66dbe-125">既にポリシーを作成している場合は [、Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-125">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="66dbe-126">最近の連絡先を表示しないようにする</span><span class="sxs-lookup"><span data-stu-id="66dbe-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="66dbe-127">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="66dbe-128">[New-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779155.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-128">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="66dbe-129">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="66dbe-130">[Grant-CsClientPolicy コマンドレットの詳細については、以下を参照](https://technet.microsoft.com/library/mt779152.aspx)してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-130">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="66dbe-131">既にポリシーを作成している場合は [、Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して設定をユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-131">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="66dbe-132">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="66dbe-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="66dbe-133">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="66dbe-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="66dbe-134">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="66dbe-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="66dbe-135">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dbe-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="66dbe-136">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="66dbe-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="66dbe-137">Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由</span><span class="sxs-lookup"><span data-stu-id="66dbe-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="66dbe-138">Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="66dbe-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="66dbe-139">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="66dbe-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="66dbe-140">Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66dbe-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="66dbe-141">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="66dbe-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="66dbe-142">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="66dbe-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="66dbe-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="66dbe-143">Related topics</span></span>
[<span data-ttu-id="66dbe-144">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="66dbe-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="66dbe-145">ポイント間のファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="66dbe-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="66dbe-146">組織で会議ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="66dbe-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
