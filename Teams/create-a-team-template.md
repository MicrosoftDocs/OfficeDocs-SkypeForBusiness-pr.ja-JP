---
title: Microsoft Teams でカスタム チーム テンプレートを作成する
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: aaglick
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams でカスタム チーム テンプレートを作成する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c99fc2ebedac1372beff283ccbcf057c0bfdf78b
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198519"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Microsoft Teams でカスタム チーム テンプレートを作成する

**カスタム テンプレートは、EDU のお客様向けにはまだサポートされていません。**

カスタム チーム テンプレートは、チャネル、タブ、アプリのセットを含む定義済みのチーム構造です。 適切なコラボレーション 空間をすばやく作成するのに役立つテンプレートを開発できます。 カスタム チーム テンプレートでは、お好みの設定が使用されます。  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


作業を開始するには:

1. Teams 管理センターにサインインします。

2. 左側のナビゲーションで、[**Teams チーム** >  テンプレート] を展開 **します**。

3. **[追加]** を選択します。

    ![[追加] が強調表示されている [チーム テンプレート] ダイアログの画像。](media/team-templates-new.png)

4. [ **チーム テンプレート** ] セクションで、[ **新しいテンプレートの作成**] を選択します。

5. [ **テンプレートの設定** ] セクションで、次のフィールドに入力し、[ **次へ**] を選択します。
    - テンプレート名
    - テンプレートの短い説明と長い説明
    - ロケールの可視性  

    ![[Team templates settings naming]\(チーム テンプレート設定の名前付け\) ダイアログの画像。](media/template-add-a-name.png)

6. [ **チャネル、タブ、アプリ** ] セクションで、チームに必要なチャネルとアプリを追加します。

    1. [ **チャネル** ] セクションで、[ **追加**] を選択します。
    2. [ **追加** ] ダイアログで、チャネルに名前を付けます。
    3. 説明を追加します。
    4. チャネルを既定で表示するかどうかを決定します。
    5. チャネルに追加するアプリ名を検索します。
    6. 完了したら、[ **適用] を** 選択します。

    ![チーム テンプレートのチャネル、タブ、アプリ画面の画像。](media/template-channels-tabs-apps.png)

8. 完了したら **[送信] を選択します** 。

新しいテンプレートが **[チーム テンプレート** ] の一覧に表示されます。 テンプレートを使用して、Teams でチームを作成できます。

> [!Note]
> チーム ユーザーがギャラリーでカスタム テンプレートの変更を確認するには、最大で 24 時間かかることがあります。

## <a name="customizing-website-tab-apps"></a>Web サイト タブ アプリのカスタマイズ

> [!Note]
> この機能は早期プレビュー段階です

カスタム チーム テンプレート内のチャネルの Web サイト タブの URL を指定することもできます。 テンプレートを使用してチームを作成するエンド ユーザーには、指定したサイト URL に事前設定された Web サイト タブがあります。

作業を開始するには:

1. 新しいチーム テンプレートを作成するか、既存のチーム テンプレートを編集します。

2. [チャネル] セクションで、新しいチャネルを追加するか、既存のチャネルを選択して **[編集**] を選択します。

3. [ **このテンプレートのアプリの追加]** セクションで、Web サイト アプリを追加します。

    ![このテンプレート オプションのアプリを追加します。](media/add-an-app-template.png)

4. 編集アイコンを選択し、任意の URL を入力します。

    ![アプリ URL を追加します。](media/add-url-app-template.png)

5. タブ アプリの編集で **[保存]** を選択し、[ **適用** ] を選択して変更を保存します。

## <a name="known-issues"></a>既知の問題

**問題**: 追加のカスタム タブを含むカスタム テンプレートからチームを作成した場合、カスタム タブ アプリの代わりに空白のタブが表示されることがあります。 既定のタブ ( **投稿**、 **ファイル**、 **Wiki** など) が期待どおりに表示されます。

**解決策**: この問題を解決するには、カスタム タブを削除し、同じアプリで新しいタブを追加します。 カスタム タブを削除して新しいタブを追加するアクセス許可がない場合は、チーム所有者に問い合わせてください。

現在、カスタム テンプレートから作成された将来のチームの修正に取り組んでいます。

**問題**: ブラウザーで Teams を使用する場合、一部の Web サイトでは Teams タブ内でのレンダリングがサポートされていません。

![ブラウザーのエラー メッセージ。](media/browser-error-message.png)

**解決策**: Web サイト タブの内容を表示できない場合は、別の Web ページでタブを開くか、デスクトップ アプリで Teams を開いて Web サイト タブ アプリを表示するようにリダイレクトされます。

## <a name="related-topics"></a>関連項目

- [管理センターでのチーム テンプレートの使用](get-started-with-teams-templates-in-the-admin-console.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
