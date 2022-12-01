---
title: Teams ネイティブ ファイルアップロード ポリシーをオフにする
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: PowerShell を使用して Teams ファイル ポリシーを作成、設定、割り当て、調整する方法について説明します。
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198529"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Teams ネイティブ ファイルアップロード ポリシーをオフにする

Microsoft Teams では、OneDrive と SharePoint を使用してコンテンツを保存および共有しますが、一部の組織やユーザーはサード パーティのストレージ プロバイダーを使用することを好む場合があります。  

組織がコンテンツ ストレージのサード パーティを選択した場合は、Teams Files ポリシーのパラメーターを `NativeFileEntryPoints` オフにする必要があります。 このパラメーターは既定で有効になっており、OneDrive または SharePoint から Teams チャットまたはチャネルにコンテンツをアップロードするオプションが表示されます。

この記事では、PowerShell を使用してパラメーターを `NativeFileEntryPoints` 作成、設定、割り当て、削除するのに役立ちます。

>[!NOTE]
>Teams ファイル ポリシーがオフの場合、ユーザーには Teams の OneDrive と SharePoint のアクセス ポイントは表示されませんが、新しいチームとチャネルの作成によって、一致する SharePoint ライブラリの生成が引き続きトリガーされます。

## <a name="prepare-to-update-the-teams-files-policy"></a>Teams ファイル ポリシーの更新を準備する

### <a name="set-up-microsoft-powershell"></a>PowerShell Microsoft設定する

現時点では、このポリシーは Teams 管理センターでは変更できません。 組織の Microsoft 365 テナント管理者は、この記事で後述する PowerShell コマンドレットを使用して変更を行う必要があります。

PowerShell ギャラリーを使用して PowerShell Teams モジュールをインストールする方法については、「Microsoft [Teams PowerShell モジュールのインストール」を](teams-powershell-install.md)参照してください。

Teams PowerShell モジュールをインストールまたはダウンロードするには、「Microsoft [Teams のPowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)」を参照してください。

Teams 管理用の PowerShell を設定する方法の詳細については、「Microsoft [Teams PowerShell を使用して Teams を管理](teams-powershell-managing-teams.md)する」を参照してください。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Teams 管理 センターでサード パーティ製アプリを許可する

この手順は Teams Files ポリシーを変更する必要はありませんが、ユーザーの Teams エクスペリエンスにサード パーティのストレージ プロバイダーを統合する準備ができたら必要です。

Microsoft 365 テナント管理者は、Teams 管理センターで "サード パーティ製アプリを許可する" ポリシーを有効にする必要があります。

サード パーティ製アプリまたはカスタム アプリを許可する方法については、「[Microsoft Teams 管理センターでアプリを管理する](/microsoftteams/manage-apps#manage-org-wide-app-settings)」の「組織全体のアプリ設定を管理する」を参照してください。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>テナント全体の NativeFileEntryPoints をオフにする

パラメーターを `-Identity` に `Global` 設定すると、組織内のすべてのユーザーにポリシー設定が適用されます。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>テナント全体の PowerShell ポリシー コマンドレットのサンプル

このサンプル PowerShell コマンドでは、テナント全体の`NativeFileEntryPoints` パラメーターを に `Disabled` 設定します。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>テナントの状態を確認する  

テナントの Teams Files ポリシーの現在の状態を表示するには、コマンドレットを `Get-CsTeamsFilesPolicy` 使用します。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>ネイティブ ファイルアップロードポイントをオンまたはオフにする

テナント全体のネイティブ ファイル アップロード ポイントをオンまたはオフにするには、パラメーターを `NativeFileEntryPoints` または `Disabled`に`Enabled`設定します。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>ユーザーのポリシーを削除する

ユーザーの Teams Files ポリシーを削除するには、 コマンドレットを `Remove-CsTeamsFilesPolicy` 使用します。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>特定のユーザーの NativeFileEntryPoints をオフにする

また、新しい Teams Files ポリシー文字列を作成し、新しく作成したポリシーをユーザーに割り当てることで、特定のユーザーの Teams ファイル ポリシー `-Identity` を更新することもできます。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定のユーザーの PowerShell ポリシー コマンドレットのサンプル

このサンプル PowerShell コマンドは、 という名前`UserPolicy`の パラメーターを `-Identity` に設定して、新しい `CsTeamsFilesPolicy` を`NativeFileEntryPoints``Disabled`作成します。

を使用してユーザーが `CsTeamsFilesPolicy` 割り当てられると `-Identity UserPolicy`、ネイティブ ファイル エントリ ポイントはオフになります。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>ユーザーにポリシーを割り当てる

新しいポリシーを作成したら、コマンドレットを使用してそのポリシーをユーザーに `Grant-CsTeamsFilesPolicy` 割り当てることができます。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>ポリシーを更新する

新しい Teams ファイル ポリシー `UserPolicy`の設定を変更する必要がある場合は、 コマンドレットを `Set-CsTeamsFilePolicy` 使用します。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>ユーザーの完全な一覧のポリシーを削除する

Teams Files ポリシーに割り当てられているすべてのユーザーからポリシー `UserPolicy`を削除するには、 コマンドレットを `Remove-CsTeamsFilesPolicy` 使用します。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> ポリシーを変更したら、ユーザーの Teams クライアントに変更を表示するには、最大 12 時間を許可します。
