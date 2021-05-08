---
title: カスタム チーム テンプレートを作成する Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: カスタム チーム テンプレートを作成する方法については、Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08dba2975886b117fcc45058c98d33aa7cde4565
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506737"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>カスタム チーム テンプレートを作成する Microsoft Teams

**カスタム テンプレートは、EDU のお客様にはまだサポートされていません。**

カスタム チーム テンプレートは、チャネル、タブ、アプリのセットを含む定義済みのチーム構造です。 適切なコラボレーション スペースをすばやく作成するのに役立つテンプレートを開発できます。 カスタム チーム テンプレートでは、お好みの設定を使用します。  

使用を開始するには:

1. Teams 管理センターにサインインします。

2. 左側のナビゲーションで、[チーム テンプレート **] Teams**  >  **展開します**。

3. **[追加]** を選択します。

    ![[追加] が強調表示された [チーム テンプレート] ダイアログの画像。](media/team-templates-new.png)

4. [ **チーム テンプレート] セクションで、[** 新しいテンプレート **の作成] を選択します**。

5. [テンプレートの **設定] セクション** で、次のフィールドに入力し、[次へ] を **選択します**。
    - テンプレート名
    - テンプレートの短い説明と長い説明
    - ロケールの可視性  

    ![チーム テンプレートの設定の名前付けダイアログの画像。](media/template-add-a-name.png)

6. [チャネル **、タブ、アプリ] セクションで** 、チームに必要なチャネルとアプリを追加します。

    1. [チャネル] **セクションで** 、[追加] を **選択します**。
    2. [追加 **] ダイアログ** で、チャネルに名前を付きます。
    3. 説明を追加します。
    4. チャネルを既定で表示する必要がある場合に決定します。
    5. チャネルに追加するアプリ名を検索します。
    6. 完了したら **、[適用** ] を選択します。

    ![チーム テンプレートのチャネル、タブ、アプリ画面の画像。](media/template-channels-tabs-apps.png)

8. 完了したら **、[送信** ] を選択します。

新しいテンプレートが [チーム テンプレート] **の一覧に表示** されます。 テンプレートを使用して、チームを作成し、Teams。

> [!Note]
> チーム ユーザーがギャラリーにカスタム テンプレートを表示するには、最大で 24 時間かかる場合があります。

## <a name="customizing-website-tab-apps"></a>Web サイト タブ アプリのカスタマイズ

> [!Note]
> この機能は早期プレビュー段階です

カスタム チーム テンプレートでは、チャネルの Web サイト タブの URL を指定できます。 テンプレートを使用してチームを作成するエンド ユーザーには、指定したサイト URL にプリセットされた Web サイト タブが表示されます。

使用を開始するには:

1. 新しいチーム テンプレートを作成するか、既存のチーム テンプレートを編集します。

2. [チャネル] セクションで、新しいチャネルを追加するか、既存のチャネルを選択し、[編集] を **選択します**。

3. [この **テンプレート用のアプリを追加する] セクションで** 、Web サイト アプリを追加します。

    ![このテンプレート オプションのアプリを追加する](media/add-an-app-template.png)

4. 編集アイコンを選択し、選択した URL を入力します。

    ![アプリの URL を追加する](media/add-url-app-template.png)

5. タブ アプリ **の** 編集で [保存] を選択し、[適用 **] を選択して** 変更を保存します。

## <a name="known-issues"></a>既知の問題

**問題**: 追加のカスタム タブを含むカスタム テンプレートからチームを作成した場合、カスタム タブ アプリの代に空白のタブが表示される場合があります。 既定のタブ **([投稿]、[****ファイル]、****および [Wiki]** など) が期待通り表示されます。

**解決策**: この問題を解決するには、カスタム タブを削除し、同じアプリで新しいタブを追加します。 カスタム タブを削除して新しいタブを追加するアクセス許可を持たなかった場合は、チームの所有者に問い合わせてください。

現在、カスタム テンプレートから作成された将来のチームの修正に取り組み中です。

**問題**: ブラウザーでTeamsを使用している場合、一部の Web サイトでは、一部の Web サイトが [Teamsされます。

![ブラウザーのエラー メッセージ](media/browser-error-message.png)

**解決策**: [Web サイト] タブの内容の表示に問題がある場合は、別の Web ページでタブを開くか、代わりにデスクトップ アプリで Teams を開き、Web サイト タブ アプリを表示します。

## <a name="related-topics"></a>関連トピック

- [管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
