---
title: チーム テンプレートを使い始める
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 151a789b6047540071aa5780fb81a895503dd70b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838892"
---
# <a name="get-started-with-teams-templates"></a>チーム テンプレートを使い始める 

チーム テンプレートはあらかじめ構築済みのように設計されたビジネス ・ ニーズやプロジェクト チームの構造を定義します。 チャネルのさまざまなトピックの豊富なコラボレーション ・ スペースを簡単に作成し、ミッション ・ クリティカルなコンテンツとサービスを取得するアプリケーションをプレインストールするのには、チーム テンプレートを使用できます。 チーム テンプレートでは、組織全体で一貫性のあるチームを簡単に作成できる定義済みのチームの構造を提供します。 

この記事でテンプレートの種類は、基本テンプレートで定義可能なプロパティを説明し、いくつかのサンプル テンプレートからチームを作成する要求の使用方法。
 
ならここでするは。

• 計画、展開、および、組織 • 開発者の間で複数のチームの管理を担当するとチームを作成しようとしている定義済みのチャネルおよびアプリケーション プログラムを使用して

## <a name="team-template-capabilities"></a>チーム テンプレートの機能

チームのほとんどのプロパティが含まれているし、テンプレートでサポートされています。 ただしは、いくつかのプロパティと機能は現在サポートされていません。 次の表は、含まれる機能とチーム テンプレートに含まれていない内容の簡単な概要を提供します。

| **チーム テンプレートでサポートされているチームのプロパティ** | **チーム テンプレートではサポートされていないチームのプロパティ** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 基本テンプレートの種類 | チームのメンバーシップ |
| チーム名 | チームの画像 |
| チームの説明 | チャンネル設定 (たとえば、自動お気に入りとプライバシー) |
| チームの可視性 (パブリックまたはプライベート) | コネクタ |
| チームの設定 (たとえば、メンバー、参照投稿 @ のゲスト) | ファイルとコンテンツ |
| 自動お気に入りチャンネル | |
| インストールされているアプリケーション | |
| 固定タブ | | 

> [!NOTE]
> 複数のテンプレートの機能は、マイクロソフトのチームの今後のリリースを追加する、サポートされているプロパティには、最新の情報をチェックしてします。

## <a name="what-are-base-template-types"></a>基本テンプレートの種類を挙げてください。

基本テンプレートの種類とは、特定の業界にマイクロソフトが作成した特別なテンプレートです。 多くの場合、これらの基本テンプレートには、チーム テンプレートでは個別にサポートされていないストアとチームのプロパティでは使用できない専用のアプリケーションが含まれています。

基本テンプレートの種類を定義すると、拡張したり、これらの特別なテンプレートを指定するには追加のプロパティをオーバーライドできます。 ただし、いくつかの種類基本テンプレートにはでは、プロパティ オーバーライドすることはできませんにはが含まれています。 

既定では、基本のテンプレートは、**標準的な**独自アプリケーションの追加や特別なプロパティが含まれていませんに設定されます。 次利用可能な基本テンプレートの種類の現在のリストに示します。

| 基本テンプレートの種類 | baseTemplateId | 基本テンプレート専用のアプリケーションや特殊なプロパティ |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | なしのアプリケーションの追加とプロパティ |
| 医療・ ケアの調整 | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | アプリケーション:<br/> -患者のアプリケーション ([**全般**] タブに固定されている)<br/> <br/>チャネル: <br/> -お知らせ<br/> -糖尿病<br/> -Cardiovascular<br/> -看護婦 |
| 医療・ プロセスの huddle | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | チャネル:<br/> -避け死亡記録<br/> の mortality レビュー <br/> -滝を防止します。 <br/> の sepsis 計画 |
| 教育のクラスのチーム<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | アプリケーション:<br/> の OneNote クラスのノートブック ([**全般**] タブに固定されている) <br/> -割り当てのアプリケーション ([**全般**] タブに固定されている) <br/><br/> チーム プロパティ <br/> チームの可視性 (オーバーライドできない) **HiddenMembership**に設定 |
| 教育のスタッフのチーム<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | アプリ<br/> の OneNote スタッフのノートブック ([**全般**] タブに固定されている) |

遅延 10 月、2018年の<sup>1</sup>の文書

> [!NOTE]
> 追加されていく複数の基本テンプレート型の将来のマイクロソフトのチームのリリースに関する最新情報についてのチェックには、プロパティがサポートされているようです。

## <a name="examples"></a>例 

[Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview)をインストールすることでテンプレートを使用してチームの作成を開始できます。

### <a name="create-a-team-from-a-template"></a>テンプレートからチームを作成します。

#### <a name="requests"></a>要求

**標準的な基本テンプレートを使用してチームを作成する要求**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**余分なチャネルを持つチームを作成し、チャンネルを削除してからメンバーを禁止するための要求**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**要求がサポートされているすべてのプロパティを使用してチームを作成するには**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>応答

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [チームの作成](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams)(プレビュー) で
- [新しいチーム](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft Teams の管理者トレーニング](itadmin-readiness.md)