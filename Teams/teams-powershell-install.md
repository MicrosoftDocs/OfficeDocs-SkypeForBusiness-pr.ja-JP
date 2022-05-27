---
title: PowerShell Microsoft Teamsインストールする
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell コントロールを使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682008"
---
# <a name="install-microsoft-teams-powershell-module"></a>PowerShell モジュールMicrosoft Teamsインストールする

この記事では、PowerShell ギャラリーを使用してMicrosoft Teams PowerShell モジュールをインストールする方法について説明します。 Microsoft Teams PowerShell モジュールは、すべてのWindows プラットフォームでサポートされています。 Mac と Linux はサポートされていません。

## <a name="requirements"></a>要件

PowerShell モジュールMicrosoft Teams、すべてのプラットフォームで PowerShell 5.1 以降が必要です。 オペレーティング システムで使用できる [最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。

PowerShell のバージョンを確認するには、PowerShell セッション内から次のコマンドを実行します。

```powershell
$PSVersionTable.PSVersion
```

Install-Module コマンドレットを使用して、Microsoft Teams PowerShell モジュールをインストールすることをお勧めします。

PowerShell ギャラリー (PSGallery) が **PowerShellGet** の信頼済みリポジトリとして構成されていない場合は、PSGallery を初めて使用すると、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

インストールを続行するには、[ **はい]** または **[はい] を [すべて** ] に応答します。

## <a name="installing-using-the-powershellgallery"></a>PowerShellGallery を使用したインストール

Microsoft Teams PowerShell モジュールは、Windowsで PowerShell 5.1 で使用するために現在サポートされています。 モジュールをインストールするには、次の手順に従います。

- [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell) に更新します。 バージョン 1607 以降Windows 10している場合は、PowerShell 5.1 が既にインストールされています。
- [.NET Framework 4.7.2](/dotnet/framework/install) 以降をインストールします。
- 次のコマンドを実行して、最新の PowerShellGet をインストールします。

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Teams PowerShell モジュールをインストールします。

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>オフライン インストール

一部の環境では、PowerShell ギャラリーに接続できません。 このような状況では、これらの [手動インストール手順](https://aka.ms/psgallery-manualdownload)に従ってください。

## <a name="sign-in"></a>サインイン

Microsoft Teams PowerShell モジュールの操作を開始するには、Azure 資格情報を使用してサインインします。

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>PowerShell モジュールTeams更新する

PowerShell モジュールを更新するには、モジュールのインストールに使用するのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用していた場合は、 [Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> PowerShell Teams既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再度開きます。

## <a name="uninstall-teams-powershell"></a>PowerShell Teamsアンインストールする

PowerShell Microsoft Teamsアンインストールするには、新しい PowerShell コマンド プロンプトを開き、次のコマンドを実行します。

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>次のステップ

これで、Microsoft Teams PowerShell を使用してMicrosoft Teamsを管理する準備が整いました。 Teams [PowerShell を使用したTeamsの管理](teams-powershell-managing-teams.md)を開始する方法に関する説明を参照してください。

## <a name="related-topics"></a>関連項目

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro)
