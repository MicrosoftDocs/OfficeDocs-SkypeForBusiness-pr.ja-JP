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
ms.openlocfilehash: b6ff40e34c6459a75d0b79a8d750902a3457e00d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239110"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="91eae-103">Outlook 会議で使用するコンテンツ プリロードの有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="91eae-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="91eae-104">ユーザーは、Outlook 会議出席依頼に添付されているコンテンツ、ファイル、添付ファイルを Skype for Business Online 会議に事前読み込みできますが、オンまたはオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="91eae-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="91eae-105">この機能は、オンラインで使用しているすべての組織で既定Skype for Businessされます。</span><span class="sxs-lookup"><span data-stu-id="91eae-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="91eae-106">会議の添付ファイル[を事前に読み込むSkype for Business参照してください](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="91eae-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="91eae-107">現在 _、MaxContentStorageMB_ と _MaxUploadFileMB_ のオンライン値を設定または表示Skype for Business Online で使用できるコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="91eae-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="91eae-108">これは、オンプレミス環境でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="91eae-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="91eae-109">添付されたコンテンツが  _MaxUploadFileSizeMB_ を超えた場合、または _MaxContentStorageMB_ の制限に達した場合、コンテンツは会議にアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="91eae-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="91eae-110">使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="91eae-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="91eae-111">スタートWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91eae-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="91eae-112">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="91eae-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="91eae-113">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="91eae-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="91eae-114">[PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="91eae-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="91eae-115">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="91eae-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="91eae-116">Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。</span><span class="sxs-lookup"><span data-stu-id="91eae-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="91eae-117">機能の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="91eae-117">Turning it on or off</span></span>

<span data-ttu-id="91eae-118">Skype for Business Online 会議への Outlook 会議出席依頼に添付されたコンテンツを事前に読み込む機能は既定で有効になっていますが、組織内のユーザーが会議のコンテンツを事前に読み込むのを防ぐ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="91eae-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="91eae-119">この設定は、組織全体でのみ有効または無効にできます。1 人のユーザーに対して有効またはオフにできない。</span><span class="sxs-lookup"><span data-stu-id="91eae-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="91eae-120">**無効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="91eae-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="91eae-121">**再び有効にするには、Windows PowerShell を開いて、次を行います。**</span><span class="sxs-lookup"><span data-stu-id="91eae-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="91eae-122">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="91eae-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="91eae-123">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="91eae-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="91eae-124">Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="91eae-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="91eae-125">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91eae-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="91eae-126">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="91eae-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="91eae-127">アプリを使用して管理や管理をWindows PowerShellする 6 Microsoft 365理由Office 365</span><span class="sxs-lookup"><span data-stu-id="91eae-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="91eae-128">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="91eae-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="91eae-129">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="91eae-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="91eae-130">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="91eae-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="91eae-131">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="91eae-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="91eae-132">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="91eae-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="91eae-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="91eae-133">Related topics</span></span>
[<span data-ttu-id="91eae-134">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="91eae-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="91eae-135">Skype for Business ユーザーが Skype の連絡先を追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="91eae-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
