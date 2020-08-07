---
title: Microsoft Teams で people manager teams を作成する
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、チームメンバーとしての各マネージャー用にチームを作成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583676"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="c54f8-103">Microsoft Teams で people manager teams を作成する</span><span class="sxs-lookup"><span data-stu-id="c54f8-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="c54f8-104">"空のスレート" (チームまたはチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c54f8-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="c54f8-105">これにより、ユーザーが既存のチームでチャネルを作成する必要があるときに、ユーザーが多数のチームを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c54f8-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="c54f8-106">適切に設計されたチームとチャネル構造を使って作業を開始するには、第1行と2行の people マネージャーのチームを作成して、各マネージャーの直属の部下をチームメンバーとして作成する PowerShell スクリプトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="c54f8-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="c54f8-107">これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されたときに、チームやチャネルが自動的に更新されることはありません)。</span><span class="sxs-lookup"><span data-stu-id="c54f8-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="c54f8-108">ただし、チームの構造について、最初からいくつかの注文を課すために使用できる便利なツールです。</span><span class="sxs-lookup"><span data-stu-id="c54f8-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="c54f8-109">このスクリプトは Azure AD を読み取り、マネージャーとその直属の部下の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="c54f8-110">このリストを使って、people マネージャーごとに1つのチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="c54f8-111">PowerShell スクリプトの使い方</span><span class="sxs-lookup"><span data-stu-id="c54f8-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="c54f8-112">まず、[エクスポートマネージャーとそのリダイレクトスクリプト](scripts/powershell-script-create-teams-from-managers-export-managers.md)を実行します (これは、 [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)と[connect-microsoft teams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps)の PowerShell モジュールを既に実行していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="c54f8-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="c54f8-113">*エクスポートマネージャーとそのリダイレクト*スクリプトは、タブ区切りのファイル (ExportedManagerDirects.txt) を作成し、すべてのマネージャーに直属の部下を表示します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="c54f8-114">次に、[[新しい people manager teams の作成] スクリプト](scripts/powershell-script-create-teams-from-managers-new-teams.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="c54f8-115">このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、そのマネージャーの直属の部下としてメンバーとしてチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="c54f8-116">いずれかのマネージャーまたはダイレクトが Teams で有効になっていない場合は、スクリプトはスキップし、チームは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c54f8-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="c54f8-117">(レポートを確認し、必要なユーザーのチームをオンにした後でスクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="c54f8-118">スクリプトでは、チームが既に作成されている管理者に対して、2つ目のチームは作成されません。</span><span class="sxs-lookup"><span data-stu-id="c54f8-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="c54f8-119">各チームの場合、スクリプトによって一般的なチャネルと "楽しい" のチャネルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c54f8-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="c54f8-120">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c54f8-120">Best practices</span></span>

- <span data-ttu-id="c54f8-121">各メンバーマネージャーに、組織の危機管理 web サイトをタブとして各チームの [全般] チャネルに追加するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="c54f8-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="c54f8-122">次の「2020年3月8日のブログ投稿: [Microsoft Teams + Power Platform を使った危機通信の調整](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)」を参照して、新しい危機通信アプリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c54f8-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c54f8-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c54f8-123">Related topics</span></span>

[<span data-ttu-id="c54f8-124">チームを編成するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c54f8-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="c54f8-125">Teams で組織全体にわたるチームを作成する</span><span class="sxs-lookup"><span data-stu-id="c54f8-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
