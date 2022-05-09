---
title: ネイティブ ファイル アップロード ポリシー Teamsオフにする
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: PowerShell を使用してTeams ファイル ポリシーを作成、設定、割り当て、調整する方法について説明します。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192496"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>ネイティブ ファイル アップロード ポリシー Teamsオフにする

Microsoft TeamsはOneDriveとSharePoint (ODSP) を使用してコンテンツを保存および共有しますが、一部の組織やユーザーはサード パーティのストレージ プロバイダーを使用することを好む場合があります。  

組織がコンテンツ ストレージのサード パーティを選択した場合は、Teams Files ポリシーでパラメーターをオフ``NativeFileEntryPoints``にする必要があります。 このパラメーターは既定で有効になっており、ODSP から Teams チャットまたはチャネルにコンテンツをアップロードするオプションが表示されます。

この記事では、PowerShell を使用してパラメーターを作成、設定、割り当て、削除 ``NativeFileEntryPoints`` する方法について説明します。

>[!NOTE]
>Teams ファイル ポリシーがオフになっていると、ユーザーはTeamsにOneDriveとSharePoint (ODSP) のアクセス ポイントを表示しませんが、新しいチームとチャネルを作成すると、一致するSharePoint ライブラリの生成が引き続きトリガーされます。

## <a name="prepare-to-update-the-teams-files-policy"></a>Teams ファイル ポリシーを更新する準備をする

### <a name="set-up-microsoft-powershell"></a>Microsoft PowerShell を設定する

現在、このポリシーはTeams管理センターでは変更できません。 組織のMicrosoft 365 テナント管理者は、この記事の後半で詳しく説明する PowerShell コマンドレットを使用して変更を加える必要があります。

PowerShell ギャラリーを使用して PowerShell Teams モジュールをインストールする方法については、「[PowerShell モジュールMicrosoft Teamsインストールする」を](teams-powershell-install.md)参照してください。

Teams PowerShell モジュールをインストールまたはダウンロードするには、[Microsoft TeamsのPowerShell ギャラリーに関するページを](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)参照してください。

Teams管理用に PowerShell を設定する方法の詳細については、「Microsoft Teams [PowerShell でTeamsを管理](teams-powershell-managing-teams.md)する」を参照してください。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Teams管理センターでサード パーティ製アプリを許可する

この手順は、Teams ファイル ポリシーを変更する必要はありませんが、サード パーティのストレージ プロバイダーをユーザーのTeams エクスペリエンスに統合する準備ができたら必須です。

Microsoft 365 テナント管理者は、Teams管理センターで "サードパーティアプリを許可する" ポリシーを有効にする必要があります。

サード パーティまたはカスタム アプリを許可する方法については、「[Microsoft Teams管理センターでアプリを管理する」で組織全体のアプリ設定を管理する](/microsoftteams/manage-apps#manage-org-wide-app-settings)方法に関するページを参照してください。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>テナント全体の NativeFileEntryPoints をオフにする

パラメーターを ``-Identity`` 設定すると ``Global`` 、組織内のすべてのユーザーにポリシー設定が適用されます。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>テナント全体の PowerShell ポリシー コマンドレットのサンプル

このサンプル PowerShell コマンドは、テナント全体の``NativeFileEntryPoints`` パラメーターを ``Disabled`` 設定します。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>テナントの状態を確認する  

テナントの Teams ファイル ポリシーの現在の状態を表示するには、コマンドレットを``Get-CsTeamsFilesPolicy``使用します。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>ネイティブ ファイルアップロード ポイントをオンまたはオフにする

テナント全体のネイティブ ファイル アップロード ポイントをオンまたはオフにするには、パラメーターを ``NativeFileEntryPoints`` どちらか ``Enabled`` または両方に設定します ``Disabled``。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>ユーザーのポリシーを削除する

ユーザーの Teams Files ポリシーを削除するには、コマンドレットを``Remove-CsTeamsFilesPolicy``使用します。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>特定のユーザーの NativeFileEntryPoints をオフにする

新しい Teams Files ポリシー文字列を作成し、新しく作成したポリシーをユーザーに割り当てることで、特定のユーザーの Teams ファイル ポリシー``-Identity``を更新することもできます。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定のユーザーの PowerShell ポリシー コマンドレットのサンプル

このサンプル PowerShell コマンドでは、名前付きの名前``UserPolicy``付きの``-Identity``新しい``CsTeamsFilesPolicy``コマンドが作成され、パラメーター``Disabled``は ``NativeFileEntryPoints`` .

ユーザーに with が割り当てられる ``CsTeamsFilesPolicy`` と ``-Identity UserPolicy``、ネイティブ ファイルエントリ ポイントはオフになります。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>ユーザーにポリシーを割り当てる

新しいポリシーを作成したら、コマンドレットを使用してそのポリシーをユーザーに ``Grant-CsTeamsFilesPolicy`` 割り当てることができます。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>ポリシーを更新する

新しいTeams ファイル ポリシー``UserPolicy``の設定を変更する必要がある場合は、コマンドレットを``Set-CsTeamsFilePolicy``使用します。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>ユーザーの完全な一覧のポリシーを削除する

Teams ファイル ポリシーに割り当てられているすべてのユーザーからポリシー``UserPolicy``を削除するには、コマンドレットを``Remove-CsTeamsFilesPolicy``使用します。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> ポリシーを変更したら、ユーザーのTeams クライアントに最大 12 時間の変更が表示されるようにします。
