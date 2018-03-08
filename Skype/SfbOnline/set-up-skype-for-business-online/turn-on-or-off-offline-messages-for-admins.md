---
title: "管理者のオンまたはオフ オフライン メッセージを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: "連絡先が PowerShell を使用してサインインしていないときでも、ビジネスのインスタント メッセージの Skype を送信する方法について説明します。"
ms.openlocfilehash: d75e710f5df8de05dbaba483f11f3e2a1fb4594b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="66f84-103">管理者のオンまたはオフ オフライン メッセージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="66f84-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="66f84-p101">サインインしていない場合でも、連絡先に Im をビジネス用 Skype を送信できます。この機能には、そこに到達する試行されていることを確認、連絡先ことができます。メッセージを送信する前に他のユーザーがオンラインになるまで待つ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66f84-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span> 
  
<span data-ttu-id="66f84-107">オフラインのメッセージの場合に知っておく重要です。</span><span class="sxs-lookup"><span data-stu-id="66f84-107">For Offline messages, it's important to know:</span></span>
  
- <span data-ttu-id="66f84-108">オフラインのメッセージは、ユーザーのメールボックスの整理されません。</span><span class="sxs-lookup"><span data-stu-id="66f84-108">Offline messages won't be archived in the user's mailbox.</span></span>
    
- <span data-ttu-id="66f84-109">オフラインのメッセージは、ユーザーのメールボックスに送信され、ユーザーが skype for Business ログインしたときに通知されます。</span><span class="sxs-lookup"><span data-stu-id="66f84-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>
    
- <span data-ttu-id="66f84-110">**不可]**または [**発表中**にメッセージの受信者の状態を設定している場合、受信者の Skype から for Business クライアント送信される不在着信したメッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="66f84-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>
    
<span data-ttu-id="66f84-111">詳細については、 [Skype for Business で使用がオフラインでメッセージ](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f84-111">For more information, see [Use offline messaging in Skype for Business](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="66f84-112">使い始めるときに</span><span class="sxs-lookup"><span data-stu-id="66f84-112">To get you started</span></span>

### 

 <span data-ttu-id="66f84-113">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="66f84-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="66f84-114">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="66f84-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="66f84-115">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="66f84-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="66f84-p102">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="66f84-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="66f84-p103">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="66f84-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="66f84-122">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f84-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="66f84-123">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="66f84-123">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="66f84-124">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="66f84-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="66f84-125">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="66f84-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66f84-126">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="66f84-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
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

<span data-ttu-id="66f84-127">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f84-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="66f84-128">またはオフラインで IM をオフにします。</span><span class="sxs-lookup"><span data-stu-id="66f84-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="66f84-129">オフライン メッセージ**だけ**クイック実行の Skype for Business クライアントの最新バージョンで利用できる、以前のクイック実行の Skype for Business を使用または、\*.msi ファイルは、Skype for Business クライアントのインストールに使用したときに使用できません。</span><span class="sxs-lookup"><span data-stu-id="66f84-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>
  
<span data-ttu-id="66f84-p104">オフラインでのメッセージが、組織内のユーザー設定_EnableIMAutoArchiving_オフラインでメッセージを送信を有効または無効にする`True`または`False`します。既定では、この設定は`True`します。</span><span class="sxs-lookup"><span data-stu-id="66f84-p104">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`. By default, this is set to `True`.</span></span>
  
<span data-ttu-id="66f84-132">非表示] に**設定 CsClientPolicy**コマンドレットを使用して、実行します。</span><span class="sxs-lookup"><span data-stu-id="66f84-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="66f84-p105">有効またはユーザーのオフライン メッセージ送信メッセージ オフラインを無効にする] に設定されて_EnableIMAutoArchiving_ `True`または`False`します。既定では、この設定は`True`します。既存のポリシーを使用したり、次の例のように作成できます。</span><span class="sxs-lookup"><span data-stu-id="66f84-p105">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`. By default, this is set to  `True`. You can use an existing policy or create one like the example below.</span></span>
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="66f84-136">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="66f84-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="66f84-p106">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f84-p106">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="66f84-140">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="66f84-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="66f84-141">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="66f84-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="66f84-p107">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="66f84-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="66f84-144">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="66f84-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="66f84-145">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="66f84-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="66f84-146">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="66f84-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="66f84-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="66f84-147">Related topics</span></span>
[<span data-ttu-id="66f84-148">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="66f84-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="66f84-149">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="66f84-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
