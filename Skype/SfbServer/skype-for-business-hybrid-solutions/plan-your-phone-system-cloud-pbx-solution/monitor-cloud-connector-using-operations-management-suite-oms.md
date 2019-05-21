---
title: Operations Management Suite (OMS) を使用した Cloud Connector の監視
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: このトピックでは、Microsoft Operations Management Suite (OMS) を使用してクラウドコネクタバージョン2.1 およびそれ以降の展開を監視する方法について説明します。
ms.openlocfilehash: 6258ad9386b895f97a6f6dc0a1b40ce1076568aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287266"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Operations Management Suite (OMS) を使用した Cloud Connector の監視

このトピックでは、Microsoft Operations Management Suite (OMS) を使用してクラウドコネクタバージョン2.1 およびそれ以降の展開を監視する方法について説明します。

Operations Management Suite (OMS)、Microsoft cloud IT Management solution を使用して、クラウドコネクタバージョン2.1 およびそれ以降の展開を監視できるようになりました。 OMS ログ分析を使用すると、物理および仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析できます。 OMS とログ分析の詳細については、「 [Operations Management Suite (OMS) とは](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)」を参照してください。

このトピックには次のセクションが含まれます。

- 前提条件

- OMS を使用するようにクラウドコネクタを構成する

- OMS を設定する

- ログ分析リポジトリのアラートを分析する

- 推奨される監視セット

## <a name="prerequisites"></a>前提条件

OMS を使ってクラウドコネクタの展開を監視するには、次のものが必要です。

- **Azure アカウントと OMS ワークスペース。** まだ Azure アカウントを持っていない場合は、OMS ログ分析を使用するようにアカウントを作成する必要があります。 Azure アカウントを作成して OMS ワークスペースを設定する方法については、「[ログ分析ワークスペースの使用を開始](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)する」を参照してください。

- **Cloud Connector バージョン2.1 以降**

- **ログ分析**クラウドコネクタを監視するには、新しいログの検索が必要です。 詳細については、「[新しいログの検索に Azure Log Analytics ワークスペースをアップグレードする](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)」を参照してください。

## <a name="configure-cloud-connector-to-use-oms"></a>OMS を使用するようにクラウドコネクタを構成する

OMS を使用するには、クラウドコネクタのオンプレミス環境を構成する必要があります。 これを行うには、OMS のワークスペース ID とキーが必要です。これは、次のように OMS ポータルを使って\>確認できます。\>設定--接続されているソース--Windows server:

![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS を使用するようにクラウドコネクタを構成する方法は、シナリオによって異なります。

- **新しいクラウドコネクタアプライアンスをインストールする場合、またはアプライアンスを再展開する場合は**、次の手順に従って、Install-ccappliance を実行します。

1. CloudConnector .ini ファイルの [Common] セクションで、OMSEnabled パラメーターを True に設定します。

    クラウドコネクタが展開またはアップグレードされるたびに、OMS エージェントを Vm に自動的にインストールしようとします。 この機能を有効にして、OMS エージェントがクラウドコネクタの自動更新を利用できるようにします。

2. OMS ID とキーを構成するには、Set-CcCredential-AccountType OMSWorkspace を実行します。 

- **既存のクラウドコネクタアプライアンスに OMS エージェントをインストールする場合**は、次の手順を実行します。

1. CloudConnector の [Common] セクションで、OMSEnabled = true を設定します。 

2. インポート-CcConfiguration を実行します。 

3. CcOMSAgent を実行します。 

    > [!NOTE]
    > OMSWorkspace 資格情報がまだ設定されていない場合は、CcOMSAgent を実行するときに資格情報の入力を求めるメッセージが表示されます。 

- **OMS エージェントが既にインストールされているクラウドコネクタのアプライアンスで、OMS ワークスペース ID またはキーを更新する場合は、次の操作を行います。**

1. OMS ID とキーを構成するには、Set-CcCredential-AccountType OMSWorkspace を実行します。 

2. 更新プログラムを適用するには、CcOMSAgent を実行します。 

- **すべてのシナリオで、エージェントが次のように接続されていることを確認します。**

    OMS ポータルで、[設定-\>接続されている\>ソース-Windows サーバー] に移動します。 接続されているコンピューターの一覧が表示されます。 

## <a name="configure-oms"></a>OMS を設定する

次に、OMS ポータルを使って OMS の設定を指定する必要があります。 具体的には、次のことを行う必要があります。

- イベントログとパフォーマンスカウンターに関する情報を指定します。

- 通知を作成する。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>イベントログとパフォーマンスカウンターに関する情報を指定する

OMS ポータルでは、次のようにイベントログとパフォーマンスカウンターに関する情報を指定する必要があります。

1. [設定-\>データ-\>Windows イベントログ] に移動し、次のイベントログを追加します。 

   - Lync Server

   - アプリケーション

     > [!NOTE]
     > テキストボックスに Lync Server を手動で入力する必要があります。 ドロップダウンリストにオプションとして表示されません。 

     詳細については、「[ログ分析の Windows イベントログデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)」を参照してください。

2. [設定-\>データ-\> Windows パフォーマンスカウンター] に移動して、次のパフォーマンスカウンターを追加します。 

   - **OS レベルカウンター**。 OS レベルのカウンター (プロセッサの使用状況、メモリ使用量、ネットワークの使用率など) を追加したり、カウンターを明示的に追加することなく、容量とパフォーマンスなどの既存のソリューションを使うことができます。 どのように監視するかにかかわらず、Microsoft は、これらの OS カウンターを監視することをお勧めします。

   - **Skype For business のカウンター**。 Skype for Business には、多数のカウンターが用意されています。 これらのカウンターは、任意の仲介サーバーにログオンして、パフォーマンスモニターを開くことで見つけることができます。 これらのカウンターは "LS:" で始まります。 Microsoft では、少なくとも次の容量カウンターから開始して、興味のあるユーザーを追加することをお勧めします。

     アクティブな通話の合計:

   - LS: MediationServer-着信通話 (_Total)\- Current 

   - LS: MediationServer-Outbound Calls (_Total)\- Current 

     アクティブなメディアの合計通話のバイパス:

   - LS: MediationServer-着信通話 (_Total)\-アクティブメディアの通話をバイパスする 

   - LS: MediationServer-送信通話 (_Total)\-アクティブメディアでの通話のバイパス 

     > [!NOTE]
     > テキストボックスにパフォーマンスカウンターを手動で入力する必要があります。 ドロップダウンリストにオプションとして表示されません。 

     詳細については、「[ログ分析の Windows と Linux のパフォーマンスデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)」を参照してください。

### <a name="create-alerts"></a>通知を作成する

OMS には2種類の通知があります。結果アラートの数と測定指標のアラートがあります。 通知の作成の詳細については、「[ログ分析で通知ルールを](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)使用する」を参照してください。

通知を作成する場合は、次の点を考慮する必要があります。

- [通知] が、既定の選択である [結果を表示する] 通知であることを確認します。 

- デモクエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。 

- タイムウィンドウと通知頻度の両方を5分に設定することをお勧めします。 

- デモの警告に対して [通知を表示しない] を有効にしないことをお勧めします。 

- 一般的なアラートシナリオの場合は、1つのエラー通知と1つのリセット通知のペアを作成することをお勧めします。 エラーメッセージについては、[重要度] を選択します。アラートのリセットで、[重大度レベルの情報] を選択します。

以下のセクションでは、サンプル通知の作成方法について説明します。

 **"RTCMEDSRV は仲介サーバーで実行されていません" という通知のペアを作成し、"RTCMEDSRV は仲介サーバーで実行中です" というメッセージが返されます。**

この通知のペアを作成するには:

- エラーアラートのクエリは次のとおりです。

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    このクエリは、コンピューターに *"MediationServer" が含まれて*いるコンピューターフィルターを使用します。 フィルターでは、名前に "MediationServer" という文字列が含まれているコンピューターのみが選択されます。

     フィルターを独自のコンピューターフィルターに置き換えるか、削除するだけです。 正規表現なしで複雑な文字列フィルターを作成できます。 詳細については、「[文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)」を参照してください。 正規表現を使用するように選択することもできます。 さらに、コンピューターグループを作成するには、検索クエリを保存し、そのグループを警告クエリのコンピューターフィルターとして使用します。 詳細については、「[ログ分析ログの検索のコンピューターグループ](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)」を参照してください。

    コンピューターごとに、エラークエリにより、RTCMEDSRV service の start と service stop の両方の最後のイベントログが取得されます。 最後のイベントがサービス停止イベントの場合は、1つのログが返されます。最後のイベントがサービス開始イベントの場合は、nothing が返されます。 つまり、このクエリは、時間ウィンドウで RTCMEDSRV が停止しているサーバーの一覧を返します。 

- リセット通知のクエリは次のとおりです。

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    リセットクエリは、エラークエリの反対の部分とまったく同じです。 各コンピューターについて、最後のイベントがサービス開始イベントの場合は1を返します。最後のイベントがサービス停止イベントの場合は、nothing が返されます。

  **通知のペアを作成する: "仲介サーバーでの同時呼び出しが多すぎる" と "同時呼び出しが通常の負荷に戻ります"**

この通知を作成するには:

- エラーアラートのクエリは次のとおりです。

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    各コンピューターについて、クエリによって、着信呼び出しと発信通話の最後のカウンターが取得され、これら2つの値が合計されます。 Sum 値が500を超えると、1つのログが返されます。そうでない場合は何も返されません。 つまり、このクエリは、同時呼び出しの時間ウィンドウの数が多すぎるサーバーのリストを返します。

- リセット通知のクエリは次のとおりです。

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    リセットクエリは、エラークエリの反対の部分とまったく同じです。 各コンピューターについて、クエリによって、着信呼び出しと発信通話の最後のカウンターが取得され、これら2つの値が合計されます。 Sum 値が500よりも小さい場合は、1つのログが返されます。それ以外の場合は何も返されません。

  **"CPU 使用率\> 90 または RTCMEDIARELAY はサーバーで停止しました" アラートを作成します。**

この通知を作成するには、次のクエリを実行します。

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

このクエリは、すべてのコンピューターからすべてのプロセッサ使用量カウンターとサービス停止イベントを取得し、いずれかのプロセッサ使用状況が 90% を超えた場合、またはサービスが停止している場合に1つのログを返します。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>ログ分析リポジトリのアラートを分析する

リポジトリ内の通知を分析するには、アラート管理ソリューションを使用します。 詳細については、「 [Operations Management Suite (OMS) でのアラート管理ソリューション](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)」を参照してください。

## <a name="recommended-minimal-monitoring-set"></a>推奨される最小の監視セット

イベントログとパフォーマンスカウンターの問題を特定するには、次の操作を行います。 

- **イベントログ。** 問題が発生した場合は、イベントのペアと、何かが間違っていることを示すイベントのセットがあります。もう1つは、すべてが適切であることを示します。 指定された期間が経過すると、その期間に対してさんが指定されているかどうかを示す最後のイベントが記録されます。

- **パフォーマンスカウンター。** 監視対象カウンターには、しきい値が必要です。

次の表に、stop イベント Id と start イベント Id の一覧を表示することにより、監視が推奨されるサービスを示します。

|サービス名  <br/> |ターゲットサーバーの役割  <br/> |イベント ID の停止  <br/> |開始イベント ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |仲介サーバー  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |エッジ サーバー  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |エッジ サーバー  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |エッジ サーバー  <br/> |22003  <br/> |22002  <br/> |

次の表は、Microsoft が監視を推奨するネットワークの問題を示しています。


| モニター名  <br/>                                        | ターゲットサーバーの役割  <br/> | 成功イベント ID の式  <br/> | エラーイベント ID 式  <br/> | エラーの例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 仲介サーバーからゲートウェイへの接続エラー  <br/>    | 仲介サーバー  <br/>   | 25062                              |                                  | 25002  <br/>           |
| ゲートウェイ間の呼び出しの完了エラー  <br/> | 仲介サーバー  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重大なネットワークの問題  <br/>                           | エッジ サーバー  <br/>        | 14353                              |                                  | 12288  <br/>           |

以下は、監視する必要がある通話容量カウンターの一覧です。 これらの数値は、クラウドコネクタの標準エディションでは500より少なくなります。クラウドコネクタの最小エディションの場合は、50未満です。

- LS: MediationServer-着信通話 (_Total)\- Current 

- LS: MediationServer-Outbound Calls (_Total)\- Current 

- LS: MediationServer-着信通話 (_Total)\-アクティブメディアの通話をバイパスする

- LS: MediationServer-送信通話 (_Total)\-アクティブメディアでの通話のバイパス

## <a name="see-also"></a>関連項目

OMS の使い方の詳細については、次を参照してください。

- [ログ分析でログの検索を使用してデータを検索する](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics の言語リファレンス](https://docs.loganalytics.io/docs/Language-Reference)

- [ログ分析の警告について](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Windows コンピューターを Azure のログ分析サービスに接続する](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


