---
title: Microsoft Teams でカスタム チーム テンプレートを作成する
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams でカスタム チーム テンプレートを作成する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e017ac0795d2fdd65d89c0532469e8e269ee0e58
ms.sourcegitcommit: e9f8e1a085cbcd2592d3386fdbcfca8a6e032b10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173093"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>Microsoft Teams でカスタム チーム テンプレートを作成する

**EDU ユーザー向けカスタム テンプレートはまだサポートされていません。**

カスタム チーム テンプレートは、チャネル、タブ、アプリのセットを含む定義済みのチーム構造です。 適切なコラボレーション スペースをすばやく作成するのに役立つテンプレートを作成できます。 カスタム チーム テンプレートでは、お好みの設定が使用されます。  

使用を開始するには:

1. Teams 管理センターにログインします。

2. 左側のナビゲーションで **、[Teams** チーム]  >  **テンプレートを展開します**。

3. **[追加]** をクリックします。

![[追加] が強調表示された [チーム テンプレート] ダイアログの画像。](media/team-templates-new.png)

4. [チーム **テンプレート] セクションで** 、[新しい **テンプレートの作成] を選択します**。

5. [テンプレートの **設定] セクションで** 、次のフィールドに入力し、[次へ] を **クリックします**。
    - テンプレート名
    - テンプレートの短い説明と長い説明
    - ロケールの表示  

![チーム テンプレートの設定の名前付けダイアログの画像。](media/template-add-a-name.png)

6. [チャネル **、タブ、アプリ** ] セクションで、チームに必要なチャネルとアプリを追加します。

    1. [チャネル] **セクションで** 、[追加] を **クリックします**。
    2. [追加] **ダイアログ** ボックスで、チャネルに名前を付きます。
    3. 説明を追加します。
    4. チャネルを既定で表示する必要がある場合に決定します。
    5. チャネルに追加するアプリ名を検索します。
    6. 完了 **したら [適用** ] をクリックします。

![チーム テンプレートのチャネル、タブ、アプリの画面の画像。](media/template-channels-tabs-apps.png)

8. 完了したら **[送信** ] をクリックします。

新しいテンプレートがチーム テンプレートの **一覧に表示** されます。 テンプレートを使用して、Teams でチームを作成できます。

> [!Note]
> チーム ユーザーがギャラリーにカスタム テンプレートを表示するには、最大で 24 時間かかる場合があります。

## <a name="known-issues"></a>既知の問題 

**問題**: 追加のカスタム タブを含むカスタム テンプレートからチームを作成した場合、カスタム タブ アプリの代ねに空白のタブが表示される場合があります。 既定のタブ (投稿、ファイル **、Wiki** など) が期待通り表示されます。 

**解決** 方法: この問題を解決するには、カスタム タブを削除し、同じアプリで新しいタブを追加します。 現在、2021/02/08 現在、すべてのカスタム テンプレートの修正に取り組み中です。

## <a name="related-topics"></a>関連トピック

- [管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [既存のチームからテンプレートを作成する](create-template-from-existing-team.md)
- [既存のチーム テンプレートからチーム テンプレートを作成する](create-template-from-existing-template.md)
