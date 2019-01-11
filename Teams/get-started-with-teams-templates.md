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
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="1e709-103">チーム テンプレートを使い始める</span><span class="sxs-lookup"><span data-stu-id="1e709-103">Get started with Teams templates</span></span> 

<span data-ttu-id="1e709-104">チーム テンプレートのように設計されたビジネス ・ ニーズやプロジェクト チームの構造体の定義があらかじめ組み込まれており。</span><span class="sxs-lookup"><span data-stu-id="1e709-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="1e709-105">チャネルのさまざまなトピックの豊富なコラボレーション ・ スペースを簡単に作成し、ミッション ・ クリティカルなコンテンツとサービスを取得するアプリケーションをプレインストールするのには、チーム テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e709-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="1e709-106">チーム テンプレートでは、組織全体で一貫性のあるチームを簡単に作成できる定義済みのチームの構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e709-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="1e709-107">この記事でテンプレートの種類は、基本テンプレートで定義可能なプロパティを説明し、いくつかのサンプル テンプレートからチームを作成する要求の使用方法。</span><span class="sxs-lookup"><span data-stu-id="1e709-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="1e709-108">ならここでするは。</span><span class="sxs-lookup"><span data-stu-id="1e709-108">This article is for you if you're:</span></span>

- <span data-ttu-id="1e709-109">計画、展開、および組織全体で複数のチームの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="1e709-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="1e709-110">開発者はプログラムで定義済みのチャネルおよびアプリケーションとチームを作成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1e709-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="1e709-111">チーム テンプレートの機能</span><span class="sxs-lookup"><span data-stu-id="1e709-111">Teams template capabilities</span></span>

<span data-ttu-id="1e709-112">チームのほとんどのプロパティが含まれているし、テンプレートでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1e709-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="1e709-113">いくつかのプロパティと、現在サポートされていない機能があります。</span><span class="sxs-lookup"><span data-stu-id="1e709-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="1e709-114">次の表は、含まれる機能とチーム テンプレートに含まれていない内容の簡単な概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e709-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="1e709-115">**チーム テンプレートでサポートされているチームのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="1e709-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="1e709-116">**チーム テンプレートではサポートされていないチームのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="1e709-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="1e709-117">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="1e709-117">Base template type</span></span> | <span data-ttu-id="1e709-118">チームのメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="1e709-118">Team membership</span></span> |
| <span data-ttu-id="1e709-119">チーム名</span><span class="sxs-lookup"><span data-stu-id="1e709-119">Team name</span></span> | <span data-ttu-id="1e709-120">チームの画像</span><span class="sxs-lookup"><span data-stu-id="1e709-120">Team picture</span></span> |
| <span data-ttu-id="1e709-121">チームの説明</span><span class="sxs-lookup"><span data-stu-id="1e709-121">Team description</span></span> | <span data-ttu-id="1e709-122">チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="1e709-122">Channel settings</span></span> |
| <span data-ttu-id="1e709-123">チームの可視性 (パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="1e709-123">Team visibility (public or private)</span></span> | <span data-ttu-id="1e709-124">コネクタ</span><span class="sxs-lookup"><span data-stu-id="1e709-124">Connectors</span></span> |
| <span data-ttu-id="1e709-125">チームの設定 (たとえば、メンバー、参照投稿 @ のゲスト)</span><span class="sxs-lookup"><span data-stu-id="1e709-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="1e709-126">ファイルとコンテンツ</span><span class="sxs-lookup"><span data-stu-id="1e709-126">Files and content</span></span> |
| <span data-ttu-id="1e709-127">自動お気に入りチャンネル</span><span class="sxs-lookup"><span data-stu-id="1e709-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="1e709-128">インストールされているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="1e709-128">Installed app</span></span> | |
| <span data-ttu-id="1e709-129">固定タブ</span><span class="sxs-lookup"><span data-stu-id="1e709-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="1e709-130">複数のテンプレートの機能は、マイクロソフトのチームの今後のリリースを追加する、サポートされているプロパティには、最新の情報をチェックしてします。</span><span class="sxs-lookup"><span data-stu-id="1e709-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="1e709-131">基本テンプレートの種類を挙げてください。</span><span class="sxs-lookup"><span data-stu-id="1e709-131">What are base template types?</span></span>

<span data-ttu-id="1e709-132">基本テンプレートの種類とは、特定の業界にマイクロソフトが作成した特別なテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="1e709-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="1e709-133">多くの場合、これらの基本テンプレートには、ストアとチーム プロパティをまだサポートされていない個別のチーム テンプレートでは利用できない独自のアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e709-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="1e709-134">基本テンプレートの種類を定義すると、拡張したり、これらの特別なテンプレートを指定するには追加のプロパティをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="1e709-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="1e709-135">ですが、いくつかの基本テンプレートの種類が含まれているプロパティをオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1e709-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="1e709-136">既定では、基本のテンプレートは、**標準的な**独自アプリケーションの追加や特別なプロパティが含まれていませんに設定されます。</span><span class="sxs-lookup"><span data-stu-id="1e709-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="1e709-137">次利用可能な基本テンプレートの種類の現在のリストに示します。</span><span class="sxs-lookup"><span data-stu-id="1e709-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="1e709-138">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="1e709-138">Base template type</span></span> | <span data-ttu-id="1e709-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="1e709-139">baseTemplateId</span></span> | <span data-ttu-id="1e709-140">基本テンプレート専用のアプリケーションや特殊なプロパティ</span><span class="sxs-lookup"><span data-stu-id="1e709-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="1e709-141">Standard</span><span class="sxs-lookup"><span data-stu-id="1e709-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="1e709-142">なしのアプリケーションの追加とプロパティ</span><span class="sxs-lookup"><span data-stu-id="1e709-142">No additional apps and properties</span></span> |
| <span data-ttu-id="1e709-143">教育-</span><span class="sxs-lookup"><span data-stu-id="1e709-143">Education -</span></span> <br><span data-ttu-id="1e709-144">チーム<sup>1</sup>をクラスします。</span><span class="sxs-lookup"><span data-stu-id="1e709-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="1e709-145">アプリケーション:</span><span class="sxs-lookup"><span data-stu-id="1e709-145">Apps:</span></span><ul><li><span data-ttu-id="1e709-146">OneNote クラスのノートブック ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="1e709-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="1e709-147">割り当てのアプリケーション ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="1e709-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="1e709-148">チームのプロパティ:</span><span class="sxs-lookup"><span data-stu-id="1e709-148">Team properties:</span></span><ul><li><span data-ttu-id="1e709-149">チームの表示/非表示に設定 (オーバーライドできない) **HiddenMembership**</span><span class="sxs-lookup"><span data-stu-id="1e709-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="1e709-150">教育-</span><span class="sxs-lookup"><span data-stu-id="1e709-150">Education -</span></span><br><span data-ttu-id="1e709-151">スタッフ チーム<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e709-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="1e709-152">アプリケーション:</span><span class="sxs-lookup"><span data-stu-id="1e709-152">Apps:</span></span><ul><li><span data-ttu-id="1e709-153">OneNote のスタッフのノートブック ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="1e709-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="1e709-154">教育-</span><span class="sxs-lookup"><span data-stu-id="1e709-154">Education -</span></span><br><span data-ttu-id="1e709-155">PLC チーム</span><span class="sxs-lookup"><span data-stu-id="1e709-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="1e709-156">アプリケーション:</span><span class="sxs-lookup"><span data-stu-id="1e709-156">Apps:</span></span><ul><li><span data-ttu-id="1e709-157">OneNote PLC のノートブック ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="1e709-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="1e709-158">遅延 10 月、2018年の<sup>1</sup>の文書</span><span class="sxs-lookup"><span data-stu-id="1e709-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="1e709-159">追加されていく複数の基本テンプレート型の将来のマイクロソフトのチームのリリースに関する最新情報についてのチェックには、プロパティがサポートされているようです。</span><span class="sxs-lookup"><span data-stu-id="1e709-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="1e709-160">例</span><span class="sxs-lookup"><span data-stu-id="1e709-160">Examples</span></span> 

<span data-ttu-id="1e709-161">[Microsoft グラフ API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)を使用してチームを作成するテンプレートを使用してを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="1e709-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="1e709-162">テンプレートからチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e709-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="1e709-163">要求</span><span class="sxs-lookup"><span data-stu-id="1e709-163">Requests</span></span>

<span data-ttu-id="1e709-164">**標準的な基本テンプレートを使用してチームを作成する要求**</span><span class="sxs-lookup"><span data-stu-id="1e709-164">**Request to create a team with the standard base template**</span></span>

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

<span data-ttu-id="1e709-165">**余分なチャネルを持つチームを作成し、チャンネルを削除してからメンバーを禁止するための要求**</span><span class="sxs-lookup"><span data-stu-id="1e709-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

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

<span data-ttu-id="1e709-166">**要求がサポートされているすべてのプロパティを使用してチームを作成するには**</span><span class="sxs-lookup"><span data-stu-id="1e709-166">**Request to create a team with all supported properties**</span></span>

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

### <a name="get-status"></a><span data-ttu-id="1e709-167">ステータスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e709-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="1e709-168">要求</span><span class="sxs-lookup"><span data-stu-id="1e709-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="1e709-169">応答</span><span class="sxs-lookup"><span data-stu-id="1e709-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="1e709-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e709-170">Related topics</span></span>

- <span data-ttu-id="1e709-171">[チームの作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)(プレビュー) で</span><span class="sxs-lookup"><span data-stu-id="1e709-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="1e709-172">新しいチーム</span><span class="sxs-lookup"><span data-stu-id="1e709-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="1e709-173">Microsoft Teams の管理者トレーニング</span><span class="sxs-lookup"><span data-stu-id="1e709-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)