---
title: ループ コンポーネントの概要 (Teams
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
description: ループ コンポーネントを管理する方法については、Teams。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a43ea4c217e09ad4473513fd21e159bd15c89716
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312449"
---
# <a name="overview-of-loop-components-in-teams"></a>ループ コンポーネントの概要 (Teams

チャット内のループ コンポーネントTeams、一緒にアイデアを作成し、決定を下す新しい方法を提供します。 表、タスク リスト、段落などのコンポーネントを送信します。このコンポーネントでは、チャット内のすべてのユーザーがインラインで編集を行い、変更内容を確認できます。 

> [!Note]
> ループ コンポーネントは、Microsoft Loop アプリの最初の機能[で](https://www.microsoft.com/en-us/microsoft-loop)、この機能を使用Teams。 

**一緒にタスクを迅速に完了します。** 議題を集め、グループのアクション アイテムを追跡したり、まとめてメモを取る。 これらは、ループ コンポーネントを使用して簡単に行うシナリオのほんの一部です。

**コンポーネントを共有します。** このリリースでは、ループ コンポーネントをさまざまなチャットTeamsできます。 受信者は、変更が行われた場所に関係なく、どこからでも編集し、更新をすぐに表示できます。

**チャットを開始し、そこからビルドします。** チャットから作成Teamsコンポーネントは、自動的にファイルに保存OneDrive。 そのため、チャットで共同作業を始め、後でファイルに移動すると、編集用の視覚的な領域が広く、必要な数のコンポーネントを追加できます。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

Teams、Mac、Linux、iOS、Android Windowsアプリで利用できます。

## <a name="loop-components-and-fluid-files"></a>ループ コンポーネントと .fluid ファイル

Teamsで作成されたループ コンポーネントは、作成者のファイルに格納されている .fluid ファイルによってOneDrive。 ファイルが含OneDriveは、ユーザーがループ コンポーネント (.fluid ファイル) を他のドキュメントと同様に簡単に作成、検出、管理Officeします。 .fluid ファイルは、電子情報開示、監査、レポート、法的ホールドなど、データ ガバナンス機能を使用します。

## <a name="how-are-fluid--files-stored"></a>.fluid ファイルの格納方法

.fluid ファイルは Office.com および OneDrive に表示されます ([最近使用したファイル] や [推奨] 領域など)。 ユーザーは、.fluid ファイル内のコンテンツを Office.com から検索し、OneDrive。 .fluid ファイルは、以前のバージョンから復元OneDrive。 ループ コンポーネントを作成するには、チャット参加者に新しいアカウントOneDriveがあります。 有効な OneDrive アカウントがない場合、チャット参加者は、有効な OneDrive アカウントを持っているが、自分で作成できない他のユーザーによって作成されたコンポーネントで共同作業を行える場合があります。 

.fluid ファイルを OneDrive サイトSharePoint移動すると、ライブ コンポーネントがチャットに読み込Teamsされます。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>ファイルの所有者が会社を離れる場合は、どうなるでしょうか。

OneDrive保持ポリシーは、ユーザーによって作成された他のコンテンツと同様に 、.fluid ファイルに適用されます。

## <a name="how-are-fluid-files-shared"></a>.fluid ファイルの共有方法

ループ コンポーネントは、チャットに挿入Teams、あるチャットから別のチャットにコピーすることができます。 (ループ コンポーネントはチャネルではまだサポートされていません)。既定では組織の既存のアクセス許可が設定されますが、ユーザーは送信する前にアクセス許可を変更して、すべてのユーザーがアクセス権を持つ必要があります。

Office.com で Teams チャットからコンポーネントを開く場合、他の Office ドキュメントに対して提供される共有オプションと同様に、ウィンドウの上部に共有機能が用意されています。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>.fluid ファイルが破損または破損した場合は、どうなるでしょうか。

[バージョン履歴] では、ファイルの以前のバージョンを確認してコピーできます。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>.fluid ファイルを開いて編集できるアプリ

.fluid ファイルは、Office.com などのブラウザーのリンクとして、およびチャット内のループ コンポーネントとしてのみTeamsできます。 ダウンロードした場合は、最初にアプリにアップロードし直さずに再度開OneDriveまたはSharePoint。

## <a name="known-issues"></a>既知の問題

- チャット内のループ コンポーネントは、Android で Office アプリを使用Teams編集することはできません。
- テナントの既定のファイルのアクセス許可が [特定のユーザー *] (ユーザー* が指定したユーザーのみ) に設定され、コンポーネントの作成時に送信者が [アクセス許可] ダイアログの [特定のユーザー] リストから一部のユーザーを削除した場合、それらのユーザーは引き続きコンテンツにアクセスできます。
- テナントの既定のファイルアクセス許可が  [特定のユーザー ( ユーザーが指定したユーザーのみ) に設定されている場合、ライブ コンポーネントへのリンクをコピーして別のチャットに貼り付けするには、送信者がアクセス許可ダイアログを使用し、[特定のユーザー] オプションに受信者を追加してアクセス権を適切に付与する必要があります。
- テナントの既定のファイルアクセス許可が  [特定のユーザー ( ユーザーが指定したユーザーのみ) に設定されている場合、20 人を超えるメンバーとグループ チャットでライブ コンポーネントを作成するには、送信者がコンポーネントのアクセス許可オプションを手動で選択する必要があります。
- 検索でループ コンポーネントTeams、チャット メッセージ自体ではなく、office.com 内のコンポーネントへのリンクが返されます。
- フェデレーション チャットでは、ループ コンポーネントが無効になります。
- B2B ゲストは、テナントが B2B ゲストがテナント メンバーと同じアクセス レベルを持つ外部アクセス オプションを設定しない限り、組織内の People リンクを介して共有されているライブ コンポーネントで共同作業を行う必要があります。 詳細については、「 [B2B 外部コラボレーション設定を構成する」を参照してください](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings)。
- ループ コンポーネントは、複数のチャネルTeamsされていません。
- チャット内のループ コンポーネントは、ファイルが別のライブラリに移動された場合にのみ読み込む必要があります。 ファイルが別のフォルダーに移動された場合、引き続きチャットに読み込みされます。
