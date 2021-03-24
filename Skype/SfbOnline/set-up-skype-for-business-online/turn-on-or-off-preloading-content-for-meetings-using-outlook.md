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
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103803"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="42923-103">Outlook 会議で使用するコンテンツ プリロードの有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="42923-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="42923-104">ユーザーは、Skype for Business Online 会議への Outlook 会議出席依頼に添付されているコンテンツ、ファイル、または添付ファイルをプリロードできますが、オンとオフを切り替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="42923-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="42923-105">Skype for Business Online を使用しているすべての組織で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="42923-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="42923-106">[Skype for Business 会議の添付ファイルをプリロードする方法をご覧ください](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="42923-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="42923-107">現在、Skype for Business Online には  _、MaxContentStorageMB_ と _MaxUploadFileMB_ のオンライン値を設定または表示するコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="42923-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="42923-108">これは、オンプレミス環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="42923-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="42923-109">添付されたコンテンツが  _MaxUploadFileSizeMB_ を超える場合、または _MaxContentStorageMB_ の制限に達した場合、コンテンツは会議にアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="42923-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="42923-110">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="42923-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="42923-111">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42923-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="42923-112">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="42923-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="42923-113">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42923-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="42923-114">Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="42923-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="42923-115">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42923-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="42923-116">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42923-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="42923-117">機能の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="42923-117">Turning it on or off</span></span>

<span data-ttu-id="42923-118">Outlook 会議出席依頼に添付されたコンテンツを Skype for Business Online 会議にプリロードできる機能は既定で有効になっていますが、組織内のユーザーが会議にコンテンツをプリロードできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="42923-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="42923-119">この設定は、組織全体でのみ有効または無効にできます。1 人のユーザーに対して有効またはオフにできない。</span><span class="sxs-lookup"><span data-stu-id="42923-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="42923-120">**無効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="42923-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="42923-121">**再び有効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="42923-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="42923-122">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="42923-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="42923-123">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="42923-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="42923-124">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="42923-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="42923-125">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42923-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="42923-126">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="42923-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="42923-127">Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由</span><span class="sxs-lookup"><span data-stu-id="42923-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="42923-128">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="42923-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="42923-129">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="42923-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="42923-130">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="42923-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="42923-131">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="42923-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="42923-132">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="42923-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="42923-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="42923-133">Related topics</span></span>
[<span data-ttu-id="42923-134">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="42923-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="42923-135">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="42923-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
