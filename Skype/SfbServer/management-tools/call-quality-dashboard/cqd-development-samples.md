---
title: CQD の開発サンプル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '概要: 通話品質ダッシュボードのチュートリアルと開発サンプルを確認します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832727"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="9e455-104">CQD の開発サンプル</span><span class="sxs-lookup"><span data-stu-id="9e455-104">CQD Development Samples</span></span>

<span data-ttu-id="9e455-105">**概要:** 通話品質ダッシュボードのチュートリアルと開発サンプルを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e455-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="9e455-106">通話品質ダッシュボードは、Skype for Business Server 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="9e455-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="9e455-107">この記事では、通話品質ダッシュボード (CQD) の開発に関するチュートリアルとサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e455-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="9e455-108">通話品質ダッシュボード (CQD) 開発サンプル</span><span class="sxs-lookup"><span data-stu-id="9e455-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="9e455-109">チュートリアル: CQD データ サービスとリポジトリ サービス API を使用してカスタマイズされたレポート プレゼンテーションを作成する。</span><span class="sxs-lookup"><span data-stu-id="9e455-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="9e455-110">CQD の概要</span><span class="sxs-lookup"><span data-stu-id="9e455-110">Introduction to CQD</span></span>

<span data-ttu-id="9e455-111">CQD は、オンプレミスの Skype for Business Server 展開に関する集約された通話品質情報にすばやく簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9e455-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="9e455-112">CQD は、QoE アーカイブ データベース、キューブ、ポータルの 3 つのコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="9e455-113">ポータルはメインのプレゼンテーション 層であり、さらに次の 3 つのコンポーネントに分かれています。</span><span class="sxs-lookup"><span data-stu-id="9e455-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="9e455-114">Data Service は、Skype for Business Server の通話品質ダッシュボード [(CQD)](data-api.md)用データ API を通じて認証済みユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9e455-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="9e455-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span><span class="sxs-lookup"><span data-stu-id="9e455-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="9e455-116">Web ポータル。CQD ユーザーが表示および操作する HTML5 ベースのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="9e455-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="9e455-117">これは、認証されたユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9e455-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="9e455-118">Web ポータルに表示されるレポートは、"レポート セット" にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="9e455-119">図は、2 つのレポートを含むレポート セットを示しています。</span><span class="sxs-lookup"><span data-stu-id="9e455-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="9e455-120">このダッシュボードの以下の各レポートは、数か月間の良好な通話数、低品質通話数、低品質通話率に関するクエリ結果を示し、さまざまなフィルターが適用されています。</span><span class="sxs-lookup"><span data-stu-id="9e455-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD サンプル レポート](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="9e455-122">CQD は CQM (Call Quality Methodology) に従って作成されます。そのため、既定の一連のレポートは、CQM によって導入された調査フローに合わせて設計されています。</span><span class="sxs-lookup"><span data-stu-id="9e455-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="9e455-123">また、ユーザーはニーズに合わせてカスタム レポートを柔軟に編集または作成できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="9e455-124">ただし、データを視覚化する方法は複数あるので、CQD によって提供される視覚エフェクトは、すべてのユーザーのニーズに完全には対応できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="9e455-125">このような場合、ユーザーはデータ API とリポジトリ API を利用してカスタム レポート ページを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="9e455-126">このチュートリアルでは、一連の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e455-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="9e455-127">ダッシュボードがデータ サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9e455-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="9e455-128">CQD ホーム ページ (例: 認証および承認されたユーザーのレポート セットと対応するレポート) に移動すると、リポジトリ サービスから http://localhost/cqd) 取得されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="9e455-129">完全な URL は、レポート セット ID と年月から作成されます (レポート セット ID は URL の '/#/' セクションの後の整数値で、既定では、現在の年月はスラッシュの後にレポート セット ID の末尾に追加されます)。</span><span class="sxs-lookup"><span data-stu-id="9e455-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="9e455-130">レポート定義は JSON 形式で格納され、リポジトリ サービスから取得されると、データ サービスへの入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="9e455-131">データ サービスは、入力に基づいて複数次元式 (MDX) クエリを生成し、キューブに対してこれらの MDX クエリを実行して、各レポートのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e455-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="9e455-132">カスタマイズされたレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="9e455-132">Building customized reports</span></span>

<span data-ttu-id="9e455-133">CQD には既に、レポートのカスタマイズに多くの柔軟性がありますが、CQD で作成された複数のレポート間でデータを集計する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="9e455-134">たとえば、次の表に示すように、有線通話のすべての可能な組み合わせの低品質通話のパーセンテージを示すレポートを作成する必要がある場合があります (図のような結果)。</span><span class="sxs-lookup"><span data-stu-id="9e455-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD テーブル](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="9e455-136">CQD が提供するポータルを使用すると、ユーザーは複数のレポートに移動して、それぞれの低品質通話率を抽出して記録する必要があります。収集する必要があるデータ ポイントが多い場合は手間がかからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="9e455-137">データ API は、データ サービスからデータを取得 (AJAX 呼び出しなど) することで、これを実現するためのプログラム的な方法をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="9e455-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="9e455-138">**例 1: 単純なレポートのサンプル**</span><span class="sxs-lookup"><span data-stu-id="9e455-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="9e455-139">最初に簡単な例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e455-139">Let us take a simple example first.</span></span> <span data-ttu-id="9e455-140">次の図のような HTML ページに、2015 年 2 月の Audio Good Stream と Audio Bad Stream の数を表示する場合:</span><span class="sxs-lookup"><span data-stu-id="9e455-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD レポートの例](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="9e455-142">必要なのは、適切なパラメーターを使用してデータ サービスに呼び出しを送信し、クエリ結果を HTML テーブルに表示することです。</span><span class="sxs-lookup"><span data-stu-id="9e455-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="9e455-143">JavaScript コードのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9e455-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="9e455-144">この例は、さらに次の 3 つの手順に分けできます。</span><span class="sxs-lookup"><span data-stu-id="9e455-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="9e455-145">クエリを作成します (この例では、これは変数 'query' で定義されています)。</span><span class="sxs-lookup"><span data-stu-id="9e455-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="9e455-146">クエリは、次のデータを含む JSON オブジェクトとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="9e455-147">a. </span><span class="sxs-lookup"><span data-stu-id="9e455-147">a.</span></span> <span data-ttu-id="9e455-148">0 個以上の次元</span><span class="sxs-lookup"><span data-stu-id="9e455-148">Zero or more dimensions.</span></span> <span data-ttu-id="9e455-149">各ディメンションは DataModelName で示されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="9e455-150">b.</span><span class="sxs-lookup"><span data-stu-id="9e455-150">b.</span></span> <span data-ttu-id="9e455-151">0 個以上のフィルター。</span><span class="sxs-lookup"><span data-stu-id="9e455-151">Zero or more filters.</span></span> <span data-ttu-id="9e455-152">各フィルターには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-152">Each filter has:</span></span>

   - <span data-ttu-id="9e455-153">DataModelName (フィルター セットを持つディメンション)。</span><span class="sxs-lookup"><span data-stu-id="9e455-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="9e455-154">値 (オペランドによって比較される値)。</span><span class="sxs-lookup"><span data-stu-id="9e455-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="9e455-155">オペランド (比較の種類、0 は "等しい" を意味します)。</span><span class="sxs-lookup"><span data-stu-id="9e455-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="9e455-156">c.</span><span class="sxs-lookup"><span data-stu-id="9e455-156">c.</span></span> <span data-ttu-id="9e455-157">1 つ以上の測定値。</span><span class="sxs-lookup"><span data-stu-id="9e455-157">One or more measurements.</span></span>

2. <span data-ttu-id="9e455-158">AJAX 呼び出しを使用してデータ サービスにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="9e455-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="9e455-159">次の要求パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="9e455-160">a. </span><span class="sxs-lookup"><span data-stu-id="9e455-160">a.</span></span> <span data-ttu-id="9e455-161">url (http://[ServerName]/QoEDataService/RunQuery である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9e455-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="9e455-162">b.</span><span class="sxs-lookup"><span data-stu-id="9e455-162">b.</span></span> <span data-ttu-id="9e455-163">data (これは 'query' 変数で定義されている JSON オブジェクトの文字列表現です)。</span><span class="sxs-lookup"><span data-stu-id="9e455-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="9e455-164">Data Service は、成功を収めるコール バック関数のパラメーターとしてクエリ結果を返します。</span><span class="sxs-lookup"><span data-stu-id="9e455-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="9e455-165">c.</span><span class="sxs-lookup"><span data-stu-id="9e455-165">c.</span></span> <span data-ttu-id="9e455-166">type (QoEDataService の場合、RunQuery は 'POST' 要求のみを受け入れる)。</span><span class="sxs-lookup"><span data-stu-id="9e455-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="9e455-167">d. </span><span class="sxs-lookup"><span data-stu-id="9e455-167">d.</span></span> <span data-ttu-id="9e455-168">非同期 (AJAX 呼び出しが同期か非同期かを示すフラグ)。</span><span class="sxs-lookup"><span data-stu-id="9e455-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="9e455-169">e. </span><span class="sxs-lookup"><span data-stu-id="9e455-169">e.</span></span> <span data-ttu-id="9e455-170">contentType ("application/json" である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9e455-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="9e455-171">f.</span><span class="sxs-lookup"><span data-stu-id="9e455-171">f.</span></span> <span data-ttu-id="9e455-172">success (AJAX 呼び出しが正常に終了した場合のコール バック関数)。</span><span class="sxs-lookup"><span data-stu-id="9e455-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="9e455-173">g. </span><span class="sxs-lookup"><span data-stu-id="9e455-173">g.</span></span> <span data-ttu-id="9e455-174">error (AJAX 呼び出しが失敗したときのエラー処理関数)。</span><span class="sxs-lookup"><span data-stu-id="9e455-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="9e455-175">HTML 内の div 要素にデータを挿入します (コードの例では、AJAX 要求が正常に完了した後、匿名関数呼び出しによって行われます)。</span><span class="sxs-lookup"><span data-stu-id="9e455-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="9e455-176">JavaScript コードを HTML ページに囲み、ページには図のようなレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e455-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="9e455-177">完全な html は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e455-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="9e455-178">これまでのところ、このレポートは非常に単純です。</span><span class="sxs-lookup"><span data-stu-id="9e455-178">So far, the report is still very simple.</span></span> <span data-ttu-id="9e455-179">ユーザーは、レポートをカスタマイズするために、測定値、ディメンション、またはフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="9e455-180">たとえば、AppSharing の低品質通話のパーセンテージを表示する場合は、AppSharing に関する新しい測定値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="9e455-181">すべての TCP 呼び出し v.s を表示する場合。</span><span class="sxs-lookup"><span data-stu-id="9e455-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="9e455-182">UDP 呼び出し。トランスポートの種類に関する新しい次元を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="9e455-183">特定の建物内の低品質な通話の数を表示する場合は、新しいフィルターを追加して、その建物との間の通話を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="9e455-184">**例 2: レポート定義のサンプル**</span><span class="sxs-lookup"><span data-stu-id="9e455-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="9e455-185">クエリを作成するときに、測定値/ディメンション/フィルターの完全なリストと対応する値を記述する方法を理解するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="9e455-186">この場合は、ポータルに移動し、レポート エディターを使用してレポートを作成し、レポート定義の JSON 文字列を表示して、定義をカスタム レポートにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="9e455-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="9e455-187">この例では、図のような Web ページを作成します。このページでは、ユーザーが既存のレポート セット (またはレポート) の ID を入力し、レポート セットまたはレポートの定義を Web ページに表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="9e455-188">その後、ユーザーは、各レポートの JSON 文字列を例 1 に示すコードにプラグインし、ユーザーが望むカスタマイズされたレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD の例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="9e455-190">レポート定義ビューアー ツールを作成するには、Repository Service への呼び出しを送信して、必要な各レポート セットの定義の JSON 文字列表現を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="9e455-191">リポジトリ API は、指定されたレポート セット ID に基づいてレポート セット定義を返します。</span><span class="sxs-lookup"><span data-stu-id="9e455-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="9e455-192">簡単な例は次のとおりです。コードには、リポジトリ サービスにクエリを送信して、その識別子に基づいてリポジトリ アイテムのコンテンツを取得する簡単な例であるブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e455-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="9e455-193">また、コードの次の部分 (processReportSetData メソッド) は、AJAX 呼び出しを送信して、そのレポート セット内の各レポートの定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e455-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="9e455-194">CQD Web ポータルの ID はレポート セットの ID です。AJAX 呼び出しはレポート セット アイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="9e455-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="9e455-195">リポジトリ API、特に GetItems の詳細については、アイテムの取得に [関するページを参照してください](get-items.md)。</span><span class="sxs-lookup"><span data-stu-id="9e455-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="9e455-196">上記の場合、図のような Web ページが作成されます (最初のアクセス時にレポート定義は表示されます)。</span><span class="sxs-lookup"><span data-stu-id="9e455-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="9e455-197">CQD ポータルからレポート セット ID を取得します (CQD ポータル URL (例:</span><span class="sxs-lookup"><span data-stu-id="9e455-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="9e455-198">をクリックし、このレポート セット ID をこの Web ページの入力セクションに挿入します。</span><span class="sxs-lookup"><span data-stu-id="9e455-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="9e455-199">[load] ボタンを押して、レポート セットの完全な定義 (測定値、ディメンション、フィルター リスト) を確認します。</span><span class="sxs-lookup"><span data-stu-id="9e455-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="9e455-200">要約すると、レポート/レポート セットの完全な定義をすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="9e455-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="9e455-201">手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e455-201">The steps are:</span></span>

1. <span data-ttu-id="9e455-202">ポータルに移動し、クエリ エディターを使用してレポートをカスタマイズします (レポートの上にある [編集] ボタンをクリックして、測定値/ディメンション/フィルターの編集、追加、削除、レポートの保存を行います)。</span><span class="sxs-lookup"><span data-stu-id="9e455-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="9e455-203">URL からレポート セット ID を取得します ('/#/' サインイン URL の後の整数)。</span><span class="sxs-lookup"><span data-stu-id="9e455-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="9e455-204">例 2 で作成したこのレポート定義 Web ページを起動し、レポート セット ID を入力して、レポート セットの完全な定義を取得します (データ API 呼び出しで使用します)。</span><span class="sxs-lookup"><span data-stu-id="9e455-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="9e455-205">**例 3: スコアカードのサンプル**</span><span class="sxs-lookup"><span data-stu-id="9e455-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="9e455-206">より複雑なタスクの時間。</span><span class="sxs-lookup"><span data-stu-id="9e455-206">Time for a more complicated task.</span></span> <span data-ttu-id="9e455-207">図のような Web ページを作成する場合</span><span class="sxs-lookup"><span data-stu-id="9e455-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="9e455-208">より大量のデータを処理できるよう、例 1 (例 2 で生成された Web ページを使用してレポートの完全な定義を取得) を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="9e455-209">この場合は、測定値とディメンション の一覧を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="9e455-210">測定値やディメンションを追加/編集する方法を理解するには、例 2 の指示に従って、完全な測定値とディメンション の一覧を含む完全なレポート定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e455-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="9e455-211">完全なレポート定義をサンプル コードに接続します。</span><span class="sxs-lookup"><span data-stu-id="9e455-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="9e455-212">図のスコアカード ページにアクセスするための詳細な手順は、例 1 に示すサンプルから次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e455-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="9e455-213">'query' 変数の測定値を更新 `[Measures].[Audio Good Streams JPDR Count]` する `[Measures].[Audio Poor Streams JPDR Count]` `[Measures].[AudioPoorJPDRPercentage]`</span><span class="sxs-lookup"><span data-stu-id="9e455-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="9e455-214">フィルターを更新します。</span><span class="sxs-lookup"><span data-stu-id="9e455-214">Update the filters.</span></span> <span data-ttu-id="9e455-215">例 1 のフィルターの JSON データには、ディメンションに設定されたフィルターが 1 つ含まれており  `[StartDate].[Month]` 、</span><span class="sxs-lookup"><span data-stu-id="9e455-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="9e455-216">Filters は JSON 配列です。フィルターの一覧に追加のディメンションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9e455-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="9e455-217">たとえば、"currentMonth" の有線呼び出し内でサーバークライアントを取得するには、次のフィルターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9e455-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="9e455-218">ここで、次元は  `[Scenarios].[ScenarioPair]` 等しくなります `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 。</span><span class="sxs-lookup"><span data-stu-id="9e455-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="9e455-219">これは  `[Scenario.][ScenarioPair]` 、レポートの作成を簡略化するために作成された特別なディメンションです。</span><span class="sxs-lookup"><span data-stu-id="9e455-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="9e455-220">それに対応する 6 つの値があります `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 。</span><span class="sxs-lookup"><span data-stu-id="9e455-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="9e455-221">そのため、6 つのフィルターを組み合わせてシナリオを定義する代わりに、1 つのフィルターのみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="9e455-222">この例では、値は次のシナリオに変換されます。1 つ目はサーバー、2 番目はサーバー、1 番目は内部、2 番目は内部、1 番目の接続の種類は有線、2 番目の接続の種類はワイヤード  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` ("Server-Client-Inside Wired" の正確な定義) です。</span><span class="sxs-lookup"><span data-stu-id="9e455-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="9e455-223">シナリオごとに 1 つのフィルター セットを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e455-223">Create one filter set per scenario.</span></span> <span data-ttu-id="9e455-224">図のスコアカードの各行は異なるシナリオを表し、これは異なるフィルターになります (次元と測定値は変わりません)。</span><span class="sxs-lookup"><span data-stu-id="9e455-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="9e455-225">AJAX 呼び出しの結果を解析し、テーブルの正しい位置に配置します。</span><span class="sxs-lookup"><span data-stu-id="9e455-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="9e455-226">これは主に HTML と JavaScript の操作です。ここでは詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="9e455-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="9e455-227">代わりに、付録 A にコードを示します。</span><span class="sxs-lookup"><span data-stu-id="9e455-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9e455-228">クロスオリジン リソース共有 (CORS) が有効な場合、ユーザーは要求されたリソースに "No 'Access-Control-Allow-Origin' ヘッダーが存在しないというエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e455-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="9e455-229">Origin 'null' is therefore not allowed access".</span><span class="sxs-lookup"><span data-stu-id="9e455-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="9e455-230">この問題を解決するには、ポータルがインストールされているフォルダーの下に HTML ファイルを配置します (既定では `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` 、</span><span class="sxs-lookup"><span data-stu-id="9e455-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="9e455-231">その後、URL を使用して任意のブラウザーから HTML にアクセスします  `http://<servername>/cqd/<html_file_name>` 。</span><span class="sxs-lookup"><span data-stu-id="9e455-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="9e455-232">(ローカル CQD ダッシュボードの既定の URL は  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="9e455-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="9e455-233">付録 A</span><span class="sxs-lookup"><span data-stu-id="9e455-233">Appendix A</span></span>

<span data-ttu-id="9e455-234">例 3 の HTML コード (スコアカードのサンプル):</span><span class="sxs-lookup"><span data-stu-id="9e455-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
