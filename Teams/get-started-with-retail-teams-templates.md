---
title: リテールでのチーム テンプレートの使用
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、チーム テンプレートを使用して小売業者のニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684555"
---
# <a name="create-a-team-using-retail-team-templates"></a>リテール チーム テンプレートを使用してチームを作成する

Microsoft チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。

チーム テンプレートには、小売業者のニーズを中心に設計されたチーム構造の事前構築された定義があります。 チーム テンプレートを使用すると、小売業者にとってうまく機能するチームの種類をすばやく作成し、組織全体に展開できます。 また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。

この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。

この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。 組織内に Teams サービスがすでに展開されています。 展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。

チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates.md)。

| 名前 | 使用する方法: |
| ---- | --------- |
| 管理者と IT プロフェッショナル | [管理センター Teamsを使用して](#use-the-team-templates-in-the-teams-admin-center)、リテール チーム テンプレートに基づいてチームを作成します。|
| 開発者およびシステム インテグレーター | [Microsoft Graphを使用](#use-the-team-templates-with-the-microsoft-graph)して、リテール チーム テンプレートに基づいてチームを作成します。 |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>管理センターでチーム テンプレートTeams使用する

### <a name="organize-a-store"></a>店舗を整理する

小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。 追加のアプリケーションを統合して、シフトの開始と終了のプロセスを合理化します。

| 基本テンプレートの種類 |baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|店舗を整理する|`retailStore`|チャネル: <ul><li>全般<li>シフトのハンドオフ</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>マネージャー コラボレーション

マネージャー コラボレーション テンプレートは、複数のマネージャーが複数の店舗/地域間で共同作業を行うチームを作成する場合に最適です。たとえば、組織にリージョンがある場合は、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべてのストア マネージャーをその地域の地域マネージャーと共に含める場合があります。

| 基本テンプレートの種類| baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|- |----------------------------------------------------- |
|小売業 - マネージャー コラボレーション|`retailManagerCollaboration` |チャネル: <ul><li>全般<li>操作</li><li>学習</li></ul> アプリ: <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Microsoft アカウントでチーム テンプレートを使用Graph

### <a name="store-template"></a>店舗テンプレート

店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。 店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| チャネル <ul><li>シフト ハンドオフ\*</li><li>学習\*</li></ul>\*自動的にお気に入りに登録されたチャネル<br><br>チームのプロパティ <ul><li>チームの可視性を公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成/更新/削除できません </li><li>アプリを追加/削除できません </li><li>タブを作成/更新/削除できません</li><li>コネクタを作成/更新/削除できません</li><ul>|
||||

組織の店舗テンプレートをカスタマイズするための推奨される方法:

- 組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。 チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。

- 組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。 手順については [、「チーム テンプレートの使用」](get-started-with-teams-templates.md) を参照してください。

### <a name="manager-collaboration-template"></a>マネージャー コラボレーションのテンプレート

マネージャー コラボレーション テンプレートは、小売業者のニーズを中心に設計されたチーム テンプレートの 1 つです。 マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。 たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>操作\*</li><li>学習\*</li></ul>\*自動的にお気に入りに登録されたチャネル<br><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成/更新/削除できます </li><li>アプリを追加/削除できます </li><li>タブを作成/更新/削除できます</li><li>コネクタを作成/更新/削除できます</li><ul>|
||||

組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:

- 組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。 手順については、Microsoft チーム テンプレート [のドキュメント](get-started-with-teams-templates.md) を参照してください。

## <a name="how-to-use-first-party-templates"></a>ファースト パーティ テンプレートの使い方

これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。  チーム テンプレートをデプロイする方法の詳細については、チームの作成方法に関する Microsoft Graph記事[を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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
