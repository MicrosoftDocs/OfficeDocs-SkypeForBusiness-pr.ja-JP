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
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238868"
---
# <a name="download-and-install-the-teams-powershell-module"></a>PowerShell モジュールをダウンロードTeamsインストールする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> 最新の[powerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)リリースは Skype for Business Online Connector と統合され、Teams および Skype for Business PowerShell 管理用の 1 つのモジュールが提供されます。


1. [PowerShell モジュール Teamsインストールします](/microsoftteams/teams-powershell-install)。
    
2. コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Windows PowerShell の起動の詳細については、「Connect を 1 つの Windows PowerShell ウィンドウですべての Microsoft 365 または[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)サービスに接続する」または「Windows PowerShell 用にコンピューターをセットアップする」[を参照](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)してください。
  
## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
