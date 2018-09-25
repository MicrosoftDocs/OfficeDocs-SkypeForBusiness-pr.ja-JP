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
ms.openlocfilehash: 0daff64e5a0f6f876de4adb7b60d913fbcce78cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016078"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="dd4ca-103">PowerShell を使用して、チームを管理するには</span><span class="sxs-lookup"><span data-stu-id="dd4ca-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="dd4ca-104">チームの機能は、ビジネス管理センターの PowerShell またはマイクロソフトのチームと Skype を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="dd4ca-105">![メモ]チームの機能のすべては、チームのコネクタ モジュールを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="dd4ca-106">Business connector は、Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="dd4ca-107">[ダウンロードしてインストール、Skype のオンライン ビジネスのコネクタ](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="dd4ca-108">手順 1: 前提条件</span><span class="sxs-lookup"><span data-stu-id="dd4ca-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="dd4ca-109">PowerShell を使用して、マイクロソフトのチームのリモート管理は、次のオペレーティング システムのいずれかの操作を実行している 64 ビット コンピューター上でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="dd4ca-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dd4ca-110">Windows 10</span></span>
- <span data-ttu-id="dd4ca-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="dd4ca-111">Windows 8.1</span></span>
- <span data-ttu-id="dd4ca-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dd4ca-112">Windows 8</span></span> 
- <span data-ttu-id="dd4ca-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dd4ca-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="dd4ca-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dd4ca-114">Windows Server 2012</span></span>
- <span data-ttu-id="dd4ca-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="dd4ca-115">Windows Server 2008</span></span>
- <span data-ttu-id="dd4ca-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dd4ca-116">Windows 7</span></span>
    
<span data-ttu-id="dd4ca-117">サポートされているオペレーティング ・ システムだけでなく、また実行するコンピューター、次の。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="dd4ca-118">PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="dd4ca-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="dd4ca-119">チーム PowerShell コネクタ モジュール</span><span class="sxs-lookup"><span data-stu-id="dd4ca-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="dd4ca-120">手順 2: インストールの PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="dd4ca-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="dd4ca-121">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="dd4ca-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="dd4ca-122">手順 3: をダウンロードして、チームのコネクタ モジュールをインストール</span><span class="sxs-lookup"><span data-stu-id="dd4ca-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="dd4ca-123">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="dd4ca-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="dd4ca-124">イザベルからのダウンロード リンクを以下に示します。https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="dd4ca-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="dd4ca-125">手順 4: 接続がチームのコネクタ モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="dd4ca-126">このトピックを使用して、ヘルプを参照</span><span class="sxs-lookup"><span data-stu-id="dd4ca-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="dd4ca-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dd4ca-127">Related topics</span></span>
- [<span data-ttu-id="dd4ca-128">PowerShell でのチームの機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="dd4ca-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)