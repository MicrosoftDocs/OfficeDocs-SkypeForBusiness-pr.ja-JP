---
title: Skype for Business Online Connector モジュールをダウンロードしてインストールする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
- PowerShell
description: Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097203"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="b99e3-103">Teams PowerShell モジュールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="b99e3-103">Download and install the Teams PowerShell module</span></span>

> [!NOTE]

> <span data-ttu-id="b99e3-104">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) パブリック リリースは、Skype for Business Online Connector と統合され、Teams と Skype for Business オンライン PowerShell 管理用の 1 つのモジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="b99e3-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="b99e3-105">Teams [PowerShell モジュールをインストールします](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="b99e3-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="b99e3-106">コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b99e3-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="b99e3-107">Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b99e3-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b99e3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="b99e3-108">Related topics</span></span>
[<span data-ttu-id="b99e3-109">Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b99e3-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)