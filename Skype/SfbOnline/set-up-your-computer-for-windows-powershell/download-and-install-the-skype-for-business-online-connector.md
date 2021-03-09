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
ms.openlocfilehash: 5883eba8dc4dd959e67e45aa27413624e0f5d941
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568943"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Teams PowerShell モジュールをダウンロードしてインストールする

> [!NOTE]

> 最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) パブリック リリースは、Skype for Business Online Connector と統合され、Teams と Skype for Business オンライン PowerShell 管理用の 1 つのモジュールを提供します。


1. Teams [PowerShell モジュールをインストールします](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Windows PowerShell の起動の詳細については、「1 つの Windows PowerShell ウィンドウで[すべての Microsoft 365 または Office 365](https://technet.microsoft.com/library/dn568015.aspx)サービスに接続する」[](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)または「Windows PowerShell 用にコンピューターをセットアップする」を参照してください。
  
## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell](set-up-your-computer-for-windows-powershell.md)
