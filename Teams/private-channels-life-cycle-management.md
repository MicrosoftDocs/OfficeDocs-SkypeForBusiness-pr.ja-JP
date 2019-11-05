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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 組織内のプライベートチャネルのライフサイクルを管理する方法について説明します。
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969415"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="94801-103">Microsoft Teams でプライベートチャネルのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="94801-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="94801-104">ここでは、組織内の[プライベートチャネル](private-channels.md)のライフサイクルを管理するために必要なガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="94801-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="94801-105">チームメンバーがプライベートチャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="94801-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="94801-106">チーム所有者は、メンバーがチーム設定でプライベートチャネルを作成できるようにする機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="94801-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="94801-107">これを行うには、チームの [**設定**] タブで、[**メンバーにプライベートチャネルの作成を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="94801-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="94801-108">管理者は、Graph API を使って、メンバーが特定のチームでプライベートチャネルを作成できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="94801-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="94801-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="94801-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="94801-110">組織内のユーザーがプライベートチャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="94801-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="94801-111">管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して、プライベートチャネルを作成できる組織内のユーザーを管理することにより、ポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="94801-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="94801-112">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="94801-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="94801-113">チームポリシーを使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="94801-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="94801-114">詳細については、「 [teams のチームポリシーを管理](teams-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94801-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="94801-115">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-115">Using PowerShell</span></span>

<span data-ttu-id="94801-116">**CsTeamsChannelsPolicy**を使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="94801-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="94801-117">ポリシーを割り当てられたユーザーがプライベートチャネルを作成できるようにするには、 **AllowPrivateChannelCreation**パラメーターを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="94801-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="94801-118">このパラメーターを**false**に設定すると、ポリシーが割り当てられているユーザーに対してプライベートチャネルを作成する機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="94801-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="94801-119">詳細については、「 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94801-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="94801-120">チーム所有者の代わりにプライベートチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="94801-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="94801-121">管理者は、PowerShell または Graph API を使用して、チーム所有者の代わりにプライベートチャネルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="94801-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="94801-122">たとえば、組織でプライベートチャネルの作成を一元化する場合は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="94801-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="94801-123">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="94801-124">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="94801-125">すべてのプライベートチャネルメッセージの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="94801-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="94801-126">プライベートチャネルで投稿されたすべてのメッセージと返信の一覧を取得して、アーカイブおよび監査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="94801-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="94801-127">Graph API を使ってこれを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94801-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="94801-128">チーム内のすべてのプライベートチャネルの SharePoint Url を検索する</span><span class="sxs-lookup"><span data-stu-id="94801-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="94801-129">プライベートチャネルのファイルに対して電子情報開示または法的保持を実行することを検討している場合、または特定のプライベートチャネルにファイルを配置する基幹業務アプリを構築する場合は、そのために作成された固有の SharePoint サイトコレクションを照会する方法が必要になります。各プライベートチャネル。</span><span class="sxs-lookup"><span data-stu-id="94801-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="94801-130">管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="94801-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="94801-131">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-131">Using PowerShell</span></span>

1. <span data-ttu-id="94801-132">管理者アカウントを使用して、 [SharePoint Online 管理シェル](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)をインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="94801-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="94801-133">&lt;Group_id&gt;がチームのグループ id である、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="94801-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="94801-134">(チームへのリンクでグループ Id を簡単に見つけることができます。)</span><span class="sxs-lookup"><span data-stu-id="94801-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="94801-135">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-135">Using Graph API</span></span>

<span data-ttu-id="94801-136">これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="94801-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="94801-137">以下を使用して、特定のチームのプライベートチャネル Id の一覧を取得します。ここで <group_id> は、チームのグループ Id です。</span><span class="sxs-lookup"><span data-stu-id="94801-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="94801-138">以降の通話では、この機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="94801-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="94801-139">(チームへのリンクからグループ Id を簡単に見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="94801-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="94801-140">**要求**</span><span class="sxs-lookup"><span data-stu-id="94801-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="94801-141">**応答**</span><span class="sxs-lookup"><span data-stu-id="94801-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="94801-142">SharePoint URL を取得するプライベートチャネルごとに、次のように要求します。ここ&lt;で&gt; 、channel_id はチャネル id です。</span><span class="sxs-lookup"><span data-stu-id="94801-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="94801-143">**要求**</span><span class="sxs-lookup"><span data-stu-id="94801-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="94801-144">**応答**</span><span class="sxs-lookup"><span data-stu-id="94801-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="94801-145">プライベートチャネルの所有者とメンバーの役割をリストして更新する</span><span class="sxs-lookup"><span data-stu-id="94801-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="94801-146">プライベートチャネルの所有者とメンバーの一覧を表示して、プライベートチャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="94801-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="94801-147">この問題は、プライベートチャネルの所有者が組織を離れていて、プライベートチャネルでチャネルの所有権を要求するために管理者のヘルプが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="94801-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="94801-148">管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="94801-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="94801-149">PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-149">Using PowerShell</span></span>

1. <span data-ttu-id="94801-150">管理者アカウントを使用して、 [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams)をインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="94801-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="94801-151">次を実行します&lt;。&gt;ここで、group_id はチームのグループ&lt;id&gt; 、channel_id はチャネル id です。</span><span class="sxs-lookup"><span data-stu-id="94801-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="94801-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="94801-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="94801-153">**応答**</span><span class="sxs-lookup"><span data-stu-id="94801-153">**Response**</span></span>

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. <span data-ttu-id="94801-154">メンバーを所有者に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="94801-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="94801-155">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="94801-155">Using Graph API</span></span>

<span data-ttu-id="94801-156">これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="94801-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="94801-157">&lt;Group_id&gt;がチームのグループ id であり、 &lt;channel_id&gt;がチャネル id である場合は、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="94801-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="94801-158">**要求**</span><span class="sxs-lookup"><span data-stu-id="94801-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="94801-159">**応答**</span><span class="sxs-lookup"><span data-stu-id="94801-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="94801-160">メンバーを所有者に昇格させるには、次&lt;の&gt;よう&lt;に&gt;します&lt;。&gt; group_id、channel_id、id は、前の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="94801-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="94801-161">ただし、 &lt;前&gt;の&lt;通話&gt;から返された id と userId は同じではないため、互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="94801-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="94801-162">Id &lt;&gt;を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="94801-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="94801-163">**要求**</span><span class="sxs-lookup"><span data-stu-id="94801-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="94801-164">**応答**</span><span class="sxs-lookup"><span data-stu-id="94801-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="94801-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="94801-165">Related topics</span></span>

- [<span data-ttu-id="94801-166">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="94801-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="94801-167">Microsoft Graph API を使用してチームと連携する</span><span class="sxs-lookup"><span data-stu-id="94801-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="94801-168">リストチャネル</span><span class="sxs-lookup"><span data-stu-id="94801-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="94801-169">チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="94801-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="94801-170">チャネルにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="94801-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="94801-171">チャンネルのメンバーの更新</span><span class="sxs-lookup"><span data-stu-id="94801-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="94801-172">チャネルからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="94801-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)