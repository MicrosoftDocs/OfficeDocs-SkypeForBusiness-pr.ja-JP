---
title: プレリリース版の Teams PowerShell モジュールをインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: PowerShell テストギャラリーからプレリリース版の Teams PowerShell モジュールをインストールするには、次の手順を実行します。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321770"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>プレリリース版の Teams PowerShell モジュールをインストールする

この記事では、 [Powershell テストギャラリー](https://www.poshtestgallery.com/packages/MicrosoftTeams/)から最新のプレリリース版の Teams PowerShell モジュールをインストールする方法について説明します。 Teams の機能を管理するためのコマンドレットは、一般的なバージョンのモジュールでサポートされておらず、プレリリース版でのみ使用できるシナリオでは、プレリリース版の Teams PowerShell モジュールが必要です。

次の手順を使用して、PowerShell テストギャラリーから最新のプレリリース版の Teams PowerShell モジュールをインストールします。

> [!NOTE]
> PowerShell テストギャラリーから、[パブリック Powershell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/)のバージョンのモジュールと共に Teams powershell モジュールをインストールしないでください。 次の手順に従って、最初にパブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールしてから、PowerShell テストギャラリーから最新バージョンのモジュールをインストールします。

1. 既存のすべての PowerShell セッションを終了します。
2. Windows PowerShell モジュールの新しいインスタンスを開始します。
3. パブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールするには、次の操作を実行します。

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 既存のすべての PowerShell セッションを終了します。
5. もう一度 Windows PowerShell モジュールを起動し、次の操作を実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 次の操作を実行して、PowerShell テストギャラリーから最新の Teams PowerShell モジュールをインストールします。

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>PowerShell テストギャラリーから最新バージョンの Teams PowerShell モジュールに更新する

PowerShell テストギャラリーから既に Teams PowerShell モジュールをインストールしている場合は、次の手順を使用して最新バージョンに更新します。

1. 既存のすべての PowerShell セッションを終了します。
2. Windows PowerShell モジュールの新しいインスタンスを開始します。
3. 次の操作を実行して、PowerShell テストギャラリーから現在インストールされている Teams PowerShell モジュールのバージョンを更新します。

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
