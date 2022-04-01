---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593672"
---
1. PowerShell バージョン 7 以降をインストールします。 詳細なガイダンスについては、「[PowerShell](/powershell/scripting/install/installing-powershell-on-windows) のインストール」を参照Windows。

1. 管理者モードで PowerShell を実行します。
1. Microsoft Graph PowerShell モジュールをインストールします。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    バージョン 1.6.1 以降を確認します。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. プレビュー PowerShell Teamsをインストールします。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    バージョン 4.1.0 以上で、Shifts コネクタ コマンドレットが含まれている必要があります。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. MSAL PowerShell モジュールをインストールします。

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. スクリプトの実行中にエラーが発生した場合は、PowerShell を終了に設定します。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. スクリプトをスクリプトで実行Windows。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```