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
ms.openlocfilehash: f3cf6d2e7eb23517477572775e7d18571463957b
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046343"
---
# <a name="use-retail-team-templates"></a>小売業チーム テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

小売業者の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、小売業のニーズに特化して設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、スタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Teams 管理センターでチーム テンプレートを管理](#manage-team-templates-in-the-teams-admin-center)します。チーム テンプレートを表示し、テンプレート ポリシーを適用して、Teams でチームを作成するためにスタッフが使用できるテンプレートを制御します。 |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、次の事前構築済みの小売業チーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

### <a name="organize-a-store"></a>店舗を整理する

小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。 追加のアプリを統合して、シフトの開始と終了のプロセスを合理化します。

| テンプレートの種類 |TemplateId | このテンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|店舗を整理する| `retailStore` |チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>ストアの準備状況<ul><li>検査 &sup1;</li></ul></li><li>学習</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>Shifts</li><li>検査</li></ul>|

&sup1; アプリがタブとしてチャネルに追加されました

### <a name="manager-collaboration"></a>マネージャー コラボレーション

マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域の地域マネージャーに合わせたその地域のすべての店舗マネージャーを含めることができます。

| テンプレートの種類| TemplateId | このテンプレートに含まれるプロパティ |
| ------------------|- |----------------------------------------------------- |
|マネージャー用小売業|`retailManagerCollaboration` |チャネル <ul><li>全般<li>操作<ul><li>タスク (操作タスク) &sup1;</li><li>検査 &sup1;</li></ul></li><li>学習<ul><li>タスク (学習タスク) &sup1;</li></ul></li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>検査</li></ul>|
||||

&sup1; アプリがタブとしてチャネルに追加されました

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

開発者は、Microsoft Graph を使用して、事前構築済みのチーム テンプレートからチームを作成できます。Microsoft Graph でチーム テンプレートを使用する方法の詳細については、「[Microsoft Graph で、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)」、「[Microsoft Teams API の概要](/graph/teams-concept-overview?view=graph-rest-1.0)」、および「[teamsTemplate リソースの種類](/graph/api/resources/teamstemplate?view=graph-rest-1.0)」を参照してください。

こちらに事前構築済みの小売業チーム テンプレートを示します。

### <a name="store"></a>ストア

店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。 店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。

| テンプレートの種類 | TemplateId | テンプレート チャネル |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| チャネル <ul><li>全般</li><li>シフトの引き継ぎ &sup2;</li><li>ストアの準備状況</li><li>学習 &sup2;</li></ul>チームのプロパティ <ul><li>チームの可視性を公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成、更新、削除できません </li><li>アプリを追加、削除できません </li><li>タブを作成、更新または削除できません</li><li>コネクタを作成、更新、削除できません</li><ul>|
||||

&sup2; お気に入りに自動登録されたチャネル

組織の店舗テンプレートをカスタマイズするための推奨される方法:

- 組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。 チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。

- 組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。

### <a name="manager-collaboration"></a>マネージャー コラボレーション

マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域の地域マネージャーに合わせたその地域のすべての店舗マネージャーを含めることができます。

| テンプレートの種類 | TemplateId | テンプレート チャネル |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>全般</li><li>操作 &sup2;</li><li>学習 &sup2;</li></ul>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成、更新、削除できます </li><li>アプリを追加および削除できます </li><li>タブを作成、更新、削除できます</li><li>コネクタを作成、更新、削除できます</li><ul>|
||||

&sup2; お気に入りに自動登録されたチャネル

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

## <a name="related-articles"></a>関連記事

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)