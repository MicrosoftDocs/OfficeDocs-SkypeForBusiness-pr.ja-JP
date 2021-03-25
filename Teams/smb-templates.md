---
title: Microsoft Graph を使用して構築された中小企業向け Teams テンプレート
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Microsoft Graph に組み込みの Microsoft Teams の定義済みテンプレートを使用すると、中小企業向けのチームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116995"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Microsoft Graph for Small and Medium Businesses に組み込みの Teams テンプレート

Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。

中小企業の場合、テンプレートは特に強力です。テンプレートは、管理者が組織全体に Teams をすばやく展開するのに役立ちます。 テンプレートは、ユーザーを方向付けし、Teams の効果的な使用を開始するのにも役立ちます。 この記事は、組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。

現在、さまざまな状況で利用できる 3 つのファースト パーティ SMB テンプレートを提供しています。 すべてのテンプレートでプライベート Teams *が作成* されます。 Teams を作成し、組織に展開する準備ができたら、必要に応じてプライバシーを組織全体または *パブリックに設定* できます。 一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」をご参照ください。

## <a name="company-wide-template"></a>Company-Wide テンプレート
このCompany-Wideテンプレートは、会社全体に関連するコミュニケーションとコラボレーションを意図しています。 会社全体のお知らせ、業界ニュース、またはエグゼクティブの投稿には、全般チャネルを使用できます。 人事チャネルは、求人、新入社員の研修、トレーニング、開発など、人事関連のすべてのアクティビティを統合する最適な場所です。 Fun Stuff チャネルは、すべてのランダムで楽しい投稿のためのソーシャル プラットフォームを提供します。

| 基本テンプレートの種類  | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>会社全体 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| チャネル <ul><li>全般\*</li><li>人事\*</li><li>楽しい情報\*</li></ul><br> アプリ<ul><li>ポータル サイト (人事チャネルにピン留 **めされた Web サイト** ) </li> </UL><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> |

*自動お気に入りチャネル 

事前に定義Company-Wide既定を取得してチームを作成するには、要求本文にチーム オブジェクトの JSON 表現を指定します。 Teams テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph [の記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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

エグゼクティブ チーム テンプレートは、会社のエグゼクティブが年間の優先事項、予算、戦略的なイニシアティブ、トップ クライアントなどの会社のイニシアティブについてコミュニケーションを取り、共同作業するためのチームを作成する場合に最適です。 このテンプレートには、特定のトピック *の* 特定のユーザーを招待するプライベート チャネルが付属しています。

| 基本テンプレートの種類  | baseTemplateId | この基本テンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>エグゼクティブ チーム | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul> アプリ<ul><li>OneNote (プライベート チャネルに **ピン留め** )</li> <li>Planner (プライベート チャネルに **ピン留め** ) </li></ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りチャネル<br>

事前に定義されたテンプレートから既定値を取得して Executives チームを作成するには、要求本文にチーム オブジェクトの JSON 表現を指定します。 Teams テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph [の記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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

部門チーム テンプレートは、個々の部署またはプロジェクトのチームを作成するために使用できます。 財務チーム テンプレートは、財務チーム メンバーとエグゼクティブ チーム メンバー内のすべての投稿、お知らせ、毎日の共同作業とコミュニケーションに最適です。 テンプレートには、特定の *トピックの* 特定のユーザーを招待するプライベート チャネルが用意されています。 また、お好みで追加、削除、または編集することで、追加の部門や特定のプロジェクトにテンプレートを拡張するために使用できる、財務チーム用のスクリプトも以下に示します。 たとえば、マーケティング部門がある場合、スクリプトはチーム名を財務からマーケティングに変更して新しいマーケティングチームを作成することで調整できます。 

| 基本テンプレートの種類 | baseTemplateId | この基本テンプレートに含まれるプロパティ |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finance  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul><br> アプリ<ul><li>OneNote (プライベート チャネルに **ピン留め** )</li> <li>Planner (プライベート チャネルに **ピン留め** ) </li> </ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りチャネル

事前に定義されたテンプレートから既定値を取得して財務チームを作成するには、要求本文にチーム オブジェクトの JSON 表現を指定します。 Teams テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph [の記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。

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

### <a name="example-finance-team-template-extension-script"></a>例: 財務チーム テンプレート拡張スクリプト

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

- [管理コンソールで Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)
- [Teams のテンプレートの使用を開始する](get-started-with-teams-templates.md)
- [チームを作成](/graph/api/team-post?view=graph-rest-beta) する (プレビューで)