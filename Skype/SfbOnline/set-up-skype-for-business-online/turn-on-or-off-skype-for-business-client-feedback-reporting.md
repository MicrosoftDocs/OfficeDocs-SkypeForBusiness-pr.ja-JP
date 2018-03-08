---
title: "無効を切り替える Skype for Business クライアントのフィードバックのレポート"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: "Skype for Business ユーザーがユーザーが問題を報告経験について Microsoft に直接フィードバックを提供できるようにする組み込み Skype for Business アプリのフィードバック ツールを使用することができます。"
ms.openlocfilehash: c60057e2b303fb9265560754fb4bb2643685ac5c
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="a9b2e-103">無効を切り替える Skype for Business クライアントのフィードバックのレポート</span><span class="sxs-lookup"><span data-stu-id="a9b2e-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="a9b2e-104">Skype for Business ユーザーがユーザーが問題を報告経験について Microsoft に直接フィードバックを提供できるようにする組み込み Skype for Business アプリのフィードバック ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-104">You can enable your Skype for Business users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business クライアントのレポートにはします。](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="a9b2e-106">このツールでは、ユーザーは、Microsoft よりを調査して可能性がある問題のトラブルシューティングのために、デバイス上のアプリケーションからログをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business クライアントのレポートにはします。](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="a9b2e-108">ユーザーが自分のフィードバックの一部として、デバイスのスクリーン ショットを含めることができます_EnableOnlineFeedbackScreenshot_設定を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business クライアントのフォームをレポートにはします。](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="a9b2e-p101">アプリのフィードバック ツールによって収集されたログを保存する問題の中には、米国内で最大 90 日間の調査にします。このため、有効にしないでくださいこのフィードバック ツール、組織のデータ保護ポリシーを次に違反している場合。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-p101">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated. Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="a9b2e-112">確認し、Windows PowerShell を起動する.</span><span class="sxs-lookup"><span data-stu-id="a9b2e-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="a9b2e-113">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="a9b2e-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="a9b2e-114">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a9b2e-115">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="a9b2e-p102">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="a9b2e-p103">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="a9b2e-122">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="a9b2e-123">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="a9b2e-123">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="a9b2e-124">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a9b2e-125">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9b2e-126">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```
<span data-ttu-id="a9b2e-127">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="a9b2e-128">組織内のすべてのユーザーに関するレポートのクライアント アプリケーション フィードバックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-128">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="a9b2e-129">フィードバックは、組織のユーザーの報告を有効にし、デバイスのスクリーン ショットを送信できるように、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-129">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
> 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a9b2e-130">Windows PowerShell の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-130">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="a9b2e-p104">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-p104">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a9b2e-134">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a9b2e-134">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a9b2e-135">Office 365 の管理に Windows PowerShell を使用する理由 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="a9b2e-135">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a9b2e-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a9b2e-138">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="a9b2e-138">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a9b2e-139">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="a9b2e-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a9b2e-140">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="a9b2e-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="a9b2e-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a9b2e-141">Related topics</span></span>
[<span data-ttu-id="a9b2e-142">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-142">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a9b2e-143">ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a9b2e-143">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)