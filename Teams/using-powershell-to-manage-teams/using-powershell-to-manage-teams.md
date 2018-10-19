---
title: PowerShell を使用して、チームを管理するには
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: マイクロソフト チームの機能のすべてを管理する Windows PowerShell を使用するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678347"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="d3e1c-103">PowerShell を使用して、チームを管理するには</span><span class="sxs-lookup"><span data-stu-id="d3e1c-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="d3e1c-104">チームの機能は、ビジネス管理センターの PowerShell またはマイクロソフトのチームと Skype を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="d3e1c-105">![メモ]チームの機能のすべては、チームのコネクタ モジュールを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="d3e1c-106">Business connector は、Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="d3e1c-107">[ダウンロードしてインストール、Skype のオンライン ビジネスのコネクタ](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="d3e1c-108">手順 1: 前提条件</span><span class="sxs-lookup"><span data-stu-id="d3e1c-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="d3e1c-109">PowerShell を使用して、マイクロソフトのチームのリモート管理は、次のオペレーティング システムのいずれかの操作を実行している 64 ビット コンピューター上でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="d3e1c-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d3e1c-110">Windows 10</span></span>
- <span data-ttu-id="d3e1c-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d3e1c-111">Windows 8.1</span></span>
- <span data-ttu-id="d3e1c-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="d3e1c-112">Windows 8</span></span> 
- <span data-ttu-id="d3e1c-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d3e1c-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="d3e1c-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d3e1c-114">Windows Server 2012</span></span>
- <span data-ttu-id="d3e1c-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="d3e1c-115">Windows Server 2008</span></span>
- <span data-ttu-id="d3e1c-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d3e1c-116">Windows 7</span></span>
    
<span data-ttu-id="d3e1c-117">サポートされているオペレーティング ・ システムだけでなく、また実行するコンピューター、次の。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="d3e1c-118">PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d3e1c-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="d3e1c-119">チーム PowerShell コネクタ モジュール</span><span class="sxs-lookup"><span data-stu-id="d3e1c-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="d3e1c-120">手順 2: インストールの PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d3e1c-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="d3e1c-121">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="d3e1c-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="d3e1c-122">手順 3: をダウンロードして、チームのコネクタ モジュールをインストール</span><span class="sxs-lookup"><span data-stu-id="d3e1c-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="d3e1c-123">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="d3e1c-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="d3e1c-124">PowerShell のギャラリーを使用してから、最新のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-124">Install the latest module from the PowerShell Gallery using:</span></span> 
  
  <span data-ttu-id="d3e1c-125">インストール モジュール MicrosoftTeams</span><span class="sxs-lookup"><span data-stu-id="d3e1c-125">Install-Module MicrosoftTeams</span></span>

<span data-ttu-id="d3e1c-126">または、詳細については、パッケージを参照してください。https://www.powershellgallery.com/packages/MicrosoftTeams/</span><span class="sxs-lookup"><span data-stu-id="d3e1c-126">Or, for more information, the package can be found here: https://www.powershellgallery.com/packages/MicrosoftTeams/</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="d3e1c-127">手順 4: 接続がチームのコネクタ モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-127">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="d3e1c-128">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="d3e1c-128">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="d3e1c-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d3e1c-129">Related topics</span></span>
- [<span data-ttu-id="d3e1c-130">PowerShell でのチームの機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="d3e1c-130">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)
