---
title: 'Lync Server 2013: ベストプラクティスアナライザーによって作成されたレポートについて'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56556d209e073be49a6c0eb2aa30461a06930238
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="1a204-102">Lync Server 2013 でのベストプラクティスアナライザーによって作成されたレポートについて</span><span class="sxs-lookup"><span data-stu-id="1a204-102">Understanding reports created by Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a204-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="1a204-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="1a204-p101">Best Practices Analyzer は、問題の分析と解決に役立つさまざまな種類のレポートを提供します。Best Practices Analyzer は、エラー、警告、その他の問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="1a204-p101">Best Practices Analyzer provides multiple types of reports that are organized to facilitate the analysis and resolution of issues. Best Practices Analyzer identifies issues such as errors, warnings, and other information.</span></span>

<div>

## <a name="reports"></a><span data-ttu-id="1a204-106">レポート</span><span class="sxs-lookup"><span data-stu-id="1a204-106">Reports</span></span>

<span data-ttu-id="1a204-107">次の各レポートを表示してスキャン結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-107">You can access the results of a scan by viewing each of the following reports:</span></span>

  - <span data-ttu-id="1a204-108">**リストレポート**   リストレポートは、特定の条件によって編成されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-108">**List reports**   List reports are organized by specific criteria.</span></span> <span data-ttu-id="1a204-109">クラス、重要度、問題ごとに結果を整理できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-109">You can arrange the results by class, severity, or issue.</span></span> <span data-ttu-id="1a204-110">たとえば、クラスごとに結果を整理すると、ディレクター関連の問題はレポートのディレクター セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-110">For example, if you organize results by class, issues related to Directors are included under the Directors section of the report.</span></span> <span data-ttu-id="1a204-111">すべての問題を表示することも、情報項目のみ表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a204-111">You can view all of the issues, or just the informational items.</span></span> <span data-ttu-id="1a204-112">メモリなど特定の項目についてリスト レポートを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-112">You can search a list report for specific items, such as memory.</span></span> <span data-ttu-id="1a204-113">レポートを印刷したり、エクスポートしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a204-113">You can also print the report or export it.</span></span>

  - <span data-ttu-id="1a204-114">**ツリーレポート**   ツリーレポートは、スキャンの実行時に指定したスキャンやその他のオプションを実行するために使用されるルールによって整理されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-114">**Tree reports**   Tree reports are organized by the rules that are used to run the scan and other options that you specified at the time the scan was run.</span></span> <span data-ttu-id="1a204-115">たとえば、テスト トポロジ ルール関連の問題はレポートのテスト トポロジ セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-115">For example, issues related to the Test Topology rules are included under the Test Topology section of the report.</span></span> <span data-ttu-id="1a204-116">すべての問題の詳細を表示することも、問題の概要のみ表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a204-116">You can view the details of all the issues, or just a summary of the issues.</span></span> <span data-ttu-id="1a204-117">メモリなど特定の項目についてツリー レポートを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-117">You can search a tree report for specific items, such as memory.</span></span> <span data-ttu-id="1a204-118">レポートを印刷したり、エクスポートしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a204-118">You can also print the report or export it.</span></span>

  - <span data-ttu-id="1a204-119">\*\*\*\*   他のレポート内の他のレポートアイテムには、スキャンに含まれていたタスクの実行時ログが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a204-119">**Other reports**   Items in other reports include the run-time log of tasks that were included in the scan.</span></span> <span data-ttu-id="1a204-120">メモリなど特定の項目についてその他のレポートを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-120">You can search the items in other reports for specific items, such as memory.</span></span> <span data-ttu-id="1a204-121">レポートを印刷したり、エクスポートしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a204-121">You can also print the report or export it.</span></span>

</div>

<div>

## <a name="issues"></a><span data-ttu-id="1a204-122">問題</span><span class="sxs-lookup"><span data-stu-id="1a204-122">Issues</span></span>

<span data-ttu-id="1a204-123">Best Practices Analyzer で生成されるレポートは、環境をスキャンして特定された次の種類の問題を示します。</span><span class="sxs-lookup"><span data-stu-id="1a204-123">The reports generated by Best Practices Analyzer indicate specific issues that are identified during the scan of your environment, including following types of issues:</span></span>

  - <span data-ttu-id="1a204-124">\*\*\*\*   環境に変更を加える必要のある重大な問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1a204-124">**Errors**   Critical issues that require you to make a change in your environment.</span></span> <span data-ttu-id="1a204-125">たとえば、Lync Server 2013 のコアコンポーネントがインストールされていない場合は、エラーがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-125">For example, if Lync Server 2013 Core Components are not installed, an error is logged.</span></span>

    <span data-ttu-id="1a204-p106">エラーとして分類される問題は、レポート内に赤い X シンボルで示されます。エラーは、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブと [**Summary View**] タブに表示されます。特定のエラーをレポートに表示しないようにするには、レポートにそのエラーの 1 つのインスタンスまたはすべてのインスタンスが表示されないように指定できます。この場合、そのエラーは、設定を変更してレポートに表示されるように指定しない限り、[**Other Reports**] ビューの [**Hidden Items**] タブのみに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-p106">Issues that are classified as errors are identified in the report by a red X symbol. Errors are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The error is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the error be displayed in the report.</span></span>

  - <span data-ttu-id="1a204-130">\*\*\*\*   ベストプラクティスの実装と一貫性のない警告の問題。</span><span class="sxs-lookup"><span data-stu-id="1a204-130">**Warnings**   Issues that are not consistent with the implementation of a best practice.</span></span> <span data-ttu-id="1a204-131">これは、環境に変更を行う必要がある場合とない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a204-131">This may or may not indicate the need for a change in your environment.</span></span> <span data-ttu-id="1a204-132">変更する必要のない特定の設定に関する既知の問題である可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="1a204-132">The issue could be a known issue with a specific setting that you do not need to change.</span></span> <span data-ttu-id="1a204-133">たとえば、サーバーで開始されていないサービスがあると警告として記録されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-133">For example, services that are not started on a server are logged as warnings.</span></span>

    <span data-ttu-id="1a204-p108">警告として分類される問題は、レポート内に黄色の三角形の警告シンボルで示されます。警告は、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブと [**Summary View**] タブに表示されます。特定の警告をレポートに表示しないようにするには、レポートにその警告の 1 つのインスタンスまたはすべてのインスタンスが表示されないように指定できます。この場合、その警告は、設定を変更してレポートに表示されるように指定しない限り、[**Other Reports**] ビューの [**Hidden Items**] タブのみに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-p108">Issues that are classified as warnings are identified in the report by a triangular yellow warning symbol. Warnings are displayed on the **All Issues** tab of the **List Reports** view, as well as on the **Detailed View** tab and the **Summary View** tab of the **Tree Reports** view. If you do not want to see a specific error in a report, you can specify that the error not be shown for a single instance or for all instances of that error in the report. The warning is then displayed only on the **Hidden Items** tab of the **Other Reports** view, unless you change the setting and specify that the warning be displayed in the report.</span></span>

  - <span data-ttu-id="1a204-138">**情報**   には、エラーまたは警告として分類されないすべての問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a204-138">**Information**   Includes all issues that are not classified as errors or warnings.</span></span> <span data-ttu-id="1a204-139">たとえば、Active Directory ドメインサービス内の Lync Server 2013 Standard Edition サーバーオブジェクトの数は、情報の問題として分類されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-139">For example, the number of Lync Server 2013 Standard Edition server objects in Active Directory Domain Services is classified as an information issue.</span></span>

    <span data-ttu-id="1a204-140">情報項目は、[**List Reports**] ビューの [**All Issues**] タブ、および [**Tree Reports**] ビューの [**Detailed View**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a204-140">Information issues are displayed on the **All Issues** tab of the **List Reports** view, and on the **Detailed View** tab of the **Tree Reports** view.</span></span>

<span data-ttu-id="1a204-141">Lync Server 2013、ベストプラクティスアナライザーは、問題を解決するために環境を変更することはありません。</span><span class="sxs-lookup"><span data-stu-id="1a204-141">The Lync Server 2013, Best Practices Analyzer does not make changes to your environment to resolve issues.</span></span> <span data-ttu-id="1a204-142">スキャンは、潜在的な問題を検出し、各問題の解決方法に関する情報が記載されたレポートを提供するのみです。</span><span class="sxs-lookup"><span data-stu-id="1a204-142">The scan only detects potential issues and provides reports that contain information about how to resolve each issue.</span></span>

<span data-ttu-id="1a204-p111">問題をクリックすると、特定の問題に関する説明とオプションが表示されます。その後、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-p111">If you click an issue, an explanation and some options are displayed for specific issues. Then, you can do any of the following:</span></span>

  - <span data-ttu-id="1a204-145">その問題に関する詳細情報と解決方法を調べます。</span><span class="sxs-lookup"><span data-stu-id="1a204-145">Find more detailed information about the issue, and how to resolve it.</span></span>

  - <span data-ttu-id="1a204-146">レポートに問題を表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1a204-146">Stop showing issues in reports:</span></span>

      - <span data-ttu-id="1a204-147">その問題の選択したインスタンスを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1a204-147">Stop showing issues for the selected instance.</span></span>

      - <span data-ttu-id="1a204-148">その問題のすべてのインスタンスを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="1a204-148">Stop showing issues for all instances of that issue.</span></span>

    <span data-ttu-id="1a204-p112">レポートに表示しないようにした問題を確認するには、[**Other Reports**] ビューの [**Hidden Items**] タブを開きます。そのタブで、レポートへの問題の表示を再開するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a204-p112">To see the issues you have stopped showing in reports, go to the **Hidden Items** tab of the **Other Reports** view. From there, you can specify to start showing issues in reports again.</span></span>

<span data-ttu-id="1a204-151">特定の問題を解決する方法の詳細については、「 [Lync Server 2013 のベストプラクティスアナライザーによって識別された問題の分析と解決](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a204-151">For details about resolving specific issues, see [Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
