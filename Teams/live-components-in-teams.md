---
title: ライブ コンポーネントを管理Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: ライブ コンポーネントを管理する方法については、Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305019"
---
# <a name="manage-live-components-in-teams"></a>ライブ コンポーネントを管理Teams

チャット内のライブ Teamsは、アイデアを作成し、一緒に意思決定を行う新しい方法を提供します。 テーブル、タスク リスト、段落などのコンポーネントを送信します。チャット内のすべてのユーザーがインラインで編集し、変更内容を確認できます。 つまり、会議の開催数を少なくし、長いチャット スレッドの必要性を最小限に抑えながら、チームからアイデアやフィードバックを収集できます。

**一緒にタスクを迅速に完了します。** 議題を集め、グループのアクション アイテムを追跡するか、メモをまとめて取る。 これらは、ライブ コンポーネントを使用して簡単に行うシナリオのほんの一部です。

**コンポーネントを共有します。** このリリースでは、ライブ コンポーネントをさまざまなチャットにTeamsできます。 受信者は、変更が行われた場所に関係なく、どこからでも編集し、更新プログラムを即座に表示できます。 今後のリリースでは、ライブ コンポーネントは、Teams 会議メモとチャネル、Outlook、および最終的にはすべての Microsoft 365 アプリケーションでサポートされます。

**チャットで開始し、そこからビルドします。** チャットから作成Teamsコンポーネントは、自動的にファイルに保存OneDrive。 そのため、チャットで共同作業を開始し、後でファイルに移動し、編集用の視覚的なスペースが大きく、必要な数のコンポーネントを追加できます。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

このアプリTeams Mac、Linux、iOS、および Android Windowsアプリで利用できます。

9 月上旬から、ライブ コンポーネントはグローバルに利用できます。 9 月下旬には、Mod (Government Community Cloud) でGCC。

## <a name="settings-management"></a>設定管理

ライブ コンポーネントは、Microsoft 流動フレームワーク スイートMicrosoft 流動フレームワーク Microsoft 365サポートされ、SharePoint Online から制御され、Teams 管理センターから制御されません。

すべての Fluid Experiences を有効または無効にするには、SharePoint [PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)モジュールの最新バージョンが必要です。Office 365です。 Microsoft 流動フレームワーク対象のリリース **テナントの既定値** は ON です。 ライブ コンポーネントはコラボレーション用に設計されているので、テナントが他のファイルの種類の表示専用に既定に設定されている場合でも、コンポーネントは常に他のユーザーが編集可能として共有されます。 詳細については、 **設定の横** にある [詳細情報] リンクを参照してください。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>オンライン PowerShell コマンドレット流動フレームワークを使用して、SharePointが有効になっているか確認する

1. [Connect PowerShell SharePointをクリックします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. 引数なしで 流動フレームワークコマンドレットを実行して、Get-SPOTenantが有効になっているか確認します。

3. IsFluidEnabled の値が true を確認 **します**。

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>オンライン PowerShell コマンドレット流動フレームワークしてSharePointを有効にする 

1. [Connect PowerShell SharePointをクリックします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. -IsFluidEnabled Set-SPOTenantコマンドレットを使用して Fluid を有効$true 
   
   この変更は、テナント全体で適用される時間が短い場合があります。 

この機能は、デスクトップ、Mac Teams Windows iOS、Android で利用できます。 有効にすると、ユーザーは、これらのクライアントのメッセージ作成エクスペリエンスにライブ コンポーネントを挿入する新しいオプションが表示されます。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>オンライン PowerShell コマンドレット流動フレームワークしてSharePointを無効にする

1. [Connect PowerShell SharePointをクリックします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

2. -IsFluidEnabled Set-SPOTenantコマンドレットをSet-SPOTenantして Fluid を無効$false。 

   この変更は、テナント全体で適用される時間が短い場合があります。 

この機能を再び有効にする必要がある場合は、オンライン PowerShell コマンドレットSharePoint使用できます。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>既知の制限

- アプリの再起動後に最初のコンポーネントとしてテーブルまたはタスク リストを作成Teams時間がかかる場合があります。

- 他のチャット メンバーは、at (@) 記号で言及すると、電子メール通知を受け取ります。 (アクティビティ フィードの通知Teams近日公開されます。

- チャット メッセージ自体ではなく、Teams内でライブ コンポーネントを検索すると、office.com コンポーネントへのリンクが返されます。

- ライブ コンポーネントはフェデレーション チャットで無効になり、Azure B2B を使用してゲスト アカウントを使用する通常のチャットに対して有効になります。

- チャネルや他のアプリでコンポーネントTeams共有Microsoft 365、受信者は現時点でほとんどの場所でリンクを取得します。 インライン編集は、今後のエクスペリエンスの向上に向け計画されています。

## <a name="storage-of-fluid-files"></a>Storageファイル `.fluid` の種類

**どのように `.fluid` 保存されますか?**

作成されたライブ コンポーネントTeams、作成者のファイルに保存されているファイル `.fluid` によってOneDrive for Business。 ファイルは、OneDrive for Businessドキュメントと同じ方法で、ライブ コンポーネント (ファイル) を簡単に作成、検出、 `.fluid` 管理Officeします。

ユーザーは、Office.com および OneDrive for Business からファイル `.fluid` 内のコンテンツを検索できます。
`.fluid` ファイルは、電子情報開示、監査、レポート、法的保持など、データ ガバナンス機能を使用します。

`.fluid`ファイルは、Office.com および OneDrive for Business[最近] や [推奨] 領域など、 に表示されます。
`.fluid`ファイルは、以前のバージョンから復元OneDrive for Business。

チャット参加者は、ライブ コンポーネントをOneDriveアカウントを持っている必要があります。 有効な OneDrive アカウントがない場合、チャット参加者は、有効な OneDrive アカウントを持っているが、自分で作成できない他のユーザーによって作成されたコンポーネントで共同作業を行える場合があります。

[ファイル](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b)を別のOneDriveサイトSharePoint移動すると、ライブ コンポーネントがチャットに読み `.fluid` 込Teamsされます。

**ファイルの所有者が会社を離れる場合は、どうなるでしょうか。**

[OneDrive保持ポリシーは](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)、ユーザーが作成した他のコンテンツと同様にファイル `.fluid` に適用されます。

**ファイルの `.fluid` 共有方法**

ライブ コンポーネントは、チャットに挿入したりTeamsチャットから別のチャットにコピーすることができます。 (ライブ コンポーネントはチャネルでまだサポートされていません)。既定ではテナントの既存のアクセス許可が設定されますが、ユーザーは送信する前にアクセス許可を変更して、すべてのユーザーがアクセス許可を持つ必要があります。

Office.com で Teams チャットからコンポーネントを開く場合は、他のドキュメントで提供される共有オプションと同様に、ウィンドウの上部で共有機能Officeします。

**ファイルが `.fluid` 破損または破損した場合は、**

バージョン履歴を使用すると、以前のバージョンのファイルを確認してコピーできます。

**ファイルを開いて編集できる `.fluid` アプリ**

`.fluid`ファイルは、Office.com などのブラウザーのリンクとして、およびチャットのライブ コンポーネントTeamsできます。 ダウンロードした場合、最初にオンラインまたはオンラインにアップロードし直OneDrive for Business開SharePointできません。
