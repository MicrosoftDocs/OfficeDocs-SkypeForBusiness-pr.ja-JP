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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="80026-103">Microsoft Teams のプライベート チャネルのライフ サイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="80026-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="80026-104">ここでは、組織内の[プライベート チャネル](private-channels.md)のライフ サイクルを管理するために必要なガイダンスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="80026-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80026-105">この記事にある PowerShell の手順を使用してプライベート チャネルを管理している場合は、[PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams/)から Teams PowerShell パブリック プレビュー モジュールをインストールして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80026-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="80026-106">モジュールをインストールする方法の手順については、「[Microsoft Teams PowerShell のインストール](teams-powershell-install.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80026-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="80026-107">最新の General Availability Teams PowerShell モジュールは、プライベート チャネルの管理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="80026-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="80026-108">チーム メンバーがプライベート チャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="80026-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="80026-109">チームの所有者は、メンバーがチーム設定でプライベート チャネルを作成する機能をオフまたはオンにできます。</span><span class="sxs-lookup"><span data-stu-id="80026-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="80026-110">これを行うには、チームの **[設定]** タブで、**[メンバーにプライベート チャネルの作成を許可する]** をオフまたはオンにします。</span><span class="sxs-lookup"><span data-stu-id="80026-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="80026-111">管理者は、Graph API を使用して、メンバーが特定のチームでプライベート チャネルを作成できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="80026-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="80026-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="80026-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="80026-113">組織内のユーザーがプライベート チャネルを作成できるかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="80026-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="80026-114">管理者は、Microsoft Teams 管理センターまたは PowerShell を使用してポリシーを設定し、組織内のどのユーザーにプライベート チャネルの作成を許可するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="80026-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="80026-115">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="80026-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="80026-116">チーム ポリシーを使用して、組織内のどのユーザーにプライベート チャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="80026-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="80026-117">詳細については、「[Teams でのチーム ポリシーを管理する](teams-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80026-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="80026-118">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="80026-118">Using PowerShell</span></span>

<span data-ttu-id="80026-119">**CsTeamsChannelsPolicy** を使用して、組織内のどのユーザーにプライベート チャネルの作成を許可するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="80026-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="80026-120">**AllowPrivateChannelCreation** パラメーターを **true** に設定して、ポリシーが割り当てられているユーザーがプライベート チャネルを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="80026-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="80026-121">パラメータを **false** に設定すると、ポリシーが割り当てられているユーザーのプライベート チャネルを作成する機能がオフになります。</span><span class="sxs-lookup"><span data-stu-id="80026-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="80026-122">詳細については、[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80026-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="80026-123">チーム所有者に代わってプライベート チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="80026-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="80026-124">管理者は、PowerShell または Graph API を使用して、チーム所有者に代わってプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="80026-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="80026-125">たとえば、組織がプライベート チャネルの作成を一元化する場合は、これを実行できます。</span><span class="sxs-lookup"><span data-stu-id="80026-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="80026-126">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="80026-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="80026-127">Graph API の使用</span><span class="sxs-lookup"><span data-stu-id="80026-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="80026-128">すべてのプライベート チャネル メッセージのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="80026-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="80026-129">アーカイブと監査の目的のため、プライベート チャネルに投稿されたすべてのメッセージと返信のリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="80026-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="80026-130">Graph API を使用してこれを行う方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80026-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="80026-131">チーム内のすべてのプライベート チャネルの SharePoint URL を検索する</span><span class="sxs-lookup"><span data-stu-id="80026-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="80026-132">プライベート チャネル内のファイルに対して電子情報開示または法的保留を実行する場合でも、特定のプライベート チャネルにファイルを配置するカスタム アプリを構築する場合でも、それぞれのプライベート チャネルに対して作成された一意の SharePoint サイト コレクションをクエリする方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="80026-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="80026-133">管理者は、PowerShell または Graph API コマンドを使用してこれらの URL をクエリできます。</span><span class="sxs-lookup"><span data-stu-id="80026-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="80026-134">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="80026-134">Using PowerShell</span></span>

1. <span data-ttu-id="80026-135">管理者アカウントを使用して、[SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) をインストールして接続します。</span><span class="sxs-lookup"><span data-stu-id="80026-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="80026-136">以下を実行します。ここで、&lt;group_id&gt; はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="80026-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="80026-137">(グループ ID は、チームへのリンクで簡単に見つけることができます。)</span><span class="sxs-lookup"><span data-stu-id="80026-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="80026-138">Graph API の使用</span><span class="sxs-lookup"><span data-stu-id="80026-138">Using Graph API</span></span>

<span data-ttu-id="80026-139">これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="80026-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="80026-140">以下を使用して、特定のチームのプライベート チャネル ID のリストを取得します。ここで、<group_id> はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="80026-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="80026-141">これは、以降の呼び出しで必要になります。</span><span class="sxs-lookup"><span data-stu-id="80026-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="80026-142">(グループ ID は、チームへのリンクで簡単に見つけることができます)。</span><span class="sxs-lookup"><span data-stu-id="80026-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="80026-143">**要求**</span><span class="sxs-lookup"><span data-stu-id="80026-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="80026-144">**応答**</span><span class="sxs-lookup"><span data-stu-id="80026-144">**Response**</span></span>

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

2. <span data-ttu-id="80026-145">SharePoint URL を取得するプライベート チャネルごとに、次の要求を行います。ここで、&lt;channel_id&gt; はチャネル ID です。</span><span class="sxs-lookup"><span data-stu-id="80026-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="80026-146">**要求**</span><span class="sxs-lookup"><span data-stu-id="80026-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="80026-147">**応答**</span><span class="sxs-lookup"><span data-stu-id="80026-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="80026-148">プライベート チャネルの所有者とメンバーの役割を一覧表示して更新する</span><span class="sxs-lookup"><span data-stu-id="80026-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="80026-149">プライベート チャネルの所有者とメンバーをリストアップして、プライベート チャネルの特定のメンバーを所有者に昇格させる必要があるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="80026-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="80026-150">これは、組織を離れたプライベート チャネルの所有者がいて、プライベート チャネルがチャネルの所有権を主張するために管理者の支援を必要とする場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80026-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="80026-151">管理者は、Microsoft Teams 管理センター、PowerShell、またはGraph API を使用してこれらのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="80026-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="80026-152">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="80026-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="80026-153">Microsoft Teams 管理センターを使用してチーム メンバーを管理する方法については、「[Microsoft Teams 管理センターでチームを管理する](manage-teams-in-modern-portal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80026-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="80026-154">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="80026-154">Using PowerShell</span></span>

1. <span data-ttu-id="80026-155">以下を実行します。ここで、&lt;group_id&gt; はチームのグループ ID であり、&lt;channel_name&gt; はチャネル名です。</span><span class="sxs-lookup"><span data-stu-id="80026-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="80026-156">メンバーを所有者に昇格させます。</span><span class="sxs-lookup"><span data-stu-id="80026-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="80026-157">Graph API の使用</span><span class="sxs-lookup"><span data-stu-id="80026-157">Using Graph API</span></span>

<span data-ttu-id="80026-158">これらのコマンドは、[Graph エクスプローラー](https://developer.microsoft.com/graph/graph-explorer)から試すことができます。</span><span class="sxs-lookup"><span data-stu-id="80026-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="80026-159">以下を使用します。ここで、&lt;group_id&gt; はチームのグループ ID であり、&lt;channel_id&gt; はチャネル ID です。</span><span class="sxs-lookup"><span data-stu-id="80026-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="80026-160">**要求**</span><span class="sxs-lookup"><span data-stu-id="80026-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="80026-161">**応答**</span><span class="sxs-lookup"><span data-stu-id="80026-161">**Response**</span></span>

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
2. <span data-ttu-id="80026-162">以下を使用して、メンバーを所有者に昇格させます。ここで、&lt;group_id&gt;、&lt;channel_id&gt;、&lt;id&gt; は前の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="80026-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="80026-163">前の呼び出しから返された &lt;id&gt; と &lt;userId&gt; は同じではなく、互換性がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="80026-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="80026-164">必ず &lt;id&gt; を使用してください。</span><span class="sxs-lookup"><span data-stu-id="80026-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="80026-165">**要求**</span><span class="sxs-lookup"><span data-stu-id="80026-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="80026-166">**応答**</span><span class="sxs-lookup"><span data-stu-id="80026-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="80026-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="80026-167">Related topics</span></span>

- [<span data-ttu-id="80026-168">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="80026-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="80026-169">Microsoft Graph API を使用して Teams で作業する</span><span class="sxs-lookup"><span data-stu-id="80026-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="80026-170">チャネルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="80026-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="80026-171">チャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="80026-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="80026-172">チャネルにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="80026-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="80026-173">チャネルでメンバーを更新する</span><span class="sxs-lookup"><span data-stu-id="80026-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="80026-174">チャネルからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="80026-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
