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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947568"
---
# <a name="install-microsoft-teams-powershell-module"></a>PowerShell モジュールMicrosoft Teamsインストールする

この記事では、PowerShell ギャラリーを使用して powerShell Microsoft Teamsをインストールする方法について説明します。 PowerShell Microsoft Teamsは、すべてのプラットフォームでWindowsされます。 

## <a name="requirements"></a>要件

Microsoft TeamsPowerShell モジュールには、すべてのプラットフォームで PowerShell 5.1 以上が必要です。 オペレーティング システム [で使用できる最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell)   をインストールします。 

PowerShell のバージョンを確認するには、PowerShell セッション内から次のコマンドを実行します。 

```powershell
$PSVersionTable.PSVersion 
```
PowerShell モジュールのインストールには、Install-Module コマンドレットを使用Microsoft Teamsすることをお勧めします。 
 
PowerShell ギャラリー (PSGallery) が **PowerShellGet** の信頼できるリポジトリとして構成されていない場合は、PSGallery を初めて使用すると、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

[ **はい]** または **[はい] を [すべて** ] に回答して、インストールを続行します。

## <a name="installing-using-the-powershellgallery"></a>PowerShellGallery を使用したインストール

Microsoft TeamsPowerShell モジュールは、現在、PowerShell 5.1 で使用Windows。 モジュールをインストールするには、次の手順に従います。 

- [5.1 Windows PowerShell に更新](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)します。 バージョン 1607 Windows 10を使用している場合は、PowerShell 5.1 が既にインストールされています。 
- [4.7.2 .NET Framework以降をインストール](/dotnet/framework/install)します。 
- 次のコマンドを実行して、最新の PowerShellGet をインストールします。
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- PowerShell モジュールTeamsインストールします。

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>オフライン インストール 

一部の環境では、PowerShell ギャラリーに接続できません。 このような場合は、次の手動インストール [手順に従ってください](https://aka.ms/psgallery-manualdownload)。  

## <a name="sign-in"></a>サインイン

PowerShell モジュールのMicrosoft Teamsするには、Azure 資格情報でサインインします。

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>PowerShell Teams更新

PowerShell モジュールを更新するには、モジュールのインストールに使用したのと同じ方法を使用する必要があります。 たとえば、最初に Install-Module を使用した場合は [、Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> PowerShell Teams PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。


## <a name="uninstall-teams-powershell"></a>PowerShell Teamsアンインストールする

PowerShell をMicrosoft Teamsするには、新しい PowerShell コマンド プロンプトを開き、次のコマンドを実行します。 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>次のステップ 

これで、PowerShell を使用してMicrosoft Teams管理Microsoft Teams準備が整いました。 使用[を開始するにはTeams PowerShell Teamsの管理に関](teams-powershell-managing-teams.md)するページを参照してください。 

## <a name="related-topics"></a>関連項目

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
