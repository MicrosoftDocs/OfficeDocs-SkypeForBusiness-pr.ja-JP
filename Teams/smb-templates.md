---
title: Microsoft Graphで構築された中小企業向けのチーム テンプレート
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: Microsoft Graphに組み込まれている定義済みテンプレートMicrosoft Teams使用して、中小企業向けのチームを迅速かつ簡単に作成します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5317b989bd7fe77f34743b6554cd356c226c2fa8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646306"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>小規模および中規模の企業向けの Microsoft Graphに組み込まれているチーム テンプレート

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

中小企業の場合、テンプレートは、組織全体にTeamsを迅速に展開するのに役立つため、特に強力です。 テンプレートは、ユーザーがTeamsを効果的に使用する方法を理解するのにも役立ちます。 この記事は、組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。

現在、さまざまな状況で使用できる中小企業向けの 3 つの事前構築済みテンプレートを提供しています。 すべてのテンプレートで *プライベート チームが作成されます* 。 チームを作成し、組織にロールアウトする準備ができたら、必要に応じて、プライバシーを *組織全体* または *パブリック* に設定できます。

チーム テンプレート全般の詳細については、[Microsoft Graphを使用したチーム テンプレートの概要](get-started-with-teams-templates.md)に関するページを参照してください。

## <a name="company-wide-template"></a>Company-Wide テンプレート

Company-Wide テンプレートは、会社全体のコミュニケーションとコラボレーションを目的としたものです。 一般チャネルは、会社全体のお知らせ、業界ニュース、またはエグゼクティブ投稿に使用できます。 人事チャネルは、役職、新入社員のオンボーディング、トレーニング、開発など、人事関連のすべてのアクティビティを統合するのに最適な場所です。 Fun Stuff チャネルは、すべてのランダムで楽しい投稿にソーシャル プラットフォームを提供します。

| テンプレートの種類  | TemplateId | このテンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>全社的 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| チャネル <ul><li>全般\*</li><li>人材\*</li><li>Fun Stuff\*</li></ul><br> アプリ<ul><li>ポータル サイト (**人事** チャネルにピン留めされた Web サイト) </li> </UL><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> |

*自動お気に入りのチャネル 

定義済みのテンプレートから既定の設定を取得してCompany-Wide チームを作成するには、要求本文でチーム オブジェクトの JSON 表現を指定します。 チーム テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph[記事を](/graph/api/team-post?view=graph-rest-beta)参照してください。

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

エグゼクティブ チーム テンプレートは、会社の経営幹部が、年間の優先順位、財政予算、戦略的イニシアチブ、トップ クライアントなどの会社のイニシアチブについてコミュニケーションと共同作業を行うためのチームを作成するのに最適です。 このテンプレートには、特定のトピックに対して選択したユーザーを招待するための *プライベート* チャネルが付属しています。

| テンプレートの種類  | TemplateId | このテンプレートに含まれるプロパティ |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>エグゼクティブ チーム | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul> アプリ<ul><li>OneNote (**プライベート** チャネルにピン留め)</li> <li>Planner ( **プライベート** チャネルにピン留め) </li></ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りのチャネル<br>

定義済みのテンプレートから既定の設定を取得して Executives チームを作成するには、要求本文でチーム オブジェクトの JSON 表現を指定します。 チーム テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph[記事を](/graph/api/team-post?view=graph-rest-beta)参照してください。

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

部門のチーム テンプレートは、個々の部署またはプロジェクトのチームを作成するために使用できます。 Finance チーム テンプレートは、必要に応じて、Finance チーム メンバーとエグゼクティブ チーム メンバー内のすべての投稿、お知らせ、毎日のコラボレーションとコミュニケーションに最適です。 テンプレートには、特定のトピックに対して選択したユーザーを招待するための *プライベート* チャネルが付属しています。

また、財務チーム向けに以下のスクリプトを提供します。このスクリプトを使用して、好みに合わせて追加、削除、または編集することで、テンプレートを追加の部署または特定のプロジェクトに拡張できます。 たとえば、 *マーケティング* 部門がある場合は、チームの名前を *Finance* から *Marketing* に変更して新しいマーケティング チームを作成することで、スクリプトを調整できます。

| テンプレートの種類 | TemplateId | このテンプレートに含まれるプロパティ |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finance  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| チャネル <ul><li>全般\*</li><li>プライベート \*</li></ul><br> アプリ<ul><li>OneNote (**プライベート** チャネルにピン留め)</li> <li>Planner ( **プライベート** チャネルにピン留め) </li> </ul><br>チームのプロパティ <ul><li>チームの可視性を非公開に設定</li></ul> | 

*自動お気に入りのチャネル

定義済みのテンプレートから既定の設定を取得して Finance チームを作成するには、要求本文でチーム オブジェクトの JSON 表現を指定します。 チーム テンプレートを展開する方法の詳細については、チームの作成に関する Microsoft Graph[記事を](/graph/api/team-post?view=graph-rest-beta)参照してください。

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

### <a name="example-finance-team-template-extension-script"></a>例: Finance Team テンプレート拡張スクリプト

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
- [チームの作成](/graph/api/team-post?view=graph-rest-beta) (プレビュー段階)
