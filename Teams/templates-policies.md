---
title: 管理センターでチーム テンプレートを管理する
author: serdars
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: 管理センターでチーム テンプレートを管理する方法について説明します
ms.openlocfilehash: 470194c8a31236e5bed000fa2837c9b1fa05003e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401181"
---
# <a name="manage-team-templates-in-the-admin-center"></a>管理センターでチーム テンプレートを管理する

管理センターでテンプレート ポリシーを作成して、エンド ユーザーに表示されるチーム テンプレートを管理します。 各テンプレート ポリシー内で、表示または非表示にするテンプレートを指定できます。
ユーザーが指定したチーム テンプレートのサブセットのみを表示できるように、異なるユーザーを異なるテンプレート ポリシーに割り当てます。

テンプレート ポリシーを管理する方法については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a>テンプレート ポリシーを作成し、使用可能なテンプレートを割り当てる

1. Teams 管理センターにサインインします。

2. **Teams** >  **Templates ポリシーを展開します**。

3. **[追加]** を選択します。

    ![テンプレート ポリシーが選択され、[追加] が強調表示されます。](media/template-policies-1.png)

1. [**テンプレート ポリシー設定**] セクションで、次のフィールドに入力します。

    - テンプレート ポリシー名

    - テンプレート ポリシーの簡単な説明

2. **[表示可能なテンプレート]** テーブルで、非表示にするテンプレートを選択し、[**非表示**] を選択します。

    ![非表示が強調表示されている選択したテンプレート。](media/template-policies-2.png)

    非表示にするように選択したテンプレートは、[ **非表示のテンプレート]** テーブルに表示されます。

1. 特定のテンプレートを再表示するには、[ **非表示のテンプレート** ] テーブルまでスクロールします。

2. 再表示するテンプレートを選択し、[ **表示**] を選択します。

   ![非表示になっていない選択したテンプレート。](media/template-policies-3.png)

   選択したテンプレートが **表示可能なテンプレート** テーブルに表示されます。
3. **[保存]** を選択します。

   新しいテンプレート ポリシーが [ **テンプレート ポリシー** ] の一覧に表示されます。

## <a name="assign-users-to-the-template-policies"></a>テンプレート ポリシーにユーザーを割り当てる

ポリシーに割り当てられたユーザーは、そのポリシー内の表示可能なテンプレートのみを表示できます。

1. **テンプレート ポリシーからポリシー** を選択し、[**ユーザーの管理**] を選択します。

2. このポリシーに割り当てるユーザーを入力します。

   ![ユーザーをテンプレート ポリシーに割り当てます。](media/template-policies-4.png)

3. **[適用]** を選択します。

> [!Note]
> エンド ユーザーが新しいポリシーを有効にするには、最大で 24 時間かかる場合があります。

## <a name="size-limits-for-template-policies"></a>テンプレート ポリシーのサイズ制限

ポリシーごとに最大 100 個のテンプレートを非表示にできます。 指定されたポリシーに既に 100 個のテンプレートが非表示になっている場合、[ **非表示]** ボタンは無効になります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: チーム テンプレート ポリシーにユーザーをバッチ割り当てできますか?**
  
A: はい。PowerShell ではテンプレート ポリシーのバッチ割り当てがサポートされています。 このアクションのポリシーの種類は TeamsTemplatePermissionPolicy です。 [詳細情報](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

**Q: グループをチーム テンプレート ポリシーに割り当てることができますか?**

A: 現在はいいえ。 この機能は今後利用できるようになります。

**Q: 新しいテンプレートが作成された場合、そのテンプレートはポリシーに含まれますか?**

A: 既定では、すべての新しいテンプレートが表示されます。 管理センターの [テンプレート ポリシー] セクションで、テンプレートを非表示にすることができます。

**Q: テンプレートが削除された場合はどうなりますか?**

A: 削除されたテンプレートは、テンプレート ポリシーに存在しなくなります。

**Q: Teams管理センターのテンプレート ポリシーに複数のユーザーを割り当てることはできますか?**

A: はい。

1. 管理センターで、[ユーザー] に移動 **します**。
1. [ユーザー] 一覧テーブルで、特定のテンプレート ポリシーに割り当てるユーザーを選択します。
1. [設定の編集] を選択し、[テンプレート ポリシー] フィールドを変更します。
1. [適用] を選択します。 [詳細情報を参照してください](./assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)。

**Q: 特定のポリシー操作方法割り当てられているすべてのユーザーを表示しますか?**

A: 管理センターで次の手順を実行します。

1. **[ユーザー]** セクションに移動します。
2. [ユーザー] 一覧テーブルでフィルターを選択し、チーム テンプレート ポリシーのフィルターを選択します。
3. **[適用]** を選択します。

![選択したテンプレート ポリシーとユーザーの表示。](media/template-policies-5.png)

**Q: PowerShell を使用してテンプレート ポリシーを管理できますか?**

A: いいえ。PowerShell でのテンプレートの管理はサポートされていません。

**Q: テンプレート ポリシーは EDU に適用されますか?**

A: いいえ。EDU のテンプレート ポリシーはサポートされていません。

## <a name="related-topics"></a>関連項目

- [管理センターでチーム テンプレートを使用して概要する](./get-started-with-teams-templates-in-the-admin-console.md)

- [カスタム チーム テンプレートを作成する](./create-a-team-template.md)

- [既存のチームからテンプレートを作成する](./create-template-from-existing-team.md)

- [既存のチーム テンプレートからチーム テンプレートを作成する](./create-template-from-existing-template.md)

- [Microsoft Teamsのユーザーにポリシーを割り当てる - Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [Batch でポリシーにユーザーを割り当てる](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
