---
title: チーム テンプレートを使い始める
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: 定義済みのチャネルを持つチームを作成するチーム テンプレートを使用する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801465"
---
# <a name="get-started-with-teams-templates"></a>チーム テンプレートを使い始める 

チーム テンプレートのように設計されたビジネス ・ ニーズやプロジェクト チームの構造体の定義があらかじめ組み込まれており。 チャネルのさまざまなトピックの豊富なコラボレーション ・ スペースを簡単に作成し、ミッション ・ クリティカルなコンテンツとサービスを取得するアプリケーションをプレインストールするのには、チーム テンプレートを使用できます。 チーム テンプレートでは、組織全体で一貫性のあるチームを簡単に作成できる定義済みのチームの構造を提供します。 

この記事でテンプレートの種類は、基本テンプレートで定義可能なプロパティを説明し、いくつかのサンプル テンプレートからチームを作成する要求の使用方法。
 
ならここでするは。

- 計画、展開、および組織全体で複数のチームの管理を担当します。<br>
- 開発者はプログラムで定義済みのチャネルおよびアプリケーションとチームを作成しようとしています。 

## <a name="teams-template-capabilities"></a>チーム テンプレートの機能

チームのほとんどのプロパティが含まれているし、テンプレートでサポートされています。 いくつかのプロパティと、現在サポートされていない機能があります。 次の表は、含まれる機能とチーム テンプレートに含まれていない内容の簡単な概要を提供します。

| **チーム テンプレートでサポートされているチームのプロパティ** | **チーム テンプレートではサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チームのメンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャネルの設定 |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チームの設定 (たとえば、メンバー、参照投稿 @ のゲスト) | ファイルとコンテンツ |
| 自動お気に入りチャンネル | |
| インストールされているアプリケーション | |
| 固定タブ | | 

> [!NOTE]
> 複数のテンプレートの機能は、マイクロソフトのチームの今後のリリースを追加する、サポートされているプロパティには、最新の情報をチェックしてします。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類を挙げてください。

基本テンプレートの種類とは、特定の業界にマイクロソフトが作成した特別なテンプレートです。 多くの場合、これらの基本テンプレートには、ストアとチーム プロパティをまだサポートされていない個別のチーム テンプレートでは利用できない独自のアプリケーションが含まれています。

基本テンプレートの種類を定義すると、拡張したり、これらの特別なテンプレートを指定するには追加のプロパティをオーバーライドできます。 ですが、いくつかの基本テンプレートの種類が含まれているプロパティをオーバーライドすることはできません。 

既定では、基本のテンプレートは、**標準的な**独自アプリケーションの追加や特別なプロパティが含まれていませんに設定されます。 次利用可能な基本テンプレートの種類の現在のリストに示します。

| 基本テンプレートの種類 | baseTemplateId | 基本テンプレート専用のアプリケーションや特殊なプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | なしのアプリケーションの追加とプロパティ |
| 教育- <br>チーム<sup>1</sup>をクラスします。 | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | アプリケーション:<ul><li>OneNote クラスのノートブック ([**全般**] タブに固定されている) </li><li>割り当てのアプリケーション ([**全般**] タブに固定されている)</li></ul> チームのプロパティ:<ul><li>チームの表示/非表示に設定 (オーバーライドできない) **HiddenMembership**</li></ul> |
| 教育-<br>スタッフ チーム<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | アプリケーション:<ul><li>OneNote のスタッフのノートブック ([**全般**] タブに固定されている)</li></ul> |
|教育-<br>PLC チーム |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | アプリケーション:<ul><li>OneNote PLC のノートブック ([**全般**] タブに固定されている)</ul></li>|
|||

遅延 10 月、2018年の<sup>1</sup>の文書

> [!NOTE]
> 追加されていく複数の基本テンプレート型の将来のマイクロソフトのチームのリリースに関する最新情報についてのチェックには、プロパティがサポートされているようです。

## <a name="examples"></a>例 

[Microsoft グラフ API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)を使用してチームを作成するテンプレートを使用してを開始することができます。

### <a name="create-a-team-from-a-template"></a>テンプレートからチームを作成します。

#### <a name="requests"></a>要求

**標準的な基本テンプレートを使用してチームを作成する要求**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**余分なチャネルを持つチームを作成し、チャンネルを削除してからメンバーを禁止するための要求**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**要求がサポートされているすべてのプロパティを使用してチームを作成するには**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>ステータスを取得します。

#### <a name="request"></a>要求

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>応答

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>関連トピック

- [チームの作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)(プレビュー) で
- [新しいチーム](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams の管理者トレーニング](itadmin-readiness.md)