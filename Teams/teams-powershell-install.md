---
title: Microsoft Teams PowerShell をインストールする
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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824938"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell をインストールする

この記事では [、PowerShellGet](/powershell/scripting/gallery/installing-psget)を使用して Microsoft Teams PowerShell モジュールをインストールする方法について説明します。 以下の手順は [、Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS、および Windows プラットフォームで動作します。

## <a name="requirements"></a>要件

Teams PowerShell を使用するには、すべてのプラットフォームでの PowerShell 5.1 以降が必要です。 使用している [オペレーティング システムで利用可能な最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。

> [!WARNING]
> PowerShell 7 および Teams PowerShell に関して既知の問題があります。 最高の操作性を得るには、PowerShell 5.1 を使用することをお勧めします。

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell モジュールをインストールする

> [!NOTE]
> 最高のエクスペリエンスを得るには、一般向け利用可能 (GA) モジュールまたはパブリック プレビュー モジュール (両方とも) を使用します。 共同作業を行うことをおすすめでした。


**PowerShellGet コマンド**レットを使用して、Teams PowerShell モジュールをインストールします。 システム上のすべてのユーザーのモジュールをインストールするには、電子のアクセス可能なアクセスが必要です。 Windows で管理者として実行するか、macOS または**Run as administrator** `sudo` Linux 上のコマンドを使用します。

```powershell
Install-Module MicrosoftTeams
```

既定では、PowerShell ギャラリー (PSGallery) は **PowerShellGet**の信頼できるリポジトリとして構成されません。 PSGallery を初めて使用する場合、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

インストール **を続** 行するには **、[はい] または [は** い] に答えます。


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell パブリック プレビューをインストールする

> [!NOTE]
> パブリック プレビュー版版の Teams PowerShell を使用している場合は、最初に Skype for Business Online Connector をアンインストールすることを強くお勧めします。

システム上のすべてのユーザーに対して、Teams PowerShell パブリック プレビュー モジュールをインストールするには、電子のアクセス許可が必要です。 Windows で管理者として実行するか、macOS または**Run as administrator** `sudo` Linux 上のコマンドを使用します。

PowerShell 5.1 を使用している場合は **、PowerShellGet** モジュールを前に更新する必要があります。 **PowerShellGet を更新したら、** 管理者向け PowerShell のスケッションを閉じて、再度開き、**最新の PowerShellGet が**読み込れるようにします。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams PowerShell パブリック プレビューをインストールするには、下の PowerShell コマンドを実行します。

> [!NOTE]
> PowerShell ギャラリーまたは [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) で、"Find-Module MicrosoftTeams -AllowPrerelease" を実行して、最新のプレビュー版を確認できます。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Skype for Business Online Connector をインストールする

> [!WARNING]
> Skype for Business Online Connector は、現在、Teams PowerShell パブリック プレビューに含されています。 この機能を Teams PowerShell の GA リリースにロールすると、Skype for Business Online Connector は利用できなくなります。

Skype for [Business PowerShell モジュールをダウンロードして](https://www.microsoft.com/download/details.aspx?id=39366)インストールし、PowerShell で次を実行します。

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>サインイン

Teams PowerShell の使用を開始するには、Azure 資ーデンシャルでサインインします。

> [!NOTE]
> 最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースを使用している場合は、Skype for Business Online Connector をインストールする必要がありません。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell を更新する

Teams PowerShell を更新するには、新しい管理者向け PowerShell コマンド プロンプトを開き、次を実行します。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> PowerShell が既に PowerShell のスケッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じて、新しい、または管理された PowerShell のスケッションを再度開きます。


## <a name="uninstall-teams-powershell"></a>Teams PowerShell をアンインストールする



Teams PowerShell をアンインストールするには、新しい管理者用 PowerShell コマンド プロンプトを開き、次を実行します。

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> PowerShell のスケッションに既にインポートされている Teams の PowerShell がある場合、モジュールをアンインストールすることはできません。 PowerShell を閉じて、新しい、または管理された PowerShell のスケッションを再度開きます。

## <a name="next-steps"></a>次の手順

Teams PowerShell を使用して Teams を管理する準備ができました。 開始 [するには、Teams PowerShell で Teams を](teams-powershell-managing-teams.md) 管理する方法を参照してください。

## <a name="related-topics"></a>関連項目

[Teams PowerShell で Teams を管理する](teams-powershell-managing-teams.md)

[Teams PowerShell リリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
