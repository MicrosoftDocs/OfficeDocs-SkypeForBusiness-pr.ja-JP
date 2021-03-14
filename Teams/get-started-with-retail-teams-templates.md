---
title: 小売業の Teams テンプレートの使用を開始する
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
description: 定義済みの設定、チャネル、および事前にインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する Teams テンプレートの使用方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424637"
---
# <a name="get-started-with-teams-templates-in-retail"></a>小売業の Teams テンプレートの使用を開始する

Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。

Teams テンプレートには、小売業者のニーズに基づいて設計されたチーム構造の定義が事前に作成されています。 Teams テンプレートを使用すると、小売業者にとって適切なチームの種類をすばやく作成し、組織全体に展開できます。 Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。

この記事では、各 Teams テンプレートを紹介し、それらの使用方法を推奨します。

この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。 組織内に Teams サービスがすでに展開されています。 展開がまだの場合は、「[Microsoft Teams の展開方法](How-to-roll-out-teams.md)」をお読みになって展開を開始してください。

一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」をご参照ください。

## <a name="store-template"></a>店舗テンプレート

店舗テンプレートは、個々の小売店の場所を表すチームを作成するのに最適です。 店舗テンプレートを使用して、組織内の小売店の場所ごとにチームを作成できます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| チャネル <ul><li>シフト ハンドオフ\*</li><li>学習\*</li></ul>\*自動的にお気に入りに登録されたチャネル<br><br>チームのプロパティ <ul><li>チームの可視性を公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成/更新/削除できません </li><li>アプリを追加/削除できません </li><li>タブを作成/更新/削除できません</li><li>コネクタを作成/更新/削除できません</li><ul>|
||||

組織の店舗テンプレートをカスタマイズするための推奨される方法:

- 組織の各店舗に部門がある場合は、部門ごとにチャネルを追加します。 チャネルを追加すると、部門内のコミュニケーションとコラボレーションが容易になります。

- 組織に内部 Web サイト (SharePoint サイトなど) がある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。 手順については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」を参照してください。

## <a name="manager-collaboration-template"></a>マネージャー コラボレーションのテンプレート

マネージャー コラボレーションのテンプレートは、小売業者のニーズに合わせて設計されたもう 1 つの Teams テンプレートです。 マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。 たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 小売業 - <br>店舗 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>操作\*</li><li>学習\*</li></ul>\*自動的にお気に入りに登録されたチャネル<br><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> <br>メンバーのアクセス許可 <ul><li>チャネルを作成/更新/削除できます </li><li>アプリを追加/削除できます </li><li>タブを作成/更新/削除できます</li><li>コネクタを作成/更新/削除できます</li><ul>|
||||

組織のマネージャー コラボレーションのテンプレートをカスタマイズするための推奨される方法:

- 組織に、SharePoint サイトなど、マネージャーに関連する内部 Web サイトがある場合は、それらを関連するチーム チャネルのタブとして固定することを検討してください。 手順については、「[Microsoft Teams テンプレートのドキュメント](get-started-with-teams-templates.md)」をご覧ください。

## <a name="how-to-use-first-party-templates"></a>ファースト パーティ テンプレートの使い方

これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。  Teams テンプレートを展開する方法の詳細については、「[Teams の作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。

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
## <a name="relate-topic"></a>関連トピック

[管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
