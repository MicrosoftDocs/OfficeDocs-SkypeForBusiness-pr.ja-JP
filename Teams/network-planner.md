---
title: Microsoft Teams のネットワークプランナーを使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: ネットワークプランナーを使用して、Microsoft Teams のネットワーク要件を特定する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c05aa9cba7305b755d4e9290467c92cf71244095
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701568"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="d8fc8-103">Microsoft Teams のネットワークプランナーを使用する</span><span class="sxs-lookup"><span data-stu-id="d8fc8-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="d8fc8-104">ネットワークプランナーへようこそ。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-104">Welcome to the Network Planner.</span></span> <span data-ttu-id="d8fc8-105">わずかな手順で、ネットワークプランナーを使用して、組織全体で Microsoft Teams ユーザーと接続するためのネットワーク要件を特定し、整理することができます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-105">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="d8fc8-106">ネットワークの詳細とチームの利用状況を入力すると、ネットワーク Planner によって、組織の物理的な場所でチームとクラウドボイスを展開するためのネットワーク要件が計算されます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-106">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![ネットワークプランナーのスクリーンショット](media/network-planner.png)

<span data-ttu-id="d8fc8-108">ネットワークプランナーでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-108">Network Planner allows you to:</span></span>

- <span data-ttu-id="d8fc8-109">サイトと Microsoft の推奨されるペルソナ (office worker、リモートワーカー、チームルームシステム) を使用して、組織の表現を作成します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-109">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8fc8-110">推奨されるペルソナは、Teams の最適使用シナリオと一般的な使用パターンのデータに基づいて開発されました。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-110">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="d8fc8-111">ただし、3つの推奨されるペルソナに加えて、最大3つのカスタムペルソナを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-111">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="d8fc8-112">チームの利用状況に関するレポートを生成し、帯域幅要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-112">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="d8fc8-113">ネットワークプランナーを使用するには、グローバル管理者、Teams サービス管理者、またはチームコミュニケーション管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-113">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="d8fc8-114">ユーザー設定のペルソナを作成する</span><span class="sxs-lookup"><span data-stu-id="d8fc8-114">Create a custom persona</span></span>

<span data-ttu-id="d8fc8-115">カスタムペルソナを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-115">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="d8fc8-116">Microsoft Teams 管理センターのネットワークプランナーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-116">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d8fc8-117">[**ペルソナ**] タブで、[ **+ カスタムペルソナ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-117">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="d8fc8-118">**新しいユーザー設定**の [ペルソナ] ウィンドウで、新しいペルソナの名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-118">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="d8fc8-119">このペルソナが組織内で使用する権限を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-119">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="d8fc8-120">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-120">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="d8fc8-121">プランを作成する</span><span class="sxs-lookup"><span data-stu-id="d8fc8-121">Build your plan</span></span>

<span data-ttu-id="d8fc8-122">ネットワーク計画の作成を開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-122">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="d8fc8-123">Microsoft Teams 管理センターのネットワークプランナーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-123">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d8fc8-124">[**ネットワーク計画**] タブで、[**ネットワーク計画の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-124">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="d8fc8-125">ネットワーク計画の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-125">Enter a name and description for your network plan.</span></span> <span data-ttu-id="d8fc8-126">利用可能なプランの一覧にネットワーク計画が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-126">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="d8fc8-127">プラン名をクリックして、新しいプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-127">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="d8fc8-128">組織のネットワークセットアップの表現を作成するために、サイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-128">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="d8fc8-129">組織のネットワークによっては、建物、オフィスの場所、または他のものを表すサイトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-129">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="d8fc8-130">インターネットや PSTN 接続の共有を可能にするために、サイトは WAN によって接続されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-130">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="d8fc8-131">最善の結果を得るには、インターネットまたは PSTN にリモート接続するサイトを作成する前に、ローカル接続を使用してサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-131">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="d8fc8-132">サイトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="d8fc8-132">To create a site:</span></span>

    1. <span data-ttu-id="d8fc8-133">サイトの名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-133">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="d8fc8-134">[**ネットワーク設定**] で、そのサイトのネットワークユーザーの数を追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-134">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="d8fc8-135">ネットワークの詳細を追加します。 WAN 対応、WAN キャパシティ、インターネット出口 (**ローカル**または**リモート**)、PSTN 出口 (なし、ローカル、リモート)。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-135">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d8fc8-136">レポートを生成するときに特定の帯域幅の推奨値を表示するには、WAN およびインターネットの容量番号を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-136">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="d8fc8-137">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-137">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="d8fc8-138">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d8fc8-138">Create a report</span></span>

<span data-ttu-id="d8fc8-139">すべてのサイトを追加した後、次のようにレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-139">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="d8fc8-140">[**レポート**] タブで、[**レポートの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-140">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="d8fc8-141">作成した各サイトについて、利用可能なペルソナを越えてユーザー数を配布します。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-141">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="d8fc8-142">Microsoft の推奨されるペルソナを使用している場合は、その番号が自動的に配布されます (80% の office worker と 20% のリモートワーカー)。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-142">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="d8fc8-143">配布が完了したら、[**レポートの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-143">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="d8fc8-144">生成されたレポートには、出力を明確に理解できるように、いくつかの異なるビューの帯域幅要件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-144">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="d8fc8-145">個々の計算を含むテーブルには、許容される各アクティビティの帯域幅要件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-145">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="d8fc8-146">追加のビューには、推奨事項による全体的な帯域幅のニーズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-146">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="d8fc8-147">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-147">Click **Save**.</span></span> <span data-ttu-id="d8fc8-148">レポートは、後で表示するためにレポートリストで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-148">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="d8fc8-149">シナリオの例</span><span class="sxs-lookup"><span data-stu-id="d8fc8-149">Example scenario</span></span>

<span data-ttu-id="d8fc8-150">ネットワークプランナーを使用してネットワーク計画を設定し、これらの手順を使用してレポートを生成する方法の例については、[ネットワークプランナーの使い方に関する PowerPoint デッキ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)(英語のみ) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="d8fc8-150">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
