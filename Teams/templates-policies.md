---
title: 管理Teamsテンプレートを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 管理センターでTeamsテンプレートを管理する方法について説明します
ms.openlocfilehash: db28d1fa3c84210c3f1e2d80e74a59252f922258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093927"
---
# <a name="manage-teams-templates-in-the-admin-center"></a>管理Teamsテンプレートを管理する

管理センター Teamsポリシーを作成して、エンド ユーザーに表示されるテンプレートを管理します。 各テンプレート ポリシー内で、どのテンプレートを表示または非表示にするか指定できます。
異なるユーザーを異なるテンプレート ポリシーに割り当てると、指定したテンプレートのサブセットTeams表示されます。

テンプレート ポリシーを管理する方法については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a>テンプレート ポリシーを作成し、使用可能なテンプレートを割り当てる

1. Teams 管理センターにサインインします。

2. [Teams  >  **ポリシー] を展開します**。

3. **[追加]** を選択します。

    ![テンプレート ポリシーが選択され、[追加] が強調表示されている](media/template-policies-1.png)

1. [テンプレート **ポリシー] セクション設定、** 次のフィールドに入力します。

    - テンプレート ポリシー名

    - テンプレート ポリシーの簡単な説明

2. [表示 **可能なテンプレート] テーブル** で、非表示にするテンプレートを選択し、[非表示] を **選択します**。

    ![非表示が強調表示されている選択したテンプレート](media/template-policies-2.png)

    非表示にしたテンプレートは、[非表示のテンプレート] テーブル **に表示** されます。

1. 特定のテンプレートを再表示するには、[非表示のテンプレート] **テーブルまでスクロール** します。

2. 再表示するテンプレートを選択し、[表示] を **選択します**。

   ![非表示ではない選択したテンプレート](media/template-policies-3.png)

   選択したテンプレートが [表示可能なテンプレート **] テーブルに表示** されます。
3. **[保存]** を選択します。

   新しいテンプレート ポリシーが [テンプレート ポリシー **] の一覧に表示** されます。

## <a name="assign-users-to-the-template-policies"></a>テンプレート ポリシーにユーザーを割り当てる

ポリシーに割り当てられたユーザーは、そのポリシー内の表示可能なテンプレートのみを表示できます。

1. [ **テンプレート ポリシー] からポリシー** を選択し、[ユーザーの管理] **を選択します**。

2. このポリシーに割り当てるユーザーを入力します。

   ![テンプレート ポリシーにユーザーを割り当てる](media/template-policies-4.png)

3. **[適用]** を選択します。

> [!Note]
> 新しいポリシーがエンド ユーザーに対して有効になるには、最大で 24 時間かかる場合があります。

## <a name="size-limits-for-template-policies"></a>テンプレート ポリシーのサイズ制限

ポリシーごとに最大 100 のテンプレートを非表示にできます。 特定 **のポリシー** で既に 100 のテンプレートが非表示になっている場合、[非表示] ボタンは無効になります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: チーム テンプレート ポリシーにユーザーをバッチ割り当てできますか。**
  
A: はい。PowerShell ではテンプレート ポリシーのバッチ割り当てがサポートされています。 このアクションのポリシーの種類は TeamsTemplatePermissionPolicy です。 [詳細情報](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

**Q: グループはチーム テンプレート ポリシーに割り当てることができますか。**

A: 現在いいえ。 この機能は、今後利用できる予定です。

**Q: 新しいテンプレートが作成された場合、テンプレートはポリシーに含まれますか。**

A: 新しいテンプレートは既定で表示されます。 管理センターの [テンプレート ポリシー] セクションでテンプレートを非表示にできます。

**Q: テンプレートが削除された場合は、どうなるでしょうか。**

A: 削除されたテンプレートは、テンプレート ポリシーに存在しなくなりました。

**Q: 管理センターで複数のユーザーをテンプレート ポリシーに割り当Teamsできますか。**

A: はい。

1. 管理センターで、[ユーザー] に **移動します**。
1. [ユーザー] リスト テーブルで、特定のテンプレート ポリシーに割り当てるユーザーを選択します。
1. [設定の編集] を選択し、[テンプレート ポリシー] フィールドを変更します。
1. [適用] を選択します。
   詳細については[、「Microsoft Docs でポリシーをユーザーに割り当Microsoft Teams - \| Microsoft Teams」を参照してください](./assign-policies.md#assign-a-policy-to-a-batch-of-users)。

**Q: 特定のポリシーに割り当てられているすべてのユーザーを表示する方法**

A: 管理センターで、次の方法を実行します。

1. [ユーザー] **セクションに移動** します。
2. [ユーザー] リスト テーブルでフィルターを選択し、Teams テンプレート ポリシーをフィルター処理します。
3. **[適用]** を選択します。

![選択したテンプレート ポリシーとユーザーの表示](media/template-policies-5.png)

**Q: PowerShell を使用してテンプレート ポリシーを管理できますか。**

A: いいえ、PowerShell でのテンプレートの管理はサポートされていません。

**Q: テンプレート ポリシーは EDU に適用されますか。**

A: いいえ、EDU のテンプレート ポリシーはサポートされていません。

## <a name="related-topics"></a>関連トピック

- [管理センターでチーム テンプレートの使用を開始する](./get-started-with-teams-templates-in-the-admin-console.md)

- [カスタム チーム テンプレートを作成する](./create-a-team-template.md)

- [既存のチームからテンプレートを作成する](./create-template-from-existing-team.md)

- [既存のチーム テンプレートからチーム テンプレートを作成する](./create-template-from-existing-template.md)

- [Microsoft Docs でポリシーをユーザーに割り当Microsoft Teams - Microsoft Teams \| Microsoft Docs](./assign-policies.md)

- [Batch でユーザーをポリシーに割り当てる](/powershell/module/teams/new-csbatchpolicyassignmentoperation)