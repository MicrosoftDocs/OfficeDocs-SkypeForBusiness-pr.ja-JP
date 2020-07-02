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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944110"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell をインストールする

この記事では、 [PowerShellGet](/powershell/scripting/gallery/installing-psget)を使って Microsoft Teams PowerShell モジュールをインストールする方法について説明します。 これらの手順は、 [Azure Cloud Shell](/azure/cloud-shell/overview)、Linux、MacOS、Windows プラットフォームで動作します。

## <a name="requirements"></a>要件

Teams PowerShell は、すべてのプラットフォームで PowerShell 6.2.4 以降で動作します。 また、Windows の PowerShell 5.1 でもサポートされています。 使用しているオペレーティングシステムに対応した[最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell)をインストールします。 PowerShell 6.2.4 以降で実行する場合、Teams PowerShell には追加要件はありません。

> [!WARNING]
> PowerShell 7 と Teams PowerShell について、既知の問題があります。 最適なエクスペリエンスを実現するには、PowerShell 5.1 を使用することをお勧めします。

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell モジュールをインストールする

> [!NOTE]
> 最適なエクスペリエンスを実現するには、一般的な可用性 (GA) とパブリックプレビューモジュールのどちらも使用してください。 共同作業を目的としているわけではありません。


**PowerShellGet**コマンドレットを使用して Teams PowerShell モジュールをインストールします。 システム上のすべてのユーザー用にモジュールをインストールするには、管理者特権が必要です。 Windows の [**管理者として実行**] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。

```powershell
Install-Module MicrosoftTeams
```

既定では、PowerShell ギャラリー (PSGallery) は、 **PowerShellGet**用の信頼できるリポジトリとして構成されていません。 初めて PSGallery を使用するときは、次のメッセージが表示されます。

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

応答 `Yes` `Yes to All` するか、インストールを続行します。


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell パブリックプレビューをインストールする

> [!NOTE]
> Teams PowerShell のパブリックプレビュー版を使用している場合は、まず Skype for Business Online Connector をアンインストールすることを強くお勧めします。

システム上のすべてのユーザー用に Teams PowerShell パブリックプレビューモジュールをインストールするには、管理者特権が必要です。 Windows の [**管理者として実行**] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。

PowerShell 5.1 を使用している場合は、 **PowerShellGet**モジュールを事前に更新する必要があります。 **PowerShellGet**を更新したら、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の**PowerShellGet**が読み込まれていることを確認します。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams Powershell パブリックプレビューをインストールするには、次の PowerShell コマンドを実行します。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>Skype for Business Online Connector をインストールする

> [!WARNING]
> Skype for Business Online Connector は現在、Teams PowerShell パブリックプレビューに含まれています。 この機能を Teams PowerShell の GA リリースにロールアウトすると、Skype for Business Online Connector は利用できなくなります。

[Skype For Business PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、PowerShell で次のように実行します。

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>サインイン

Teams PowerShell の使用を開始するには、Azure の資格情報を使用してサインインします。

> [!NOTE]
> 最新の[Teams PowerShell パブリックプレビューリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell の更新

Teams PowerShell を更新するには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。 PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。


## <a name="uninstall-teams-powershell"></a>Teams PowerShell をアンインストールする



Teams PowerShell をアンインストールするには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。 PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。

## <a name="next-steps"></a>次の手順

これで、Teams PowerShell を使用してチームを管理する準備が整いました。 始めるには、「 [Teams PowerShell で teams を管理](teams-powershell-managing-teams.md)する」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams PowerShell を使用してチームを管理する](teams-powershell-managing-teams.md)

[Teams PowerShell リリースノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
