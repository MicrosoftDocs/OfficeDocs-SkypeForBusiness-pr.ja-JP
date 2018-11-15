---
title: CQD の開発サンプル
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '概要: は、品質のダッシュ ボードを呼び出すためのチュートリアルと開発のサンプルを確認します。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。'
ms.openlocfilehash: 994a26af99ec141b531ed3011a42f626c0c62886
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531068"
---
# <a name="cqd-development-samples"></a>CQD の開発サンプル

**の概要:** 品質のダッシュ ボードを呼び出すためのチュートリアルと開発のサンプルを確認してください。 通話品質のダッシュ ボードは、Skype ビジネス サーバー用のツールです。

この記事では、通話品質ダッシュボード (CQD) の開発に関するチュートリアルとサンプルを示します。

## <a name="call-quality-dashboard-cqd-development-samples"></a>通話品質ダッシュボード (CQD) の開発サンプル

チュートリアル: CQD Data Service および Repository Service API を使用してカスタマイズされたレポート プレゼンテーションの作成

### <a name="introduction-to-cqd"></a>CQD の概要

CQD により、オンプレミス Skype for Business Server 展開に関して集計された通話品質情報にすばやく簡単にアクセスできます。 CQD は、QoE アーカイブ データベース、キューブ、およびポータルの 3 つのコンポーネントから構成されています。 ポータルはメインのプレゼンテーション層で、さらに次の 3 つのコンポーネントに分割することができます。

1. データ サービスは、アクセスできないためには、 [API の呼び出し品質ダッシュ ボード (救難) ビジネス サーバーの Skype でのデータ](data-api.md)を使用してユーザーが認証されます。

2. リポジトリ サービスには、[リポジトリ API の呼び出し品質ダッシュ ボード (救難) Skype ビジネス サーバーで](repository-api.md)認証されたユーザーにアクセスします。

3. CQD のユーザーが表示および操作する、HTML5 ベースのインターフェイスである Web ポータル。 これは、認証済みユーザーがアクセスできます。

Web ポータルに表示されるレポートは、レポートの「セット」にグループ化されます。 図には、2 つのレポートが含まれるレポート セットが表示されています。 以下のダッシュボードの各レポートには、さまざまなフィルターが適用された、数か月の良好な通話数、低品質な通話数、および低品質な通話のパーセンテージに関するクエリ結果が表示されています。 

![CQD のサンプル レポート](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD は、CQM (通話の品質保証の方法論) に従って作成されるため、レポートの既定のセットは、CQM により導入される調査フローに合わせて作成されます。またユーザーは、ニーズに合うようカスタム レポートを柔軟に編集または作成できます。ただし、データの視覚化には複数の方法があるため、CQD により提供される視覚化では、すべてのユーザーのニーズが完全には満たされない場合があります。このような場合、ユーザーは Data API と Repository API を利用してカスタム レポートのページを作成できます。このチュートリアルでは、一連の例を紹介します。

### <a name="how-the-dashboard-consumes-the-data-service"></a>ダッシュボードでデータ サービスを利用する方法

救難のホームページに移動する場合 (例: http://localhost/cqd)、レポートの設定、およびリポジトリ ・ サービスからの認証および承認されたユーザーに対応するレポートが取得されます。 レポート セットの ID には、年、月の完全な URL が作成される (レポート セットの ID 番号の整数 ' #/' url] セクションの後で、既定で現在の年・月が追加されますレポート セットの ID の末尾にスラッシュの後)。 レポートの定義は JSON 形式で格納され、Repository Service から取得されると、Data Service への入力として使用されます。 Data Service は入力に基づいて多次元式 (MDX) クエリを生成し、これらの MDX クエリをキューブに対して実行して、各レポートのデータを取得します。 

### <a name="building-customized-reports"></a>カスタマイズされたレポートの作成

CQD では既に非常に柔軟なレポートのカスタマイズが可能ですが、CQD で作成された複数のレポートにわたるデータを集計したい場合もあります。たとえば、有線通話のすべての可能な組み合わせに対して、低品質な通話のパーセンテージを表に示すレポートを作成したい場合などです (図のような結果です)。

![CQD のテーブル](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

CQD により提供されるポータルを使用すると、ユーザーは複数のレポートを参照して各レポートの低品質な通話のパーセンテージを抽出および記録する必要があります。これは、収集する必要があるデータ ポイントが多い場合には手間のかかる作業です。Data API は、Data Service からデータを取得することによって同じことをプログラムにより実現する手段 (AJAX 呼び出し経由など) を提供するものです。 

 **例 1: シンプルなレポートのサンプル**

まずは、シンプルな例について説明します。以下の図のように、HTML ページに 2015 年 2 月の Audio Good Streams と Audio Bad Stream の数を示す場合:

![CQD のレポート例](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

必要な操作は、適切なパラメーターを使用して Data Service への呼び出しを送信し、HTML テーブルにクエリの結果を示すことです。以下に、JavaScript コードのサンプルを示します。

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

この例は、さらに次の 3 つのステップに分けることができます。

1. (これは、変数 'クエリ' の定義の例) でクエリを構築します。 クエリは JSON オブジェクトとして定義され、次のデータを含みます。

   a. ゼロまたは 1 つ以上の次元。 各次元は DataModelName により示されます。

   b. ゼロまたは 1 つ以上のフィルター。 各フィルターには以下が割り当てられます。

   - DataModelName (フィルター セットが含まれる次元)。

   - Value (オペランドにより比較される値)。

   - オペランド (比較の種類、0 の場合は「等しい」など)。

     c. 1 つ以上の測定値。

2. AJAX 呼び出しを介して Data Service にクエリを送信します。 次の要求パラメーターが必要です。

   a. url (http://[サーバー名]/QoEDataService/RunQuery を指定する必要があります)。

   b. (これは、'クエリ' 変数で定義されている JSON オブジェクトの文字列形式) のデータです。 Data Service は、成功時のコールバック関数のパラメーターとしてクエリの結果を返します。

   c. (QoEDataService の RunQuery のみを受け入れる ' POST' 要求) を入力します。

   d. async (AJAX 呼び出しを同期と非同期のどちらにするかを示すフラグです)。

   e。 contentType を (「アプリケーションと json」をする必要があります)。

   f。 success (AJAX 呼び出しが正常に完了した場合のコールバック関数)。

   g です。 error (AJAX 呼び出しが失敗した場合のエラー処理関数)。

3. HTML の div 要素にデータを配置します (コード例では、AJAX 要求が正常に完了した後、匿名の関数呼び出しによりこの処理が行われます)。

この JavaScript コードを HTML ページに埋め込むと、ページでは図に示すようなレポートが表示されます。全 HTML は次のとおりです。

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

ここまでのレポートは非常にシンプルです。ユーザーは、レポートをカスタマイズするために測定値、次元、またはフィルターを追加できます。たとえば、AppSharing の低品質な通話のパーセンテージを表示したい場合は、AppSharing に関する新しい測定値を追加する必要があります。すべての TCP 呼び出しと UDP 呼び出しを対比して表示したい場合は、転送の種類に関する新しい次元を追加する必要があります。特定の建物内の低品質な通話数を表示したい場合は、その建物で入出力される通話を選択するために新しいフィルターを追加する必要があります。

 **例 2: レポート定義のサンプル**

ユーザーによっては、クエリを作成する際の測定値/次元/フィルターと対応する値の全一覧を記述することが難しい場合があります。この場合は、ポータルに移動し、レポート エディターを使用してレポートを作成します。そして、レポート定義の JSON 文字列を表示して、定義をカスタム レポートにコピーします。 

この例では、図に示すような Web ページを作成します。この Web ページでは、ユーザーは既存のレポート セット (またはレポート) の ID を入力し、レポート セットまたはレポートの定義を表示することができます。そして、ユーザーは各レポートの JSON 文字列を、例 1 で示したようなコードに挿入し、ユーザーが求めるカスタマイズしたレポートを作成することができます。 

![CQD の例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

レポート定義の表示ツールを作成するには、Repository Service に呼び出しを送信して、必要な各 report-set の定義の JSON 文字列表現を取得する必要があります。Repository API は、指定のレポート セット ID に基づいて report-set の定義を返します。 

簡単な例は、次のように、コードには、その識別子に基づいたリポジトリ アイテムの内容を取得するのにはリポジトリ サービスにクエリを送信する簡単な例は、ブロックが含まれています。 コード (processReportSetData メソッド) の次の部分がそのレポートのセット内の各レポートの定義を取得する AJAX 呼び出しを送信します。 救難 web ポータルの ID がレポート セットの ID であるため、AJAX 呼び出しは、レポート アイテムの設定を返します。 詳細については、リポジトリ API であり、特に GetItems、[項目の取得](get-items.md)にあります。 

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

上記、web ページ (最初に訪問時にレポートの定義) に図のようになります。 救難ポータルからレポートのセット ID を取得する (' #/' 救難ポータルにサインイン後の URL (例。 レポートの最初の図形 ID は 3024)、このレポートのセット ID をこの web ページの [入力] セクションに配置するとします。 Load ボタンを押すし、レポートのセットの完全定義 (測定、分析コード、フィルターのリスト) を参照してください。

要約すると、レポートまたはレポートのセットの完全な定義を簡単に取得するためにします。 手順は次のとおりです。

1. ポータルに移動し、([編集] を選択し、上レポートを編集、追加、フィルター/測定/分析コードを削除するボタンをクリックし、レポートを保存] をクリックします)、レポートをカスタマイズするのにはクエリ ・ エディターを使用します。

2. (' #/' の後の整数は、URL で署名) の URL からレポートのセット ID を取得します。

3. 例 2 で作成したレポート定義の Web ページを開き、レポート セット ID を入力して、(Data API 呼び出しで使用するために) レポート セットの全定義を取得します。

   **例 3: スコアカードのサンプル**

次は、より複雑なタスクです。図のような Web ページを作成したい場合はどうすればよいでしょうか? より大量のデータを処理できるように (レポートの全定義を取得するために例 2 で生成した Web ページを活用して)、例 1 を更新する必要があります。

この場合、測定値と次元の一覧を更新する必要があります。測定値/次元を追加/編集する方法としては、例 2 の指示に従い、測定値と次元の全一覧を含む、レポートの全定義を取得します。そのレポートの全定義をサンプル コードに挿入します。 

例 1 に示されているサンプルから、図でスコアカード ページを取得する詳細な手順は以下のとおりです。

1. 'クエリ' 変数の測定値を更新`[Measures].[Audio Good Streams JPDR Count]`と`[Measures].[Audio Poor Streams JPDR Count]`を`[Measures].[AudioPoorJPDRPercentage]`。 

2. フィルターを更新します。 例 1 のフィルターの JSON データの分析コードに対して設定されている 1 つのフィルターには`[StartDate].[Month]`です。 フィルターは JSON 配列であるため、フィルターの一覧に次元を追加できます。 たとえば、"currentMonth"のワイヤード (有線) の呼び出しの内部サーバーのクライアントを取得する必要な次のフィルター。

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

   分析コードをここで`[Scenarios].[ScenarioPair]`と等しくなるように設定されて`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`。 `[Scenario.][ScenarioPair]`は、特別なディメンションがレポートの作成を簡略化するために作成します。 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` に対応する 6 つの値があるため、シナリオを定義するために 6 つのフィルターの組み合わせを使用するのではなく、1 つのフィルターを使用するだけで済みます。 この例では、値  は、1 つ目がサーバー、2 つ目がサーバーではない、1 つ目が内部、2 つ目が内部、1 つ目の接続の種類が有線、2 つ目の接続の種類が有線であるシナリオに変換されます。 例では、値`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`シナリオに変換する: 最初サーバーは、2 つ目はサーバーではないの内部は、最初の内部は、2 つ目は最初の接続の種類は、ワイヤード (有線)、および 2 番目の接続の種類は、ワイヤード (有線)、正確な定義である」サーバー-クライアント-内側ワイヤード (有線)」です。

3. シナリオごとに 1 つのフィルター セットを作成します。図のスコアカードの各行は個別のシナリオを表し、また個別のフィルターになります (一方、次元と測定値は同じままです)。 

4. AJAX 呼び出しの結果を解析し、解析結果をテーブルの適切な位置に配置します。これは大部分が HTML と JavaScript の操作であるため、ここでは詳細を説明しません。その代わりに、付録 A にコードを示します。

    > [!NOTE]
    >  クロス元リソース共有 (CORS) を有効にすると、ユーザーがエラーが発生のように 'アクセス制御の許可-発信元' ヘッダーがありません"要求されたリソース上に存在します。 'Null' の原点は、そのためアクセスを許可しない"です。 この問題を解決するには、ポータルがインストールされているフォルダー (既定では `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`) に HTML ファイルを配置します。 URL を使用して任意のブラウザーを使って、html、アクセス`http://<servername>/cqd/<html_file_name>`。 (ローカルの救難のダッシュ ボードの既定の URL は、 `http://<servername>/cqd.`) 

### <a name="appendix-a"></a>付録 A

例 3 の HTML コード (スコアカードのサンプル):

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