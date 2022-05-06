---
title: Microsoft Teamsでカスタム チーム テンプレートを作成する
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teamsでカスタム チーム テンプレートを作成する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fa114e6bc15ff8aeb6d0e75dcb6c0c45871b436
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399551"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Microsoft Teamsでカスタム チーム テンプレートを作成する

**カスタム テンプレートは、EDU のお客様にはまだサポートされていません。**

カスタム チーム テンプレートは、チャネル、タブ、アプリのセットを含む定義済みのチーム構造です。 適切なコラボレーション空間をすばやく作成するのに役立つテンプレートを開発できます。 カスタム チーム テンプレートでは、好みの設定が使用されます。  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


作業を開始するには:

1. Teams 管理センターにサインインします。

2. 左側のナビゲーションで、**Teams** >  **Team テンプレートを展開します**。

3. **[追加]** を選択します。

    ![[追加] が強調表示された [チーム テンプレート] ダイアログの画像。](media/team-templates-new.png)

4. [ **チーム テンプレート** ] セクションで、[ **まったく新しいテンプレートの作成**] を選択します。

5. [ **テンプレートの設定]** セクションで、次のフィールドに入力し、[ **次へ**] を選択します。
    - テンプレート名
    - テンプレートの短い説明と長い説明
    - ロケールの可視性  

    ![チーム テンプレート設定の名前付けダイアログの画像。](media/template-add-a-name.png)

6. [ **チャネル]、[タブ]、[アプリ** ] セクションで、チームが必要とするチャネルとアプリを追加します。

    1. [ **チャネル** ] セクションで、[ **追加**] を選択します。
    2. [ **追加]** ダイアログで、チャネルに名前を付けます。
    3. 説明を追加します。
    4. チャネルを既定で表示するかどうかを決定します。
    5. チャネルに追加するアプリ名を検索します。
    6. [ **完了時に適用]** を選択します。

    ![チーム テンプレートのチャネル、タブ、アプリの画面の画像。](media/template-channels-tabs-apps.png)

8. 完了したら **、[送信] を選択します** 。

新しいテンプレートが **チーム テンプレート** の一覧に表示されます。 テンプレートは、Teamsでチームを作成するために使用できます。

> [!Note]
> Teams ユーザーがギャラリーでカスタム テンプレートの変更を表示するには、最大で 24 時間かかる場合があります。

## <a name="customizing-website-tab-apps"></a>Web サイト タブ アプリのカスタマイズ

> [!Note]
> この機能は早期プレビュー段階です

カスタム チーム テンプレート内のチャネルの Web サイト タブの URL を指定することもできます。 テンプレートを使用してチームを作成するエンド ユーザーには、指定したサイト URL に事前設定された Web サイト タブがあります。

作業を開始するには:

1. 新しいチーム テンプレートを作成するか、既存のチーム テンプレートを編集します。

2. [チャネル] セクションで、新しいチャネルを追加するか、既存のチャネルを選択して **[編集]** を選択します。

3. [ **このテンプレートのアプリの追加]** セクションで、Web サイト アプリを追加します。

    ![このテンプレート オプションのアプリを追加します。](media/add-an-app-template.png)

4. 編集アイコンを選択し、任意の URL を入力します。

    ![アプリの URL を追加します。](media/add-url-app-template.png)

5. タブ アプリの編集に **[保存] を** 選択し、[ **適用** ] を選択して変更を保存します。

## <a name="known-issues"></a>既知の問題

**問題**: 追加のカスタム タブを含むカスタム テンプレートからチームを作成した場合、カスタム タブ アプリの代わりに空白のタブが表示される場合があります。 既定のタブ ( **投稿**、 **ファイル**、 **Wiki** など) は期待どおりに表示されます。

**解決策**: この問題を解決するには、カスタム タブを削除し、同じアプリで新しいタブを追加します。 カスタム タブを削除して新しいタブを追加するアクセス許可がない場合は、チームの所有者にお問い合わせください。

現在、カスタム テンプレートから作成された将来のチームの修正に取り組んでいます。

**問題**: ブラウザーでTeamsを使用している場合、一部の Web サイトでは Teams タブ内でのレンダリングがサポートされていません。

![ブラウザーのエラー メッセージ。](media/browser-error-message.png)

**解決策**: Web サイト タブの内容を表示できない場合は、別の Web ページでタブを開くか、デスクトップ アプリでTeamsを開いて Web サイト タブ アプリを表示するようにリダイレクトされます。

## <a name="related-topics"></a>関連項目

- [管理センターでチーム テンプレートを使用して概要する](get-started-with-teams-templates-in-the-admin-console.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
