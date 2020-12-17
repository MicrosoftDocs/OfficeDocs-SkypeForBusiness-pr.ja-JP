---
title: Microsoft Teams のプライベート チャネルのライフ サイクルを管理する
author: MikePlumleyMSFT
ms.author: mikeplum
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
description: 組織内のプライベート チャネルのライフ サイクルを管理する方法について説明します。
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601662"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Microsoft Teams のプライベート チャネルのライフ サイクルを管理する

ここでは、組織内の[プライベート チャネル](private-channels.md)のライフ サイクルを管理するために必要なガイダンスを見つけることができます。

> [!IMPORTANT]
> この記事にある PowerShell の手順を使用してプライベート チャネルを管理している場合は、[PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/)から Teams PowerShell パブリック プレビュー モジュールをインストールして使用する必要があります。 モジュールをインストールする方法の手順については、「[Microsoft Teams PowerShell のインストール](teams-powershell-install.md)」を参照してください。 最新の General Availability Teams PowerShell モジュールは、プライベート チャネルの管理をサポートしていません。

## <a name="set-whether-team-members-can-create-private-channels"></a>チーム メンバーがプライベート チャネルを作成できるかどうかを設定する

チームの所有者は、メンバーがチーム設定でプライベート チャネルを作成する機能をオフまたはオンにできます。 これを行うには、チームの **[設定]** タブで、**[メンバーにプライベート チャネルの作成を許可する]** をオフまたはオンにします。

管理者は、Graph API を使用して、メンバーが特定のチームでプライベート チャネルを作成できるかどうかを制御できます。 次に例を示します。

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>組織内のユーザーがプライベート チャネルを作成できるかどうかを設定する

管理者は、Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定し、組織内のどのユーザーにプライベート チャネルの作成を許可するかを制御できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

チーム ポリシーを使用して、組織内のどのユーザーにプライベート チャネルの作成を許可するかを設定します。 詳細については、「[Teams でのチーム ポリシーを管理する](teams-policies.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

**CsTeamsChannelsPolicy** を使用して、組織内のどのユーザーにプライベート チャネルの作成を許可するかを設定します。 **AllowPrivateChannelCreation** パラメーターを **true** に設定して、ポリシーが割り当てられているユーザーがプライベート チャネルを作成できるようにします。 パラメータを **false** に設定すると、ポリシーが割り当てられているユーザーのプライベート チャネルを作成する機能がオフになります。

詳細については、[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps) を参照してください。

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>チーム所有者に代わってプライベート チャネルを作成する

管理者は、PowerShell または Graph API を使用して、チーム所有者に代わってプライベート チャネルを作成できます。 たとえば、組織がプライベート チャネルの作成を一元化する場合は、これを実行できます。

### <a name="using-powershell"></a>PowerShell の使用

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Graph API の使用

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

## <a name="get-a-list-of-all-private-channel-messages"></a>すべてのプライベート チャネル メッセージのリストを取得する

アーカイブと監査の目的のため、プライベート チャネルに投稿されたすべてのメッセージと返信のリストを取得できます。  Graph API を使用してこれを行う方法は次のとおりです。

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>チーム内のすべてのプライベート チャネルの SharePoint URL を検索する

プライベート チャネル内のファイルに対して電子情報開示または法的保留を実行する場合でも、特定のプライベート チャネルにファイルを配置するカスタム アプリを構築する場合でも、それぞれのプライベート チャネルに対して作成された一意の SharePoint サイト コレクションをクエリする方法が必要になります。

管理者は、PowerShell または Graph API コマンドを使用してこれらの URL をクエリできます。

### <a name="using-powershell"></a>PowerShell の使用

1. 管理者アカウントを使用して、[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) をインストールして接続します。
2. 以下を実行します。ここで、&lt;group_id&gt; はチームのグループ ID です。 (グループ ID は、チームへのリンクで簡単に見つけることができます。)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Graph API の使用

これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。

1. 以下を使用して、特定のチームのプライベート チャネル ID のリストを取得します。ここで、<group_id> はチームのグループ ID です。 これは、以降の呼び出しで必要になります。 (グループ ID は、チームへのリンクで簡単に見つけることができます)。

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

2. SharePoint URL を取得するプライベート チャネルごとに、次の要求を行います。ここで、&lt;channel_id&gt; はチャネル ID です。

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>プライベート チャネルの所有者とメンバーの役割を一覧表示して更新する

プライベート チャネルの所有者とメンバーをリストアップして、プライベート チャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを決定できます。 これは、組織を離れたプライベート チャネルの所有者がいて、プライベート チャネルがチャネルの所有権を主張するために管理者の支援を必要とする場合に発生する可能性があります。

管理者は、Microsoft Teams 管理センター、PowerShell、またはGraph API を使用してこれらのアクションを実行できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

Microsoft Teams 管理センターを使用してチーム メンバーを管理する方法については、「[Microsoft Teams 管理センターでチームを管理する](manage-teams-in-modern-portal.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

1. 以下を実行します。ここで、&lt;group_id&gt; はチームのグループ ID であり、&lt;channel_name&gt; はチャネル名です。

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. メンバーを所有者に昇格させます。

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Graph API の使用

これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。

1. 以下を使用します。ここで、&lt;group_id&gt; はチームのグループ ID であり、&lt;channel_id&gt; はチャネル ID です。

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
2. 以下を使用して、メンバーを所有者に昇格させます。ここで、&lt;group_id&gt;、&lt;channel_id&gt;、&lt;id&gt; は前の呼び出しから返されます。 前の呼び出しから返された &lt;id&gt; と &lt;userId&gt; は同じではなく、互換性がないことに注意してください。 必ず &lt;id&gt; を使用してください。

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
    - [チャネルを一覧表示する](https://docs.microsoft.com/graph/api/channel-list)
    - [チャネルを作成する](https://docs.microsoft.com/graph/api/channel-post)
    - [チャネルにメンバーを追加する](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [チャネルでメンバーを更新する](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [チャネルからメンバーを削除する](https://docs.microsoft.com/graph/api/conversationmember-delete)
