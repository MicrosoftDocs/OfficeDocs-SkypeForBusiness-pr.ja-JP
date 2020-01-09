---
title: CQD の開発サンプル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '概要: 通話品質ダッシュボードのチュートリアルと開発サンプルを確認します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: 5e650047fefb865f7fe9af84f93a5f57e7bbf086
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992864"
---
# <a name="cqd-development-samples"></a>CQD の開発サンプル

**概要:** 通話品質ダッシュボードのチュートリアルと開発サンプルを確認します。 通話品質ダッシュボードは、Skype for Business Server のツールです。

この記事では、通話品質ダッシュボード (CQD) の開発に関するチュートリアルとサンプルを示します。

## <a name="call-quality-dashboard-cqd-development-samples"></a>通話品質ダッシュボード (CQD) の開発サンプル

チュートリアル: CQD Data Service および Repository Service API を使用してカスタマイズされたレポート プレゼンテーションの作成

### <a name="introduction-to-cqd"></a>CQD の概要

CQD により、オンプレミス Skype for Business Server 展開に関して集計された通話品質情報にすばやく簡単にアクセスできます。 CQD は、QoE アーカイブ データベース、キューブ、およびポータルの 3 つのコンポーネントから構成されています。 ポータルはメインのプレゼンテーション層で、さらに次の 3 つのコンポーネントに分割することができます。

1. データサービス。 [Skype For Business Server の通話品質ダッシュボード (CQD) のデータ API を](data-api.md)通じて、認証されたユーザーがアクセスできます。

2. リポジトリサービス。 [Skype For Business Server の通話品質ダッシュボード (CQD) のリポジトリ API を](repository-api.md)通じて、認証されたユーザーがアクセスできます。

3. CQD のユーザーが表示および操作する、HTML5 ベースのインターフェイスである Web ポータル。 これは、認証済みユーザーがアクセスできます。

Web ポータルに表示されるレポートは、"レポートセット" にグループ化されています。 図には、2 つのレポートが含まれるレポート セットが表示されています。 以下のダッシュボードの各レポートには、さまざまなフィルターが適用された、数か月の良好な通話数、低品質な通話数、および低品質な通話のパーセンテージに関するクエリ結果が表示されています。 

![CQD のサンプル レポート](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD は、CQM (通話の品質保証の方法論) に従って作成されるため、レポートの既定のセットは、CQM により導入される調査フローに合わせて作成されます。またユーザーは、ニーズに合うようカスタム レポートを柔軟に編集または作成できます。ただし、データの視覚化には複数の方法があるため、CQD により提供される視覚化では、すべてのユーザーのニーズが完全には満たされない場合があります。このような場合、ユーザーは Data API と Repository API を利用してカスタム レポートのページを作成できます。このチュートリアルでは、一連の例を紹介します。

### <a name="how-the-dashboard-consumes-the-data-service"></a>ダッシュボードでデータ サービスを利用する方法

CQD のホームページに移動する場合 ( http://localhost/cqd)たとえば、認証されたユーザーと承認されているユーザーのレポートセットおよび対応するレポートは、リポジトリサービスから取得されます)。 完全な URL は、レポートセット ID と年の月から構成されます (レポート-セット id は URL の '/#/' セクションの後の整数値であり、既定では、現在の年の月はレポートセット ID の末尾にスラッシュの後に追加されます)。 レポートの定義は JSON 形式で格納され、Repository Service から取得されると、Data Service への入力として使用されます。 Data Service は入力に基づいて多次元式 (MDX) クエリを生成し、これらの MDX クエリをキューブに対して実行して、各レポートのデータを取得します。 

### <a name="building-customized-reports"></a>カスタマイズされたレポートの作成

CQD では既に非常に柔軟なレポートのカスタマイズが可能ですが、CQD で作成された複数のレポートにわたるデータを集計したい場合もあります。たとえば、有線通話のすべての可能な組み合わせに対して、低品質な通話のパーセンテージを表に示すレポートを作成したい場合などです (図のような結果です)。

![CQD のテーブル](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

CQD により提供されるポータルを使用すると、ユーザーは複数のレポートを参照して各レポートの低品質な通話のパーセンテージを抽出および記録する必要があります。これは、収集する必要があるデータ ポイントが多い場合には手間のかかる作業です。Data API は、Data Service からデータを取得することによって同じことをプログラムにより実現する手段 (AJAX 呼び出し経由など) を提供するものです。 

 **例 1: シンプルなレポートのサンプル**

まずは、シンプルな例について説明します。以下の図のように、HTML ページに 2015 年 2 月の Audio Good Streams と Audio Bad Stream の数を示す場合:

![CQD のレポート例](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

必要な操作は、適切なパラメーターを使用して Data Service への呼び出しを送信し、HTML テーブルにクエリの結果を示すことです。以下に、JavaScript コードのサンプルを示します。

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

この例は、さらに次の 3 つのステップに分けることができます。

1. クエリを作成します (この例では、変数 ' query ' で定義されています)。 クエリは JSON オブジェクトとして定義され、次のデータを含みます。

   a. ゼロまたは 1 つ以上の次元。 各次元は DataModelName により示されます。

   b. ゼロまたは 1 つ以上のフィルター。 各フィルターには以下が割り当てられます。

   - DataModelName (フィルター セットが含まれる次元)。

   - Value (オペランドにより比較される値)。

   - オペランド (比較の型、0は "等しい" を意味します)。

     c. 1 つ以上の測定値。

2. AJAX 呼び出しを介して Data Service にクエリを送信します。 次の要求パラメーターが必要です。

   a. url (http://[サーバー名]/QoEDataService/RunQuery を指定する必要があります)。

   b. データ (この値は、' query ' 変数で定義された JSON オブジェクトの文字列表現) です。 Data Service は、成功時のコールバック関数のパラメーターとしてクエリの結果を返します。

   c. type (QoEDataService の場合、RunQuery は "POST" 要求のみを許可します)。

   d. async (AJAX 呼び出しを同期と非同期のどちらにするかを示すフラグです)。

   •. contentType ("application/json" である必要があります)。

   f. success (AJAX 呼び出しが正常に完了した場合のコールバック関数)。

   agdlp. error (AJAX 呼び出しが失敗した場合のエラー処理関数)。

3. HTML の div 要素にデータを配置します (コード例では、AJAX 要求が正常に完了した後、匿名の関数呼び出しによりこの処理が行われます)。

この JavaScript コードを HTML ページに埋め込むと、ページでは図に示すようなレポートが表示されます。全 HTML は次のとおりです。

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

ここまでのレポートは非常にシンプルです。ユーザーは、レポートをカスタマイズするために測定値、次元、またはフィルターを追加できます。たとえば、AppSharing の低品質な通話のパーセンテージを表示したい場合は、AppSharing に関する新しい測定値を追加する必要があります。すべての TCP 呼び出しと UDP 呼び出しを対比して表示したい場合は、転送の種類に関する新しい次元を追加する必要があります。特定の建物内の低品質な通話数を表示したい場合は、その建物で入出力される通話を選択するために新しいフィルターを追加する必要があります。

 **例 2: レポート定義のサンプル**

ユーザーによっては、クエリを作成する際の測定値/次元/フィルターと対応する値の全一覧を記述することが難しい場合があります。この場合は、ポータルに移動し、レポート エディターを使用してレポートを作成します。そして、レポート定義の JSON 文字列を表示して、定義をカスタム レポートにコピーします。 

この例では、図に示すような Web ページを作成します。この Web ページでは、ユーザーは既存のレポート セット (またはレポート) の ID を入力し、レポート セットまたはレポートの定義を表示することができます。そして、ユーザーは各レポートの JSON 文字列を、例 1 で示したようなコードに挿入し、ユーザーが求めるカスタマイズしたレポートを作成することができます。 

![CQD の例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

レポート定義の表示ツールを作成するには、Repository Service に呼び出しを送信して、必要な各 report-set の定義の JSON 文字列表現を取得する必要があります。Repository API は、指定のレポート セット ID に基づいて report-set の定義を返します。 

簡単な例として、コードには、リポジトリサービスにクエリを送信して、その識別子に基づいてリポジトリアイテムのコンテンツを取得するための単純な例として、次のようなブロックがあります。 コードの次の部分 (processReportSetData メソッド) は、AJAX 呼び出しを送信して、そのレポートセット内の各レポートの定義を取得します。 CQD web ポータルの ID はレポートセットの ID であるため、AJAX 呼び出しはレポートセット項目を返します。 リポジトリ API と特に GetItems の詳細については、「 [Get アイテム](get-items.md)」を参照してください。 

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

上の例では、図のような web ページが表示されます (最初にアクセスしたときに、レポートの定義はありません)。 CQD ポータルからレポートセット ID を取得します ('/#/' サインイン後の CQD ポータル URL (例: 最初の図では、レポートセット ID は 3024) で、このレポートセット ID はこの web ページの入力セクションに入れます。 [読み込み] ボタンを押すと、レポートセットの完全な定義 (寸法、サイズ、フィルターリスト) が表示されます。

レポート/レポートセットの完全な定義をすばやく取得するために、[概要] を選びます。 手順は次のとおりです。

1. ポータルに移動し、クエリエディターを使用してレポートをカスタマイズします (レポートの上にある [編集] ボタンをクリックして、測定/ディメンション/フィルターを編集、追加、削除し、レポートを保存します)。

2. URL からレポートセット ID を取得します ('/#/' サインイン URL の後の整数)。

3. 例 2 で作成したレポート定義の Web ページを開き、レポート セット ID を入力して、(Data API 呼び出しで使用するために) レポート セットの全定義を取得します。

   **例 3: スコアカードのサンプル**

次は、より複雑なタスクです。図のような Web ページを作成したい場合はどうすればよいでしょうか? より大量のデータを処理できるように (レポートの全定義を取得するために例 2 で生成した Web ページを活用して)、例 1 を更新する必要があります。

この場合、測定値と次元の一覧を更新する必要があります。測定値/次元を追加/編集する方法としては、例 2 の指示に従い、測定値と次元の全一覧を含む、レポートの全定義を取得します。そのレポートの全定義をサンプル コードに挿入します。 

例 1 に示されているサンプルから、図でスコアカード ページを取得する詳細な手順は以下のとおりです。

1. "Query" 変数の測定値を`[Measures].[Audio Good Streams JPDR Count]` [および`[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`] に更新します。 

2. フィルターを更新します。 例1のフィルターの JSON データには、ディメンション`[StartDate].[Month]`に対して設定される1つのフィルターがあります。 フィルターは JSON 配列であるため、フィルターの一覧に次元を追加できます。 たとえば、"currentMonth" に対してサーバークライアントの内部通信を取得するには、次のフィルターを使用する必要があります。

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

   ディメンション`[Scenarios].[ScenarioPair]`は、次のように`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`等しい値に設定されます。 レポート`[Scenario.][ScenarioPair]`の作成を簡単にするために作成された特殊なディメンションです。 これには、に`[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`対応する6つの値があります。 この例では、値 [1]&[0]&[1]&[1]&[Wired]&[Wired] は、1 つ目がサーバー、2 つ目がサーバーではない、1 つ目が内部、2 つ目が内部、1 つ目の接続の種類が有線、2 つ目の接続の種類が有線であるシナリオに変換されます。 この例では、値`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`は、first is server、second is server、第1の接続の種類はワイヤード、第2の接続の種類はワイヤード、第2の接続の種類はワイヤードであるというシナリオに変換されます。これは、"クライアント内部のワイヤード" という完全な定義です。

3. シナリオごとに 1 つのフィルター セットを作成します。図のスコアカードの各行は個別のシナリオを表し、また個別のフィルターになります (一方、次元と測定値は同じままです)。 

4. AJAX 呼び出しの結果を解析し、解析結果をテーブルの適切な位置に配置します。これは大部分が HTML と JavaScript の操作であるため、ここでは詳細を説明しません。その代わりに、付録 A にコードを示します。

    > [!NOTE]
    >  クロスオリジンリソース共有 (CORS) が有効になっていると、要求されたリソースに、ユーザーが "No" アクセス制御-許可元のヘッダーなどのエラーが発生する場合があります。 元の ' null ' はアクセスが許可されていません。 この問題を解決するには、ポータルがインストールされているフォルダーの下に HTML ファイルを配置し`%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`ます (既定では、必要です)。 次に、URL `http://<servername>/cqd/<html_file_name>`を使用して任意のブラウザーから html にアクセスします。 (Local CQD dashboard の既定の URL は`http://<servername>/cqd.`です) 

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
