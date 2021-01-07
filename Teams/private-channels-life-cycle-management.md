---
title: Graph API を使用して Microsoft Teams のプライベート チャネルを管理する
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
description: Graph API を使用して組織内のプライベート チャネルを管理する方法について説明します。
ms.openlocfilehash: 854e8721dac7d49e258db42845b84480955bfec7
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772040"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="91b9c-103">Microsoft Teams のプライベート チャネルのライフ サイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="91b9c-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="91b9c-104">ここでは、Graph API を使用して組織内の [Teams](https://docs.microsoft.com/microsoftteams/private-channels) のプライベート チャネルを管理するために管理する必要があるガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="91b9c-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](https://docs.microsoft.com/microsoftteams/private-channels) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="91b9c-105">チーム メンバーがプライベート チャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="91b9c-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="91b9c-106">管理者は、Graph API を使用して、メンバーが特定のチームでプライベート チャネルを作成できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="91b9c-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="91b9c-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="91b9c-108">チーム所有者に代わってプライベート チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="91b9c-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="91b9c-109">管理者は、Graph API を使用して、チーム所有者の代わりにプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="91b9c-110">たとえば、組織がプライベート チャネルの作成を一元化する場合は、これを実行できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="91b9c-111">すべてのプライベート チャネル メッセージのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="91b9c-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="91b9c-112">アーカイブと監査の目的のため、プライベート チャネルに投稿されたすべてのメッセージと返信のリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="91b9c-113">Graph API を使用してこれを行う方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="91b9c-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="91b9c-114">チーム内のすべてのプライベート チャネルの SharePoint URL を検索する</span><span class="sxs-lookup"><span data-stu-id="91b9c-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="91b9c-115">プライベート チャネル内のファイルに対して電子情報開示または法的保留を実行する場合でも、特定のプライベート チャネルにファイルを配置するカスタム アプリを構築する場合でも、それぞれのプライベート チャネルに対して作成された一意の SharePoint サイト コレクションをクエリする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="91b9c-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="91b9c-116">管理者は、Graph API コマンドを使用してこれらの URL に対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="91b9c-117">これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="91b9c-118">以下を使用して、特定のチームのプライベート チャネル ID のリストを取得します。ここで、<group_id> はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="91b9c-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="91b9c-119">これは、以降の呼び出しで必要になります。</span><span class="sxs-lookup"><span data-stu-id="91b9c-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="91b9c-120">(グループ ID は、チームへのリンクで簡単に見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="91b9c-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="91b9c-121">**要求**</span><span class="sxs-lookup"><span data-stu-id="91b9c-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="91b9c-122">**応答**</span><span class="sxs-lookup"><span data-stu-id="91b9c-122">**Response**</span></span>

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

2. <span data-ttu-id="91b9c-123">SharePoint URL を取得するプライベート チャネルごとに、次の要求を行います。ここで、&lt;channel_id&gt; はチャネル ID です。</span><span class="sxs-lookup"><span data-stu-id="91b9c-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="91b9c-124">**要求**</span><span class="sxs-lookup"><span data-stu-id="91b9c-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="91b9c-125">**応答**</span><span class="sxs-lookup"><span data-stu-id="91b9c-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="91b9c-126">プライベート チャネルの所有者とメンバーの役割を一覧表示して更新する</span><span class="sxs-lookup"><span data-stu-id="91b9c-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="91b9c-127">プライベート チャネルの所有者とメンバーをリストアップして、プライベート チャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="91b9c-128">これは、組織を離れたプライベート チャネルの所有者がいて、プライベート チャネルがチャネルの所有権を主張するために管理者の支援を必要とする場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91b9c-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="91b9c-129">管理者は、Graph API を使用してこれらのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="91b9c-130">これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="91b9c-131">以下を使用します。ここで、&lt;group_id&gt; はチームのグループ ID であり、&lt;channel_id&gt; はチャネル ID です。</span><span class="sxs-lookup"><span data-stu-id="91b9c-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="91b9c-132">**要求**</span><span class="sxs-lookup"><span data-stu-id="91b9c-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="91b9c-133">**応答**</span><span class="sxs-lookup"><span data-stu-id="91b9c-133">**Response**</span></span>

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
2. <span data-ttu-id="91b9c-134">以下を使用して、メンバーを所有者に昇格させます。ここで、&lt;group_id&gt;、&lt;channel_id&gt;、&lt;id&gt; は前の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="91b9c-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="91b9c-135">前の呼び出しから返された &lt;id&gt; と &lt;userId&gt; は同じではなく、互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="91b9c-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="91b9c-136">必ず &lt;id&gt; を使用してください。</span><span class="sxs-lookup"><span data-stu-id="91b9c-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="91b9c-137">**要求**</span><span class="sxs-lookup"><span data-stu-id="91b9c-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="91b9c-138">**応答**</span><span class="sxs-lookup"><span data-stu-id="91b9c-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="91b9c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="91b9c-139">Related topics</span></span>

[<span data-ttu-id="91b9c-140">Microsoft Graph API を使用して Teams で作業する</span><span class="sxs-lookup"><span data-stu-id="91b9c-140">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="91b9c-141">チャネルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="91b9c-141">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)

[<span data-ttu-id="91b9c-142">チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="91b9c-142">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)

[<span data-ttu-id="91b9c-143">チャネルにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="91b9c-143">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)

[<span data-ttu-id="91b9c-144">チャネルでメンバーを更新する</span><span class="sxs-lookup"><span data-stu-id="91b9c-144">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)

[<span data-ttu-id="91b9c-145">チャネルからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="91b9c-145">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
