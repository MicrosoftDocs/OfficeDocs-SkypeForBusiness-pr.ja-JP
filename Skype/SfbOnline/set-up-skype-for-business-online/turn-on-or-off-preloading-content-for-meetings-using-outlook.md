---
title: Outlook 会議で使用するコンテンツ プリロードの有効化と無効化
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 7ad2eae6f38a0587503cc9f0786b3a999e04ff3e
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="6143d-103">Outlook 会議で使用するコンテンツ プリロードの有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="6143d-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="6143d-104">ユーザーにプリロードするコンテンツ、ファイル、または、Skype ビジネス オンライン会議を開くのために、Outlook の会議出席依頼に関連付けられている添付ファイルは、有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6143d-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="6143d-105">これは、ビジネス オンラインの Skype を使用しているすべての組織においてデフォルトでなっています。</span><span class="sxs-lookup"><span data-stu-id="6143d-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="6143d-106">参照してください[に Skype ビジネス会議のための添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法です。</span><span class="sxs-lookup"><span data-stu-id="6143d-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6143d-107">現在はありませんコマンドレットに使用できるビジネス オンラインの Skype の設定または_MaxContentStorageMB_と_MaxUploadFileMB_のオンラインの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6143d-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="6143d-108">これは、オンプレミス環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6143d-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="6143d-109">知っている必要が接続されているコンテンツは、 _MaxUploadFileSizeMB_を超える場合、または_MaxContentStorageMB_の制限に達した場合、会議にそのコンテンツをアップロードできなきます。</span><span class="sxs-lookup"><span data-stu-id="6143d-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="6143d-110">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6143d-110">To get you started</span></span>

### 

 <span data-ttu-id="6143d-111">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="6143d-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="6143d-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6143d-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6143d-113">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="6143d-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6143d-p103">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6143d-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6143d-p104">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6143d-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="6143d-120">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6143d-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="6143d-121">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="6143d-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="6143d-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6143d-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6143d-123">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="6143d-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6143d-124">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="6143d-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="6143d-125">Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6143d-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="6143d-126">機能の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="6143d-126">Turning it on or off</span></span>

<span data-ttu-id="6143d-127">Skype をビジネス オンライン会議のため、Outlook 会議出席依頼に添付されているコンテンツを事前にできることになって、デフォルトでは、会議の内容を事前に読み込むことから、組織内のユーザーを防止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6143d-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6143d-128">この設定できますのみ、オンまたはオフは組織全体の機能のオンとオフは、1 人のユーザーにできません。</span><span class="sxs-lookup"><span data-stu-id="6143d-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="6143d-129">**無効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="6143d-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="6143d-130">**再び有効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="6143d-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6143d-131">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="6143d-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6143d-p105">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6143d-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6143d-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="6143d-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6143d-136">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="6143d-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6143d-p106">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="6143d-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6143d-139">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6143d-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6143d-140">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="6143d-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6143d-141">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="6143d-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6143d-142">See also</span><span class="sxs-lookup"><span data-stu-id="6143d-142">Related topics</span></span>
[<span data-ttu-id="6143d-143">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="6143d-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6143d-144">Skype for Business ユーザーが Skype 連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="6143d-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 