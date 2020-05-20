---
title: Microsoft Teams でプライベートチャネルのライフサイクルを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 組織内のプライベートチャネルのライフサイクルを管理する方法について説明します。
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321703"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Microsoft Teams でプライベートチャネルのライフサイクルを管理する

ここでは、組織内の[プライベートチャネル](private-channels.md)のライフサイクルを管理するために必要なガイダンスについて説明します。

> [!IMPORTANT]
> この記事の PowerShell の手順を使用してプライベートチャネルを管理している場合は、 [Powershell テストギャラリー](https://www.poshtestgallery.com/packages/MicrosoftTeams/)から最新のプレリリース版の Teams PowerShell モジュールをインストールして使用する必要があります。 モジュールをインストールする手順については、「[プレリリース版の Teams PowerShell モジュールをインストール](install-prerelease-teams-powershell-module.md)する」を参照してください。 最新の一般公開バージョンの Teams PowerShell モジュールは、プライベートチャネルの管理をサポートしていません。

## <a name="set-whether-team-members-can-create-private-channels"></a>チームメンバーがプライベートチャネルを作成できるかどうかを設定する

チーム所有者は、メンバーがチーム設定でプライベートチャネルを作成できるようにする機能を有効または無効にすることができます。 これを行うには、チームの [**設定**] タブで、[**メンバーにプライベートチャネルの作成を許可する**] をオンまたはオフにします。

管理者は、Graph API を使って、メンバーが特定のチームでプライベートチャネルを作成できるかどうかを制御できます。 次に例を示します。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>組織内のユーザーがプライベートチャネルを作成できるかどうかを設定する

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して、プライベートチャネルを作成できる組織内のユーザーを管理することにより、ポリシーを設定することができます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

チームポリシーを使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。 詳細については、「 [teams のチームポリシーを管理](teams-policies.md)する」を参照してください。

### <a name="using-powershell"></a>PowerShell を使用する場合

**CsTeamsChannelsPolicy**を使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。 ポリシーを割り当てられたユーザーがプライベートチャネルを作成できるようにするには、 **AllowPrivateChannelCreation**パラメーターを**true**に設定します。 このパラメーターを**false**に設定すると、ポリシーが割り当てられているユーザーに対してプライベートチャネルを作成する機能が無効になります。

詳細については、「 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)」を参照してください。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>チーム所有者の代わりにプライベートチャネルを作成する

管理者は、PowerShell または Graph API を使用して、チーム所有者の代わりにプライベートチャネルを作成することができます。 たとえば、組織でプライベートチャネルの作成を一元化する場合は、これを行うことができます。

### <a name="using-powershell"></a>PowerShell を使用する場合

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Graph API を使用する

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>すべてのプライベートチャネルメッセージの一覧を取得する

プライベートチャネルで投稿されたすべてのメッセージと返信の一覧を取得して、アーカイブおよび監査を行うことができます。  Graph API を使ってこれを行う方法を次に示します。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>チーム内のすべてのプライベートチャネルの SharePoint Url を検索する

プライベートチャネルのファイルに対して電子情報開示または法的保持を実行することを検討している場合、または特定のプライベートチャネルにファイルを配置するカスタムアプリを構築する場合は、プライベートチャネルごとに作成された固有の SharePoint サイトコレクションを照会する方法が必要になります。

管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。

### <a name="using-powershell"></a>PowerShell を使用する場合

1. 管理者アカウントを使用して、 [SharePoint Online 管理シェル](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)をインストールして接続します。
2. &lt;Group_id &gt; がチームのグループ id である場合は、次のように実行します。 (チームへのリンクでグループ ID を簡単に見つけることができます。)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Graph API を使用する

これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。

1. 以下を使用して、特定のチームのプライベートチャネル Id の一覧を取得します。ここで <group_id> はチームのグループ ID です。 以降の通話では、この機能が必要になります。 (チームへのリンクからグループ ID を簡単に見つけることができます)。

    **要求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **応答**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. SharePoint URL を取得するプライベートチャネルごとに、次のように要求し &lt; ます。ここで channel_id &gt; はチャネル id です。

    **要求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **応答**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>プライベートチャネルの所有者とメンバーの役割をリストして更新する

プライベートチャネルの所有者とメンバーの一覧を表示して、プライベートチャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを判断することができます。 この問題は、プライベートチャネルの所有者が組織を離れていて、プライベートチャネルでチャネルの所有権を要求するために管理者のヘルプが必要な場合に発生します。

管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。

### <a name="using-powershell"></a>PowerShell を使用する場合

1. 次を実行し &lt; ます。ここでは、group_id &gt; がチームのグループ id で &lt; あり、channel_name &gt; がチャネル名であることを示します。

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. メンバーを所有者に昇格させます。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Graph API を使用する

これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。

1. 以下を使用します。ここでは、 &lt; group_id &gt; がチームのグループ id で &lt; あり、CHANNEL_ID &gt; がチャネル id です。

    **要求**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **応答**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. メンバーを所有者に昇格させるには、次のようにし &lt; &gt; &lt; ます。 group_id、channel_id &gt; 、 &lt; id &gt; は前の呼び出しから返されます。 ただし、 &lt; &gt; &lt; &gt; 前の通話から返された id と userId は同じではないため、互換性がありません。 Id を使用していることを確認してください &lt; &gt; 。

    **要求**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **応答**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [Microsoft Graph API を使用して Teams で作業する](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [リストチャネル](https://docs.microsoft.com/graph/api/channel-list)
    - [チャネルを作成する](https://docs.microsoft.com/graph/api/channel-post)
    - [チャネルにメンバーを追加する](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [チャンネルのメンバーの更新](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [チャネルからメンバーを削除する](https://docs.microsoft.com/graph/api/conversationmember-delete)
