---
title: TeamsのLoop コンポーネントの概要
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: TeamsでLoop コンポーネントを管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088583"
---
# <a name="overview-of-loop-components-in-teams"></a>TeamsのLoop コンポーネントの概要

Teams チャットのLoop コンポーネントは、アイデアを作成し、一緒に意思決定を行う新しい方法を提供します。 コンポーネント (テーブル、タスク リスト、段落など) を送信します。ここで、チャット内のすべてのユーザーがインラインで編集でき、加えられた変更を確認できます。 

> [!Note]
> Loop コンポーネントは、[Microsoft Loop アプリ](https://www.microsoft.com/en-us/microsoft-loop)の最初の機能であり、Teamsで使用できるようになります。 

**一緒にタスクを迅速に実行します。** 議題をクラウドソースにしたり、グループのアクションアイテムを追跡したり、まとめてメモを取ったりします。 これらは、Loop コンポーネントを使用して簡単に行えるいくつかのシナリオに過ぎません。

**コンポーネントを共有します。** このリリースでは、Loop コンポーネントをさまざまなTeams チャットに共有できます。 受信者はどこからでも編集でき、変更が行われた場所に関係なく、更新プログラムを即座に表示できます。

**チャットで開始し、そこからビルドします。** Teams チャットから作成するすべてのコンポーネントは、OneDriveのファイルに自動的に保存されます。 そのため、チャットで共同作業を開始した後、ファイルに移動し、編集用の視覚的な領域が広がり、必要な数のコンポーネントを追加できます。

TeamsのLoop コンポーネントの管理者設定については、「SharePoint[でLoop コンポーネントを管理する](/sharepoint/manage-loop-components)」を参照してください。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

Windows、Mac、Linux、iOS、Android上のTeams アプリで利用できます。

## <a name="loop-components-and-fluid-files"></a>Loop コンポーネントと .fluid ファイル

Teamsで作成されたLoop コンポーネントは、作成者のOneDriveに格納されている .fluid ファイルによってバックアップされます。 OneDriveファイルであるということは、ユーザーがOfficeドキュメントと同じくらい簡単にLoopコンポーネント (.fluid ファイル) を作成、検出、管理できることを意味します。 

## <a name="how-are-fluid--files-stored"></a>.fluid ファイルはどのように保存されますか?

.fluid ファイルは、Office.com やOneDrive (最近使用したファイルや推奨された領域など) に表示されます。 ユーザーは、Office.com およびOneDriveから .fluid ファイル内のコンテンツを検索できます。 .fluid ファイルは、OneDriveから以前のバージョンに復元できます。 Loop コンポーネントを作成するには、チャット参加者がOneDrive アカウントを持っている必要があります。 有効なOneDrive アカウントがない場合でも、チャット参加者は、有効なOneDrive アカウントを持っているが、独自のアカウントを作成できない他のユーザーによって作成されたコンポーネントで共同作業できる場合があります。 

.fluid ファイルをOneDriveからSharePoint サイトに移動すると、ライブ コンポーネントがチャットに読み込まれTeams。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>ファイルの所有者が会社を離れた場合はどうなりますか?

OneDriveアイテム保持ポリシーは、ユーザーによって作成された他のコンテンツと同様に、.fluid ファイルに適用されます。

## <a name="how-are-fluid-files-shared"></a>.fluid ファイルはどのように共有されますか?

Loopコンポーネントは、Teams チャットに挿入することも、あるチャットから別のチャットにコピーすることもできます。 (Loop コンポーネントはチャネルではまだサポートされていません。)既定では組織の既存のアクセス許可が使用されますが、ユーザーは送信前にアクセス許可を変更して、すべてのユーザーがアクセス権を持っていることを確認できます。

Office.com でTeams チャットからコンポーネントを開くと、他のOfficeドキュメントで提供される共有オプションと同様に、ウィンドウの上部に共有機能が提供されます。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>.fluid ファイルが破損または破損した場合はどうなりますか?

バージョン履歴を使用すると、以前のバージョンのファイルを確認してコピーできます。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>.fluid ファイルを開いて編集できるアプリは何ですか?

.fluid ファイルは、ブラウザー (Office.com など) のリンクとして、およびチャットのLoopコンポーネントとしてのみ開Teams。 ダウンロードした場合は、最初にOneDriveまたはSharePointにアップロードしないと、再び開く必要があります。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid ファイルは電子情報開示をサポートしていますか?

.fluid ファイルは検出可能ですが、電子情報開示ワークフローのサポートは限られています。 現在、.fluid ファイルは作成者のOneDriveに格納され、電子情報開示 (Standard) と電子情報開示 (プレミアム) の両方で検索と収集に使用できます。 ただし、プレビューではレンダリングされず、レビュー用のエクスポート形式は既存のツールでは使用できません。 エクスポートされたコンテンツを表示するには、OneDriveにアップロードします。 必要に応じて、[設定管理](/sharepoint/manage-loop-components#settings-management)セクションで説明されているように、これらのエクスペリエンスを一時的に無効にすることができます。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>管理者スイッチからLoopが無効になっている場合、ユーザー エクスペリエンスはどうなりますか?

[設定管理](/sharepoint/manage-loop-components#settings-management)セクションで説明されているようにこれらのエクスペリエンスを無効にすると、次のエクスペリエンスの変更が適用されます。

- メッセージング内の作成/挿入エントリ ポイントTeams非表示になります。 ユーザーは新しい .fluid ファイルを作成できません。
- 以前は対話型のLoop コンポーネントとしてレンダリングされた既存のメッセージは、代わりにハイパーリンク "Loop コンポーネント" としてレンダリングされます。 Teams内に対話型コンテンツは表示されません。
- エンド ユーザーが "Loop コンポーネント" ハイパーリンクをクリックするか、OneDrive for Businessの .fluid ファイルを参照して開くと、別のブラウザー タブでファイルが開きますが、エンド ユーザーはファイルを編集できません。

## <a name="known-issues"></a>既知の問題

- AndroidでTeamsを使用している場合、チャット内のLoopコンポーネントをOffice アプリ経由で編集することはできません。
- テナントの既定のファイルのアクセス許可が *特定のユーザー* (ユーザーが指定したユーザーのみ) に設定され、コンポーネントの作成時に送信者が [アクセス許可] ダイアログの *[特定のユーザー* ] リストから一部のユーザーを削除した場合、それらのユーザーは引き続きコンテンツにアクセスできます。
- テナントの既定のファイルアクセス許可が *[特定のユーザー* ] に設定されている場合 (ユーザーが指定したユーザーのみ)、ライブ コンポーネントへのリンクをコピーし、別のチャットで貼り付ける場合は、送信者がアクセス許可ダイアログを使用し、[特定のユーザー] オプションで受信者を追加して適切にアクセスを許可する必要があります。
- テナントの既定のファイルアクセス許可が *[特定のユーザー* ] に設定されている場合 (ユーザーが指定したユーザーのみ)、20 人を超えるメンバーを含むグループ チャットでライブ コンポーネントを作成するには、送信者がコンポーネントのアクセス許可オプションを手動で選択する必要があります。
- Teams検索でLoopコンポーネントを検索すると、チャット メッセージ自体ではなく、office.com 内のコンポーネントへのリンクが返されます。
- フェデレーション チャットでは、Loop コンポーネントは無効になっています。
- B2B ゲストは、Company Share Link を介して共有されているライブ コンポーネントで共同作業することはできません。 **このチャットに現在参加しているユーザーに** アクセス許可を設定して、B2B ゲストとコンポーネントを共有します。
- Loop コンポーネントは、Teams チャネルではサポートされていません。
- チャットのLoop コンポーネントは、ファイルが別のライブラリに移動された場合にのみ読み込まれません。 ファイルが別のフォルダーに移動された場合、チャットで読み込み続けます。
