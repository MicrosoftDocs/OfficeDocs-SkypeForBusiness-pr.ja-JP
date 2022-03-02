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
ms.openlocfilehash: 3f9ca97a0088c703dc482d69406a9e9c2c8b2a22
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043375"
---
# <a name="overview-of-loop-components-in-teams"></a>ループ コンポーネントの概要 (Teams

チャット内のループ コンポーネントTeams、一緒にアイデアを作成し、決定を下す新しい方法を提供します。 表、タスク リスト、段落などのコンポーネントを送信します。このコンポーネントでは、チャット内のすべてのユーザーがインラインで編集を行い、変更内容を確認できます。 

> [!Note]
> ループ コンポーネントは、Microsoft Loop アプリの最初[の機能です](https://www.microsoft.com/en-us/microsoft-loop)。この機能は、Teams。 

**一緒にタスクを迅速に完了します。** 議題を集め、グループのアクション アイテムを追跡したり、まとめてメモを取る。 これらは、ループ コンポーネントを使用して簡単に行うシナリオのほんの一部です。

**コンポーネントを共有します。** このリリースでは、ループ コンポーネントをさまざまなチャットにTeamsできます。 受信者は、変更が行われた場所に関係なく、どこからでも編集し、更新をすぐに表示できます。

**チャットを開始し、そこからビルドします。** チャットから作成したコンポーネントTeams、チャット内のファイルに自動的にOneDrive。 そのため、チャットで共同作業を始め、後でファイルに移動すると、編集用の視覚的な領域が広く、必要な数のコンポーネントを追加できます。

ループ コンポーネントの管理設定については、「Teams のループ コンポーネントの管理[」をSharePoint](/sharepoint/manage-loop-components)。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

Teams、Mac、Linux、iOS、および Android Windowsアプリで利用できます。

## <a name="loop-components-and-loop-files"></a>ループ コンポーネントと .loop ファイル

Teamsで作成されたループ コンポーネントは、作成者のファイルに格納されている .loop ファイルによってOneDrive。 ファイルが含OneDrive、ユーザーは任意のドキュメントと同じ方法でループ コンポーネント (.loop ファイル) を簡単に作成、検出、管理Officeします。 .loop ファイルは、電子情報開示、監査、レポート、法的ホールドなど、データ ガバナンス機能を使用します。

## <a name="how-are-loop--files-stored"></a>.loop ファイルの格納方法

.loop ファイルは Office.com および OneDrive に表示されます ([最近使用したファイル] 領域や [推奨] 領域など)。 ユーザーは、.loop ファイル内のコンテンツを Office.com および OneDrive から検索できます。 .loop ファイルは、以前のバージョンから復元OneDrive。 ループ コンポーネントを作成するには、チャット参加者に新しいアカウントOneDriveがあります。 有効な OneDrive アカウントがない場合、チャット参加者は、有効な OneDrive アカウントを持っているが、自分で作成できない他のユーザーによって作成されたコンポーネントで共同作業を行える場合があります。 

.loop ファイルを別のOneDriveサイトSharePoint移動すると、ライブ コンポーネントがチャットに読み込Teamsされます。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>ファイルの所有者が会社を離れる場合は、どうなるでしょうか。

OneDrive保持ポリシーは、ユーザーによって作成された他のコンテンツと同様に 、.loop ファイルに適用されます。

## <a name="how-are-loop-files-shared"></a>.loop ファイルの共有方法

ループ コンポーネントは、チャットに挿入Teams、あるチャットから別のチャットにコピーすることができます。 (ループ コンポーネントはチャネルではまだサポートされていません)。既定では組織の既存のアクセス許可が設定されますが、ユーザーは送信する前にアクセス許可を変更して、すべてのユーザーがアクセス権を持つ必要があります。

Office.com で Teams チャットからコンポーネントを開くには、他の Office ドキュメントで提供される共有オプションと同様に、ウィンドウの上部に共有機能が用意されています。

## <a name="what-if-a-loop-file-becomes-corrupted-or-damaged"></a>.loop ファイルが破損または破損した場合は、どうなるでしょうか。

[バージョン履歴] では、ファイルの以前のバージョンを確認してコピーできます。

## <a name="what-apps-can-open-and-edit-loop-files"></a>.loop ファイルを開いて編集できるアプリ

.loop ファイルは、Office.com などのブラウザーのリンクとして、およびチャット内のループ コンポーネントとしてのみTeamsできます。 ダウンロードした場合は、最初にアプリにアップロードし直さずに再度開OneDriveまたはSharePoint。

## <a name="known-issues"></a>既知の問題

- チャット内のループ コンポーネントは、Android で Office アプリを使用Teamsで編集することはできません。
- テナントの既定のファイルのアクセス許可が [特定のユーザー *] (ユーザー* が指定したユーザーのみ) に設定され、コンポーネントの作成時に送信者が [アクセス許可] ダイアログの [特定のユーザー] リストから一部のユーザーを削除した場合、それらのユーザーは引き続きコンテンツにアクセスできます。
- テナントの既定のファイルアクセス許可が  [特定のユーザー ( ユーザーが指定したユーザーのみ) に設定されている場合、ライブ コンポーネントへのリンクをコピーして別のチャットに貼り付けするには、送信者がアクセス許可ダイアログを使用し、[特定のユーザー] オプションに受信者を追加してアクセス権を適切に付与する必要があります。
- テナントの既定のファイルアクセス許可が  [特定のユーザー ( ユーザーが指定したユーザーのみ) に設定されている場合、20 人を超えるメンバーとグループ チャットでライブ コンポーネントを作成するには、送信者がコンポーネントのアクセス許可オプションを手動で選択する必要があります。
- 検索でループ コンポーネントTeams、チャット メッセージ自体ではなく、office.com 内のコンポーネントへのリンクが返されます。
- フェデレーション チャットでは、ループ コンポーネントが無効になります。
- B2B ゲストは、会社の共有リンクを介して共有されているライブ コンポーネントで共同作業を行う必要があります。 B2B ゲスト **とコンポーネントを共有** するには、このチャットに現在参加しているユーザーにアクセス許可を設定します。
- ループ コンポーネントは、複数のチャネルTeamsされていません。
- チャット内のループ コンポーネントは、ファイルが別のライブラリに移動された場合にのみ読み込む必要があります。 ファイルが別のフォルダーに移動された場合、引き続きチャットに読み込みされます。
