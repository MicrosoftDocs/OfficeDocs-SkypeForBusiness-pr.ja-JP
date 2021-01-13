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
# <a name="cqd-development-samples"></a>CQD の開発サンプル

**概要:** 通話品質ダッシュボードのチュートリアルと開発サンプルを確認します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。

この記事では、通話品質ダッシュボード (CQD) の開発に関するチュートリアルとサンプルを提供します。

## <a name="call-quality-dashboard-cqd-development-samples"></a>通話品質ダッシュボード (CQD) 開発サンプル

チュートリアル: CQD データ サービスとリポジトリ サービス API を使用してカスタマイズされたレポート プレゼンテーションを作成する。

### <a name="introduction-to-cqd"></a>CQD の概要

CQD は、オンプレミスの Skype for Business Server 展開に関する集約された通話品質情報にすばやく簡単にアクセスできます。 CQD は、QoE アーカイブ データベース、キューブ、ポータルの 3 つのコンポーネントで構成されます。 ポータルはメインのプレゼンテーション 層であり、さらに次の 3 つのコンポーネントに分かれています。

1. Data Service は、Skype for Business Server の通話品質ダッシュボード [(CQD)](data-api.md)用データ API を通じて認証済みユーザーがアクセスできます。

2. Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).

3. Web ポータル。CQD ユーザーが表示および操作する HTML5 ベースのインターフェイスです。 これは、認証されたユーザーがアクセスできます。

Web ポータルに表示されるレポートは、"レポート セット" にグループ化されます。 図は、2 つのレポートを含むレポート セットを示しています。 このダッシュボードの以下の各レポートは、数か月間の良好な通話数、低品質通話数、低品質通話率に関するクエリ結果を示し、さまざまなフィルターが適用されています。 

![CQD サンプル レポート](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD は CQM (Call Quality Methodology) に従って作成されます。そのため、既定の一連のレポートは、CQM によって導入された調査フローに合わせて設計されています。 また、ユーザーはニーズに合わせてカスタム レポートを柔軟に編集または作成できます。 ただし、データを視覚化する方法は複数あるので、CQD によって提供される視覚エフェクトは、すべてのユーザーのニーズに完全には対応できない場合があります。 このような場合、ユーザーはデータ API とリポジトリ API を利用してカスタム レポート ページを作成できます。 このチュートリアルでは、一連の例を示します。

### <a name="how-the-dashboard-consumes-the-data-service"></a>ダッシュボードがデータ サービスを使用する方法

CQD ホーム ページ (例: 認証および承認されたユーザーのレポート セットと対応するレポート) に移動すると、リポジトリ サービスから http://localhost/cqd) 取得されます。 完全な URL は、レポート セット ID と年月から作成されます (レポート セット ID は URL の '/#/' セクションの後の整数値で、既定では、現在の年月はスラッシュの後にレポート セット ID の末尾に追加されます)。 レポート定義は JSON 形式で格納され、リポジトリ サービスから取得されると、データ サービスへの入力として使用されます。 データ サービスは、入力に基づいて複数次元式 (MDX) クエリを生成し、キューブに対してこれらの MDX クエリを実行して、各レポートのデータを取得します。 

### <a name="building-customized-reports"></a>カスタマイズされたレポートを作成する

CQD には既に、レポートのカスタマイズに多くの柔軟性がありますが、CQD で作成された複数のレポート間でデータを集計する必要がある場合があります。 たとえば、次の表に示すように、有線通話のすべての可能な組み合わせの低品質通話のパーセンテージを示すレポートを作成する必要がある場合があります (図のような結果)。

![CQD テーブル](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

CQD が提供するポータルを使用すると、ユーザーは複数のレポートに移動して、それぞれの低品質通話率を抽出して記録する必要があります。収集する必要があるデータ ポイントが多い場合は手間がかからない可能性があります。 データ API は、データ サービスからデータを取得 (AJAX 呼び出しなど) することで、これを実現するためのプログラム的な方法をユーザーに提供します。 

 **例 1: 単純なレポートのサンプル**

最初に簡単な例を示します。 次の図のような HTML ページに、2015 年 2 月の Audio Good Stream と Audio Bad Stream の数を表示する場合:

![CQD レポートの例](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

必要なのは、適切なパラメーターを使用してデータ サービスに呼び出しを送信し、クエリ結果を HTML テーブルに表示することです。 JavaScript コードのサンプルを次に示します。

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

この例は、さらに次の 3 つの手順に分けできます。

1. クエリを作成します (この例では、これは変数 'query' で定義されています)。 クエリは、次のデータを含む JSON オブジェクトとして定義されます。

   a.  0 個以上の次元 各ディメンションは DataModelName で示されます。

   b. 0 個以上のフィルター。 各フィルターには次の機能があります。

   - DataModelName (フィルター セットを持つディメンション)。

   - 値 (オペランドによって比較される値)。

   - オペランド (比較の種類、0 は "等しい" を意味します)。

     c. 1 つ以上の測定値。

2. AJAX 呼び出しを使用してデータ サービスにクエリを送信します。 次の要求パラメーターを指定する必要があります。

   a.  url (http://[ServerName]/QoEDataService/RunQuery である必要があります)。

   b. data (これは 'query' 変数で定義されている JSON オブジェクトの文字列表現です)。 Data Service は、成功を収めるコール バック関数のパラメーターとしてクエリ結果を返します。

   c. type (QoEDataService の場合、RunQuery は 'POST' 要求のみを受け入れる)。

   d.  非同期 (AJAX 呼び出しが同期か非同期かを示すフラグ)。

   e.  contentType ("application/json" である必要があります)。

   f. success (AJAX 呼び出しが正常に終了した場合のコール バック関数)。

   g.  error (AJAX 呼び出しが失敗したときのエラー処理関数)。

3. HTML 内の div 要素にデータを挿入します (コードの例では、AJAX 要求が正常に完了した後、匿名関数呼び出しによって行われます)。

JavaScript コードを HTML ページに囲み、ページには図のようなレポートが表示されます。 完全な html は次のとおりです。

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

これまでのところ、このレポートは非常に単純です。 ユーザーは、レポートをカスタマイズするために、測定値、ディメンション、またはフィルターを追加できます。 たとえば、AppSharing の低品質通話のパーセンテージを表示する場合は、AppSharing に関する新しい測定値を追加する必要があります。 すべての TCP 呼び出し v.s を表示する場合。 UDP 呼び出し。トランスポートの種類に関する新しい次元を追加する必要があります。 特定の建物内の低品質な通話の数を表示する場合は、新しいフィルターを追加して、その建物との間の通話を選択する必要があります。

 **例 2: レポート定義のサンプル**

クエリを作成するときに、測定値/ディメンション/フィルターの完全なリストと対応する値を記述する方法を理解するのは困難な場合があります。 この場合は、ポータルに移動し、レポート エディターを使用してレポートを作成し、レポート定義の JSON 文字列を表示して、定義をカスタム レポートにコピーできます。 

この例では、図のような Web ページを作成します。このページでは、ユーザーが既存のレポート セット (またはレポート) の ID を入力し、レポート セットまたはレポートの定義を Web ページに表示できます。 その後、ユーザーは、各レポートの JSON 文字列を例 1 に示すコードにプラグインし、ユーザーが望むカスタマイズされたレポートを作成できます。 

![CQD の例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

レポート定義ビューアー ツールを作成するには、Repository Service への呼び出しを送信して、必要な各レポート セットの定義の JSON 文字列表現を取得する必要があります。 リポジトリ API は、指定されたレポート セット ID に基づいてレポート セット定義を返します。 

簡単な例は次のとおりです。コードには、リポジトリ サービスにクエリを送信して、その識別子に基づいてリポジトリ アイテムのコンテンツを取得する簡単な例であるブロックが含まれています。 また、コードの次の部分 (processReportSetData メソッド) は、AJAX 呼び出しを送信して、そのレポート セット内の各レポートの定義を取得します。 CQD Web ポータルの ID はレポート セットの ID です。AJAX 呼び出しはレポート セット アイテムを返します。 リポジトリ API、特に GetItems の詳細については、アイテムの取得に [関するページを参照してください](get-items.md)。 

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

上記の場合、図のような Web ページが作成されます (最初のアクセス時にレポート定義は表示されます)。 CQD ポータルからレポート セット ID を取得します (CQD ポータル URL (例: をクリックし、このレポート セット ID をこの Web ページの入力セクションに挿入します。 [load] ボタンを押して、レポート セットの完全な定義 (測定値、ディメンション、フィルター リスト) を確認します。

要約すると、レポート/レポート セットの完全な定義をすばやく取得します。 手順は次のとおりです。

1. ポータルに移動し、クエリ エディターを使用してレポートをカスタマイズします (レポートの上にある [編集] ボタンをクリックして、測定値/ディメンション/フィルターの編集、追加、削除、レポートの保存を行います)。

2. URL からレポート セット ID を取得します ('/#/' サインイン URL の後の整数)。

3. 例 2 で作成したこのレポート定義 Web ページを起動し、レポート セット ID を入力して、レポート セットの完全な定義を取得します (データ API 呼び出しで使用します)。

   **例 3: スコアカードのサンプル**

より複雑なタスクの時間。 図のような Web ページを作成する場合 より大量のデータを処理できるよう、例 1 (例 2 で生成された Web ページを使用してレポートの完全な定義を取得) を更新する必要があります。

この場合は、測定値とディメンション の一覧を更新する必要があります。 測定値やディメンションを追加/編集する方法を理解するには、例 2 の指示に従って、完全な測定値とディメンション の一覧を含む完全なレポート定義を取得します。 完全なレポート定義をサンプル コードに接続します。 

図のスコアカード ページにアクセスするための詳細な手順は、例 1 に示すサンプルから次のとおりです。

1. 'query' 変数の測定値を更新 `[Measures].[Audio Good Streams JPDR Count]` する `[Measures].[Audio Poor Streams JPDR Count]` `[Measures].[AudioPoorJPDRPercentage]` 

2. フィルターを更新します。 例 1 のフィルターの JSON データには、ディメンションに設定されたフィルターが 1 つ含まれており  `[StartDate].[Month]` 、 Filters は JSON 配列です。フィルターの一覧に追加のディメンションを追加できます。 たとえば、"currentMonth" の有線呼び出し内でサーバークライアントを取得するには、次のフィルターが必要です。

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

   ここで、次元は  `[Scenarios].[ScenarioPair]` 等しくなります `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 。 これは  `[Scenario.][ScenarioPair]` 、レポートの作成を簡略化するために作成された特別なディメンションです。 それに対応する 6 つの値があります `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 。 そのため、6 つのフィルターを組み合わせてシナリオを定義する代わりに、1 つのフィルターのみを使用する必要があります。 この例では、値は次のシナリオに変換されます。1 つ目はサーバー、2 番目はサーバー、1 番目は内部、2 番目は内部、1 番目の接続の種類は有線、2 番目の接続の種類はワイヤード  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` ("Server-Client-Inside Wired" の正確な定義) です。

3. シナリオごとに 1 つのフィルター セットを作成します。 図のスコアカードの各行は異なるシナリオを表し、これは異なるフィルターになります (次元と測定値は変わりません)。 

4. AJAX 呼び出しの結果を解析し、テーブルの正しい位置に配置します。 これは主に HTML と JavaScript の操作です。ここでは詳しく説明します。 代わりに、付録 A にコードを示します。

    > [!NOTE]
    >  クロスオリジン リソース共有 (CORS) が有効な場合、ユーザーは要求されたリソースに "No 'Access-Control-Allow-Origin' ヘッダーが存在しないというエラーが発生する可能性があります。 Origin 'null' is therefore not allowed access". この問題を解決するには、ポータルがインストールされているフォルダーの下に HTML ファイルを配置します (既定では `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` 、 その後、URL を使用して任意のブラウザーから HTML にアクセスします  `http://<servername>/cqd/<html_file_name>` 。 (ローカル CQD ダッシュボードの既定の URL は  `http://<servername>/cqd.` ) 

### <a name="appendix-a"></a>付録 A

例 3 の HTML コード (スコアカードのサンプル):

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
