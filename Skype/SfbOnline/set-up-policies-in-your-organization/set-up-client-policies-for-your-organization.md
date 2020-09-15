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
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814356"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="78b8a-103">組織のクライアント ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="78b8a-103">Set up client policies for your organization</span></span>

<span data-ttu-id="78b8a-104">[] クライアント ポリシーはユーザーが利用できる Skype for Business Online の機能を決めるのに役立ちます。たとえば、一部のユーザーにファイルを転送する権限を与えて、他のユーザーに対してはその権限を与えないようにする場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="78b8a-105">クライアントポリシー設定はポリシーが作成されるときに構成することができます。また、 **Set-CsClientPolicy** コマンドレットを使用して、既存のポリシーの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="78b8a-106">クライアント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="78b8a-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="78b8a-107">Skype for Business Online のすべてのクライアント ポリシー設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。</span><span class="sxs-lookup"><span data-stu-id="78b8a-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="78b8a-108">Windows PowerShell を検証および開始する</span><span class="sxs-lookup"><span data-stu-id="78b8a-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="78b8a-109">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="78b8a-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="78b8a-110">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="78b8a-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="78b8a-111">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="78b8a-112">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b8a-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="78b8a-113">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="78b8a-114">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-114">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="78b8a-115">また、Skype for Business Online に接続するリモート Windows PowerShell セッションを作成できるようにする、Teams 用の Windows PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78b8a-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="78b8a-116">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="78b8a-117">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="78b8a-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="78b8a-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78b8a-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="78b8a-119">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78b8a-120">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="78b8a-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="78b8a-121">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78b8a-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="78b8a-122">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="78b8a-123">絵文字、プレゼンスの通知を無効にして、インスタントメッセージ (IM) の保存を防止する</span><span class="sxs-lookup"><span data-stu-id="78b8a-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="78b8a-124">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="78b8a-125">詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="78b8a-126">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="78b8a-127">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="78b8a-128">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="78b8a-129">URL またはハイパーリンクを有効にしてインスタントメッセージ (IM) でクリックできる状態にする</span><span class="sxs-lookup"><span data-stu-id="78b8a-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="78b8a-130">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="78b8a-131">詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="78b8a-132">作成した新しいポリシーを組織内のすべてのユーザーに付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="78b8a-133">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="78b8a-134">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="78b8a-135">最近の連絡先を表示しないようにする</span><span class="sxs-lookup"><span data-stu-id="78b8a-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="78b8a-136">これらの設定のために新しいポリシーを作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="78b8a-137">詳細については、「 [新しい-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="78b8a-138">Amos Marble に作成した新しいポリシーを付与するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="78b8a-139">詳細については、「 [Grant Clientpolicy](https://technet.microsoft.com/library/mt779152.aspx) コマンドレット」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="78b8a-140">既にポリシーを作成している場合は、 [Set-csclientpolicy](https://technet.microsoft.com/library/mt779153.aspx) コマンドレットを使用して既存のポリシーに変更を加え、[ [権限の付与] クライアントポリシー](https://technet.microsoft.com/library/mt779152.aspx) コマンドレットを使用して、ユーザーに設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78b8a-141">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="78b8a-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="78b8a-142">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="78b8a-143">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="78b8a-144">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78b8a-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78b8a-145">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="78b8a-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="78b8a-146">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="78b8a-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="78b8a-147">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="78b8a-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="78b8a-148">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="78b8a-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="78b8a-149">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="78b8a-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="78b8a-150">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="78b8a-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="78b8a-151">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="78b8a-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="78b8a-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="78b8a-152">Related topics</span></span>
[<span data-ttu-id="78b8a-153">カスタム外部アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="78b8a-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="78b8a-154">ポイントツーポイントファイル転送をブロックする</span><span class="sxs-lookup"><span data-stu-id="78b8a-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="78b8a-155">組織内の会議ポリシーをセットアップする</span><span class="sxs-lookup"><span data-stu-id="78b8a-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
