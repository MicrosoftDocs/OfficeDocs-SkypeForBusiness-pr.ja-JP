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
f1keywords: None
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: f876519ba7d3cf25e61f4f6458129d724d1bcb84
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962785"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="352ff-103">Outlook 会議で使用するコンテンツ プリロードの有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="352ff-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="352ff-104">ユーザーは、Outlook 会議出席依頼に添付されているコンテンツ、ファイル、または添付ファイルを Skype for Business Online の会議にプリロードできますが、オンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="352ff-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="352ff-105">Skype for Business Online を使用しているすべての組織に対して、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="352ff-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="352ff-106">[Skype For business 会議の添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="352ff-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="352ff-107">現時点では、 _Maxcontentstoragemb 枠_と_Maxcontentstoragemb_のオンライン値を設定または表示するために、Skype for business Online で利用可能なコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="352ff-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="352ff-108">これは、オンプレミス環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="352ff-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="352ff-109">添付されたコンテンツが_Maxuploadfilesizemb 枠_を超えている場合、または_Maxcontentstorag飾り_枠の制限に達している場合は、コンテンツが会議にアップロードされないことを知っておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="352ff-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="352ff-110">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="352ff-110">To get you started</span></span>

### 

 <span data-ttu-id="352ff-111">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="352ff-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="352ff-112">3.0 以降のバージョンが実行されていることを確認する場合: **[スタート] メニュー** > **[Windows PowerShell]**。</span><span class="sxs-lookup"><span data-stu-id="352ff-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="352ff-113">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="352ff-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="352ff-114">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="352ff-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="352ff-115">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="352ff-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="352ff-116">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="352ff-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="352ff-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="352ff-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="352ff-120">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="352ff-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="352ff-121">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="352ff-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="352ff-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="352ff-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="352ff-123">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="352ff-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="352ff-124">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="352ff-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="352ff-125">Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="352ff-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="352ff-126">機能の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="352ff-126">Turning it on or off</span></span>

<span data-ttu-id="352ff-127">Outlook の会議出席依頼に添付されているコンテンツを Skype for Business Online の会議に自動的に読み込むことができるようになっている場合、既定ではオンになっていますが、組織内のユーザーが会議のコンテンツを事前に設定できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="352ff-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="352ff-128">この設定は組織全体で有効または無効にすることができます。1人のユーザに対して有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="352ff-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="352ff-129">**無効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="352ff-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="352ff-130">**再び有効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="352ff-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="352ff-131">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="352ff-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="352ff-132">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="352ff-132">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="352ff-133">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="352ff-133">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="352ff-134">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="352ff-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="352ff-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="352ff-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="352ff-136">Windows PowerShell を使用して Office 365 を管理する6つの理由</span><span class="sxs-lookup"><span data-stu-id="352ff-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="352ff-137">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="352ff-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="352ff-138">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="352ff-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="352ff-139">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="352ff-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="352ff-140">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="352ff-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="352ff-141">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="352ff-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="352ff-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="352ff-142">Related topics</span></span>
[<span data-ttu-id="352ff-143">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="352ff-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="352ff-144">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="352ff-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
