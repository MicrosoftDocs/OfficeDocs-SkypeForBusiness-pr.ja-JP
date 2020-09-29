---
title: Microsoft Graph で構築されている中小企業向けの Teams テンプレート
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
description: Microsoft Graph に組み込まれている Microsoft Teams の組み込みテンプレートを使用して、中小規模企業向けのチームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294553"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="ffe89-103">中小規模企業向け Microsoft Graph で構築されたチームテンプレート</span><span class="sxs-lookup"><span data-stu-id="ffe89-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="ffe89-104">Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ffe89-105">小規模または中規模の企業では、管理者が組織全体にチームをすばやく展開できるように、テンプレートを特に強力にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="ffe89-106">テンプレートを使用すると、ユーザーの向きを確認したり、チームの効率的な使い方を始めることができます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="ffe89-107">この記事は、組織内の複数のチームの計画、展開、管理を担当しているユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="ffe89-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="ffe89-108">現時点では、さまざまな状況に応じて利用できる、3つのファーストパーティの SMB テンプレートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ffe89-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="ffe89-109">すべてのテンプレートによって *プライベート* チームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="ffe89-110">チームを作成し、組織に展開する準備ができたら、必要に応じてプライバシーを *組織全体* または *一般*向けに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="ffe89-111">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe89-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="ffe89-112">会社全体のテンプレート</span><span class="sxs-lookup"><span data-stu-id="ffe89-112">Company-Wide template</span></span>
<span data-ttu-id="ffe89-113">会社全体のテンプレートは、会社全体に関連したコミュニケーションとコラボレーションを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ffe89-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="ffe89-114">[全般] チャネルは、会社全体のお知らせ、業界ニュース、役員の投稿に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="ffe89-115">人事チャネルは、求人、新入社員のオンボード、トレーニング、開発など、人事関連のすべてのアクティビティを統合するのに最適な場所です。</span><span class="sxs-lookup"><span data-stu-id="ffe89-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="ffe89-116">楽しい機能チャネルは、すべてのランダムで楽しい投稿のソーシャルプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="ffe89-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="ffe89-117">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="ffe89-117">Base template type</span></span>  | <span data-ttu-id="ffe89-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ffe89-118">baseTemplateId</span></span> | <span data-ttu-id="ffe89-119">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ffe89-120">中堅</span><span class="sxs-lookup"><span data-stu-id="ffe89-120">SMB -</span></span> <br><span data-ttu-id="ffe89-121">会社全体</span><span class="sxs-lookup"><span data-stu-id="ffe89-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="ffe89-122">チャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-122">Channels</span></span> <ul><li><span data-ttu-id="ffe89-123">一般\*</span><span class="sxs-lookup"><span data-stu-id="ffe89-123">General\*</span></span></li><li><span data-ttu-id="ffe89-124">人事\*</span><span class="sxs-lookup"><span data-stu-id="ffe89-124">Human Resources\*</span></span></li><li><span data-ttu-id="ffe89-125">楽しい機能\*</span><span class="sxs-lookup"><span data-stu-id="ffe89-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="ffe89-126">アプリ</span><span class="sxs-lookup"><span data-stu-id="ffe89-126">Apps</span></span><ul><li><span data-ttu-id="ffe89-127">会社ポータル ( **人事** チャネルに固定された web サイト)</span><span class="sxs-lookup"><span data-stu-id="ffe89-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="ffe89-128">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-128">Team properties</span></span> <ul><li><span data-ttu-id="ffe89-129">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="ffe89-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="ffe89-130">\* 自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="ffe89-131">定義済みのテンプレートから既定のテンプレートを取得して会社全体のチームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe89-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ffe89-132">Teams テンプレートの展開方法について詳しくは、「 [チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffe89-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ffe89-133">要求</span><span class="sxs-lookup"><span data-stu-id="ffe89-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="ffe89-134">エグゼクティブチームテンプレート</span><span class="sxs-lookup"><span data-stu-id="ffe89-134">Executive Team template</span></span>

<span data-ttu-id="ffe89-135">エグゼクティブチームテンプレートは、会社の役員向けのチームを作成して、年間の優先度、会計予算、戦略的イニシアチブ、トップクライアントなど、会社のイニシアチブを伝達して共同作業するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="ffe89-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="ffe89-136">このテンプレートには、特定のトピックについて選択したユーザーを招待するための *プライベート* チャネルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ffe89-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="ffe89-137">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="ffe89-137">Base template type</span></span>  | <span data-ttu-id="ffe89-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ffe89-138">baseTemplateId</span></span> | <span data-ttu-id="ffe89-139">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ffe89-140">中堅</span><span class="sxs-lookup"><span data-stu-id="ffe89-140">SMB -</span></span> <br><span data-ttu-id="ffe89-141">エグゼクティブチーム</span><span class="sxs-lookup"><span data-stu-id="ffe89-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="ffe89-142">チャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-142">Channels</span></span> <ul><li><span data-ttu-id="ffe89-143">一般\*</span><span class="sxs-lookup"><span data-stu-id="ffe89-143">General\*</span></span></li><li><span data-ttu-id="ffe89-144">外字 \*</span><span class="sxs-lookup"><span data-stu-id="ffe89-144">Private \*</span></span></li></ul> <span data-ttu-id="ffe89-145">アプリ</span><span class="sxs-lookup"><span data-stu-id="ffe89-145">Apps</span></span><ul><li><span data-ttu-id="ffe89-146">OneNote ( **プライベート** チャネルに固定されています)</span><span class="sxs-lookup"><span data-stu-id="ffe89-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="ffe89-147">Planner ( **プライベート** チャネルに固定されています)</span><span class="sxs-lookup"><span data-stu-id="ffe89-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="ffe89-148">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-148">Team properties</span></span> <ul><li><span data-ttu-id="ffe89-149">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="ffe89-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="ffe89-150">\* 自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="ffe89-151">定義済みのテンプレートから既定値を取得してエグゼクティブチームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe89-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ffe89-152">Teams テンプレートの展開方法について詳しくは、「 [チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffe89-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ffe89-153">要求</span><span class="sxs-lookup"><span data-stu-id="ffe89-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="ffe89-154">部門チームテンプレート</span><span class="sxs-lookup"><span data-stu-id="ffe89-154">Departmental Team template</span></span>

<span data-ttu-id="ffe89-155">部門チームテンプレートを使用して、個々の部門またはプロジェクトのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="ffe89-156">財務チームテンプレートは、財務チームメンバーと役員チームメンバー内のすべての投稿、お知らせ、および毎日の共同作業、および日常のコミュニケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="ffe89-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="ffe89-157">このテンプレートには、特定のトピックについてのユーザーを選択するための *プライベート* チャネルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ffe89-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="ffe89-158">また、お好みに合わせて追加、削除、または編集することで、テンプレートを追加の部署または特定のプロジェクトに拡張するために使用できる、次のような財務チーム用のスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="ffe89-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="ffe89-159">たとえば、 *マーケティング* 部門を使用している場合は、 *財務* から *マーケティング* にチームの名前を変更して新しいマーケティングチームを作成することによって、スクリプトを調整できます。</span><span class="sxs-lookup"><span data-stu-id="ffe89-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="ffe89-160">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="ffe89-160">Base template type</span></span> | <span data-ttu-id="ffe89-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ffe89-161">baseTemplateId</span></span> | <span data-ttu-id="ffe89-162">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ffe89-163">中堅</span><span class="sxs-lookup"><span data-stu-id="ffe89-163">SMB -</span></span> <br><span data-ttu-id="ffe89-164">Finance</span><span class="sxs-lookup"><span data-stu-id="ffe89-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="ffe89-165">チャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-165">Channels</span></span> <ul><li><span data-ttu-id="ffe89-166">一般\*</span><span class="sxs-lookup"><span data-stu-id="ffe89-166">General\*</span></span></li><li><span data-ttu-id="ffe89-167">外字 \*</span><span class="sxs-lookup"><span data-stu-id="ffe89-167">Private \*</span></span></li></ul><br> <span data-ttu-id="ffe89-168">アプリ</span><span class="sxs-lookup"><span data-stu-id="ffe89-168">Apps</span></span><ul><li><span data-ttu-id="ffe89-169">OneNote ( **プライベート** チャネルに固定されています)</span><span class="sxs-lookup"><span data-stu-id="ffe89-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="ffe89-170">Planner ( **プライベート** チャネルに固定されています)</span><span class="sxs-lookup"><span data-stu-id="ffe89-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="ffe89-171">チームのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ffe89-171">Team properties</span></span> <ul><li><span data-ttu-id="ffe89-172">チームの表示はプライベートに設定</span><span class="sxs-lookup"><span data-stu-id="ffe89-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="ffe89-173">\* 自動お気に入りチャネル</span><span class="sxs-lookup"><span data-stu-id="ffe89-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="ffe89-174">定義済みのテンプレートから既定値を取得して財務チームを作成するには、要求本文にチームオブジェクトの JSON 表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe89-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ffe89-175">Teams テンプレートの展開方法について詳しくは、「 [チームの作成」の](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffe89-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ffe89-176">要求</span><span class="sxs-lookup"><span data-stu-id="ffe89-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="ffe89-177">例: 財務チームテンプレート拡張スクリプト</span><span class="sxs-lookup"><span data-stu-id="ffe89-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="ffe89-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffe89-178">Related topics</span></span>

- [<span data-ttu-id="ffe89-179">管理コンソールで Teams のテンプレートを使ってみる</span><span class="sxs-lookup"><span data-stu-id="ffe89-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="ffe89-180">Teams のテンプレートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="ffe89-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="ffe89-181">[チームを作成する](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="ffe89-181">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

