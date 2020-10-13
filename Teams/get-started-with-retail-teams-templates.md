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
description: チームテンプレートを使用して、定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424637"
---
# <a name="get-started-with-teams-templates-in-retail"></a>小売業の Teams テンプレートの使用を開始する

Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。

Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。 Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。 また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。

この記事では、各チームテンプレートを紹介し、その使用方法をお勧めします。

この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。 組織に Teams サービスを既に展開している。 まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。

チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates.md)」を参照してください。

## <a name="store-template"></a>ストアテンプレート

ストアテンプレートは、個々の小売店の場所を表すチームの作成に適しています。 ストアテンプレートを使用して、組織内の各小売店舗の場所に対してチームを作成できます。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 向け <br>ストア | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| チャネル <ul><li>シフトシフト\*</li><li>意欲\*</li></ul>\*自動お気に入りチャネル<br><br>チームのプロパティ <ul><li>チームの表示がパブリックに設定</li></ul> <br>メンバーの権限 <ul><li>チャンネルを作成、更新、削除できません </li><li>アプリを追加または削除できない </li><li>タブの作成、更新、削除ができない</li><li>コネクタの作成、更新、削除ができない</li><ul>|
||||

組織のストアテンプレートをカスタマイズするための推奨される方法:

- 組織が各ストア内に部署を持っている場合は、部門ごとにチャネルを追加します。 チャネルを追加すると、部門内での通信とコラボレーションが容易になります。

- 組織に内部の web サイトがある場合 (SharePoint サイトなど) は、関連するチームチャネルのタブとしてピン留めすることを検討してください。 手順については、「 [チームテンプレートの使用を開始](get-started-with-teams-templates.md) する」を参照してください。

## <a name="manager-collaboration-template"></a>Manager グループ作業テンプレート

マネージャーコラボレーションテンプレートは、小売業者のニーズに合わせて設計された Teams テンプレートのもう1つです。 マネージャーグループ作業テンプレートは、ストアや地域などで共同作業するためのチームを作成するのに適しています。 たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| 向け <br>ストア | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| チャネル <ul><li>操作\*</li><li>意欲\*</li></ul>\*自動お気に入りチャネル<br><br>チームのプロパティ <ul><li>チームの表示はプライベートに設定</li></ul> <br>メンバーの権限 <ul><li>チャンネルを作成、更新、削除できます </li><li>アプリを追加/削除できる </li><li>タブを作成、更新、削除できます</li><li>コネクタを作成、更新、削除できます</li><ul>|
||||

組織のマネージャーコラボレーションテンプレートをカスタマイズするには、次の方法をお勧めします。

- 組織に SharePoint サイトなどの内部 web サイトがあり、マネージャーに関連している場合は、それらを関連チームチャネルのタブとしてピン留めすることを検討してください。 手順については、 [Microsoft Teams のテンプレート](get-started-with-teams-templates.md) に関するドキュメントを参照してください。

## <a name="how-to-use-first-party-templates"></a>ファーストパーティテンプレートの使用方法

これらのテンプレートを使用するには、要求本文の ' template@odata ' プロパティを ' standard ' から TemplateIDs に変更します。  Teams テンプレートの展開方法の詳細については、Microsoft Graph の記事「 [チームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)する方法」を参照してください。

> [!NOTE]
> テンプレートのチャネルは、[全般] タブに自動的に作成されます。

### <a name="example-store-template-extension-script"></a>例: ストアテンプレート拡張機能スクリプト

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
## <a name="relate-topic"></a>トピックの関連付け

[管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
