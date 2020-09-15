---
title: Outlook 会議で使用するコンテンツ プリロードの有効化と無効化
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814586"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="94157-103">Outlook 会議で使用するコンテンツ プリロードの有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="94157-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="94157-104">ユーザーは、Outlook 会議出席依頼に添付されているコンテンツ、ファイル、または添付ファイルを Skype for Business Online の会議にプリロードできますが、オンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="94157-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="94157-105">Skype for Business Online を使用しているすべての組織に対して、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="94157-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="94157-106">[Skype For business 会議の添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94157-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="94157-107">現時点では、  _Maxcontentstoragemb 枠_ と _Maxcontentstoragemb_のオンライン値を設定または表示するために、Skype for business Online で利用可能なコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="94157-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="94157-108">これは、オンプレミス環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="94157-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="94157-109">添付されたコンテンツが  _Maxuploadfilesizemb 枠_ を超えている場合、または _Maxcontentstorag飾り_ 枠の制限に達している場合は、コンテンツが会議にアップロードされないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="94157-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="94157-110">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="94157-110">To get you started</span></span>

### 

 <span data-ttu-id="94157-111">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="94157-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="94157-112">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="94157-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="94157-113">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="94157-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="94157-114">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94157-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="94157-115">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94157-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="94157-116">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94157-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="94157-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94157-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="94157-120">詳細については、「 [単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94157-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="94157-121">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="94157-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="94157-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="94157-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="94157-123">**Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。</span><span class="sxs-lookup"><span data-stu-id="94157-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="94157-124">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="94157-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="94157-125">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94157-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="94157-126">Windows PowerShell の起動の詳細については、「 [1 つの Windows powershell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx) する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94157-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="94157-127">機能の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="94157-127">Turning it on or off</span></span>

<span data-ttu-id="94157-128">Outlook の会議出席依頼に添付されているコンテンツを Skype for Business Online の会議に自動的に読み込むことができるようになっている場合、既定ではオンになっていますが、組織内のユーザーが会議のコンテンツを事前に設定できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94157-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="94157-129">この設定は組織全体で有効または無効にすることができます。1人のユーザに対して有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94157-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="94157-130">**無効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="94157-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="94157-131">**再び有効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="94157-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="94157-132">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="94157-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="94157-133">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="94157-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="94157-134">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して、Microsoft 365 または Office 365 と Skype for Business Online を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="94157-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="94157-135">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94157-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="94157-136">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="94157-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="94157-137">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="94157-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="94157-138">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="94157-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="94157-139">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="94157-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="94157-140">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="94157-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="94157-141">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="94157-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="94157-142">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="94157-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="94157-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="94157-143">Related topics</span></span>
[<span data-ttu-id="94157-144">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="94157-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="94157-145">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="94157-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
