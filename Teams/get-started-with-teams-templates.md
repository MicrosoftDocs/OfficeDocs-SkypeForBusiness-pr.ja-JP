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
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531017"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="f8880-103">チーム テンプレートを使い始める</span><span class="sxs-lookup"><span data-stu-id="f8880-103">Get started with Teams templates</span></span> 

<span data-ttu-id="f8880-104">チーム テンプレートはあらかじめ構築済みのように設計されたビジネス ・ ニーズやプロジェクト チームの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="f8880-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="f8880-105">チャネルのさまざまなトピックの豊富なコラボレーション ・ スペースを簡単に作成し、ミッション ・ クリティカルなコンテンツとサービスを取得するアプリケーションをプレインストールするのには、チーム テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8880-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="f8880-106">チーム テンプレートでは、組織全体で一貫性のあるチームを簡単に作成できる定義済みのチームの構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8880-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="f8880-107">この記事でテンプレートの種類は、基本テンプレートで定義可能なプロパティを説明し、いくつかのサンプル テンプレートからチームを作成する要求の使用方法。</span><span class="sxs-lookup"><span data-stu-id="f8880-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="f8880-108">ならここでするは。</span><span class="sxs-lookup"><span data-stu-id="f8880-108">This article is for you if you're:</span></span>

<span data-ttu-id="f8880-109">• 計画、展開、および、組織 • 開発者の間で複数のチームの管理を担当するとチームを作成しようとしている定義済みのチャネルおよびアプリケーション プログラムを使用して</span><span class="sxs-lookup"><span data-stu-id="f8880-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="f8880-110">チーム テンプレートの機能</span><span class="sxs-lookup"><span data-stu-id="f8880-110">Team template capabilities</span></span>

<span data-ttu-id="f8880-111">チームのほとんどのプロパティが含まれているし、テンプレートでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f8880-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="f8880-112">ただしは、いくつかのプロパティと機能は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f8880-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="f8880-113">次の表は、含まれる機能とチーム テンプレートに含まれていない内容の簡単な概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8880-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="f8880-114">**チーム テンプレートでサポートされているチームのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8880-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="f8880-115">**チーム テンプレートではサポートされていないチームのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f8880-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="f8880-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="f8880-116">Base template type</span></span> | <span data-ttu-id="f8880-117">チームのメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="f8880-117">Team membership</span></span> |
| <span data-ttu-id="f8880-118">チーム名</span><span class="sxs-lookup"><span data-stu-id="f8880-118">Team name</span></span> | <span data-ttu-id="f8880-119">チームの画像</span><span class="sxs-lookup"><span data-stu-id="f8880-119">Team picture</span></span> |
| <span data-ttu-id="f8880-120">チームの説明</span><span class="sxs-lookup"><span data-stu-id="f8880-120">Team description</span></span> | <span data-ttu-id="f8880-121">チャンネル設定 (たとえば、自動お気に入りとプライバシー)</span><span class="sxs-lookup"><span data-stu-id="f8880-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="f8880-122">チームの可視性 (パブリックまたはプライベート)</span><span class="sxs-lookup"><span data-stu-id="f8880-122">Team visibility (public or private)</span></span> | <span data-ttu-id="f8880-123">コネクタ</span><span class="sxs-lookup"><span data-stu-id="f8880-123">Connectors</span></span> |
| <span data-ttu-id="f8880-124">チームの設定 (たとえば、メンバー、参照投稿 @ のゲスト)</span><span class="sxs-lookup"><span data-stu-id="f8880-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="f8880-125">ファイルとコンテンツ</span><span class="sxs-lookup"><span data-stu-id="f8880-125">Files and content</span></span> |
| <span data-ttu-id="f8880-126">自動お気に入りチャンネル</span><span class="sxs-lookup"><span data-stu-id="f8880-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="f8880-127">インストールされているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f8880-127">Installed app</span></span> | |
| <span data-ttu-id="f8880-128">固定タブ</span><span class="sxs-lookup"><span data-stu-id="f8880-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="f8880-129">複数のテンプレートの機能は、マイクロソフトのチームの今後のリリースを追加する、サポートされているプロパティには、最新の情報をチェックしてします。</span><span class="sxs-lookup"><span data-stu-id="f8880-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="f8880-130">基本テンプレートの種類を挙げてください。</span><span class="sxs-lookup"><span data-stu-id="f8880-130">What are base template types?</span></span>

<span data-ttu-id="f8880-131">基本テンプレートの種類とは、特定の業界にマイクロソフトが作成した特別なテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="f8880-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="f8880-132">多くの場合、これらの基本テンプレートには、チーム テンプレートでは個別にサポートされていないストアとチームのプロパティでは使用できない専用のアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8880-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="f8880-133">基本テンプレートの種類を定義すると、拡張したり、これらの特別なテンプレートを指定するには追加のプロパティをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f8880-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="f8880-134">ただし、いくつかの種類基本テンプレートにはでは、プロパティ オーバーライドすることはできませんにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8880-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="f8880-135">既定では、基本のテンプレートは、**標準的な**独自アプリケーションの追加や特別なプロパティが含まれていませんに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8880-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="f8880-136">次利用可能な基本テンプレートの種類の現在のリストに示します。</span><span class="sxs-lookup"><span data-stu-id="f8880-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="f8880-137">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="f8880-137">Base template type</span></span> | <span data-ttu-id="f8880-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f8880-138">baseTemplateId</span></span> | <span data-ttu-id="f8880-139">基本テンプレート専用のアプリケーションや特殊なプロパティ</span><span class="sxs-lookup"><span data-stu-id="f8880-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="f8880-140">Standard</span><span class="sxs-lookup"><span data-stu-id="f8880-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="f8880-141">なしのアプリケーションの追加とプロパティ</span><span class="sxs-lookup"><span data-stu-id="f8880-141">No additional apps and properties</span></span> |
| <span data-ttu-id="f8880-142">医療・ ケアの調整</span><span class="sxs-lookup"><span data-stu-id="f8880-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="f8880-143">アプリケーション:</span><span class="sxs-lookup"><span data-stu-id="f8880-143">Apps:</span></span><br/> <span data-ttu-id="f8880-144">-患者のアプリケーション ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="f8880-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="f8880-145">チャネル:</span><span class="sxs-lookup"><span data-stu-id="f8880-145">Channels:</span></span> <br/> <span data-ttu-id="f8880-146">-お知らせ</span><span class="sxs-lookup"><span data-stu-id="f8880-146">- Announcements</span></span><br/> <span data-ttu-id="f8880-147">-糖尿病</span><span class="sxs-lookup"><span data-stu-id="f8880-147">- Diabetes</span></span><br/> <span data-ttu-id="f8880-148">-Cardiovascular</span><span class="sxs-lookup"><span data-stu-id="f8880-148">- Cardiovascular</span></span><br/> <span data-ttu-id="f8880-149">-看護婦</span><span class="sxs-lookup"><span data-stu-id="f8880-149">- Registered nurses</span></span> |
| <span data-ttu-id="f8880-150">医療・ プロセスの huddle</span><span class="sxs-lookup"><span data-stu-id="f8880-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="f8880-151">チャネル:</span><span class="sxs-lookup"><span data-stu-id="f8880-151">Channels:</span></span><br/> <span data-ttu-id="f8880-152">-避け死亡記録</span><span class="sxs-lookup"><span data-stu-id="f8880-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="f8880-153">の mortality レビュー</span><span class="sxs-lookup"><span data-stu-id="f8880-153">- Mortality review</span></span> <br/> <span data-ttu-id="f8880-154">-滝を防止します。</span><span class="sxs-lookup"><span data-stu-id="f8880-154">- Preventing falls</span></span> <br/> <span data-ttu-id="f8880-155">の sepsis 計画</span><span class="sxs-lookup"><span data-stu-id="f8880-155">- Sepsis plans</span></span> |
| <span data-ttu-id="f8880-156">教育のクラスのチーム<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f8880-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="f8880-157">アプリケーション:</span><span class="sxs-lookup"><span data-stu-id="f8880-157">Apps:</span></span><br/> <span data-ttu-id="f8880-158">の OneNote クラスのノートブック ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="f8880-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="f8880-159">-割り当てのアプリケーション ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="f8880-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="f8880-160">チーム プロパティ</span><span class="sxs-lookup"><span data-stu-id="f8880-160">Team properties</span></span> <br/> <span data-ttu-id="f8880-161">チームの可視性 (オーバーライドできない) **HiddenMembership**に設定</span><span class="sxs-lookup"><span data-stu-id="f8880-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="f8880-162">教育のスタッフのチーム<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f8880-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="f8880-163">アプリ</span><span class="sxs-lookup"><span data-stu-id="f8880-163">Apps</span></span><br/> <span data-ttu-id="f8880-164">の OneNote スタッフのノートブック ([**全般**] タブに固定されている)</span><span class="sxs-lookup"><span data-stu-id="f8880-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="f8880-165">遅延 10 月、2018年の<sup>1</sup>の文書</span><span class="sxs-lookup"><span data-stu-id="f8880-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="f8880-166">追加されていく複数の基本テンプレート型の将来のマイクロソフトのチームのリリースに関する最新情報についてのチェックには、プロパティがサポートされているようです。</span><span class="sxs-lookup"><span data-stu-id="f8880-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="f8880-167">例</span><span class="sxs-lookup"><span data-stu-id="f8880-167">Examples</span></span> 

<span data-ttu-id="f8880-168">[Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview)をインストールすることでテンプレートを使用してチームの作成を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f8880-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="f8880-169">テンプレートからチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8880-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="f8880-170">要求</span><span class="sxs-lookup"><span data-stu-id="f8880-170">Requests</span></span>

<span data-ttu-id="f8880-171">**標準的な基本テンプレートを使用してチームを作成する要求**</span><span class="sxs-lookup"><span data-stu-id="f8880-171">**Request to create a team with the standard base template**</span></span>

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

<span data-ttu-id="f8880-172">**余分なチャネルを持つチームを作成し、チャンネルを削除してからメンバーを禁止するための要求**</span><span class="sxs-lookup"><span data-stu-id="f8880-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

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

<span data-ttu-id="f8880-173">**要求がサポートされているすべてのプロパティを使用してチームを作成するには**</span><span class="sxs-lookup"><span data-stu-id="f8880-173">**Request to create a team with all supported properties**</span></span>

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

#### <a name="response"></a><span data-ttu-id="f8880-174">応答</span><span class="sxs-lookup"><span data-stu-id="f8880-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="f8880-175">ステータスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f8880-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="f8880-176">要求</span><span class="sxs-lookup"><span data-stu-id="f8880-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="f8880-177">応答</span><span class="sxs-lookup"><span data-stu-id="f8880-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="f8880-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f8880-178">Related topics</span></span>

- <span data-ttu-id="f8880-179">[チームの作成](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams)(プレビュー) で</span><span class="sxs-lookup"><span data-stu-id="f8880-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="f8880-180">新しいチーム</span><span class="sxs-lookup"><span data-stu-id="f8880-180">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="f8880-181">Microsoft Teams の管理者トレーニング</span><span class="sxs-lookup"><span data-stu-id="f8880-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)