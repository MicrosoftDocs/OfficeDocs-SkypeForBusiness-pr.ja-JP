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
ms.openlocfilehash: 317cded1be30beac8fefbb579d5f0c24258f2fa1
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637204"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="38572-103">Microsoft Teams でプライベートチャネルのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="38572-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="38572-104">ここでは、組織内の[プライベートチャネル](private-channels.md)のライフサイクルを管理するために必要なガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38572-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38572-105">この記事の PowerShell の手順を使用してプライベートチャネルを管理している場合は、PowerShell テストギャラリーから最新バージョンの Teams PowerShell モジュールをインストールして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38572-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="38572-106">この方法については、「 [Powershell テストギャラリーから最新の Teams powershell モジュールをインストール](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38572-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="38572-107">最新の一般公開バージョンの Teams PowerShell モジュール (現在[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) では、プライベートチャネルの管理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="38572-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="38572-108">チームメンバーがプライベートチャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="38572-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="38572-109">チーム所有者は、メンバーがチーム設定でプライベートチャネルを作成できるようにする機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38572-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="38572-110">これを行うには、チームの [**設定**] タブで、[**メンバーにプライベートチャネルの作成を許可する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="38572-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="38572-111">管理者は、Graph API を使って、メンバーが特定のチームでプライベートチャネルを作成できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="38572-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="38572-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="38572-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="38572-113">組織内のユーザーがプライベートチャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="38572-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="38572-114">管理者は、Microsoft Teams 管理センターまたは PowerShell を使用して、プライベートチャネルを作成できる組織内のユーザーを管理することにより、ポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="38572-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="38572-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="38572-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="38572-116">チームポリシーを使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="38572-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="38572-117">詳細については、「 [teams のチームポリシーを管理](teams-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38572-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="38572-118">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="38572-118">Using PowerShell</span></span>

<span data-ttu-id="38572-119">**CsTeamsChannelsPolicy**を使用して、組織内のどのユーザーにプライベートチャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="38572-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="38572-120">ポリシーを割り当てられたユーザーがプライベートチャネルを作成できるようにするには、 **AllowPrivateChannelCreation**パラメーターを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="38572-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="38572-121">このパラメーターを**false**に設定すると、ポリシーが割り当てられているユーザーに対してプライベートチャネルを作成する機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="38572-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="38572-122">詳細については、「 [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38572-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="38572-123">チーム所有者の代わりにプライベートチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="38572-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="38572-124">管理者は、PowerShell または Graph API を使用して、チーム所有者の代わりにプライベートチャネルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="38572-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="38572-125">たとえば、組織でプライベートチャネルの作成を一元化する場合は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="38572-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="38572-126">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="38572-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="38572-127">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="38572-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="38572-128">すべてのプライベートチャネルメッセージの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="38572-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="38572-129">プライベートチャネルで投稿されたすべてのメッセージと返信の一覧を取得して、アーカイブおよび監査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="38572-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="38572-130">Graph API を使ってこれを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="38572-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="38572-131">チーム内のすべてのプライベートチャネルの SharePoint Url を検索する</span><span class="sxs-lookup"><span data-stu-id="38572-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="38572-132">プライベートチャネルのファイルに対して電子情報開示または法的保持を実行することを検討している場合、または特定のプライベートチャネルにファイルを配置する基幹業務アプリを構築する場合は、そのために作成された固有の SharePoint サイトコレクションを照会する方法が必要になります。各プライベートチャネル。</span><span class="sxs-lookup"><span data-stu-id="38572-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="38572-133">管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="38572-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="38572-134">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="38572-134">Using PowerShell</span></span>

1. <span data-ttu-id="38572-135">管理者アカウントを使用して、 [SharePoint Online 管理シェル](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)をインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="38572-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="38572-136">&lt;Group_id&gt;がチームのグループ id である場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="38572-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="38572-137">(チームへのリンクでグループ ID を簡単に見つけることができます。)</span><span class="sxs-lookup"><span data-stu-id="38572-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="38572-138">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="38572-138">Using Graph API</span></span>

<span data-ttu-id="38572-139">これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="38572-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="38572-140">以下を使用して、特定のチームのプライベートチャネル Id の一覧を取得します。ここで <group_id> はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="38572-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="38572-141">以降の通話では、この機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="38572-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="38572-142">(チームへのリンクからグループ ID を簡単に見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="38572-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="38572-143">**要求**</span><span class="sxs-lookup"><span data-stu-id="38572-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="38572-144">**応答**</span><span class="sxs-lookup"><span data-stu-id="38572-144">**Response**</span></span>

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

2. <span data-ttu-id="38572-145">SharePoint URL を取得するプライベートチャネルごとに、次のように要求します。ここ&lt;で&gt; channel_id はチャネル id です。</span><span class="sxs-lookup"><span data-stu-id="38572-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="38572-146">**要求**</span><span class="sxs-lookup"><span data-stu-id="38572-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="38572-147">**応答**</span><span class="sxs-lookup"><span data-stu-id="38572-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="38572-148">プライベートチャネルの所有者とメンバーの役割をリストして更新する</span><span class="sxs-lookup"><span data-stu-id="38572-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="38572-149">プライベートチャネルの所有者とメンバーの一覧を表示して、プライベートチャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="38572-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="38572-150">この問題は、プライベートチャネルの所有者が組織を離れていて、プライベートチャネルでチャネルの所有権を要求するために管理者のヘルプが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="38572-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="38572-151">管理者として、PowerShell または Graph Api コマンドを使って、これらの Url を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="38572-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="38572-152">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="38572-152">Using PowerShell</span></span>

1. <span data-ttu-id="38572-153">次を実行します&lt;。&gt;ここでは、group_id がチームの&lt;グループ&gt; id であり、channel_name がチャネル名であることを示します。</span><span class="sxs-lookup"><span data-stu-id="38572-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="38572-154">メンバーを所有者に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="38572-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="38572-155">Graph API を使用する</span><span class="sxs-lookup"><span data-stu-id="38572-155">Using Graph API</span></span>

<span data-ttu-id="38572-156">これらのコマンドは、 [Graph エクスプローラ](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="38572-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="38572-157">以下を使用します&lt;。&gt;ここでは、group_id がチームの&lt;グループ&gt; id であり、channel_id がチャネル id です。</span><span class="sxs-lookup"><span data-stu-id="38572-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="38572-158">**要求**</span><span class="sxs-lookup"><span data-stu-id="38572-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="38572-159">**応答**</span><span class="sxs-lookup"><span data-stu-id="38572-159">**Response**</span></span>

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
2.  <span data-ttu-id="38572-160">メンバーを所有者に昇格させるには、次&lt;の&gt;よう&lt;に&gt;します&lt;。&gt; group_id、channel_id、id は前の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="38572-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="38572-161">ただし、 &lt;前&gt;の&lt;通話&gt;から返された id と userId は同じではないため、互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="38572-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="38572-162">Id &lt;&gt;を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38572-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="38572-163">**要求**</span><span class="sxs-lookup"><span data-stu-id="38572-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="38572-164">**応答**</span><span class="sxs-lookup"><span data-stu-id="38572-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="38572-165">Teams Powershell モジュール</span><span class="sxs-lookup"><span data-stu-id="38572-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="38572-166">PowerShell テストギャラリーから最新の Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="38572-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="38572-167">最新の一般公開バージョンの Teams PowerShell モジュール (現在[1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) では、プライベートチャネルの管理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="38572-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span> <span data-ttu-id="38572-168">次の手順を使用して、PowerShell テストギャラリーからプライベートチャネルのサポート (現在 1.0.18) を使用して、最新バージョンの Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38572-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="38572-169">PowerShell テストギャラリーから、パブリック PowerShell ギャラリーのバージョンのモジュールと共に Teams PowerShell モジュールをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="38572-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="38572-170">次の手順に従って、最初にパブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールしてから、PowerShell テストギャラリーから最新バージョンのモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38572-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="38572-171">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="38572-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="38572-172">Windows PowerShell モジュールの新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="38572-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="38572-173">パブリック PowerShell ギャラリーから Teams PowerShell モジュールをアンインストールするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="38572-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="38572-174">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="38572-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="38572-175">もう一度 Windows PowerShell モジュールを起動し、次の操作を実行して、PowerShell テストギャラリーを信頼できるソースとして登録します。</span><span class="sxs-lookup"><span data-stu-id="38572-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="38572-176">次の操作を実行して、PowerShell テストギャラリーから最新の Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38572-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="38572-177">次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38572-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="38572-178">PowerShell テストギャラリーから最新バージョンの Teams PowerShell モジュールに更新する</span><span class="sxs-lookup"><span data-stu-id="38572-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="38572-179">PowerShell テストギャラリーから既に Teams PowerShell モジュールをインストールしている場合は、次の手順を使用して最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="38572-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="38572-180">既存のすべての PowerShell セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="38572-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="38572-181">Windows PowerShell モジュールの新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="38572-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="38572-182">次の操作を実行して、PowerShell テストギャラリーから現在インストールされている Teams PowerShell モジュールのバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="38572-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="38572-183">次の操作を実行して、PowerShell テストギャラリーの最新バージョンの Teams PowerShell モジュールが正常にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38572-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="38572-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="38572-184">Related topics</span></span>

- [<span data-ttu-id="38572-185">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="38572-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="38572-186">Microsoft Graph API を使用して Teams で作業する</span><span class="sxs-lookup"><span data-stu-id="38572-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="38572-187">リストチャネル</span><span class="sxs-lookup"><span data-stu-id="38572-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="38572-188">チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="38572-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="38572-189">チャネルにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="38572-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="38572-190">チャンネルのメンバーの更新</span><span class="sxs-lookup"><span data-stu-id="38572-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="38572-191">チャネルからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="38572-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
