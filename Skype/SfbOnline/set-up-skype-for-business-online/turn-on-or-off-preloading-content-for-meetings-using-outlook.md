---
title: "オンまたはオフに Outlook を使用して会議のプリロードされたコンテンツを有効にします。"
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
description: "プリロードされたコンテンツを切り替える skype for Business の会議、Outlook の会議出席依頼にファイルまたは添付ファイルを使用する方法を参照してください。 "
ms.openlocfilehash: 33f412388d08d37154c1700a61908e310e9375d3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="a2208-103">オンまたはオフに Outlook を使用して会議のプリロードされたコンテンツを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a2208-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="a2208-p101">コンテンツ、ファイル、または添付ファイルを Outlook 会議出席依頼に Skype for Business Online の会議に接続されているユーザーにプリロードすることができます、オンまたはオフにします。これは、ために、Skype for Business Online を使用しているすべての組織の既定でなっています。表示[する Skype for Business 会議の添付ファイルをプリロード](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)する方法。</span><span class="sxs-lookup"><span data-stu-id="a2208-p101">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off. It's turned on by default for all organizations that are using Skype for Business Online. See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2208-p102">現時点ではありませんコマンドレットの設定]、または_MaxContentStorageMB_と_MaxUploadFileMB_のオンラインの値を表示する Skype for Business Online で利用できます。内部設置型の展開についてはのみです。確認することが重要_MaxContentStorageMB_制限に達した場合や接続されているコンテンツが_MaxUploadFileSizeMB_を超えると、会議にコンテンツをアップロードしません。</span><span class="sxs-lookup"><span data-stu-id="a2208-p102">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_. They are only available for on-premises deployments. It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="a2208-110">使い始めるときに</span><span class="sxs-lookup"><span data-stu-id="a2208-110">To get you started</span></span>

### 

 <span data-ttu-id="a2208-111">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="a2208-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="a2208-112">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="a2208-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a2208-113">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2208-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="a2208-p103">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2208-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="a2208-p104">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a2208-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="a2208-120">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2208-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="a2208-121">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="a2208-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="a2208-122">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="a2208-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a2208-123">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="a2208-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a2208-124">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="a2208-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
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

<span data-ttu-id="a2208-125">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2208-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="a2208-126">オンまたはオフ</span><span class="sxs-lookup"><span data-stu-id="a2208-126">Turning it on or off</span></span>

<span data-ttu-id="a2208-127">Outlook 会議の招待状に Skype for Business Online の会議に接続されているコンテンツを事前にできることが有効で、既定では、会議の内容をプリロードから組織のユーザーを防止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2208-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a2208-128">この設定だけができますオンまたはオフに組織の全体用にします。1 人のユーザーの機能のオンとオフを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2208-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="a2208-129">**オフにするにはを Windows PowerShell を開き、次の操作します。**</span><span class="sxs-lookup"><span data-stu-id="a2208-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="a2208-130">**操作に戻り、Windows PowerShell を開いていることを有効にして、次の操作を行う場合**</span><span class="sxs-lookup"><span data-stu-id="a2208-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a2208-131">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="a2208-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="a2208-p105">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2208-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a2208-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a2208-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a2208-136">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="a2208-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a2208-p106">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="a2208-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a2208-139">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="a2208-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a2208-140">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="a2208-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a2208-141">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="a2208-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a2208-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a2208-142">Related topics</span></span>
[<span data-ttu-id="a2208-143">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a2208-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a2208-144">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a2208-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
