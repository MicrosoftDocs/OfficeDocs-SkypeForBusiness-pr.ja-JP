---
title: 非営利団体のチーム テンプレートを使用する
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: 非営利団体のスタッフがボランティアの管理アクティビティに関するコミュニケーションや共同作業を行えるよう、ボランティアの管理チーム テンプレートを管理および使用してチームを簡単にすばやく作成する方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f0a6218d9843c0ed99c80c517fe9986f41d79b6
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641347"
---
# <a name="use-nonprofit-team-templates"></a>非営利団体のチーム テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

非営利団体の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、ボランティアの管理アクティビティを効率化するように設計された、ボランティアの管理チーム テンプレートが含まれています。 この事前構築済みのテンプレートを使用してチームをすばやく作成し、スタッフがボランティアの管理タスクとアクティビティに関するコミュニケーションや共同作業を行えるようにします。

この記事では、ボランティアの管理チーム テンプレートと、それを使用してチームを作成する方法について説明します。 この記事では、Teams 管理センターでチーム テンプレートを管理する方法の概要も示します。

## <a name="manage-volunteers-team-template"></a>ボランティアの管理チーム テンプレート

ボランティアの管理タスクとアクティビティに関するコミュニケーションや共同作業が行えるよう、スタッフを集めます。

このテンプレートには、ボランティアの管理アクティビティを効率化するように設計されたチャネルとアプリが含まれています。 スタッフは、オンボード資料や頻繁に使用されるドキュメントを整理および共有したり、レポートを表示したり、チームおよびイベントの重要な最新のアナウンスを把握したりすることなどができます。 また、このテンプレートは、[Microsoft Cloud for Nonprofit](/industry/nonprofit/) を構成するアプリである ["ボランティアの管理"](/dynamics365/industry/nonprofit/volunteer-management-use) と統合されており、これを使用することでスタッフは Teams 内でボランティア エンゲージメントの機会を管理できます。

次に、ボランティアの管理チーム テンプレートに含まれるチャネルとアプリを示します。

| テンプレートの種類 |TemplateId | このテンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|ボランティアの管理| `ManageVolunteers` |チャネル: <ul><li>全般<ul><li>Web サイト&sup1;</li></ul><li>お知らせ</li><li>レポート<ul><li>Power BI&sup1;</li></ul></li><li>ボランティアの管理<ul><li>Power Apps&sup1;</li></ul></li><li>エンゲージメントの機会<ul><li>タスク&sup1;</li></ul></li><li>ボランティア オンボーディング<ul><li>SharePoint&sup1;</li><li>OneNote&sup1;</li></ul></li></ul> アプリ: <ul><li>Web サイト</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>タスク</li><li>SharePoint</li><li>OneNote</li></ul>|

&sup1; アプリがタブとしてチャネルに追加されました。

## <a name="create-a-team-using-the-manage-volunteers-team-template"></a>ボランティアの管理チーム テンプレートを使用してチームを作成する

### <a name="create-the-team"></a>チームを作成する

ボランティアの管理チーム テンプレートからチームを作成するために必要なのは、いくつかのクイック操作だけです。

1. Teams で、**[Teams]** > **[チームに参加または作成する]** > **[チームの作成]** の順に移動します。
2. **[ボランティアの管理]** チーム テンプレートを選択します。
3. プライバシー レベルを選択します:
    - **プライベート**: チームに参加するには、チーム所有者からのアクセス許可が必要です。
    - **パブリック**: 組織内のすべてのユーザーがチームに参加できます。
4. チームに名前を付け、説明を追加します。 チャネルの名前を変更してチームをカスタマイズすることもできます。
5. **[作成]** を選択します。

詳細については、「[チーム テンプレートを使用してチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)」を参照してください。

### <a name="add-the-volunteer-management-app-to-the-power-apps-tab"></a>[Power Apps] タブにボランティアの管理アプリを追加する

Teams でボランティアの管理アプリを使用するには、ボランティアの管理チャネルの [Power Apps] タブに追加します。 

1. Teams で、作成したチームに移動し、ボランティアの管理チャネルを選択してから、**[Power Apps]** タブを選択します。
2. ドロップダウン リストで、**[モデル駆動型アプリ]** を選択してから、**[ボランティアの管理]** を検索して選択します。
3. **[保存]** を選択します。

詳細については、「[モデル駆動型アプリをタブ アプリとして Teams に埋め込む](/powerapps/teams/embed-model-driven-teams-tab)」を参照してください。

## <a name="view-and-manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを表示および管理する

管理者は、Microsoft Teams 管理センターでチーム テンプレートを表示および管理できます。 ボランティアの管理テンプレートを表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

[テンプレート ポリシーを作成してユーザーに割り当て](templates-policies.md)、チームの作成のために Teams で表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

## <a name="related-articles"></a>関連記事

- [Teams のヘルプ ドキュメント](https://support.microsoft.com/teams)
- [Microsoft Cloud for Nonprofit のドキュメント](/industry/nonprofit/)
