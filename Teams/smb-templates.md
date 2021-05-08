---
title: Teams Microsoft Graph を使用して構築された中小企業向けのテンプレート
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Microsoft Microsoft Teamsに組み込Graphテンプレートを使用して、中小企業向けのチームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116995"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="7652c-103">Teams Microsoft Graph for Small and Medium Businesses に組み込みのテンプレート</span><span class="sxs-lookup"><span data-stu-id="7652c-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="7652c-104">Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="7652c-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7652c-105">中小企業の場合、テンプレートは特に強力な機能を備え、管理者は組織全体にTeamsを迅速にデプロイするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7652c-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="7652c-106">テンプレートは、ユーザーを方向付けし、効果的に使用Teamsにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7652c-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="7652c-107">この記事は、組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7652c-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="7652c-108">現在、さまざまな状況で利用できる 3 つのファースト パーティ SMB テンプレートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7652c-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="7652c-109">すべてのテンプレートでプライベート テンプレート *がTeams。*</span><span class="sxs-lookup"><span data-stu-id="7652c-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="7652c-110">アプリケーションを作成Teams組織に展開する準備ができたら、必要に応じてプライバシーを *Org-Wide* または *Public* に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7652c-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="7652c-111">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="7652c-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="7652c-112">Company-Wide テンプレート</span><span class="sxs-lookup"><span data-stu-id="7652c-112">Company-Wide template</span></span>
<span data-ttu-id="7652c-113">このCompany-Wideは、会社全体に関連するコミュニケーションとコラボレーションを意図しています。</span><span class="sxs-lookup"><span data-stu-id="7652c-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="7652c-114">会社全体のお知らせ、業界ニュース、またはエグゼクティブの投稿には、[全般] チャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7652c-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="7652c-115">人事チャネルは、ジョブの投稿、新しい従業員のオンボーディング、トレーニング、開発など、人事関連のすべてのアクティビティを統合する最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="7652c-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="7652c-116">[Fun Stuff] チャネルは、すべてのランダムで楽しい投稿にソーシャル プラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="7652c-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="7652c-117">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="7652c-117">Base template type</span></span>  | <span data-ttu-id="7652c-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7652c-118">baseTemplateId</span></span> | <span data-ttu-id="7652c-119">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="7652c-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="7652c-120">SMB -</span></span> <br><span data-ttu-id="7652c-121">会社全体</span><span class="sxs-lookup"><span data-stu-id="7652c-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="7652c-122">チャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-122">Channels</span></span> <ul><li><span data-ttu-id="7652c-123">全般\*</span><span class="sxs-lookup"><span data-stu-id="7652c-123">General\*</span></span></li><li><span data-ttu-id="7652c-124">人事\*</span><span class="sxs-lookup"><span data-stu-id="7652c-124">Human Resources\*</span></span></li><li><span data-ttu-id="7652c-125">楽しい情報\*</span><span class="sxs-lookup"><span data-stu-id="7652c-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="7652c-126">アプリ</span><span class="sxs-lookup"><span data-stu-id="7652c-126">Apps</span></span><ul><li><span data-ttu-id="7652c-127">ポータル サイト (人事チャネルにピン留めされた Web **サイト**)</span><span class="sxs-lookup"><span data-stu-id="7652c-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="7652c-128">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-128">Team properties</span></span> <ul><li><span data-ttu-id="7652c-129">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="7652c-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="7652c-130">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="7652c-131">定義済みのテンプレートCompany-Wide既定値を取得してチームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="7652c-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="7652c-132">テンプレートをデプロイする方法の詳細についてはTeamsチームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="7652c-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="7652c-133">要求</span><span class="sxs-lookup"><span data-stu-id="7652c-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="7652c-134">エグゼクティブ チーム テンプレート</span><span class="sxs-lookup"><span data-stu-id="7652c-134">Executive Team template</span></span>

<span data-ttu-id="7652c-135">エグゼクティブ チーム テンプレートは、年間の優先順位、会計予算、戦略イニシアティブ、トップ クライアントなどの会社のイニシアティブについて、会社のエグゼクティブがコミュニケーションを取り、共同作業するためのチームを作成する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="7652c-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="7652c-136">このテンプレートには、特定のトピック *の* 選択したユーザーを招待するプライベート チャネルが付属しています。</span><span class="sxs-lookup"><span data-stu-id="7652c-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="7652c-137">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="7652c-137">Base template type</span></span>  | <span data-ttu-id="7652c-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7652c-138">baseTemplateId</span></span> | <span data-ttu-id="7652c-139">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="7652c-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="7652c-140">SMB -</span></span> <br><span data-ttu-id="7652c-141">エグゼクティブ チーム</span><span class="sxs-lookup"><span data-stu-id="7652c-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="7652c-142">チャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-142">Channels</span></span> <ul><li><span data-ttu-id="7652c-143">全般\*</span><span class="sxs-lookup"><span data-stu-id="7652c-143">General\*</span></span></li><li><span data-ttu-id="7652c-144">プライベート \*</span><span class="sxs-lookup"><span data-stu-id="7652c-144">Private \*</span></span></li></ul> <span data-ttu-id="7652c-145">アプリ</span><span class="sxs-lookup"><span data-stu-id="7652c-145">Apps</span></span><ul><li><span data-ttu-id="7652c-146">OneNote (プライベート チャンネルに **ピン留め**)</span><span class="sxs-lookup"><span data-stu-id="7652c-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="7652c-147">Planner (プライベート チャネル **にピン留め** )</span><span class="sxs-lookup"><span data-stu-id="7652c-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="7652c-148">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-148">Team properties</span></span> <ul><li><span data-ttu-id="7652c-149">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="7652c-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="7652c-150">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="7652c-151">定義済みのテンプレートから既定値を取得して Executives チームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="7652c-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="7652c-152">テンプレートをデプロイする方法の詳細についてはTeamsチームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="7652c-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="7652c-153">要求</span><span class="sxs-lookup"><span data-stu-id="7652c-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="7652c-154">部門チーム テンプレート</span><span class="sxs-lookup"><span data-stu-id="7652c-154">Departmental Team template</span></span>

<span data-ttu-id="7652c-155">部門チーム テンプレートは、個々の部門またはプロジェクトのチームを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7652c-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="7652c-156">財務チーム テンプレートは、必要に応じて、財務チーム メンバーおよびエグゼクティブ チーム メンバー内のすべての投稿、お知らせ、毎日の共同作業とコミュニケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="7652c-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="7652c-157">このテンプレートには、特定のトピック *の選択* したユーザーを招待するプライベート チャネルが付属しています。</span><span class="sxs-lookup"><span data-stu-id="7652c-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="7652c-158">また、お好みで追加、削除、または編集することで、追加の部門や特定のプロジェクトにテンプレートを拡張するために使用できる財務チーム向けスクリプトも以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7652c-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="7652c-159">たとえば、マーケティング部門がある場合は、財務からマーケティングにチームの名前を変更して新しいマーケティングチームを作成することで、スクリプトを調整できます。 </span><span class="sxs-lookup"><span data-stu-id="7652c-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="7652c-160">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="7652c-160">Base template type</span></span> | <span data-ttu-id="7652c-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7652c-161">baseTemplateId</span></span> | <span data-ttu-id="7652c-162">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="7652c-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="7652c-163">SMB -</span></span> <br><span data-ttu-id="7652c-164">Finance</span><span class="sxs-lookup"><span data-stu-id="7652c-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="7652c-165">チャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-165">Channels</span></span> <ul><li><span data-ttu-id="7652c-166">全般\*</span><span class="sxs-lookup"><span data-stu-id="7652c-166">General\*</span></span></li><li><span data-ttu-id="7652c-167">プライベート \*</span><span class="sxs-lookup"><span data-stu-id="7652c-167">Private \*</span></span></li></ul><br> <span data-ttu-id="7652c-168">アプリ</span><span class="sxs-lookup"><span data-stu-id="7652c-168">Apps</span></span><ul><li><span data-ttu-id="7652c-169">OneNote (プライベート チャンネルに **ピン留め**)</span><span class="sxs-lookup"><span data-stu-id="7652c-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="7652c-170">Planner (プライベート チャネル **にピン留め** )</span><span class="sxs-lookup"><span data-stu-id="7652c-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="7652c-171">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7652c-171">Team properties</span></span> <ul><li><span data-ttu-id="7652c-172">チームの可視性を非公開に設定</span><span class="sxs-lookup"><span data-stu-id="7652c-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="7652c-173">\*自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="7652c-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="7652c-174">定義済みのテンプレートから既定値を取得して財務チームを作成するには、要求本文に team オブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="7652c-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="7652c-175">テンプレートをデプロイする方法の詳細についてはTeamsチームの作成に関する Microsoft Graph[記事を参照してください](/graph/api/team-post?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="7652c-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="7652c-176">要求</span><span class="sxs-lookup"><span data-stu-id="7652c-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="7652c-177">例: Finance Team テンプレート拡張機能スクリプト</span><span class="sxs-lookup"><span data-stu-id="7652c-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="7652c-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7652c-178">Related topics</span></span>

- [<span data-ttu-id="7652c-179">管理コンソールでTeamsテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7652c-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="7652c-180">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7652c-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="7652c-181">[チームを作成](/graph/api/team-post?view=graph-rest-beta) する (プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="7652c-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>