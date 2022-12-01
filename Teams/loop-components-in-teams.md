---
title: Teams のループ コンポーネントの概要
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
description: Teams でループ コンポーネントを管理する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1405464a3eb963d55c357b5fcc165c67a143e5e1
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198549"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams のループ コンポーネントの概要

Teams チャットのループ コンポーネントは、アイデアを作成し、一緒に意思決定を行う新しい方法を提供します。 テーブル、タスク リスト、段落などのコンポーネントを送信します。ここで、チャット内のすべてのユーザーがインラインで編集し、変更内容を確認できます。 

> [!Note]
> ループ コンポーネントは、[Microsoft Loop アプリ](https://www.microsoft.com/en-us/microsoft-loop)の最初の機能であり、Teams で使用できるようになります。 

**一緒にタスクを迅速に完了します。** 議題のクラウド ソース、グループのアクション アイテムの追跡、またはまとめてメモを取ります。 これらは、Loop コンポーネントを使用して簡単に行えるシナリオがいくつかあります。

**コンポーネントを共有します。** このリリースでは、ループ コンポーネントをさまざまな Teams チャットに共有できます。 受信者はどこからでも編集でき、変更が行われた場所に関係なくすぐに更新プログラムを確認できます。

**チャットで開始し、そこからビルドします。** Teams チャットから作成したすべてのコンポーネントは、OneDrive のファイルに自動的に保存されます。 そのため、チャットで共同作業を開始し、後で Office.com 上のファイルに移動します。ここで、編集用のビジュアル領域が大きくなり、必要な数のコンポーネントを追加できます。

Teams のループ コンポーネントの管理設定については、「 [SharePoint でのループ コンポーネントの管理](/sharepoint/manage-loop-components)」を参照してください。

## <a name="clients-and-platforms"></a>クライアントとプラットフォーム

Windows、Mac、Linux、iOS、Android の Teams アプリで使用できます。

## <a name="loop-components-and-fluid-files"></a>ループ コンポーネントと .fluid ファイル

Teams で作成されたループ コンポーネントは、作成者の OneDrive に格納されている .fluid (近い将来に .loop に変更されます) ファイルによってサポートされます。 OneDrive のファイルは、ユーザーが任意の Office ドキュメントと同じくらい簡単にループ コンポーネント (.fluid ファイル) を作成、検出、管理できることを意味します。 

## <a name="how-are-fluid-files-stored"></a>fluid ファイルはどのように保存されますか?

.fluid ファイルは、[最近] 領域や [推奨] 領域など、Office.com と OneDrive に表示されます。 ユーザーは、Office.com と OneDrive から .fluid ファイル内のコンテンツを検索できます。 .fluid ファイルは、OneDrive から以前のバージョンに復元できます。 ループ コンポーネントを作成するには、チャット参加者に OneDrive アカウントが必要です。 有効な OneDrive アカウントがない場合でも、チャット参加者は、有効な OneDrive アカウントを持っていても独自に作成できない他のユーザーによって作成されたコンポーネントで共同作業できる場合があります。 

OneDrive から SharePoint サイトに .fluid ファイルを移動すると、ライブ コンポーネントが Teams チャットに読み込みに失敗します。

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>ファイルの所有者が退職した場合はどうなりますか?

OneDrive アイテム保持ポリシーは、ユーザーによって作成された他のコンテンツと同様に、.fluid ファイルにも適用されます。

## <a name="how-are-fluid-files-shared"></a>fluid ファイルはどのように共有されますか?

ループ コンポーネントは、Teams チャットに挿入することも、あるチャットから別のチャットにコピーすることもできます。 (ループ コンポーネントはチャネルではまだサポートされていません)。既定では組織の既存のアクセス許可になりますが、ユーザーは送信前にアクセス許可を変更して、すべてのユーザーがアクセス権を持っていることを確認できます。

Office.com で Teams チャットからコンポーネントを開くと、他の Office ドキュメントに提供される共有オプションと同様に、ウィンドウの上部に共有機能が提供されます。

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>fluid ファイルが破損または破損した場合はどうなりますか?

バージョン履歴を使用すると、以前のバージョンのファイルを確認、復元、またはコピーできます。

## <a name="what-apps-can-open-and-edit-fluid-files"></a>どのアプリが.fluidファイルを開いて編集することができますか?

.fluid ファイルは、Office.com などのブラウザーのリンクとして、および Teams チャットのループ コンポーネントとしてのみ開くことができます。 ダウンロードした場合、OneDrive または SharePoint に最初にアップロードしないと、もう一度開けなくなります。

## <a name="does-fluid-files-support-ediscovery"></a>.fluid ファイルは電子情報開示をサポートしていますか?

.fluid ファイルは検出可能ですが、電子情報開示ワークフローのサポートは限られています。 現在、.fluid ファイルは作成者の OneDrive に格納され、電子情報開示 (Standard) と電子情報開示 (Premium) の両方で検索と収集に使用できます。 ただし、プレビューではレンダリングされず、レビュー用のエクスポート形式は既存のツールでは使用できません。 エクスポートされたコンテンツを表示するには、それらを任意の OneDrive にアップロードします。 必要に応じて、「 [設定管理」](/sharepoint/manage-loop-components#settings-management) セクションで説明されているように、これらのエクスペリエンスを一時的に無効にすることができます。

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>管理者スイッチからループが無効になっている場合、ユーザー エクスペリエンスは何になりますか?

[[設定管理]](/sharepoint/manage-loop-components#settings-management) セクションで説明されているようにこれらのエクスペリエンスを無効にすると、次のエクスペリエンスの変更が適用されます。

- Teams メッセージング内の作成/挿入エントリ ポイントは非表示になります。 ユーザーは新しい .fluid ファイルを作成できません。
- 以前は対話型のループ コンポーネントとしてレンダリングされた既存のメッセージは、代わりにハイパーリンク "ループ コンポーネント" としてレンダリングされます。 Teams 内に対話型コンテンツは表示されません。
- エンド ユーザーが [ループ コンポーネント] ハイパーリンクをクリックするか、OneDrive for Businessの .fluid ファイルを参照して開くと、別のブラウザー タブでファイルが開きます。エンド ユーザーはファイルを編集できます。

## <a name="known-issues"></a>既知の問題

- テナントの既定のファイルアクセス許可が *[特定のユーザー* ] (ユーザーが指定したユーザーのみ) に設定されている場合、Loop コンポーネントへのリンクをコピーして別のチャットに貼り付ける場合、送信者はアクセス許可ダイアログを使用し、[特定のユーザー] オプションに受信者を追加してアクセス権を適切に付与する必要があります。
- テナントの既定のファイルのアクセス許可が *[特定のユーザー* ( ユーザーが指定したユーザーのみ)] に設定されている場合、20 人以上のメンバーを含むグループ チャットでライブ コンポーネントを作成するには、送信者がコンポーネントのアクセス許可オプションを手動で選択する必要があります。
- Teams 検索でループ コンポーネントを検索すると、チャット メッセージ自体ではなく、office.com 内のコンポーネントへのリンクが返されます。
- フェデレーション チャットではループ コンポーネントが無効になります。
- ゲストは、Company Share Link を介して共有されているライブ コンポーネントで共同作業を行うことができません。 この **チャットで現在People** アクセス許可を設定して、ゲストとコンポーネントを共有します。
- ループ コンポーネントは、Teams チャネルではサポートされていません。
- チャット内のループ コンポーネントは、ファイルが別のライブラリに移動された場合にのみ読み込まれません。 ファイルが別のフォルダーに移動された場合は、引き続きチャットに読み込まれます。
