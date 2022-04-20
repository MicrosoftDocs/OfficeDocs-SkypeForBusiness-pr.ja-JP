---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976021"
---
1. PowerShell バージョン 7 以降をインストールします。 詳細なガイダンスについては、「[Windowsへの PowerShell のインストール](/powershell/scripting/install/installing-powershell-on-windows)」を参照してください。

1. PowerShell を管理者モードで実行します。
1. Microsoft Graph PowerShell モジュールをインストールします。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    バージョン 1.6.1 以降であることを確認します。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Teams プレビュー PowerShell モジュールをインストールします。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    少なくともバージョン 4.1.0 で、Shifts コネクタコマンドレットが含まれていることを確認します。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. スクリプトの実行時にエラーが発生した場合は、PowerShell を終了するように設定します。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. スクリプトをWindowsで実行できるようにします。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```