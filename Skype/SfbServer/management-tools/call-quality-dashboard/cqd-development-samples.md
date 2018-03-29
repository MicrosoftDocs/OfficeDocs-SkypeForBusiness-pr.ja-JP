---
title: CQD の開発サンプル
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '概要: は、品質のダッシュ ボードを呼び出すためのチュートリアルと開発のサンプルを確認します。 通話品質のダッシュ ボードは、ビジネス サーバー 2015 の Skype のツールです。'
ms.openlocfilehash: 40e6defd85cc9e8dd86956a3539b51e1846b6da5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="cqd-development-samples"></a><span data-ttu-id="1b51e-104">CQD の開発サンプル</span><span class="sxs-lookup"><span data-stu-id="1b51e-104">CQD Development Samples</span></span>
 
<span data-ttu-id="1b51e-p102">**概要:** 通話品質ダッシュボードのチュートリアルと開発サンプルを示します。通話品質ダッシュボードは Skype for Business Server 2015 用のツールです。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p102">**Summary:** Review a tutorial and development samples for Call Quality Dashboard. Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1b51e-107">この記事では、通話品質ダッシュボード (CQD) の開発に関するチュートリアルとサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>
  
## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="1b51e-108">通話品質ダッシュボード (CQD) の開発サンプル</span><span class="sxs-lookup"><span data-stu-id="1b51e-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="1b51e-109">チュートリアル: CQD Data Service および Repository Service API を使用してカスタマイズされたレポート プレゼンテーションの作成</span><span class="sxs-lookup"><span data-stu-id="1b51e-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>
  
### <a name="introduction-to-cqd"></a><span data-ttu-id="1b51e-110">CQD の概要</span><span class="sxs-lookup"><span data-stu-id="1b51e-110">Introduction to CQD</span></span>

<span data-ttu-id="1b51e-111">CQD により、オンプレミス Skype for Business Server 展開に関して集計された通話品質情報にすばやく簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="1b51e-112">CQD は、QoE アーカイブ データベース、キューブ、およびポータルの 3 つのコンポーネントから構成されています。</span><span class="sxs-lookup"><span data-stu-id="1b51e-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="1b51e-113">ポータルはメインのプレゼンテーション層で、さらに次の 3 つのコンポーネントに分割することができます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>
  
1. <span data-ttu-id="1b51e-114">アクセスできないため、データ サービスには、 [API の呼び出し品質ダッシュ ボード (救難) ビジネス サーバー 2015 の Skype でのデータ](data-api.md)を使用してユーザーが認証されます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](data-api.md).</span></span>
    
2. <span data-ttu-id="1b51e-115">リポジトリ サービスには、[リポジトリ API の呼び出し品質ダッシュ ボード (救難) ビジネス サーバー 2015 の Skype で](repository-api.md)を使用して認証されたユーザーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1b51e-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015](repository-api.md).</span></span>
    
3. <span data-ttu-id="1b51e-p104">CQD のユーザーが表示および操作する、HTML5 ベースのインターフェイスである Web ポータル。これは、認証済みユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p104">Web portal, which is the HTML5 based interface that CQD users see and interact with. This is accessible for authenticated users.</span></span>
    
<span data-ttu-id="1b51e-118">Web ポータルに表示されるレポートは、レポートの「セット」にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="1b51e-119">図には、2 つのレポートが含まれるレポート セットが表示されています。</span><span class="sxs-lookup"><span data-stu-id="1b51e-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="1b51e-120">以下のダッシュボードの各レポートには、さまざまなフィルターが適用された、数か月の良好な通話数、低品質な通話数、および低品質な通話のパーセンテージに関するクエリ結果が表示されています。</span><span class="sxs-lookup"><span data-stu-id="1b51e-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 
  
![CQD のサンプル レポート](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)
  
<span data-ttu-id="1b51e-p106">CQD は、CQM (通話の品質保証の方法論) に従って作成されるため、レポートの既定のセットは、CQM により導入される調査フローに合わせて作成されます。またユーザーは、ニーズに合うようカスタム レポートを柔軟に編集または作成できます。ただし、データの視覚化には複数の方法があるため、CQD により提供される視覚化では、すべてのユーザーのニーズが完全には満たされない場合があります。このような場合、ユーザーは Data API と Repository API を利用してカスタム レポートのページを作成できます。このチュートリアルでは、一連の例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>
  
### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="1b51e-127">ダッシュボードでデータ サービスを利用する方法</span><span class="sxs-lookup"><span data-stu-id="1b51e-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="1b51e-128">救難のホームページに移動する場合 (例: http://localhost/cqd)、レポートの設定、およびリポジトリ ・ サービスからの認証および承認されたユーザーに対応するレポートが取得されます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="1b51e-129">レポート セットの ID には、年、月の完全な URL が作成される (レポート セットの ID 番号の整数 ' #/' url] セクションの後で、既定で現在の年・月が追加されますレポート セットの ID の末尾にスラッシュの後)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="1b51e-130">レポートの定義は JSON 形式で格納され、Repository Service から取得されると、Data Service への入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="1b51e-131">Data Service は入力に基づいて多次元式 (MDX) クエリを生成し、これらの MDX クエリをキューブに対して実行して、各レポートのデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 
  
### <a name="building-customized-reports"></a><span data-ttu-id="1b51e-132">カスタマイズされたレポートの作成</span><span class="sxs-lookup"><span data-stu-id="1b51e-132">Building customized reports</span></span>

<span data-ttu-id="1b51e-p108">CQD では既に非常に柔軟なレポートのカスタマイズが可能ですが、CQD で作成された複数のレポートにわたるデータを集計したい場合もあります。たとえば、有線通話のすべての可能な組み合わせに対して、低品質な通話のパーセンテージを表に示すレポートを作成したい場合などです (図のような結果です)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>
  
![CQD のテーブル](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)
  
<span data-ttu-id="1b51e-p109">CQD により提供されるポータルを使用すると、ユーザーは複数のレポートを参照して各レポートの低品質な通話のパーセンテージを抽出および記録する必要があります。これは、収集する必要があるデータ ポイントが多い場合には手間のかかる作業です。Data API は、Data Service からデータを取得することによって同じことをプログラムにより実現する手段 (AJAX 呼び出し経由など) を提供するものです。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 
  
 <span data-ttu-id="1b51e-138">**例 1: シンプルなレポートのサンプル**</span><span class="sxs-lookup"><span data-stu-id="1b51e-138">**Example 1: Simple report sample**</span></span>
  
<span data-ttu-id="1b51e-p110">まずは、シンプルな例について説明します。以下の図のように、HTML ページに 2015 年 2 月の Audio Good Streams と Audio Bad Stream の数を示す場合:</span><span class="sxs-lookup"><span data-stu-id="1b51e-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>
  
![CQD のレポート例](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)
  
<span data-ttu-id="1b51e-p111">必要な操作は、適切なパラメーターを使用して Data Service への呼び出しを送信し、HTML テーブルにクエリの結果を示すことです。以下に、JavaScript コードのサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>
  
```
        
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

<span data-ttu-id="1b51e-144">この例は、さらに次の 3 つのステップに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-144">This example can be further deconstructed into three steps:</span></span>
  
1. <span data-ttu-id="1b51e-145">(これは、変数 'クエリ' の定義の例) でクエリを構築します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="1b51e-146">クエリは JSON オブジェクトとして定義され、次のデータを含みます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-146">The query is defined as a JSON object, which includes the following data:</span></span>
    
   <span data-ttu-id="1b51e-147">a.</span><span class="sxs-lookup"><span data-stu-id="1b51e-147">a.</span></span> <span data-ttu-id="1b51e-148">ゼロまたは 1 つ以上の次元。</span><span class="sxs-lookup"><span data-stu-id="1b51e-148">Zero or more dimensions.</span></span> <span data-ttu-id="1b51e-149">各次元は DataModelName により示されます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-149">Each dimension is indicated by a DataModelName.</span></span>
    
   <span data-ttu-id="1b51e-150">b.</span><span class="sxs-lookup"><span data-stu-id="1b51e-150">b.</span></span> <span data-ttu-id="1b51e-151">ゼロまたは 1 つ以上のフィルター。</span><span class="sxs-lookup"><span data-stu-id="1b51e-151">Zero or more filters.</span></span> <span data-ttu-id="1b51e-152">各フィルターには以下が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-152">Each filter has:</span></span>
    
      - <span data-ttu-id="1b51e-153">DataModelName (フィルター セットが含まれる次元)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-153">DataModelName (the dimension that will have the filter set).</span></span>
    
      - <span data-ttu-id="1b51e-154">Value (オペランドにより比較される値)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-154">Value (the value that will be compared by the operand).</span></span>
    
      - <span data-ttu-id="1b51e-155">オペランド (比較の種類、0 の場合は「等しい」など)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-155">Operand (comparison type, 0 means "Equal").</span></span>
    
    <span data-ttu-id="1b51e-156">c.</span><span class="sxs-lookup"><span data-stu-id="1b51e-156">c.</span></span> <span data-ttu-id="1b51e-157">1 つ以上の測定値。</span><span class="sxs-lookup"><span data-stu-id="1b51e-157">One or more measurements.</span></span>
    
2. <span data-ttu-id="1b51e-p116">AJAX 呼び出しを介して Data Service にクエリを送信します。次の要求パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p116">Send the query to Data Service via AJAX call. The following request parameters need to be provided:</span></span>
    
   <span data-ttu-id="1b51e-160">a.</span><span class="sxs-lookup"><span data-stu-id="1b51e-160">a.</span></span> <span data-ttu-id="1b51e-161">url (http://[サーバー名]/QoEDataService/RunQuery を指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>
    
   <span data-ttu-id="1b51e-162">b.</span><span class="sxs-lookup"><span data-stu-id="1b51e-162">b.</span></span> <span data-ttu-id="1b51e-163">(これは、'クエリ' 変数で定義されている JSON オブジェクトの文字列形式) のデータです。</span><span class="sxs-lookup"><span data-stu-id="1b51e-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="1b51e-164">Data Service は、成功時のコールバック関数のパラメーターとしてクエリの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>
    
   <span data-ttu-id="1b51e-165">c.</span><span class="sxs-lookup"><span data-stu-id="1b51e-165">c.</span></span> <span data-ttu-id="1b51e-166">(QoEDataService の RunQuery のみを受け入れる ' POST' 要求) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>
    
   <span data-ttu-id="1b51e-167">d.</span><span class="sxs-lookup"><span data-stu-id="1b51e-167">d.</span></span> <span data-ttu-id="1b51e-168">async (AJAX 呼び出しを同期と非同期のどちらにするかを示すフラグです)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>
    
   <span data-ttu-id="1b51e-169">e。</span><span class="sxs-lookup"><span data-stu-id="1b51e-169">e.</span></span> <span data-ttu-id="1b51e-170">contentType を (「アプリケーションと json」をする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-170">contentType (should be "application/json").</span></span>
    
   <span data-ttu-id="1b51e-171">f。</span><span class="sxs-lookup"><span data-stu-id="1b51e-171">f.</span></span> <span data-ttu-id="1b51e-172">success (AJAX 呼び出しが正常に完了した場合のコールバック関数)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-172">success (call-back function for when the AJAX call finishes successfully).</span></span>
    
   <span data-ttu-id="1b51e-173">g です。</span><span class="sxs-lookup"><span data-stu-id="1b51e-173">g.</span></span> <span data-ttu-id="1b51e-174">error (AJAX 呼び出しが失敗した場合のエラー処理関数)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-174">error (error handling function for when AJAX call fails).</span></span>
    
3. <span data-ttu-id="1b51e-175">HTML の div 要素にデータを配置します (コード例では、AJAX 要求が正常に完了した後、匿名の関数呼び出しによりこの処理が行われます)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>
    
<span data-ttu-id="1b51e-p124">この JavaScript コードを HTML ページに埋め込むと、ページでは図に示すようなレポートが表示されます。全 HTML は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>
  
```
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

<span data-ttu-id="1b51e-p125">ここまでのレポートは非常にシンプルです。ユーザーは、レポートをカスタマイズするために測定値、次元、またはフィルターを追加できます。たとえば、AppSharing の低品質な通話のパーセンテージを表示したい場合は、AppSharing に関する新しい測定値を追加する必要があります。すべての TCP 呼び出しと UDP 呼び出しを対比して表示したい場合は、転送の種類に関する新しい次元を追加する必要があります。特定の建物内の低品質な通話数を表示したい場合は、その建物で入出力される通話を選択するために新しいフィルターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>
  
 <span data-ttu-id="1b51e-184">**例 2: レポート定義のサンプル**</span><span class="sxs-lookup"><span data-stu-id="1b51e-184">**Example 2: Report definition sample**</span></span>
  
<span data-ttu-id="1b51e-p126">ユーザーによっては、クエリを作成する際の測定値/次元/フィルターと対応する値の全一覧を記述することが難しい場合があります。この場合は、ポータルに移動し、レポート エディターを使用してレポートを作成します。そして、レポート定義の JSON 文字列を表示して、定義をカスタム レポートにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 
  
<span data-ttu-id="1b51e-p127">この例では、図に示すような Web ページを作成します。この Web ページでは、ユーザーは既存のレポート セット (またはレポート) の ID を入力し、レポート セットまたはレポートの定義を表示することができます。そして、ユーザーは各レポートの JSON 文字列を、例 1 で示したようなコードに挿入し、ユーザーが求めるカスタマイズしたレポートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 
  
![CQD の例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)
  
<span data-ttu-id="1b51e-p128">レポート定義の表示ツールを作成するには、Repository Service に呼び出しを送信して、必要な各 report-set の定義の JSON 文字列表現を取得する必要があります。Repository API は、指定のレポート セット ID に基づいて report-set の定義を返します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 
  
<span data-ttu-id="1b51e-192">簡単な例は、次のように、コードには、その識別子に基づいたリポジトリ アイテムの内容を取得するのにはリポジトリ サービスにクエリを送信する簡単な例は、ブロックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b51e-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="1b51e-193">コード (processReportSetData メソッド) の次の部分がそのレポートのセット内の各レポートの定義を取得する AJAX 呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="1b51e-194">救難 web ポータルの ID がレポート セットの ID であるため、AJAX 呼び出しは、レポート アイテムの設定を返します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="1b51e-195">詳細については、リポジトリ API であり、特に GetItems、[項目の取得](get-items.md)にあります。</span><span class="sxs-lookup"><span data-stu-id="1b51e-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 
  
```
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

<span data-ttu-id="1b51e-196">上記、web ページ (最初に訪問時にレポートの定義) に図のようになります。</span><span class="sxs-lookup"><span data-stu-id="1b51e-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="1b51e-197">救難ポータルからレポートのセット ID を取得する (' #/' 救難ポータルにサインイン後の URL (例。</span><span class="sxs-lookup"><span data-stu-id="1b51e-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="1b51e-198">レポートの最初の図形 ID は 3024)、このレポートのセット ID をこの web ページの [入力] セクションに配置するとします。</span><span class="sxs-lookup"><span data-stu-id="1b51e-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="1b51e-199">Load ボタンを押すし、レポートのセットの完全定義 (測定、分析コード、フィルターのリスト) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b51e-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>
  
<span data-ttu-id="1b51e-p131">以下に、レポート/レポート セットの全定義をすばやく取得するための手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p131">In summary, in order to quickly get the full definition of a report/report set. The steps are:</span></span>
  
1. <span data-ttu-id="1b51e-202">ポータルに移動し、([編集] を選択し、上レポートを編集、追加、フィルター/測定/分析コードを削除するボタンをクリックし、レポートを保存] をクリックします)、レポートをカスタマイズするのにはクエリ ・ エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>
    
2. <span data-ttu-id="1b51e-203">(' #/' の後の整数は、URL で署名) の URL からレポートのセット ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>
    
3. <span data-ttu-id="1b51e-204">例 2 で作成したレポート定義の Web ページを開き、レポート セット ID を入力して、(Data API 呼び出しで使用するために) レポート セットの全定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>
    
 <span data-ttu-id="1b51e-205">**例 3: スコアカードのサンプル**</span><span class="sxs-lookup"><span data-stu-id="1b51e-205">**Example 3: Scorecard sample**</span></span>
  
<span data-ttu-id="1b51e-p132">次は、より複雑なタスクです。図のような Web ページを作成したい場合はどうすればよいでしょうか? より大量のデータを処理できるように (レポートの全定義を取得するために例 2 で生成した Web ページを活用して)、例 1 を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>
  
<span data-ttu-id="1b51e-p133">この場合、測定値と次元の一覧を更新する必要があります。測定値/次元を追加/編集する方法としては、例 2 の指示に従い、測定値と次元の全一覧を含む、レポートの全定義を取得します。そのレポートの全定義をサンプル コードに挿入します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 
  
<span data-ttu-id="1b51e-212">例 1 に示されているサンプルから、図でスコアカード ページを取得する詳細な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b51e-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>
  
1. <span data-ttu-id="1b51e-213">'クエリ' 変数の測定値を更新`[Measures].[Audio Good Streams JPDR Count]`と`[Measures].[Audio Poor Streams JPDR Count]`を`[Measures].[AudioPoorJPDRPercentage]`。</span><span class="sxs-lookup"><span data-stu-id="1b51e-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 
    
2. <span data-ttu-id="1b51e-214">フィルターを更新します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-214">Update the filters.</span></span> <span data-ttu-id="1b51e-215">例 1 のフィルターの JSON データの分析コードに対して設定されている 1 つのフィルターには`[StartDate].[Month]`です。</span><span class="sxs-lookup"><span data-stu-id="1b51e-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="1b51e-216">フィルターは JSON 配列であるため、フィルターの一覧に次元を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="1b51e-217">たとえば、"currentMonth"のワイヤード (有線) の呼び出しの内部サーバーのクライアントを取得する必要な次のフィルター。</span><span class="sxs-lookup"><span data-stu-id="1b51e-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>
    
  ```
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

  <span data-ttu-id="1b51e-218">分析コードをここで`[Scenarios].[ScenarioPair]`と等しくなるように設定されて`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`。</span><span class="sxs-lookup"><span data-stu-id="1b51e-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="1b51e-219">`[Scenario.][ScenarioPair]`は、特別なディメンションがレポートの作成を簡略化するために作成します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="1b51e-220">`[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` に対応する 6 つの値があるため、シナリオを定義するために 6 つのフィルターの組み合わせを使用するのではなく、1 つのフィルターを使用するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="1b51e-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="1b51e-221">したがって 6 フィルターの組み合わせを使用するシナリオを定義するのには、代わりにのみ必要があります 1 つのフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="1b51e-222">例では、値`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`シナリオに変換する: 最初サーバーは、2 つ目はサーバーではないの内部は、最初の内部は、2 つ目は最初の接続の種類は、ワイヤード (有線)、および 2 番目の接続の種類は、ワイヤード (有線)、正確な定義である」サーバー-クライアント-内側ワイヤード (有線)」です。</span><span class="sxs-lookup"><span data-stu-id="1b51e-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>
    
3. <span data-ttu-id="1b51e-p136">シナリオごとに 1 つのフィルター セットを作成します。図のスコアカードの各行は個別のシナリオを表し、また個別のフィルターになります (一方、次元と測定値は同じままです)。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 
    
4. <span data-ttu-id="1b51e-p137">AJAX 呼び出しの結果を解析し、解析結果をテーブルの適切な位置に配置します。これは大部分が HTML と JavaScript の操作であるため、ここでは詳細を説明しません。その代わりに、付録 A にコードを示します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="1b51e-228">クロス元リソース共有 (CORS) を有効にすると、ユーザーがエラーが発生のように 'アクセス制御の許可-発信元' ヘッダーがありません"要求されたリソース上に存在します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="1b51e-229">'Null' の原点は、そのためアクセスを許可しない"です。</span><span class="sxs-lookup"><span data-stu-id="1b51e-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="1b51e-230">この問題を解決するには、ポータルがインストールされているフォルダー (既定では `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`) に HTML ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="1b51e-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="1b51e-231">URL を使用して任意のブラウザーを使って、html、アクセス`http://<servername>/cqd/<html_file_name>`。</span><span class="sxs-lookup"><span data-stu-id="1b51e-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="1b51e-232">(ローカルの救難のダッシュ ボードの既定の URL は、 `http://<servername>/cqd.`)</span><span class="sxs-lookup"><span data-stu-id="1b51e-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 
  
### <a name="appendix-a"></a><span data-ttu-id="1b51e-233">付録 A</span><span class="sxs-lookup"><span data-stu-id="1b51e-233">Appendix A</span></span>

<span data-ttu-id="1b51e-234">例 3 の HTML コード (スコアカードのサンプル):</span><span class="sxs-lookup"><span data-stu-id="1b51e-234">HTML code for Example 3 (Scorecard sample):</span></span>
  
```
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


