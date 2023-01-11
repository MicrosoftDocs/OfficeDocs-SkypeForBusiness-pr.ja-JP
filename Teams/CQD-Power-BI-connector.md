---
title: Power BI コネクタをインストールして CQD クエリ テンプレートを使用する
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Power BI Connector をインストールして通話品質ダッシュボード (CQD) クエリ テンプレートを使用する
ms.openlocfilehash: 534103fc2bec48566a1d0a57eeb390ed6ae0606c
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774752"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Power BI 用の Microsoft Call Quality コネクタをインストールして通話品質ダッシュボード クエリ テンプレートを使用する

Microsoft Teams 通話品質ダッシュボード (CQD) 用の Power BI クエリ テンプレート (PBIX ファイル) を使用するには、[ダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)に含まれている *MicrosoftCallQuality.pqx* ファイルを使用して、Power BI 用の Microsoft Call Quality コネクタをインストールする必要があります。

これらのテンプレートについては、「 [Power BI を使用して Teams の CQD データを分析](CQD-Power-BI-query-templates.md) する」を参照してください。

Power BI レポートにアクセスするための適切な [CQD アクセス ロール](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) があることを確認します。

> [!NOTE]
> Microsoft Call Quality コネクタでは、Power BI での DirectQuery のみがサポートされます。インポート モードはサポートされていません。 

## <a name="installation"></a>インストール

カスタム コネクタをインストールし、コネクタを使用できるようにセキュリティを調整するプロセスについては、 [Power BI ドキュメント](/power-bi/desktop-connector-extensibility)で詳しく説明されています。 わかりやすくするために、簡単な説明を次に示します。

1. コンピューターに *Documents\]\\ Power BI Desktop\\ Custom Connectors フォルダーが既\[* にあるかどうかを確認します。 そうでない場合は、このフォルダーを作成します。<sup>1</sup>

2. コネクタ ファイル ( *\*.mez* または *\*.pqx* ファイル) をダウンロードし、 *カスタム コネクタ* ディレクトリに配置します。

3. **コネクタ ファイルが *.mez ファイルの\** 場合は、**[カスタム コネクタのセットアップ に](/power-bi/desktop-connector-extensibility#data-extension-security)関するドキュメントの説明に従って、セキュリティ設定を調整する必要もあります。

Microsoft Call Quality コネクタの新しいバージョンがリリースされた場合は、 *カスタム コネクタ* ディレクトリ内の古いコネクタ ファイルを新しいファイルに置き換えます。

## <a name="setup"></a>セットアップ

レポートを作成してクエリを実行するには、まず CQD データ ソースに接続する必要があります。 接続するには、次の手順に従います。

1. Power BI Desktopの [ホーム] タブで、[*データの取得*] をクリックします。

    ![Power BI コネクタでデータを取得します。](media/CQD-power-bi-connector1-resize.png)

2. [ *データの取得* ] ウィンドウは、この時点で表示されます。 *[オンライン サービス*] に移動し、[*Microsoft 通話品質 (ベータ版)]* を選択し、[*接続*] をクリックします。

    ![Power BI コネクタの Microsoft 通話品質。](media/CQD-power-bi-connector2-resize.png)

3. 次にサインインするように求められます。 通話品質ダッシュボードに使用する資格情報と同じ資格情報を使用します。<sup>2</sup>

4. 次のプロンプトでは、2 つの *データ接続モード* 間のオプションが表示されます。 [ *DirectQuery]* を選択し、[ *OK] をクリックします*。

5. 最後に、通話品質ダッシュボードのデータ モデル全体を示す最後のプロンプトが表示されます。 この時点ではデータは表示されません。CQD のデータ モデルのみです。 [ *読み込み]* を選択して、セットアップ プロセスを完了します。

6. この時点で、Power BI はウィンドウの右側にデータ モデルを読み込みます。 それ以外の場合、ページは空白のままになり、既定ではクエリは読み込まれません。 クエリを **作成** してデータを返すには、以下の「クエリの作成」に進みます。

このセットアップ プロセス中の手順のいずれかが明確でなかった場合は、「[クイック スタート: Power BI Desktopのデータに接続する」](/power-bi/desktop-quickstart-connect-to-data)でプロセスの詳細な説明を確認できます。

## <a name="building-queries"></a>クエリの作成

セットアップが完了すると、[ *フィールド* ] ウィンドウに数百個のディメンションとメジャーの読み込みの名前が表示されます。 ここから実際のクエリを作成するのは簡単です。クエリに必要なディメンションとメジャーを選択し、ページにドラッグ アンド ドロップするだけです。 簡単な例を使用して、より詳細な説明を次に示します。

1. [視覚化] ウィンドウから、使用する *視覚化を* 選択します。 その視覚化の空のバージョンがページに表示されます。 この例では、 *テーブル* の視覚化を使用します。

    ![Power BI コネクタの [視覚化] ウィンドウ。](media/CQD-power-bi-connector3-resize.png)

2. クエリに使用するディメンションとメジャー (名前で集計記号で示される) を決定し、手動で選択し、黒の視覚化にドラッグします。 または、視覚化オプションの下にある *[値* ] フィールドにドラッグします。

    !Power BI コネクタの視覚化クエリ。](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 通話品質ダッシュボードには、クエリを実行するためのメジャーが必要です。 クエリにメジャーを追加しないと、そのクエリは失敗します。

3. 次に、フィルターを適用するディメンションを選択 *し、[* フィルター] ウィンドウの *[このビジュアル フィールドのフィルター] に* ドラッグします。 現在、Microsoft 通話品質コネクタでは *、基本的なフィルター処理* (使用可能なディメンション値の一覧から値を選択)、 *高度なフィルター* 処理 (通話品質ダッシュボードと同様にフィルター処理する値とオペランドを手動で指定)、 *相対日付フィルター処理* ( *終了時刻* ディメンションと *開始時刻* ディメンションでのみ使用できます) がサポートされています。 *上位 N* に従ったフィルター処理は、通話品質ダッシュボードではサポートされていません。

    ![Power BI コネクタの視覚化フィルター。](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > フィルターは、ディメンションに適用された場合にのみサポートされます。 通話品質ダッシュボードでは、測定の値に対するフィルター処理はサポートされていません。

4. 最後に、[*視覚化*] ウィンドウ内の [*書式*] タブを選択して、クエリのスタイル設定と書式設定を行います。

    > [!NOTE]
    > 通話品質ダッシュボード クエリを実行するには、少なくとも 1 つのメジャーが必要です。 クエリが読み込まれない場合は、クエリにメジャーが含まれていることを再確認します。

## <a name="creating-a-drillthrough-report"></a>ドリルスルー レポートの作成

[Power BI のドリルスルー](/power-bi/desktop-drillthrough) を使用すると、他のレポートの値をコンテキストとして使用してすばやくフィルター処理できるフォーカスのあるレポートを作成できます。 Microsoft Call Quality コネクタを使用して最初のクエリを作成する方法がわかったら、ドリルスルーの作成がさらに簡単になります。

1. フォーカスのあるレポート用の別のページを作成し、そのページにクエリを追加します。

2. ドリルスルー フィルターとして使用するディメンションを選択し、[*視覚化*] ウィンドウの下の *[ドリルスルー*] フィールドにドラッグします。

    ![Power BI コネクタのドリルスルー。](media/CQD-power-bi-connector6-resize.png)

3. **それです\!** そのディメンションを使用する別のページの他のクエリは、ドリルスルー ディメンションの値をフィルターとして自動的に適用して、そのページにドリルスルーできるようになりました。

    ![Power BI コネクタのドリルスルー フィルター。](media/CQD-power-bi-connector7-resize.png)

通話品質ダッシュボードとは異なり、Power BI では非シーケンシャルドリルスルーがサポートされています。 クエリに必要なディメンションが含まれている場合は、他のページにドリルスルーできます。

### <a name="best-practice"></a>ベスト プラクティス

Microsoft Call Quality コネクタ クエリは、ドリルスルー機能を念頭に置いて設計する必要があります。 すべてのデータを一度に読み込み、フィルターでスライスする代わりに、より広範でカーディナリティの低いクエリから開始し、カーディナリティの高いクエリにドリルダウンします。 たとえば、品質の問題に最も影響を与えるサブネットを診断する場合は、最初に問題に貢献するリージョンと国を特定し、そのリージョンまたは国のサブネットにドリルダウンすると便利です。 Call Quality コネクタ テンプレートは、例として機能するために、この方法で設計されています。

## <a name="limitations"></a>制限事項

Power BI を利用しているにもかかわらず、通話品質ダッシュボードのデータ モデルまたは DirectQuery コネクタ全般に関する制限の結果として、すべての Power BI 機能が Microsoft Call Quality コネクタによってサポートされているわけではありません。 次の一覧は、コネクタの特筆すべき制限事項をいくつか示していますが、この一覧は網羅的と見なすべきではありません。

1. **計算列 –** 一般に、DirectQuery コネクタでは、Power BI の計算列のサポートが制限されています。 計算列の中には、コネクタで動作する場合があります。これらの列は例外です。 一般に、計算列は機能しません。

2. **集計–** Call Quality Dashboard データ モデルはキューブ モデルに基づいて構築されています。つまり、集計はメジャーの形式で既にサポートされています。 別のディメンションに集計を手動で追加しようとしたり、メジャーの集計の種類を変更したりしようとすると、コネクタでは機能せず、一般にエラーが発生します。

3. **カスタム ビジュアル –** Microsoft Call Quality コネクタはさまざまなカスタム ビジュアルで動作しますが、すべてのカスタム ビジュアルとの互換性を保証することはできません。 多くのカスタム ビジュアルは、計算列またはインポートされたデータの使用に依存しますが、どちらも DirectQuery コネクタではサポートされていません。

4. **キャッシュされたデータの参照 –** 現在、Power BI では、DirectQuery コネクタからキャッシュされたデータの参照はサポートされていません。 クエリの結果を参照しようとすると、新しいクエリが作成されます。

5. **相対データ フィルター処理 –** Microsoft 通話品質コネクタではサポートされていますが、 *開始時刻* と *終了時刻* のディメンションでのみサポートされます。 *Date* ディメンションは、相対日付フィルターの明確な選択である場合がありますが、*Date* は日付時刻オブジェクトとして格納されないため、Power BI での相対日付フィルター処理はサポートされていません。

6. **測定専用クエリ -** 現時点では、Microsoft 通話品質コネクタではサポートされていません。 3 つ以上の測定値を含む視覚化を作成し、ディメンションを指定しない場合、列データは入れ替えされます。 これを回避するには、常に少なくとも 1 つのディメンション (例: 月年) を視覚化に含めます。 これは、Power BI 用の Microsoft Call Quality コネクタの今後のリリースで解決される予定です。

7. **Government Community Cloud (GCC) のサポート –** GCC 環境のお客様の場合、Microsoft Call Quality コネクタは、Power BI Desktopのみを使用する場合に機能します。 Microsoft Call Quality コネクタは現在、GCC のお客様向けのPower BI サービスと互換性がありません。

これらの問題のほとんどは、Power BI での DirectQuery コネクタの設計に対する制限か、CQD データ モデルの設計の基礎です。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Date 列を Date スライサーとして使用しようとしています。 この列のデータ型を Date に変換するとすぐに、このエラーが発生します

> **このビジュアルのデータを読み込めませんでした**。 OLE DB または ODBC エラー: [Expression.Error] 式をデータ ソースにフォールドできませんでした。 より単純な式を試してください。

日付スライサーは、Microsoft 通話品質コネクタではサポートされていません。 日付範囲を指定するには、レポートに 2 つのフィルターを適用し、日付より小さいと大きいを指定します。

または、表示する日付が最新の場合は、相対日付フィルターを適用して、過去 N 日/週/月のデータのみを表示します。


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>レポートに特定のディメンションを追加すると、ビジュアルはすぐに **"このビジュアルのデータを読み込めませんでした" を** 返します。 ディメンションを削除すると、ビジュアルが修正されます。何が起こっていますか?

これは、Microsoft 通話品質コネクタの既知の問題です。整数として公開されているディメンションは、Power BI に "集計" 列として表示されます。ここで、Power BI は既定の集計アクション (通常は "合計") を試みます。 場合によっては、Second WiFi Channel のようなディメンションの "合計" は意味がないため、結果が役に立たない場合でも、この動作は値の合計に成功します。 それ以外の場合、この要約アクションは失敗し、ビジュアルにエラーが発生します。

この問題を回避するには、まずビジュアルからディメンションを削除します。 [フィールド] リストからディメンションを選択し、リボンの [列ツール] タブを参照し、[概要] ドロップダウン メニューをクリックして、[ **集計しない**] を選択します。 ディメンションをビジュアルに再度追加できるようになりました。


## <a name="error-codes"></a>エラー コード

Power BI 用の Microsoft Call Quality コネクタは、構築できるクエリの種類に関してブラウザー アプリよりも制限が少ないため、クエリの作成中に多くのエラーが発生することがあります。 "CQDError" 型のエラー メッセージが表示された場合。 RunQuery – Query Execution Error", reference the list with the ErrorType number provided to troubleshoot the possible issue with the query. CQD Power BI コネクタで発生する可能性がある最も一般的なエラーの種類コードを次に示します。

- **ErrorType 1 - クエリ構造エラー:** クエリ構造エラーは、通常、コネクタが適切な形式のクエリを作成できなかったために発生します。 これは、上記の制限事項で指定されているように、サポートされていない機能を使用する場合に最も頻繁に発生します。 そのクエリに計算列またはカスタム ビジュアルが使用されていないことを再確認します。

  - **ErrorType 2 - クエリの作成エラー:** クエリの作成エラーは、Microsoft Call Quality コネクタがビルドしようとしているクエリを適切に解析できなかったことが原因で発生します。 これは、上記の制限事項で指定されているように、サポートされていない機能を使用する場合に最も頻繁に発生します。 そのクエリに計算列またはカスタム ビジュアルが使用されていないことを再確認します。

  - **ErrorType 5 - 実行タイムアウト:** クエリがタイムアウトする前に、可能な限り最大のランタイムに達しました。スコープを制限するために、クエリにフィルターを追加してみてください。 多くの場合、データ範囲を狭くすることが、これを実現するための最も効果的な方法です。

  - **ErrorType 7 - 測定エラーなし:** 品質ダッシュボードクエリを呼び出すには、機能するためにメジャーが必要です。 クエリにメジャーが含まれていることを再確認します。 Microsoft Call Quality コネクタのメジャーは、名前の前に集計 (合計) 記号で示されます。

この範囲外で追加のエラーが発生した場合は、問題のトラブルシューティングを行い、必要に応じてドキュメントを更新できるように、通話品質ダッシュボード チームに通知してください。

## <a name="footnotes"></a>脚注

**<sup>1</sup>** 特定のプロセスとアプリ (OneDrive など) により、Documents ルート フォルダーが変更される可能性があります。*Power BI Desktop\\ Custom Connectors* ディレクトリが現在のルート フォルダー Documents フォルダー内に配置されていることを確認します。

**<sup>2</sup>** 通話品質ダッシュボードに使用するログイン資格情報は、Power BI Desktop アプリ自体へのログインに使用する資格情報と同じである必要 *はありません*。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Power BI コネクタはいつ "ベータ" 状態から更新されますか?

ベータ タグにもかかわらず、Power BI 用の Microsoft Call Quality (Beta) コネクタは、コネクタの最初のリリース バージョンであり、これを反映するために Power BI チームによって正式にセキュリティ署名されています。 コネクタの最初のリリース時、Power BI チームはサポートと広範な認定を提供できませんでしたが、Microsoft Call Quality コネクタのセキュリティ、信頼性、および一般的な機能を証明する準備が整いました。 今後、近い将来、Power BI 用の Microsoft Call Quality コネクタに投資する予定です。

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>ブラウザーの通話品質ダッシュボードに比べてコネクタの速度が遅いように見えるのはなぜですか? パフォーマンスを向上させるにはどうすればよいですか?

さまざまなテンプレートのクエリ パフォーマンスは、実際にはブラウザーとコネクタの両方で同じです。  他のスタンドアロン アプリと同様に、Power BI は認証とレンダリング時間をパフォーマンスに追加します。 さらに、この違いは、同時に実行されるクエリの数にあります。 ブラウザー内バージョンの通話品質ダッシュボードには、あまり開発されておらず、情報密度の高い視覚化オプションがなかったため、ほとんどのレポートは一度に 2 ~ 3 個のクエリを読み込むことに制限されていました。 一方、コネクタ テンプレートには、多くの場合、20 以上の同時クエリが表示されます。 以前のレポートと同じくらい応答性の高いレポートを作成する場合は、タブごとに 2 ~ 3 個以下のクエリを含むレポートを作成してみてください。

詳細については、次の記事を参照してください。

- [Power BI の最適化ガイド](/power-bi/guidance/power-bi-optimization)
- [DirectQuery モデルのガイダンス](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>クエリの実行時に、定期的に 10,000 行の制限に達していることがわかります。 コネクタから 10,000 行を超える行を返すようにするにはどうすればよいですか?

10,000 行の制限は API エンドで実際に指定されており、パフォーマンスを大幅に向上させ、メモリ不足の状態に起因するクエリ実行エラーのリスクを軽減するために設計されています。

結果の行数を増やそうとするのではなく、コネクタのベスト プラクティスに従ってレポートを再構築することをお勧めします。 含まれているテンプレートは、これらのベスト プラクティスを示すために設計されています。 可能であれば、月、年、日付、地域、国など、より広範で低いカーディナリティディメンションを使用して KPI を確認することから始めます。そこから、ますます高いカーディナリティディメンションにドリルダウンできます。 ヘルプデスクレポートとLocation-Enhancedレポートはどちらも、このドリルダウン ワークフローの良い例です。



## <a name="related-topics"></a>関連項目

[Power BI を使用して Teams の CQD データを分析する](CQD-Power-BI-query-templates.md)
