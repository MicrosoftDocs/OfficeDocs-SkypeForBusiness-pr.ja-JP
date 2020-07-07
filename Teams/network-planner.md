---
title: Microsoft Teams で Network Planner を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 管理者は、Network Planner を使用して、Microsoft Teams のネットワーク要件を特定する方法についてを知ることができます。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a4676349dab9c7b587e63dcc9a538c9f0b43a80
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904799"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="cfcd2-103">Microsoft Teams で Network Planner を使用する</span><span class="sxs-lookup"><span data-stu-id="cfcd2-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="cfcd2-104">Network Planner は、Teams 管理センターで利用できる新しいツールです。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="cfcd2-105">これは、**プランナー**  >  **Network Planner** でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-105">It can be found by going to **Planner** > **Network planner**.</span></span> <span data-ttu-id="cfcd2-106">ほんの少しの手順で、Network Planner では組織全体で Microsoft Teams ユーザーに接続するためのネットワーク要件を決定し、整理できます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="cfcd2-107">ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Network Planner のスクリーンショット](media/network-planner.png)

<span data-ttu-id="cfcd2-109">Network Planner では次のことができます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-109">Network Planner allows you to:</span></span>

- <span data-ttu-id="cfcd2-110">サイトと Microsoft 推奨のペルソナ (オフィス ワーカー、リモート ワーカー、Teams ルーム システム) を使用して組織の表現を作成します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfcd2-111">推奨されるペルソナは、Teams の最適な使用シナリオと一般的な使用パターンに基づいて開発されました。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="cfcd2-112">ただし、推奨される3つのペルソナに加えて、最大3つのカスタム ペルソナを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="cfcd2-113">Teams の使用状況の帯域幅要件に関するレポートを作成し計算します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="cfcd2-114">Network Planner を使用するには、グローバル管理者、Teams サービス管理者、または Teams 通信管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-114">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="cfcd2-115">カスタム ペルソナを作成する</span><span class="sxs-lookup"><span data-stu-id="cfcd2-115">Create a custom persona</span></span>

<span data-ttu-id="cfcd2-116">カスタム レポートを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="cfcd2-117">Microsoft Teams 管理センターの Network Planner にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-117">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="cfcd2-118">[**ペルソナ**] タブで、[**+ カスタム ペルソナ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="cfcd2-119">**新しいカスタム ペルソナ** ウィンドウで、新しいペルソナの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="cfcd2-120">このペルソナが組織内で使用するアクセス権を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="cfcd2-121">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="cfcd2-122">プランを作成する</span><span class="sxs-lookup"><span data-stu-id="cfcd2-122">Build your plan</span></span>

<span data-ttu-id="cfcd2-123">ネットワーク プランを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="cfcd2-124">Microsoft Teams 管理センターの Network Planner にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-124">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="cfcd2-125">[**ネットワーク プラン**] タブで、[**ネットワーク プランの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="cfcd2-126">新しいネットワーク プランの名前と説明を入力してください。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="cfcd2-127">使用可能なプランのリストにネットワーク プランが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="cfcd2-128">プラン名をクリックして新しいプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="cfcd2-129">組織のネットワーク セットアップを作成するには、サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="cfcd2-130">組織のネットワークによっては、ビル、オフィスの位置、またその他を表現するのにサイトを使用したい場合があるでしょう。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="cfcd2-131">サイトは WAN によって接続され、インターネットや PSTN の接続が共有できるようになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="cfcd2-132">最良の結果を得るには、インターネットまたは PSTN にリモート接続するサイトを作成する前に、ローカル接続を使用してサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="cfcd2-133">サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="cfcd2-133">To create a site:</span></span>

    1. <span data-ttu-id="cfcd2-134">サイトの名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="cfcd2-135">[**ネットワーク設定**] の下に、そのサイトのネットワーク ユーザー数を追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="cfcd2-136">ネットワークの詳細を追加します。WAN 対応、WAN 容量、インターネット エグレス (**ローカル** または **リモート**)、PSTN エグレス (なし、ローカル、またはリモート)。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="cfcd2-137">レポートを生成するときに、特定の帯域幅の推奨値を表示するには、WAN およびインターネットの容量を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="cfcd2-138">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="cfcd2-139">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="cfcd2-139">Create a report</span></span>

<span data-ttu-id="cfcd2-140">すべてのサイトを追加したら、次のようにレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="cfcd2-141">[**レポート**] タブで、[**レポートを開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="cfcd2-142">作成する各サイトについて、使用可能なペルソナにユーザー数を分配します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="cfcd2-143">Microsoft が推奨するペルソナを使用している場合、この数字は自動的に分配されます (オフィス ワーカーが 80% で、リモートワーカーが 20%)。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="cfcd2-144">分配が完了したら、**レポートの作成**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="cfcd2-145">生成されたレポートには、次のようなさまざまなビューの帯域幅要件が表示されるので、出力を正確に理解できます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="cfcd2-146">個々の計算を含むテーブルには、許可されている各アクティビティの帯域幅要件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="cfcd2-147">追加のビューには、推奨事項による全体的な帯域幅ニーズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="cfcd2-148">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-148">Click **Save**.</span></span> <span data-ttu-id="cfcd2-149">レポートはレポート リストで、後で表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="cfcd2-150">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="cfcd2-150">Example scenario</span></span>

<span data-ttu-id="cfcd2-151">Network Planner を使用してネットワーク プランをセットアップし、これらの手順でレポートを生成する方法の例を見るには、[Network Planner の使用方法に関する PowerPoint デック](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)　(英語のみ) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-151">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
