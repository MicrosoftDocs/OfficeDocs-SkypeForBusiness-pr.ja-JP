---
title: Microsoft Teams で People Manager チームを作成する
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして作成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094413"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="04c68-103">Microsoft Teams で People Manager チームを作成する</span><span class="sxs-lookup"><span data-stu-id="04c68-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="04c68-104">"空白のスレート" (チームまたはチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="04c68-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="04c68-105">これにより、ユーザーが既存のチームでチャネルを作成する必要があるときに多数のチームを作成する "チームの広がり" を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04c68-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="04c68-106">よく設計されたチームとチャネル構造の使用を開始するために、各マネージャーの直販レポートをチーム メンバーとして使用して、最初と 2 行目の各担当者のチームを作成する PowerShell スクリプトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="04c68-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="04c68-107">これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されると、チームまたはチャネルは自動的に更新されません)。</span><span class="sxs-lookup"><span data-stu-id="04c68-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="04c68-108">ただし、最初から Teams の構造に何らかの注文を課すのに使用できる貴重なツールです。</span><span class="sxs-lookup"><span data-stu-id="04c68-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="04c68-109">このスクリプトは Azure アカウントを読AD、マネージャーとその直下のレポートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="04c68-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="04c68-110">このリストを使用して、ユーザー マネージャーごとに 1 つのチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="04c68-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="04c68-111">PowerShell スクリプトの使い方</span><span class="sxs-lookup"><span data-stu-id="04c68-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="04c68-112">まず、 [エクスポート](scripts/powershell-script-create-teams-from-managers-export-managers.md) マネージャーとその直販スクリプトを実行します [(Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) および [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell モジュールを既に実行している場合)。</span><span class="sxs-lookup"><span data-stu-id="04c68-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="04c68-113">エクスポート *マネージャーとその直* 職スクリプトでは、すべてのマネージャーが直販レポートを含むタブ区切りファイル (ExportedManagerDirects.txt) を作成します。</span><span class="sxs-lookup"><span data-stu-id="04c68-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="04c68-114">次に、新しい [People Manager チームの作成スクリプトを実行します](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="04c68-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="04c68-115">このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、各マネージャーのチームを作成し、そのマネージャーの直下の部下をメンバーとして作成します。</span><span class="sxs-lookup"><span data-stu-id="04c68-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="04c68-116">マネージャーまたは直職が Teams に対して有効になっていない場合、スクリプトはそれらをスキップし、チームを作成しません。</span><span class="sxs-lookup"><span data-stu-id="04c68-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="04c68-117">(レポートを確認し、必要なユーザーに対して Teams を有効にした後、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="04c68-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="04c68-118">スクリプトでは、既にチームを作成しているマネージャーの 2 番目のチームは作成されません)。</span><span class="sxs-lookup"><span data-stu-id="04c68-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="04c68-119">チームごとに、スクリプトによって [全般] チャネルと [楽しみのために] チャネルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="04c68-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="04c68-120">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="04c68-120">Best practices</span></span>

- <span data-ttu-id="04c68-121">各メンバー マネージャーに、チームごとに [全般] チャネルにタブとして組織のクライシス コミュニケーション Web サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="04c68-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="04c68-122">2020 年 3 月 8 日のブログ投稿「Microsoft Teams + Power Platform を使用してクライシス コミュニケーションを調整する」を参照して、新しいクライシス コミュニケーション アプリ [を確認してください](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。</span><span class="sxs-lookup"><span data-stu-id="04c68-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="04c68-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c68-123">Related topics</span></span>

[<span data-ttu-id="04c68-124">チームを編成するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="04c68-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="04c68-125">Teams で組織全体にわたるチームを作成する</span><span class="sxs-lookup"><span data-stu-id="04c68-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)