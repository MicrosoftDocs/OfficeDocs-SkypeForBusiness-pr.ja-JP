---
title: オフライン メッセージの有効化と無効化 (管理者向け)
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103823"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="fe1c3-103">オフライン メッセージの有効化と無効化 (管理者向け)</span><span class="sxs-lookup"><span data-stu-id="fe1c3-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="fe1c3-p101">[] サインインしていない連絡先にも Skype for Business で IM を送信できるようになりました。これにより、連絡しようとしていることを相手に知らせることができます。相手がオンラインでなくても、メッセージを送ることができます。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="fe1c3-107">オフライン メッセージでは、次のことに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="fe1c3-108">オフライン メッセージはユーザーの受信箱にアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="fe1c3-109">オフライン メッセージがユーザーの受信箱に送信され、ユーザーが Skype for Business にログインすると、受信が通知されます。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="fe1c3-110">メッセージ受信者のステータスが [ **応答不可**] または [ **プレゼンテーション中**] に設定されている場合は、受信者の Skype for Business クライアントから不在着信メッセージが送られます。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="fe1c3-111">詳細については、「[Skype for Business でオフライン メッセージを使う](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="fe1c3-112">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="fe1c3-113">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="fe1c3-114">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="fe1c3-115">Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="fe1c3-116">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="fe1c3-117">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウですべての[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="fe1c3-118">オフライン IM の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="fe1c3-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="fe1c3-119">オフライン メッセージは、最新バージョンのクイック実行 Skype for Business クライアントで **のみ** 使用できます。旧バージョンのクイック実行 Skype for Business を使用している場合や \*.msi ファイルを使用して Skype for Business クライアントをインストールした場合は、使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="fe1c3-120">組織のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="fe1c3-121">既定では、この設定は `True` .</span><span class="sxs-lookup"><span data-stu-id="fe1c3-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="fe1c3-122">この設定をオフにするには、 **Set-CsClientPolicy** コマンドレットを使用して、実行します。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="fe1c3-123">1 人のユーザーのオフラインメッセージの送信を有効または無効にするには、[ _EnableIMAutoArchiving_] を [ `True`] または [ `False`] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="fe1c3-124">既定ではこれは  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="fe1c3-125">既存のポリシーを使用するか、次の例のようなポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fe1c3-126">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="fe1c3-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="fe1c3-127">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fe1c3-128">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="fe1c3-129">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="fe1c3-130">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="fe1c3-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="fe1c3-131">Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由</span><span class="sxs-lookup"><span data-stu-id="fe1c3-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="fe1c3-132">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fe1c3-133">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe1c3-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="fe1c3-134">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fe1c3-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="fe1c3-135">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="fe1c3-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="fe1c3-136">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="fe1c3-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="fe1c3-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe1c3-137">Related topics</span></span>
[<span data-ttu-id="fe1c3-138">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fe1c3-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fe1c3-139">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="fe1c3-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)