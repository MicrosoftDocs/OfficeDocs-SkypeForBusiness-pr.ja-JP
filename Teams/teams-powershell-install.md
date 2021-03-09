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
ms.openlocfilehash: a99967df019a91460bde5fd4e3e6e7aee15444d3
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569113"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell をインストールする

この記事では [、PowerShellGet](/powershell/scripting/gallery/installing-psget)を使用して Microsoft Teams PowerShell モジュールをインストールする方法について説明します。 これらの手順は [、Azure Cloud Shell、Linux、macOS、Windows](/azure/cloud-shell/overview)プラットフォームで動作します。

## <a name="requirements"></a>要件

Teams PowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。 オペレーティング システム [で利用可能な最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。

> [!WARNING]
> PowerShell 7 および Teams PowerShell には、既知の問題があります。 最適なエクスペリエンスを得る場合は、PowerShell 5.1 を使用することをお勧めします。

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell モジュールをインストールする

> [!NOTE]
> 最適なエクスペリエンスを得る場合は、両方ではなく、一般提供 (GA) モジュールまたはパブリック プレビュー モジュールのいずれかを使用します。 これらは、一緒に作業するつもりではありません。


**PowerShellGet コマンドレットを** 使用して、Teams PowerShell モジュールをインストールします。 システム上のすべてのユーザーにモジュールをインストールするには、管理者特権が必要です。 Windows の管理者として実行を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。

```powershell
Install-Module MicrosoftTeams
```

既定では、PowerShell ギャラリー (PSGallery) は PowerShellGet の信頼できるリポジトリ **として構成されていません**。 PSGallery を初めて使用すると、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

[ **はい]** または **[はい] から [すべて] に回答** して、インストールを続行します。


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell パブリック プレビューをインストールする

> [!NOTE]
> Teams PowerShell のパブリック プレビュー 版を使用している場合は、最初に Skype for Business Online Connector をアンインストールすることを強く推奨します。

システム上のすべてのユーザーに Teams PowerShell パブリック プレビュー モジュールをインストールするには、管理者特権が必要です。 Windows の [管理者として実行] を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。

PowerShell 5.1 を使用している場合は、事前に **PowerShellGet モジュールを** 更新する必要があります。 **PowerShellGet を更新した** 後、昇格された PowerShell セッションを閉じてもう一度開き、最新の **PowerShellGet** が読み込まれるのを確認します。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams PowerShell パブリック プレビューをインストールするには、次の PowerShell コマンドを実行します。

> [!NOTE]
> PowerShell ギャラリーまたは [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) で最新のプレビュー バージョンを見つけるには、"Find-Module MicrosoftTeams -AllowPrerelease" を実行します。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Skype for Business Online Connector をインストールする

> [!NOTE]
>
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
> 最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>サインイン

Teams PowerShell の使用を開始するには、Azure の資格情報でサインインします。

> [!NOTE]
> 最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell を更新する

Teams PowerShell を更新するには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。


## <a name="uninstall-teams-powershell"></a>Teams PowerShell をアンインストールする



Teams PowerShell をアンインストールするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。 PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。

## <a name="next-steps"></a>次の手順

Teams PowerShell を使用して Teams を管理する準備ができました。 使用 [を開始するには、「Teams PowerShell で Teams](teams-powershell-managing-teams.md) を管理する」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams PowerShell での Teams の管理](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
