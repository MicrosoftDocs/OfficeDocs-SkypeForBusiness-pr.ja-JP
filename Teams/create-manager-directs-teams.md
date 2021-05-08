---
title: Microsoft Teams で People Manager チームを作成する
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして直接作成する方法について説明します。
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="9651f-103">Microsoft Teams で People Manager チームを作成する</span><span class="sxs-lookup"><span data-stu-id="9651f-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="9651f-104">"空白のスレート" (チームやチャネルなし) で起動するのではなく、Microsoft Teams を展開する場合は、チームとチャネルの基本フレームワークを設定することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9651f-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="9651f-105">これは、ユーザーが既存のチームでチャネルを作成する必要があるときに多数のチームを作成する "チームの広がり" を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9651f-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="9651f-106">うまく設計されたチームとチャネルの構造を使い始めるのに役立つ PowerShell スクリプトを作成しました。このスクリプトでは、各マネージャーの直下の部下をチーム メンバーとして、1 番目と 2 番目の各担当者マネージャーのチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9651f-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="9651f-107">これは "ポイントインタイム" スクリプトです (ユーザーが組織に追加または削除されると、チームやチャネルは自動的に更新されません)。</span><span class="sxs-lookup"><span data-stu-id="9651f-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="9651f-108">ただし、最初からシステム構造に何らかの順序を付けるTeamsツールです。</span><span class="sxs-lookup"><span data-stu-id="9651f-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="9651f-109">このスクリプトは、Azure ADを読み取り、マネージャーとその直下のレポートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9651f-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="9651f-110">このリストを使用して、People マネージャーごとに 1 つのチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9651f-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="9651f-111">PowerShell スクリプトの使い方</span><span class="sxs-lookup"><span data-stu-id="9651f-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="9651f-112">まず、エクスポート マネージャーとその直接[スクリプトを実行](scripts/powershell-script-create-teams-from-managers-export-managers.md)します ([これは、Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0)モジュールと[Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell モジュールを既に実行済みである場合)。</span><span class="sxs-lookup"><span data-stu-id="9651f-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="9651f-113">エクスポート *マネージャーとその* 直接スクリプトでは、すべてのマネージャーを直接レポートと一覧表示するタブ区切りファイル (ExportedManagerDirects.txt) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9651f-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="9651f-114">次に、新しい [People マネージャー チームの作成スクリプト を実行します](scripts/powershell-script-create-teams-from-managers-new-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9651f-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="9651f-115">このスクリプトは、ExportedManagerDirects.txt ファイルを読み取り、各マネージャーのチームを作成し、そのマネージャーの直接レポートをメンバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="9651f-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="9651f-116">管理者または監督が管理者に対して有効になっていないTeamsスクリプトはそれらをスキップし、チームを作成しません。</span><span class="sxs-lookup"><span data-stu-id="9651f-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="9651f-117">(レポートを確認し、必要なユーザーに対して Teamsを有効にした後、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="9651f-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="9651f-118">スクリプトでは、既にチームを作成しているマネージャーの 2 つ目のチームは作成されません)。</span><span class="sxs-lookup"><span data-stu-id="9651f-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="9651f-119">各チームについて、スクリプトは General チャネルと "Just for fun" チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9651f-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="9651f-120">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="9651f-120">Best practices</span></span>

- <span data-ttu-id="9651f-121">各チームの [全般] チャネルにタブとして組織の危機コミュニケーション Web サイトを追加して、各人のマネージャーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="9651f-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="9651f-122">2020 年 3 月 8 日のブログ投稿「Microsoft Teams + Power Platform を使用して危機的な通信を調整する」を参照して、新しいクライ[シス コミュニケーション アプリを確認してください](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)。</span><span class="sxs-lookup"><span data-stu-id="9651f-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9651f-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9651f-123">Related topics</span></span>

[<span data-ttu-id="9651f-124">チームを編成するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="9651f-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="9651f-125">Teams で組織全体にわたるチームを作成する</span><span class="sxs-lookup"><span data-stu-id="9651f-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)