---
title: Microsoft Graph を使用して構築された中小企業向けのチーム テンプレート
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Microsoft Microsoft Teamsに組み込Graphテンプレートを使用して、中小企業向けのチームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 324470ffc3366750777c75776e4ae4e783dbb17f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045683"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>中小企業向けの Microsoft Graph組み込みのチーム テンプレート

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

中小企業の場合、テンプレートは特に強力な機能を備える可能性があります。テンプレートを使用すると、組織全体にすばやくTeams展開できます。 また、テンプレートを使用すると、ユーザーはアプリを効果的に使用する方法をTeams。 この記事は、組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。

現在、さまざまな状況で使用できる中小企業向けの 3 つの事前構築済みテンプレートを提供しています。 すべてのテンプレートでプライベート チーム *が作成* されます。 チームを作成し、組織に展開する準備ができたら、必要に応じてプライバシーを *Org-Wide* または *Public* に設定できます。

チーム テンプレート全般の詳細については、「Microsoft Graph を使用してチーム テンプレートを使用する[」を参照してください](get-started-with-teams-templates.md)。

## <a name="company-wide-template"></a>Company-Wide テンプレート

このCompany-Wideテンプレートは、会社全体のコミュニケーションとコラボレーションを意図しています。 会社全体のお知らせ、業界ニュース、またはエグゼクティブの投稿には、[全般] チャネルを使用できます。 人事チャネルは、ジョブの投稿、新しい従業員のオンボーディング、トレーニング、開発など、人事関連のすべてのアクティビティを統合する最適な場所です。 [Fun Stuff] チャネルは、すべてのランダムで楽しい投稿にソーシャル プラットフォームを提供します。

| テンプレートの種類  | TemplateId | このテンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>会社全体 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| チャネル <ul><li>全般\*</li><li>人事\*</li><li>楽しい情報\*</li></ul><br> アプリ<ul><li>ポータル サイト (人事チャネルにピン留め **された** Web サイト) </li> </UL><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> |

*自動お気に入りチャネル 

定義済みのテンプレートCompany-Wide既定の設定を取得してチームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。 チーム テンプレートをデプロイする方法の詳細については、チームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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

## <a name="executive-team-template"></a>エグゼクティブ チーム テンプレート

エグゼクティブ チーム テンプレートは、会社のエグゼクティブが年間の優先順位、会計予算、戦略イニシアチブ、トップ クライアントなどの会社のイニシアティブについてコミュニケーションと共同作業を行うチームを作成する場合に最適です。 このテンプレートには、特定のトピック *の選択* したユーザーを招待するプライベート チャネルが付属しています。

| テンプレートの種類  | TemplateId | このテンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>エグゼクティブ チーム | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul> アプリ<ul><li>OneNote (プライベート チャンネルに **ピン留め**)</li> <li>Planner (プライベート チャネル **にピン留め** ) </li></ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りチャネル<br>

定義済みのテンプレートから既定の設定を取得して Executives チームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。 チーム テンプレートをデプロイする方法の詳細については、チームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

#### <a name="request"></a>要求 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>部門チーム テンプレート

部門チーム テンプレートは、個々の部門またはプロジェクトのチームを作成するために使用できます。 財務チーム テンプレートは、必要に応じて、財務チーム メンバーおよびエグゼクティブ チーム メンバー内のすべての投稿、お知らせ、毎日の共同作業とコミュニケーションに最適です。 テンプレートには、特定のトピック *の選択* したユーザーを招待するプライベート チャネルが付属しています。

また、お好みで追加、削除、または編集することで、追加の部門や特定のプロジェクトにテンプレートを拡張するために使用できる財務チーム向けスクリプトも以下に示します。 たとえば、マーケティング部門がある場合は、財務からマーケティングにチームの名前を変更して新しいマーケティングチームを作成することで、スクリプトを調整できます。 

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finance  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul><br> アプリ<ul><li>OneNote (プライベート チャンネルに **ピン留め**)</li> <li>Planner (プライベート チャネル **にピン留め** ) </li> </ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りチャネル

定義済みのテンプレートから既定の設定を取得して財務チームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。 チーム テンプレートをデプロイする方法の詳細については、チームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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
```

### <a name="example-finance-team-template-extension-script"></a>例: Finance Team テンプレート拡張機能スクリプト

```powershell
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

## <a name="related-topics"></a>関連項目

- [Teams 管理センターで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](get-started-with-teams-templates.md)
- [チームを作成](/graph/api/team-post?view=graph-rest-beta) する (プレビュー中)
