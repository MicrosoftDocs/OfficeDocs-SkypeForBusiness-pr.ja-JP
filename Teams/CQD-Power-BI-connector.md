---
title: CQD クエリテンプレートを使用するために Power BI コネクタをインストールする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: CQD クエリテンプレートを使用するために Power BI コネクタをインストールする
ms.openlocfilehash: d9619fbf39558597c0f6c168f57f8b240d3c2a20
ms.sourcegitcommit: 5692900c0fc0a2552fe3f8ece40920c839e1ea23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43952446"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a><span data-ttu-id="5a7e2-103">CQD クエリテンプレートを使用するために Power BI コネクタをインストールする</span><span class="sxs-lookup"><span data-stu-id="5a7e2-103">Install Power BI Connector to use CQD query templates</span></span>

<span data-ttu-id="5a7e2-104">CQD (.PBIX ファイル) 用の Power BI クエリテンプレートを使用するには、Microsoft CQD の Power BI Connector をインストールする必要があります。これには、[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に含まれている microsoft の power bi*のファイルを*使用します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-104">Before you can use the Power BI query templates for CQD (PBIX files), you'll need to install the Power BI Connector for Microsoft CQD, using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="5a7e2-105">これらのテンプレートについては、「 [POWER BI を使用してチームの CQD データを分析](CQD-Power-BI-query-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-105">Read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md) to learn about these templates.</span></span>


## <a name="installation"></a><span data-ttu-id="5a7e2-106">インストール</span><span class="sxs-lookup"><span data-stu-id="5a7e2-106">Installation</span></span>

<span data-ttu-id="5a7e2-107">コネクタの使用を有効にするためのカスタムコネクタのインストールとセキュリティの調整のプロセスについては、「 [POWER BI ドキュメント](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)」で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-107">The process for installing a custom connector and adjusting security to enable use of the connector is described in detail in the [Power BI documentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).</span></span> <span data-ttu-id="5a7e2-108">わかりやすくするために、簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-108">For the sake of simplicity, here's a quick explanation:</span></span>

1.  <span data-ttu-id="5a7e2-109">\  * \[\]Power BI デスクトップ\\カスタムコネクタフォルダーがコンピューターに既に含まれているかどうかを確認し\\*ます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-109">Check to see if your computer already has a *\[Documents\]\\Power BI Desktop\\Custom Connectors* folder.</span></span> <span data-ttu-id="5a7e2-110">見つからない場合は、このフォルダーを作成します。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5a7e2-110">If not, create this folder.<sup>1</sup></span></span>

2.  <span data-ttu-id="5a7e2-111">コネクタファイル ( \* \*mez*また* \*は pqx*ファイル) をダウンロードして、*カスタムコネクタ\*ディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-111">Download the connector file (either a *\*.mez* or *\*.pqx* file) and place it in the *Custom Connectors* directory.</span></span>

3.  <span data-ttu-id="5a7e2-112">**コネクタファイルが* \*mez*ファイルの場合\*\*は、[カスタムコネクタのセットアップのドキュメント](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)で説明されているように、セキュリティ設定を調整する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-112">**If the connector file is a *\*.mez* file,** you will also need to adjust your security settings as described in the [custom connector setup documentation](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security).</span></span>

<span data-ttu-id="5a7e2-113">この Power BI Connector for Microsoft Teams の新しいバージョンがリリースされた場合は、*カスタムコネクタ*ディレクトリにある古いコネクタファイルを新しいファイルに置き換えるだけです。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-113">If a new version of this Power BI Connector for Microsoft Teams is released, simply replace the old connector file in the *Custom Connectors* directory with the new file.</span></span>

## <a name="setup"></a><span data-ttu-id="5a7e2-114">セットアップ</span><span class="sxs-lookup"><span data-stu-id="5a7e2-114">Setup</span></span>

<span data-ttu-id="5a7e2-115">レポートを作成してクエリを実行するには、まず CQD データソースに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-115">In order to build a report and run queries, you will first need to connect to the CQD data source.</span></span> <span data-ttu-id="5a7e2-116">接続するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-116">Follow the steps below in order to connect:</span></span>

1.  <span data-ttu-id="5a7e2-117">Power BI デスクトップの [ホーム] タブで、[*データの取り込み*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-117">In the Home tab of Power BI Desktop, click on *Get Data*.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector1.png)

2.  <span data-ttu-id="5a7e2-119">この時点で [*データの取得*] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-119">The *Get Data* window should appear at this point.</span></span> <span data-ttu-id="5a7e2-120">[*オンラインサービス*] に移動し、[ *Microsoft 通話品質 (ベータ版)* ] を選択して、[*接続*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-120">Navigate to *Online Services*, then select *Microsoft Call Quality (Beta)* and hit *Connect*.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector2.png)

3.  <span data-ttu-id="5a7e2-122">次のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-122">You will be prompted to login next.</span></span> <span data-ttu-id="5a7e2-123">CQD に使用するのと同じ資格情報を使用します。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5a7e2-123">Use the same credentials that you use for CQD.<sup>2</sup></span></span>

4.  <span data-ttu-id="5a7e2-124">次のプロンプトは、2つの*データ接続モード*の間でオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-124">The next prompt will give you the option between two *Data Connectivity modes*.</span></span> <span data-ttu-id="5a7e2-125">[ *DirectQuery* ] を選択して、 *[OK]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-125">Select *DirectQuery* and hit *OK*.</span></span>

5.  <span data-ttu-id="5a7e2-126">最後に、CQD のデータモデル全体を示す最後のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-126">Finally, you will be given a final prompt showing you the entire data model for CQD.</span></span> <span data-ttu-id="5a7e2-127">この時点では、データは表示されません。 CQD のデータモデルだけです。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-127">No data will be visible at this point, only the data model for CQD.</span></span> <span data-ttu-id="5a7e2-128">[*読み込み*] を選択して、セットアッププロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-128">Select *Load* to complete the setup process.</span></span>

6.  <span data-ttu-id="5a7e2-129">Power BI は、この時点で、データモデルをウィンドウの右側に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-129">At this point, Power BI will load the data model onto the right side of the window.</span></span> <span data-ttu-id="5a7e2-130">ページは空白のままになり、既定ではクエリは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-130">The page will remain otherwise blank, and no queries will be loaded by default.</span></span> <span data-ttu-id="5a7e2-131">**以下のクエリを作成し**て、クエリを作成してデータを返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-131">Proceed to **Building Queries** below in order to build a query and return data.</span></span>

<span data-ttu-id="5a7e2-132">このセットアッププロセス中にいずれかの手順を実行しても問題が解決しない場合は、[ここ](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)に記載されているプロセスの詳細な説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-132">If any of the steps during this setup process were not completely clear, a more detailed explanation of the process can be found [here](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data).</span></span>

## <a name="building-queries"></a><span data-ttu-id="5a7e2-133">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="5a7e2-133">Building Queries</span></span>

<span data-ttu-id="5a7e2-134">セットアップが完了すると、数百のディメンションとメジャーの名前が [*フィールド*] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-134">Once setup is complete, you should see the names of several hundred dimensions and measures load in the *Fields* pane.</span></span> <span data-ttu-id="5a7e2-135">実際のクエリをここで作成するのは簡単です。クエリに必要な寸法とメジャーを選んで、ページにドラッグアンドドロップするだけです。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-135">Constructing actual queries from here is simple, just select the dimensions and measures you want for your query, then drag and drop them onto the page.</span></span> <span data-ttu-id="5a7e2-136">次に、簡単な例を示した、より詳細な説明を示します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-136">Here's a more detailed explanation, with a simple example:</span></span>

1.  <span data-ttu-id="5a7e2-137">*視覚エフェクト*ウィンドウで、使用する視覚エフェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-137">Select the visualization you want to use from the *Visualizations* pane.</span></span> <span data-ttu-id="5a7e2-138">その視覚エフェクトの空のバージョンがページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-138">A blank version of that visualization should appear on the page.</span></span> <span data-ttu-id="5a7e2-139">この例では、*テーブル*の視覚エフェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-139">For the purposes of this example, we will be using the *Table* visualization.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector3.png)

2.  <span data-ttu-id="5a7e2-141">クエリに使用するディメンションとメジャー (名前で集計記号で示されます) を特定し、手動で選択して、黒い視覚エフェクトにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-141">Determine which dimensions and measures (denoted by an aggregation symbol by their name) you wish to use for your query, then manually select them and drag them onto the black visualization.</span></span> <span data-ttu-id="5a7e2-142">または、視覚エフェクトオプションの下にある [*値*] フィールドにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-142">Alternately, drag them onto the *Values* field beneath the visualization options.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector4.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="5a7e2-144">通話品質ダッシュボードを使用するには、クエリを実行するためのメジャーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-144">Call Quality Dashboard requires a measure for any query to run.</span></span> <span data-ttu-id="5a7e2-145">クエリにメジャーを追加しないと、クエリが失敗します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-145">Failure to add a measure to a query will cause that query to fail.</span></span>

3.  <span data-ttu-id="5a7e2-146">次に、フィルターを適用する寸法を選択し、[*フィルター* ] ウィンドウの [*このビジュアルフィールドのフィルター* ] にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-146">Next, select any dimensions you want to filter on and drag them to the *Filters on this visual* field in the *Filters* pane.</span></span> <span data-ttu-id="5a7e2-147">現在、CQD Power BI コネクタは、*基本的なフィルター*処理をサポートしています (可能なディメンション値の一覧から値を選択します)。*高度なフィルター*処理 (フィルター処理する値とオペランドを手動で指定する、詳細なフィルター処理を行う場合)、*相対日付フィルター処理*(*終了時刻*と*開始時刻*のディメンションでのみ使用可能)。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-147">The CQD Power BI Connector currently supports *Basic filtering* (select values from a list of possible dimension values), *Advanced filtering* (manually specify values and operands to filter on, similar to Advanced CQD), and *Relative date filtering* (only available for the *End Time* and *Start Time* dimensions).</span></span> <span data-ttu-id="5a7e2-148">*上位 N*に基づくフィルター処理は、CQD ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-148">Filtering according to *Top N* is not supported by CQD.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector5.png)

4.  <span data-ttu-id="5a7e2-150">最後に、[*視覚エフェクト*] ウィンドウ内の [*書式*] タブを選択して、クエリのスタイルと書式設定を行います。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-150">Finally, select the *Format* tab within the *Visualizations* pane to style and format your query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a7e2-151">CQD クエリを実行するには、少なくとも1つのメジャーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-151">CQD queries require at least one measure in order to run.</span></span> <span data-ttu-id="5a7e2-152">クエリが読み込まれない場合は、クエリにメジャーが含まれていることをもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-152">If your query does not load, double check that you have included a measure in the query.</span></span>

## <a name="creating-a-drillthrough-report"></a><span data-ttu-id="5a7e2-153">ドリルスルーレポートの作成</span><span class="sxs-lookup"><span data-stu-id="5a7e2-153">Creating a Drillthrough Report</span></span>

<span data-ttu-id="5a7e2-154">[POWER BI のドリルスルーで](https://docs.microsoft.com/power-bi/desktop-drillthrough)は、他のレポートの値をコンテキストとしてすばやくフィルター処理できる優先レポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-154">[Drillthrough in Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context.</span></span> <span data-ttu-id="5a7e2-155">CQD コネクタを使用して最初のクエリを作成する方法がわかったら、ドリルスルーの作成がさらに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-155">Once you know how to create your first query with the CQD Connector, creating a drillthrough is even simpler.</span></span>

1.  <span data-ttu-id="5a7e2-156">優先レポート用に別のページを作成し、そのページにクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-156">Create another page for the focused report, and then add your queries to that page.</span></span>

2.  <span data-ttu-id="5a7e2-157">ドリルスルーフィルターとして使用するディメンションを選択し、[*視覚エフェクト*] ウィンドウの下にある [*ドリルスルー* ] フィールドにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-157">Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector6.png)

3.  <span data-ttu-id="5a7e2-159">**それです\!**</span><span class="sxs-lookup"><span data-stu-id="5a7e2-159">**That's it\!**</span></span> <span data-ttu-id="5a7e2-160">そのディメンションを使用する他のページに対する他のクエリで、そのページにドリルスルーし、ドリルスルーディメンションの値をフィルターとして自動的に適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-160">Any other query on another page that uses that dimension can now drillthrough to that page, automatically applying the drillthrough dimension's value as a filter.</span></span>

    ![スクリーンショット: Power BI コネクタ](media/CQD-power-bi-connector7.png)

<span data-ttu-id="5a7e2-162">Advanced CQD とは異なり、Power BI は連続していないドリルスルーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-162">Unlike Advanced CQD, Power BI supports non-sequential drillthrough.</span></span> <span data-ttu-id="5a7e2-163">クエリに必要なディメンションが含まれていれば、他のページにドリルスルーできます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-163">So long as a query includes the necessary dimension, it can drillthrough to any other page.</span></span>

### <a name="best-practice"></a><span data-ttu-id="5a7e2-164">ベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="5a7e2-164">Best practice</span></span>

<span data-ttu-id="5a7e2-165">通話品質コネクタクエリは、ドリルスルー機能を考慮して設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-165">Call Quality connector queries should be designed with drillthrough functionality in mind.</span></span> <span data-ttu-id="5a7e2-166">すべてのデータを一度に読み込んでから、フィルターを使用して分割していく代わりに、大規模な小さい基数のクエリを使い始めて、長い基数のクエリにドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-166">Instead of trying to load all the data at once, and then slicing down with filters, start with broader, low-cardinality queries and drill down to high-cardinality queries.</span></span> <span data-ttu-id="5a7e2-167">たとえば、どのサブネットが最も品質の問題を発生させているかを診断する際には、まず問題の原因となる地域と国を特定し、その地域内のサブネットにドリルダウンすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-167">For instance, when attempting to diagnose which subnets contribute most to quality issues, it's helpful to first identify those regions and countries which contribute to the problem, then drill down to the subnets in that region or country.</span></span> <span data-ttu-id="5a7e2-168">通話品質コネクタのテンプレートは、例として機能するために、この方法で設計されています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-168">The Call Quality connector templates have been designed in this manner in order to act as an example.</span></span>

## <a name="limitations"></a><span data-ttu-id="5a7e2-169">伴う</span><span class="sxs-lookup"><span data-stu-id="5a7e2-169">Limitations</span></span>

<span data-ttu-id="5a7e2-170">Power BI を使用しているにもかかわらず、Power BI 機能はすべて、CQD コネクタでサポートされているわけではありません。 CQD データモデルまたは DirectQuery コネクタの制限の結果としては、すべての Power BI 機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-170">Despite making use of Power BI, not all Power BI functionality is support by the CQD Connector, either as a result of limitations on CQD data model or on DirectQuery connectors in general.</span></span> <span data-ttu-id="5a7e2-171">以下の一覧は、コネクタの注目すべき制限をいくつか示していますが、この一覧は、すべてを網羅と見なすことはできません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-171">The list below notes some of the Connector's more noteworthy limitations, but this list should not be considered exhaustive:</span></span>

1.  <span data-ttu-id="5a7e2-172">**集計列–** 一般的な DirectQuery コネクタは、Power BI での計算列のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-172">**Calculated Columns –** DirectQuery connectors in general have limited support for calculated columns in Power BI.</span></span> <span data-ttu-id="5a7e2-173">一部の集計列はコネクタで動作する可能性がありますが、例外と見なされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-173">While some calculated columns may work with the Connector, these should be considered exceptions.</span></span> <span data-ttu-id="5a7e2-174">一般的な規則として、集計列は機能しません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-174">As a general rule, calculated columns will not function.</span></span>

2.  <span data-ttu-id="5a7e2-175">**集計–** CQD データモデルはキューブモデルに基づいて構築されます。これは、メジャー形式で集計が既にサポートされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-175">**Aggregations –** The CQD data model is built on a cube model, meaning that aggregations are already supported in the form of measures.</span></span> <span data-ttu-id="5a7e2-176">異なる次元に集計を手動で追加しようとした場合、またはメジャーの集計の種類を変更しても、コネクタでは動作しません。通常はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-176">Attempting to manually add aggregations to different dimensions or changing the aggregation type of a measure will not work with the Connector, and it will generally result in an error.</span></span>

3.  <span data-ttu-id="5a7e2-177">**カスタムビジュアル–** CQD Connector は、さまざまなカスタムビジュアルで動作しますが、すべてのカスタムビジュアルとの互換性を保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-177">**Custom Visuals –** While the CQD Connector does work with a range of custom visuals, we are unable to guarantee compatibility with all custom visuals.</span></span> <span data-ttu-id="5a7e2-178">多くのカスタムビジュアルは、計算列またはインポートされたデータの使用に依存していますが、DirectQuery コネクタではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-178">Many custom visuals rely on the use of calculated columns or imported data, neither or which are supported by DirectQuery connectors.</span></span>

4.  <span data-ttu-id="5a7e2-179">**キャッシュデータの参照:** 現在、Power BI では、DirectQuery コネクタからのキャッシュされたデータの参照を任意の方法でサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-179">**Referencing Cached Data –** Power BI currently does not support referencing cached data from a DirectQuery connector in any way.</span></span> <span data-ttu-id="5a7e2-180">クエリの結果を参照しようとすると、新しいクエリになります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-180">Any attempt to reference the results of a query will result in a new query.</span></span> 

5.  <span data-ttu-id="5a7e2-181">**相対データフィルター処理–** は、CQD コネクタでサポートされていますが、[*開始*時刻] と [*終了時刻*] のサイズに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-181">**Relative Data Filtering –** Is supported in the CQD Connector, but only with the *Start Time* and *End Time* dimensions.</span></span> <span data-ttu-id="5a7e2-182">*日付ディメンションは*、相対的な日付フィルター処理の候補として表示される場合もあり*ますが、日付は日付*時刻オブジェクトとして保存されないため、power BI での相対的な日付フィルター処理はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-182">Although the *Date* dimension may be the obvious choice for relative date filtering, *Date* is not stored as a date time object and thus does not support relative date filtering in Power BI.</span></span>

<span data-ttu-id="5a7e2-183">コネクタはプレビュー版ですが、これらの制限は、コネクタの最終リリースによって変更されることはありませんのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-183">Please note, although the Connector is in preview, these limitations are unlikely to change with the final release of the Connector.</span></span> <span data-ttu-id="5a7e2-184">これらの問題のほとんどは、Power BI での DirectQuery コネクタの設計への制限、または CQD データモデルの設計に対する基本事項です。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-184">Most of these issues are either restrictions to DirectQuery connector design in Power BI or fundamental to the design of the CQD data model.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5a7e2-185">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5a7e2-185">Troubleshooting</span></span>

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a><span data-ttu-id="5a7e2-186">Date 列を日付スライサーとして使用しようとしています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-186">I'm trying to use the Date column as a Date slicer.</span></span> <span data-ttu-id="5a7e2-187">この列のデータ型を Date に変換すると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-187">As soon as I convert the data type of this column to Date, I get this error:</span></span>

> <span data-ttu-id="5a7e2-188">**このビジュアルのデータを読み込めませんでした**: OLE DB または ODBC エラー: [式. エラー] 式をデータソースに折りたたむことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-188">**Couldn't load the data for this visual**: OLE DB or ODBC error: [Expression.Error] We couldn't fold the expression to the data source.</span></span> <span data-ttu-id="5a7e2-189">もっと簡単な式をお試しください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-189">Please try a simpler expression.</span></span> 

<span data-ttu-id="5a7e2-190">Power BI コネクタでスライサーはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-190">Date slicers aren't supported with the Power BI Connector.</span></span> <span data-ttu-id="5a7e2-191">日付範囲を指定するには、次の2つのフィルターをレポートに適用します。指定した日付よりも小さい値と大きい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-191">To specify a date range, apply two filters to the report, specifying a less than and greater than date.</span></span>

<span data-ttu-id="5a7e2-192">または、表示する日付が最新である場合は、相対的な日付フィルターを適用して、過去 N 日間/週/月のデータのみが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-192">Alternatively, if the dates you want to view are recent, apply a relative date filter to show only data for the last N days/weeks/months.</span></span>

## <a name="error-codes"></a><span data-ttu-id="5a7e2-193">エラーコード</span><span class="sxs-lookup"><span data-stu-id="5a7e2-193">Error Codes</span></span>

<span data-ttu-id="5a7e2-194">CQD Power BI コネクタは、作成できるクエリの種類によってはブラウザーアプリより制限が少ないため、クエリの作成中にいくつかのエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-194">Because the CQD Power BI Connector is less restricted than the browser app in terms of kinds of queries you can construct, you may occasionally encounter a number of errors while building your queries.</span></span> <span data-ttu-id="5a7e2-195">"CQDError" という種類のエラーメッセージが表示された場合。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-195">In the event that you receive an error message of the type "CQDError.</span></span> <span data-ttu-id="5a7e2-196">RunQuery –クエリ実行エラー "で、クエリの可能性がある問題のトラブルシューティングのために提供されている ErrorType 番号を使用して、以下のリストを参照します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-196">RunQuery – Query Execution Error", reference the list below with the ErrorType number provided in order to troubleshoot the possible issue with the query.</span></span> <span data-ttu-id="5a7e2-197">CQD Power BI コネクタで発生する可能性のある最も一般的なエラーの種類コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-197">The following are the most common Error Type codes you may encounter with the CQD Power BI Connector:</span></span>

  - <span data-ttu-id="5a7e2-198">**ErrorType 1-クエリ構造エラー:** 通常、クエリ構造のエラーは、コネクタが適切に書式設定されたクエリを作成できない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-198">**ErrorType 1 - Query Structure Error:** A query structure error is typically caused by the Connector failing to build a properly formatted query.</span></span> <span data-ttu-id="5a7e2-199">これは、上記の制限で指定されているように、サポートされていない機能を使用する場合によく発生します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-199">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="5a7e2-200">クエリで集計列やカスタムビジュアルを使用していないことを再確認します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-200">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="5a7e2-201">**ErrorType 2-クエリの作成エラー:** CQD Connector が、作成しようとしているクエリを適切に解析できないことが原因で、クエリの作成エラーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-201">**ErrorType 2 - Query Building Error:** A query building error is caused by the CQD Connector being unable to properly parse the query you are attempting to build.</span></span> <span data-ttu-id="5a7e2-202">これは、上記の制限で指定されているように、サポートされていない機能を使用する場合によく発生します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-202">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="5a7e2-203">クエリで集計列やカスタムビジュアルを使用していないことを再確認します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-203">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="5a7e2-204">**ErrorType 5-実行タイムアウト:** タイムアウトする前に、クエリの実行可能時間の上限に達しました。スコープを制限するために、クエリにフィルターを追加してみてください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-204">**ErrorType 5 - Execution Timeout:** The query has reached the maximum possible runtime before timing out. Try adding more filters to the query in order to limit its scope.</span></span> <span data-ttu-id="5a7e2-205">データ範囲の絞り込みは、多くの場合、これを実現するための最も効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-205">Narrowing the data range is often the most effective way to achieve this.</span></span>

  - <span data-ttu-id="5a7e2-206">**ErrorType 7-測定エラーはありません。** CQD クエリを機能させるには、メジャーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-206">**ErrorType 7 - No Measurements Error:** CQD queries require a measure in order to function.</span></span> <span data-ttu-id="5a7e2-207">クエリにメジャーが含まれていることをもう一度確認します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-207">Double check that your query includes measure.</span></span> <span data-ttu-id="5a7e2-208">CQD コネクタのメジャーは、名前の前に aggregation (sum) 記号で示されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-208">Measures in the CQD Connector are denoted by the aggregation (sum) symbol before their name.</span></span>

<span data-ttu-id="5a7e2-209">この範囲外の追加のエラーが発生した場合は、CQD チームに通知して、問題のトラブルシューティングを行い、必要に応じてドキュメントを更新してください。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-209">If you encounter any additional errors outside of this scope, please notify the CQD team so that we can help troubleshoot the issue and update the documentation as appropriate.</span></span>

## <a name="footnotes"></a><span data-ttu-id="5a7e2-210">脚注</span><span class="sxs-lookup"><span data-stu-id="5a7e2-210">Footnotes</span></span>

<span data-ttu-id="5a7e2-211">**<sup>1</sup>** 特定のプロセスとアプリ (OneDrive など) によって、ドキュメントのルートフォルダーが変更されることがあります。*POWER BI デスクトップ\\カスタムコネクタ*ディレクトリが、現在のルートフォルダーの [ドキュメント] フォルダー内に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-211">**<sup>1</sup>** Certain processes and apps (e.g., OneDrive) may cause your Documents root folder to change; make sure that the *Power BI Desktop\\Custom Connectors* directory is placed inside of the current root folder Documents folder.</span></span>

<span data-ttu-id="5a7e2-212">**<sup>2</sup>** CQD で使用するログイン資格情報は、Power BI デスクトップアプリ自体へのログインに使用する資格情報と同じである必要はあり*ません*。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-212">**<sup>2</sup>** The login credentials you use for CQD *do not* need to be the same credentials you use for logging into the Power BI Desktop app itself.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="5a7e2-213">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="5a7e2-213">Frequently asked questions</span></span>

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a><span data-ttu-id="5a7e2-214">Power BI コネクタは、"ベータ" 状態から更新されますか?</span><span class="sxs-lookup"><span data-stu-id="5a7e2-214">When will the Power BI Connector be updated from "Beta" status?</span></span>

<span data-ttu-id="5a7e2-215">ベータタグにもかかわらず、Power BI 用の通話品質コネクタは、リリース版のコネクタであり、Power BI teams によって正式なセキュリティが署名されており、これを反映しています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-215">Despite the Beta tag, the Call Quality Connector for Power BI is the release version of the connector and has been officially security signed by the Power BI team to reflect this.</span></span> <span data-ttu-id="5a7e2-216">このベータ版タグを削除する認定プロセスは広範囲であるため、Power BI チームからのコミットメントを得て、コネクタに直接サポートを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-216">The certification process to remove that Beta tag is an extensive one and requires a commitment from the Power BI team to provide direct support to the connector as well.</span></span> <span data-ttu-id="5a7e2-217">現時点では時間の制約があるため、Power BI チームは現在、そのサポートとより広範な認定を提供することはできませんが、Microsoft Call Quality コネクタのセキュリティ、完全性、および全般的な機能を証明するための準備は完了しています。</span><span class="sxs-lookup"><span data-stu-id="5a7e2-217">Due to time constraints, the Power BI team is currently unable to provide that support and broader certification, but is still prepared to attest to the security, authenticity, and general functionality of the Microsoft Call Quality connector.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a7e2-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a7e2-218">Related topics</span></span>

[<span data-ttu-id="5a7e2-219">Power BI を使用して Teams の CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="5a7e2-219">Use Power BI to analyze CQD data for Teams</span></span>](CQD-Power-BI-query-templates.md)
