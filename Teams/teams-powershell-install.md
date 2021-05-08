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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768343"
---
# <a name="install-microsoft-teams-powershell"></a>PowerShell Microsoft Teamsインストールする

この記事では、PowerShellGet を使用して PowerShell Microsoft Teamsをインストールする[方法について説明します](/powershell/scripting/gallery/installing-psget)。 これらの手順は[、Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS、および Windowsで動作します。

## <a name="requirements"></a>要件

TeamsPowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。 オペレーティング システム [で使用できる最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。

> [!NOTE]
> 最適なエクスペリエンスを得る場合は、PowerShell 5.1 を使用することをお勧めします。

## <a name="install-the-teams-powershell-module"></a>PowerShell モジュールTeamsインストールする

> [!NOTE]
> 最適なエクスペリエンスを得る場合は、一般公開 (GA) モジュールまたはパブリック プレビュー モジュール (両方ではなく) を使用してください。 これらは、一緒に作業することを目的としません。


**PowerShellGet コマンドレットを** 使用して、PowerShell モジュールTeamsインストールします。 システム上のすべてのユーザーに対してモジュールをインストールするには、昇格された特権が必要です。 [管理者として実行]**を使用** して PowerShell Windowsを開始するか、macOS または Linux で `sudo` コマンドを使用します。

```powershell
Install-Module MicrosoftTeams
```

既定では、PowerShell ギャラリー (PSGallery) は **、PowerShellGet** の信頼できるリポジトリとして構成されていません。 PSGallery を初めて使用すると、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

[ **はい]** または **[はい] を [すべて** ] に回答して、インストールを続行します。

## <a name="sign-in"></a>サインイン

PowerShell のTeamsするには、Azure 資格情報でサインインします。

> [!NOTE]
> [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースTeams最新バージョンを使用している場合は、Skype for Business Online Connector をインストールする必要があります。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>MFA と最新の認証を使用してサインインする

 アカウントで多要素認証を使用する場合は、このセクションの手順を使用します。

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>PowerShell Teams更新

PowerShell をTeamsするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次のコマンドを実行します。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> PowerShell Teams PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。


## <a name="uninstall-teams-powershell"></a>PowerShell Teamsアンインストールする

PowerShell をTeamsするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次のコマンドを実行します。

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> PowerShell Teams PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。

## <a name="install-teams-powershell-public-preview"></a>PowerShell Teams プレビューをインストールする

> [!NOTE]
> PowerShell のパブリック プレビュー バージョンを使用している場合は、Teams Online Connector をアンインストールすることを強Skype for Business勧めします。

システム上のすべてのTeams PowerShell パブリック プレビュー モジュールをインストールするには、昇格された特権が必要です。 [管理者として実行]**を使用** して PowerShell セッションをWindows、macOS または Linux で `sudo` コマンドを使用します。

PowerShell 5.1 を使用している場合は、事前に **PowerShellGet モジュールを更新する** 必要があります。 **PowerShellGet を更新した** 後、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の **PowerShellGet** が読み込まれるのを確認します。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

PowerShell パブリック Teamsインストールするには、次の PowerShell コマンドを実行します。

> [!NOTE]
> 最新のプレビュー バージョンは [、PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams) または PowerShell で見つけることができます。"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions" を実行します。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>次のステップ

これで、PowerShell を使用してTeams管理Teams準備が整いました。 使用[を開始するにはTeams PowerShell Teamsの管理に関](teams-powershell-managing-teams.md)するページを参照してください。

## <a name="related-topics"></a>関連トピック

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
