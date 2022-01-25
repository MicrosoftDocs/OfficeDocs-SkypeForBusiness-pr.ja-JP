---
title: ライブ コンポーネントを管理Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
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
ms.openlocfilehash: b54ccf83aadcec724d8e54a791770578ef147bbd
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191858"
---
# <a name="manage-live-components-in-teams"></a>ライブ コンポーネントを管理Teams

チャット内のライブ Teamsは、一緒にアイデアを作成し、決定を下す新しい方法を提供します。 表、タスク リスト、段落などのコンポーネントを送信します。このコンポーネントでは、チャット内のすべてのユーザーがインラインで編集し、変更内容を確認できます。 つまり、会議を開催し、長いチャット スレッドの必要性を最小限に抑えながら、チームからアイデアやフィードバックを収集できます。
> [!Note]
> ライブ コンポーネントは、Microsoft Loop アプリの最初[の機能で](https://www.microsoft.com/en-us/microsoft-loop)、Teams。 "Live components" の名前は、2022 年初めに "ループ コンポーネント" に変更される予定です。

**一緒にタスクを迅速に完了します。** 議題を集め、グループのアクション アイテムを追跡したり、まとめてメモを取る。 これらは、ライブ コンポーネントを使用して簡単に行うシナリオのほんの一部です。

**コンポーネントを共有します。** このリリースでは、ライブ コンポーネントをさまざまなチャットにTeamsできます。 受信者は、変更が行われた場所に関係なく、どこからでも編集し、更新をすぐに表示できます。 今後のリリースでは、ライブ コンポーネントは、Teams 会議のノートとチャネル、Outlook、および最終的にはすべての Microsoft 365 アプリケーションでサポートされる予定です。

**チャットを開始し、そこからビルドします。** チャットから作成したコンポーネントTeams、チャット内のファイルに自動的にOneDrive。 そのため、チャットで共同作業を始め、後でファイルに移動すると、編集用の視覚的な領域が広く、必要な数のコンポーネントを追加できます。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

Teams、Mac、Linux、iOS、Android Windows アプリで利用できます。

## <a name="settings-management"></a>設定管理

ライブ コンポーネントは、Microsoft 流動フレームワーク Microsoft 365 スイート全体でサポートされ、SharePoint Online から管理され、管理センターからTeamsされません。

すべての Fluid Experiences を有効または無効にするには、SharePoint [Online PowerShell](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell)モジュールの最新バージョンがOffice 365されます。 Microsoft 流動フレームワーク対象のリリース **テナントの** 既定値は ON です。 ライブ コンポーネントはコラボレーション用に設計されています。テナントが既定で他の種類のファイルの表示専用に設定されている場合でも、コンポーネントは常に他のユーザーが編集可能として共有されます。 詳細については、 **設定の横** にある [詳細情報] リンクを参照してください。

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>SharePoint Online PowerShell コマンドレットを使用して、流動フレームワークが有効になっているか確認する

1. [Connect Online PowerShell SharePointにアクセスします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. 引数なしで 流動フレームワーク コマンドレットを実行して、Get-SPOTenantが有効になっているか確認します。

3. IsFluidEnabled の値が true を確認 **します**。

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>流動フレームワーク Online PowerShell コマンドレットを使用SharePointを有効にする

1. [Connect Online PowerShell SharePointにアクセスします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password)。 

2. -IsFluidEnabled コマンドレットを使用Set-SPOTenant Fluid を有効$true 
   
   この変更は、テナント全体に適用されるのに少し時間がかかる場合があります。 

この機能は、Teams Windows、Mac、iOS、Android で利用できます。 有効にすると、ユーザーには、これらのクライアントのメッセージ作成エクスペリエンスにライブ コンポーネントを挿入する新しいオプションが表示されます。

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>オンライン PowerShell コマンドレット流動フレームワークしてSharePointを無効にする

1. [Connect Online PowerShell SharePointにアクセスします](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

2. -IsFluidEnabled コマンドレットをSet-SPOTenantしてSet-SPOTenant Fluid を無効$false。 

   この変更は、テナント全体に適用されるのに少し時間がかかる場合があります。 

この機能を再び有効にする必要がある場合は、オンライン PowerShell コマンドレットSharePoint使用できます。

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $true
PS C:\\WINDOWS\\system32&gt;
```
## <a name="known-issues"></a>既知の問題

- チャット内のライブ コンポーネントは、Android で Office アプリを使用Teams編集することはできません。

- テナントの既定のファイルアクセス許可が [特定のユーザー ( ユーザーが指定したユーザーのみ **)**] に設定され、コンポーネントの作成時に送信者が [アクセス許可] ダイアログの [特定のユーザー] リストから一部のユーザーを削除した場合、それらのユーザーはコンテンツに引き続きアクセスできます。 この問題は、アクセス許可ダイアログのアクセス管理の制限が原因で、今後のリリースで修正される予定です。

- テナントの条件付きアクセス ポリシー設定でクライアント ネットワークが に接続できない場合、ライブ コンポーネントは、サービスに対するリアルタイムの変更を節約するために期待した通り `https://pushchannel.1drv.ms` 動作しません。

## <a name="known-limitations"></a>既知の制限

- 検索でライブ コンポーネントを検索Teams、チャット メッセージ自体ではなく、office.com 内のコンポーネントへのリンクが返されます。

- フェデレーション チャットでは、ライブ コンポーネントが無効になります。

- B2B ゲストは、B2B ゲストがテナント メンバーと同じアクセス レベルを持つ外部アクセス オプションを設定しない限り、会社の共有リンクを介して共有されているライブ コンポーネントで共同作業を行う必要があります。 詳細については [、「B2B 外部コラボレーション設定を構成する」を参照してください](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings)。

- Teams Web クライアントでは、Live コンポーネントの完全なサポートが間もなく提供される予定です。

- ライブ コンポーネントは、Teams チャネルではサポートされていませんが、チャネル内でのインライン編集は、今後より多くのエクスペリエンスを得る予定です。

- テナントの既定のファイルアクセス許可が [特定のユーザー (ユーザーが指定したユーザーのみ **)**] に設定されている場合、ライブ コンポーネントへのリンクをコピーし、別のチャットに貼り付けするには、送信者がアクセス許可ダイアログを使用し、[特定のユーザー] オプションに受信者を追加してアクセス権を適切に付与する必要があります。

- テナントの既定のファイルアクセス許可が [特定のユーザー (ユーザーが指定したユーザーのみ **)]** に設定されている場合、グループ チャットで 20 を超えるメンバーとライブ コンポーネントを作成するには、送信者がコンポーネントのアクセス許可オプションを手動で選択する必要があります。

- チャット内のライブ コンポーネントは、ファイルが別のライブラリに移動された場合にのみ読み込む必要があります。 ファイルが別のフォルダーに移動された場合、引き続きチャットに読み込みされます。

## <a name="how-to-check-your-tenants-default-file-permissions"></a>テナントの既定のファイルアクセス許可を確認する方法

1. [] をクリック[Microsoft 365 管理センター。](https://admin.microsoft.com/)

2. 左側の [管理センター]**で、[管理** センター] を選択 **SharePoint。**

3. [**ポリシーの**  >  **共有] を** 選択し、[ファイルとフォルダー **のリンク**] で、テナントの既定のファイルアクセス許可を表示します。

## <a name="storage-of-fluid-files"></a>Storageの `.fluid` 種類

**どのように `.fluid` 保存されますか?**

Teamsで作成されたライブ コンポーネントは、作成者のファイルに格納されたファイル `.fluid` によってOneDrive for Business。 ファイルは、OneDrive for Businessドキュメントと同じ方法で、ライブ コンポーネント (ファイル) を簡単に作成、検出、 `.fluid` 管理Officeします。

ユーザーは、Office.com および OneDrive for Business からファイル内 `.fluid` のコンテンツを検索できます。
`.fluid` ファイルは、電子情報開示、監査、レポート、法的ホールドなど、データ ガバナンス機能と機能します。

`.fluid`ファイルが Office.com および OneDrive for Business に表示されます ([最近使用したファイル] 領域や [推奨] 領域など)。
`.fluid`ファイルは、以前のバージョンから復元OneDrive for Business。

チャット参加者は、ライブ コンポーネントをOneDriveアカウントを持っている必要があります。 有効な OneDrive アカウントがない場合、チャット参加者は、有効な OneDrive アカウントを持っているが、自分で作成できない他のユーザーによって作成されたコンポーネントで共同作業を行える場合があります。

[ファイル](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b)を別のOneDriveサイトSharePoint移動すると、ライブ コンポーネントがチャットに読み `.fluid` 込Teamsされます。

**ファイルの所有者が会社を離れる場合は、どうなるでしょうか。**

[OneDrive保持ポリシーは、](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization)ユーザーによって作成された他のコンテンツと同様に `.fluid` 、ファイルに適用されます。

**ファイルの `.fluid` 共有方法**

ライブ コンポーネントは、チャットに挿入Teamsチャットから別のチャットにコピーすることができます。 (ライブ コンポーネントはチャネルではまだサポートされていません)。既定ではテナントの既存のアクセス許可が設定されますが、ユーザーは送信前にアクセス許可を変更して、すべてのユーザーがアクセス権を持つ必要があります。

Office.com で Teams チャットからコンポーネントを開くには、他の Office ドキュメントに対して提供される共有オプションと同様に、ウィンドウの上部に共有機能が用意されています。

**ファイルが `.fluid` 破損または破損した場合は、どうなるでしょうか。**

[バージョン履歴] では、ファイルの以前のバージョンを確認してコピーできます。

**ファイルを開 `.fluid` いて編集できるアプリ**

`.fluid`ファイルは、Office.com などのブラウザーのリンクとして、およびチャット内のライブ コンポーネントとしてのみTeamsできます。 ダウンロードした場合、最初にオンラインまたはオンラインにアップロードし直OneDrive for Business開SharePointできません。
