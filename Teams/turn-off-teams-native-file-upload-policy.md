---
title: ネイティブ ファイルTeamsポリシーをアップロードする
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: PowerShell を使用してファイル ポリシーの作成、設定、割り当Teams調整する方法について説明します。
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
# <a name="turn-off-teams-native-file-upload-policy"></a>ネイティブ ファイルTeamsポリシーをアップロードする

Microsoft Teams OneDrive SharePoint (ODSP) を使用してコンテンツを保存および共有しますが、一部の組織やユーザーはサード パーティのストレージ プロバイダーを使用することを好む場合があります。  

組織でコンテンツ ストレージのサード パーティを選択している場合は、[ファイルの管理] ポリシーでパラメーター ``NativeFileEntryPoints`` Teams必要があります。 このパラメーターは既定で有効になっています。ODSP から他のチャットまたはチャネルにコンテンツをアップロードTeamsオプションが表示されます。

この記事では、PowerShell を使用してパラメーターを作成、設定、割り当て、 ``NativeFileEntryPoints`` 削除する方法について説明します。

>[!NOTE]
>Teams Files ポリシーをオフにすると、Teams の OneDrive と SharePoint (ODSP) のアクセス ポイントはユーザーに表示されますが、新しいチームとチャネルの作成によって、一致する SharePoint ライブラリの生成がトリガーされます。

## <a name="prepare-to-update-the-teams-files-policy"></a>ファイル ポリシーの更新Teams準備する

### <a name="set-up-microsoft-powershell"></a>Microsoft PowerShell を設定する

現在、このポリシーは管理センターのTeamsできません。 組織のテナント管理者Microsoft 365、この記事で後で詳しく説明する PowerShell コマンドレットを使用して変更を加える必要があります。

PowerShell ギャラリーを使用して PowerShell Teams モジュールをインストールする方法については、「PowerShell モジュールのインストール[」Microsoft Teams覧ください](teams-powershell-install.md)。

PowerShell モジュールをインストールまたはダウンロードTeams、PowerShell Gallery for Microsoft Teams を[参照してください](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)。

管理用に PowerShell を設定する方法の詳細については、「Teams PowerShell を使用した管理[Teams」Microsoft Teams参照してください](teams-powershell-managing-teams.md)。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>管理センターでサード パーティ製Teamsを許可する

Teams Files ポリシーを変更するには、この手順は必要ありませんが、サード パーティのストレージ プロバイダーをユーザーの Teams エクスペリエンスに統合する準備が整っている場合に必要です。

テナントMicrosoft 365管理者は、管理センターで [サード パーティ製アプリを許可する] Teams必要があります。

サード パーティまたはカスタム アプリを許可する方法については、「管理管理センターでアプリを管理する」の「組織全体のアプリ設定を管理するMicrosoft Teams[参照してください](/microsoftteams/manage-apps#manage-org-wide-app-settings)。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>テナント全体の NativeFileEntryPoints をオフにする

パラメーターを ``-Identity`` に設定 ``Global`` すると、組織のすべてのユーザーにポリシー設定が適用されます。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>テナント全体のサンプル PowerShell ポリシー コマンドレット

このサンプル PowerShell コマンドは、テナント全体 ``NativeFileEntryPoints`` の ``Disabled`` パラメーターを に設定します。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>テナントの状態を確認する  

テナントの [ファイル] ポリシーの現在の状態Teamsコマンドレットを使用 ``Get-CsTeamsFilesPolicy`` します。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>ネイティブ ファイルのアップロード ポイントをオンまたはオフにする

テナント全体のネイティブ ファイル アップロード ポイントを有効またはオフにする場合は、 パラメーターを または ``NativeFileEntryPoints`` に設定 ``Enabled`` します ``Disabled`` 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>ユーザーのポリシーを削除する

ユーザーの Teams Files ポリシーを削除するには、 コマンドレットを使用 ``Remove-CsTeamsFilesPolicy`` します。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>特定のユーザーの NativeFileEntryPoints をオフにする

新しい Teams Files ポリシー文字列を作成し、新しく作成したポリシーをユーザーに割り当てると、特定のユーザーの Teams Files ポリシー ``-Identity`` を更新することもできます。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定のユーザー用のサンプル PowerShell ポリシー コマンドレット

このサンプル PowerShell コマンドは、 という名前の 新しい を作成 ``CsTeamsFilesPolicy`` ``-Identity`` し、 パラメーターを ``UserPolicy`` ``NativeFileEntryPoints`` に設定します ``Disabled`` 。

を使用してユーザーが割 ``CsTeamsFilesPolicy`` り当 ``-Identity UserPolicy`` てられると、ネイティブ ファイルエントリ ポイントはオフになります。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>ユーザーにポリシーを割り当てる

新しいポリシーを作成したら、 コマンドレットを使用して、そのポリシーをユーザーに割り当 ``Grant-CsTeamsFilesPolicy`` てできます。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>ポリシーを更新する

新しいファイル ポリシーの設定を変更する必要Teamsコマンドレット ``UserPolicy`` を使用 ``Set-CsTeamsFilePolicy`` します。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>ユーザーの完全な一覧のポリシーを削除する

Teams Files ポリシー に割り当てられているすべてのユーザーからポリシーを削除するには、 ``UserPolicy`` コマンドレットを使用 ``Remove-CsTeamsFilesPolicy`` します。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> ポリシーに変更を加えた後、変更がユーザーのクライアントに表示されるのに最大 12 時間Teamsします。
