---
title: 小売業チーム テンプレートを使用する
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: 小売業組織のチームを迅速かつ簡単に作成するために、Teams 管理センターや Microsoft Graph で小売業テンプレートを管理および使用する方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69644ce0261d37fb6a7a5e4270a68fb2a79a7d19
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046917"
---
# <a name="use-retail-team-templates"></a>小売業チーム テンプレートを使用する

## <a name="overview"></a>概要

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

小売業者の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、小売業のニーズに特化して設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、スタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、次の事前構築済みの小売業チーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

> [!NOTE]
> アスタリスク (*) は、テンプレートが *Microsoft 365 接続されたテンプレート* であることを示します。 ユーザーがテンプレートを使用してチームを作成すると、接続された SharePoint テンプレートがサイトとチームに適用されます。 ページ、リスト、Power Platform 統合などの SharePoint コンポーネントは、チームの [全般] チャネルにタブとして自動的に追加され、ピン留めされます。 ユーザーは、Teams 内から直接これらのページとリストを編集できます。
>
> SharePoint テンプレートの詳細については、「 [SharePoint サイト テンプレートの適用とカスタマイズ](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)」を参照してください。

### <a name="manage-a-store"></a>ストアを管理する*

小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。 追加のアプリケーションを統合して、シフトの開始プロセスと終了プロセスを効率化します。

> [!div class="mx-tdBreakAll"]
>| テンプレートの種類 |TemplateId | このテンプレートに含まれるプロパティ |
>| ------------------|-- |----------------------------------------------------- |
>| ストアを管理する| `retailStore` |チャネル: <ul><li>全般<li>Shift ハンドオフ</li><li>ストアの準備状況</li><li>学習</li></ul> アプリ: <ul><li>承認</li><li>検査</li><li>リスト<ul><li>インベントリ リスト</li></ul></li><li>SharePoint ページ<ul><li>ストア</li></ul></li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>マネージャー向けリテール*

一連のマネージャーのチームを作成して、ストアまたはリージョン間で共同作業を行います。 たとえば、組織にリージョンがある場合は、カリフォルニアリージョンのチームを作成し、そのリージョンのすべてのストア マネージャーと、そのリージョンの地域マネージャーを含めることができます。

> [!div class="mx-tdBreakAll"]
>| テンプレートの種類| TemplateId | このテンプレートに含まれるプロパティ |
>| ------------------|- |----------------------------------------------------- |
>| マネージャー向けリテール| `retailManagerCollaboration` |チャネル: <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>承認</li><li>検査</li><li>SharePoint ページ<ul><li>ストア</li></ul></li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

こちらに事前構築済みの小売業チーム テンプレートを示します。

> [!NOTE]
> アスタリスク (*) は、テンプレートが *Microsoft 365 接続されたテンプレート* であることを示します。 ユーザーがテンプレートを使用してチームを作成すると、接続された SharePoint テンプレートがサイトとチームに適用されます。 ページ、リスト、Power Platform 統合などの SharePoint コンポーネントは、チームの [全般] チャネルにタブとして自動的に追加され、ピン留めされます。 ユーザーは、Teams 内から直接これらのページとリストを編集できます。
>
> SharePoint テンプレートの詳細については、「 [SharePoint サイト テンプレートの適用とカスタマイズ](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates)」を参照してください。

### <a name="manage-a-store"></a>ストアを管理する*

このテンプレートを使用して、組織内の各小売店の場所のチームを作成します。

> [!div class="mx-tdBreakAll"]
>| テンプレートの種類 | TemplateId | テンプレート チャネル |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| チャネル <ul><li>全般</li><li>Shift ハンドオフ</li><li>ストアの準備状況</li><li>学習</li></ul>チームのプロパティ <ul><li>チームの可視性を公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成、更新、削除できません </li><li>アプリを追加、削除できません </li><li>タブを作成、更新または削除できません</li><li>コネクタを作成、更新、削除できません</li><ul>|

組織の店舗テンプレートをカスタマイズするための推奨される方法:

- 組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。 チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。

- 組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。

### <a name="retail-for-managers"></a>マネージャー向けリテール*

このテンプレートを使用して、一連のマネージャーが複数のストアまたはリージョンで共同作業するためのチームを作成します。 たとえば、組織にリージョンがある場合は、カリフォルニアリージョンのチームを作成し、そのリージョンのすべてのストア マネージャーと、そのリージョンの地域マネージャーを含めることができます。

> [!div class="mx-tdBreakAll"]
>| テンプレートの種類 | TemplateId | テンプレート チャネル |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 小売業 - <br>マネージャー コラボレーション | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>全般</li><li>操作</li><li>学習</li></ul>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成、更新、削除できます </li><li>アプリを追加および削除できます </li><li>タブを作成、更新、削除できます</li><li>コネクタを作成、更新、削除できます</li><ul>|

組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:

- 組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する方法

これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。  Teams テンプレートを展開する方法の詳細については、「[Teams の作成](/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。

> [!NOTE]
> テンプレートのチャネルは自動的に [全般] タブに作成されます。

### <a name="example-store-template-extension-script"></a>例: 店舗テンプレート拡張スクリプト

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

> [!NOTE]
> Microsoft Graph を使用して、Microsoft 365 接続されたテンプレートを使用して既存の Microsoft 365 グループまたはチームからチームを作成する場合、接続された SharePoint テンプレートはサイトまたはチームに自動的に適用されません。 チームの作成後に SharePoint サイト テンプレートを手動で適用する必要があります。 Teams で、チームに移動し、右上隅の **[その他のオプション** ] > **SharePoint で開く** を選択します。 次に、[**設定] を** > 選択して **サイト テンプレートを適用** し、対応するサイト テンプレートを選択します。

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)