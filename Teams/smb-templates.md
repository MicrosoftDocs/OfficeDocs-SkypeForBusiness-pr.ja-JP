---
title: 中小企業向けの Teams テンプレートを使ってみる
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: 中小企業向けの Teams テンプレートを使ってみる
ms.openlocfilehash: fd0d17ac78dc7dea0efde95315604189671caa9e
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35420562"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>中小企業向けの Teams テンプレートを使ってみる

Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。

小規模または中規模の企業では、管理者が組織全体にチームをすばやく展開できるように、テンプレートを特に強力にすることができます。 テンプレートを使用すると、ユーザーの向きを確認したり、チームの効率的な使い方を始めることができます。 この記事は、組織内の複数のチームの計画、展開、管理を担当しているユーザーを対象としています。

現在、さまざまな状況で利用できる、3つ目のパーティの SMB テンプレートが提供されています。 すべてのテンプレートによって*プライベート*チームが作成されます。 チームを作成し、組織に展開する準備ができたら、必要に応じて、プライバシーを*組織全体*または*一般*向けに設定できます。 チームテンプレートの詳細については、「[チームテンプレートの概要](get-started-with-teams-templates.md)」を参照してください。

## <a name="company-wide-template"></a>会社全体のテンプレート
会社全体のテンプレートは、会社全体に関連したコミュニケーションとコラボレーションを目的としています。 [全般] チャネルは、会社全体のお知らせ、業界ニュース、役員の投稿に使用できます。 人事チャネルは、求人、新入社員のオンボード、トレーニング、開発など、人事関連のすべてのアクティビティを統合するのに最適な場所です。 楽しい機能チャネルは、すべてのランダムで楽しい投稿のソーシャルプラットフォームを提供します。

| ベーステンプレートの種類  | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 中堅 <br>会社全体 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| チャネル <ul><li>General\*</li><li>人事\*</li><li>楽しい機能\*</li></ul><br> アプリ<ul><li>会社ポータル (**人事**チャネルに固定された web サイト) </li> </UL><br>チームのプロパティ <ul><li>チームの表示はプライベートに設定</li></ul> |

* 自動お気に入りチャネル 

定義済みのテンプレートから既定のテンプレートを取得して会社全体のチームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。 Teams テンプレートの展開方法について詳しくは、「[チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。

#### <a name="request"></a>要求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>エグゼクティブチームテンプレート

エグゼクティブチームテンプレートは、会社の役員向けのチームを作成して、年間の優先度、会計予算、戦略的イニシアチブ、トップクライアントなど、会社のイニシアチブを伝達して共同作業するのに最適です。このテンプレートには、特定のトピックについて選択したユーザーを招待するための*プライベート*チャネルが用意されています。

| ベーステンプレートの種類  | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 中堅 <br>エグゼクティブチーム | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | チャネル <ul><li>General\*</li><li>外字\*</li></ul> アプリ<ul><li>OneNote (**プライベート**チャネルに固定されています)</li> <li>Planner (**プライベート**チャネルに固定されています) </li></ul><br>チームのプロパティ <ul><li>チームの表示はプライベートに設定</li></ul> | 

* 自動お気に入りチャネル<br>

定義済みのテンプレートから既定値を取得してエグゼクティブチームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。 Teams テンプレートの展開方法について詳しくは、「[チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。

#### <a name="request"></a>要求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>部門チームテンプレート

部門チームテンプレートを使用して、個々の部門またはプロジェクトのチームを作成できます。 財務チームテンプレートは、財務チームメンバー内のすべての投稿、お知らせ、日常的なコラボレーション、コミュニケーション、およびチームメンバーの経営陣に最適です。 このテンプレートには、特定のトピックについてのユーザーを選択するための*プライベート*チャネルが用意されています。 また、必要に応じて追加、削除、または編集することで、テンプレートを追加の部署または特定のプロジェクトに拡張するために使用できる、次のような財務チーム用のスクリプトを提供します。 たとえば、*マーケティング*部門を使用している場合は、*財務*から*マーケティング*にチームの名前を変更して新しいマーケティングチームを作成することによって、スクリプトを調整できます。

| ベーステンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| 中堅 <br>Finance  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| チャネル <ul><li>General\*</li><li>外字\*</li></ul><br> アプリ<ul><li>OneNote (**プライベート**チャネルに固定されています)</li> <li>Planner (**プライベート**チャネルに固定されています) </li> </ul><br>チームのプロパティ <ul><li>チームの表示はプライベートに設定</li></ul> | 

* 自動お気に入りチャネル

定義済みのテンプレートから既定値を取得して財務チームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。 Teams テンプレートの展開方法について詳しくは、「[チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。

#### <a name="request"></a>要求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
``

### Example: Finance Team template extension script

``` Powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>関連トピック

- [Teams のテンプレートの使用を開始する](get-started-with-teams-templates.md)
- [チームを作成する](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)(プレビュー中)

