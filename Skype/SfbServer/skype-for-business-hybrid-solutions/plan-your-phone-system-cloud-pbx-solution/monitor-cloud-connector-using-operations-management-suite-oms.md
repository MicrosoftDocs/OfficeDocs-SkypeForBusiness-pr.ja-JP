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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: このトピックでは、Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン2.1 以降の展開を監視する方法について説明します。
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359093"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Operations Management Suite (OMS) を使用した Cloud Connector の監視

> [!Important]
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。

このトピックでは、Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン2.1 以降の展開を監視する方法について説明します。

Microsoft cloud IT management solution である Operations Management Suite (OMS) を使用して、Cloud Connector バージョン2.1 以降の展開を監視できるようになりました。 OMS ログ分析を使用すると、物理および仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析することができます。 OMS とログ分析の詳細については、「 [Operations Management Suite (oms) とは](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)」を参照してください。

このトピックは、以下のセクションで構成されています。

- 前提条件

- OMS を使用するように Cloud Connector を構成する

- OMS を構成する

- ログ分析リポジトリのアラートを分析する

- 推奨される監視セット

## <a name="prerequisites"></a>前提条件

OMS を使用して Cloud Connector の展開を監視するには、次のものが必要になります。

- **Azure アカウントおよび OMS ワークスペース。** まだ Azure アカウントを持っていない場合は、OMS ログ分析を使用するためのアカウントを作成する必要があります。 Azure アカウントを作成し、OMS ワークスペースをセットアップする方法については、「 [Log Analytics workspace の使用を開始](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)する」を参照してください。

- **Cloud Connector バージョン2.1 以降**

- **Log Analytics 新しいログの検索** は、Cloud Connector の監視に必要です。 詳細については、「 [Azure Log Analytics workspace を新しいログ検索にアップグレードする](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)」を参照してください。

## <a name="configure-cloud-connector-to-use-oms"></a>OMS を使用するように Cloud Connector を構成する

OMS を使用するには、Cloud Connector のオンプレミス環境を構成する必要があります。 これを行うには、OMS ワークスペース ID とキーが必要です。これは、次のように、OMS ポータルを使用して確認できます。設定-- \> 接続されているソース-- \> Windows サーバー:

![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS を使用するように Cloud Connector を構成する方法は、シナリオによって異なります。

- **新しい Cloud Connector アプライアンスをインストールする場合、またはアプライアンスを再展開する場合は**、次の手順に従ってインストール-ccappliance を実行してください。

    1. [CloudConnector.ini ファイル [Common]] セクションで、OMSEnabled パラメーターを True に設定します。

        Cloud Connector が展開またはアップグレードされるたびに、OMS エージェントを Vm に自動的にインストールしようとします。 この機能を有効にすると、OMS エージェントは Cloud Connector の自動更新を使用できるようになります。

    2. OMS ID とキーを構成するには、「Set-CcCredential-AccountType OMSWorkspace」を実行します。 

- **既存の Cloud Connector アプライアンスに OMS エージェントをインストールする場合**は、次の手順を実行します。

    1. CloudConnector.ini ファイル [Common] セクションで、OMSEnabled = true に設定します。 

    2. Import-CcConfiguration を実行します。 

    3. CcOMSAgent を実行します。 

        > [!NOTE]
        > OMSWorkspace 資格情報が設定されていない場合は、CcOMSAgent を実行するときに資格情報の入力を求められます。 

- **Oms エージェントが既にインストールされている Cloud Connector アプライアンスで、OMS ワークスペース ID またはキーを更新する場合は、次のようにします。**

    1. OMS ID とキーを構成するには、「Set-CcCredential-AccountType OMSWorkspace」を実行します。 

    2. 更新プログラムを適用するには、CcOMSAgent を実行します。 

- **すべてのシナリオで、エージェントが次のように接続されていることを確認します。**

    OMS ポータルで、[設定- \> 接続されたソース-Windows サーバー] に移動し \> ます。 接続されているコンピューターの一覧が表示されます。 

## <a name="configure-oms"></a>OMS を構成する

次に、OMS ポータルを使用して OMS 構成を指定する必要があります。 具体的には、次のことを行う必要があります。

- イベントログとパフォーマンスカウンターに関する情報を指定します。

- 通知を作成します。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>イベントログとパフォーマンスカウンターに関する情報を指定する

OMS ポータルでは、次のように、イベントログとパフォーマンスカウンターに関する情報を指定する必要があります。

1. [設定- \> データ- \> Windows イベントログ] に移動し、イベントログを次のように追加します。 

   - Lync Server

   - アプリケーション

     > [!NOTE]
     > テキストボックスには、Lync Server を手動で入力する必要があります。 ドロップダウンリストにはオプションとして表示されません。 

     詳細については、「 [Log Analytics の Windows イベントログデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)」を参照してください。

2. [設定- \> データ- \> Windows パフォーマンスカウンター] に移動し、以下のパフォーマンスカウンターを追加します。 

   - **OS レベルのカウンター**。 OS レベルのカウンター (プロセッサの使用状況、メモリ使用率、ネットワークの使用状況など) を追加したり、カウンターを明示的に追加せずに容量やパフォーマンスなどの既存のソリューションを使用したりすることができます。 これらの監視をどのように決定するかにかかわらず、Microsoft では、これらの OS カウンターを監視することをお勧めします。

   - **Skype For business のカウンター**。 Skype for Business で提供されるカウンターは多数あります。 これらのカウンターは、仲介サーバーにログオンしてパフォーマンスモニターを開くことで見つけることができます。 これらのカウンターは、"LS:" から始まります。 Microsoft では、少なくとも次の容量カウンターから始めて、興味のあるユーザーを追加することをお勧めします。

     アクティブな通話の合計数:

       - LS: MediationServer-着信呼び出し (_Total) \- Current 

       - LS: MediationServer-送信呼び出し (_Total) \- Current 

     アクティブなメディアバイパス呼び出しの合計数:

       - LS: MediationServer-着信呼び出し (_Total) \- アクティブメディアバイパス呼び出し 

       - LS: MediationServer-送信呼び出し (_Total) \- アクティブメディアバイパス呼び出し 

     > [!NOTE]
     > テキストボックスには、パフォーマンスカウンターを手動で入力する必要があります。 ドロップダウンリストにはオプションとして表示されません。 

     詳細については、「 [Windows と Linux のパフォーマンスデータソース (ログ分析](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters))」を参照してください。

### <a name="create-alerts"></a>通知を作成する

OMS には、結果アラート数と指標測定通知の2種類の通知があります。 通知の作成の詳細については、「 [Log Analytics で通知ルール](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)を使用する」を参照してください。

通知を作成するときは、次の点を考慮する必要があります。

- 通知は、既定の選択である [結果の数] 通知であることを確認してください。 

- デモクエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。 

- 時間枠と警告頻度の両方を5分に設定することをお勧めします。 

- デモ通知に対して [通知の抑制] を有効にしないことをお勧めします。 

- 一般的な警告シナリオでは、1つのエラー通知と1つのリセット通知のペアを作成することをお勧めします。 エラーアラートの場合は、[重要度レベル] を選択します。[リセット] 通知で、[重大度レベルの情報] を選択します。

次のセクションでは、サンプル通知を作成する方法について説明します。

 **通知のペアを作成する: "RTCMEDSRV は、仲介サーバーで実行されていません" および "RTCMEDSRV は、仲介サーバーで実行中です" というメッセージが返されます。**

このアラートのペアを作成するには

- エラーアラートのクエリは次のとおりです。

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    このクエリは、コンピューターに  *"MediationServer" が含まれて*  いるコンピューターフィルターを使用します。 このフィルターでは、名前に "MediationServer" という文字列が含まれているコンピューターのみが選択されます。

     フィルターを自分のコンピューターフィルターに置き換えるか、削除するだけです。 正規表現を使用せずに複雑な文字列フィルターを作成することができます。 詳細については、「 [文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)」を参照してください。 正規表現を使用するように選択することもできます。 さらに、検索クエリを保存し、そのグループを警告クエリのコンピューターフィルターとして使用することによって、コンピューターグループを作成できます。 詳細については、「 [Log Analytics log 検索のコンピューターグループ](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)」を参照してください。

    エラークエリは、各コンピューターについて、RTCMEDSRV サービス開始とサービス停止の両方の最後のイベントログを取得します。 最後のイベントがサービス停止イベントの場合は、1つのログが返されます。最後のイベントがサービス開始イベントの場合、nothing が返されます。 省略すると、クエリは、時間枠で RTCMEDSRV が停止しているサーバーの一覧を返します。 

- リセット警告のクエリは次のとおりです。

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    リセットクエリは、エラークエリの逆の処理を行います。 各コンピュータでは、最後のイベントがサービス開始イベントの場合は1を返します。最後のイベントがサービス停止イベントの場合は、nothing が返されます。

**通知のペアを作成する: "仲介サーバーでの同時通話が多すぎます" および "同時呼び出しは通常の負荷に戻されます"**

この通知を作成するには:

- エラーアラートのクエリは次のとおりです。

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    各コンピューターに対して、クエリは着信呼び出しと発信呼び出しの最後のカウンターを取得し、これら2つの値を合計します。 合計値が500を超えた場合、1つのログを返します。そうでない場合は nothing を返します。 省略すると、クエリは、時間枠に同時呼び出しが多すぎるサーバーの一覧を返します。

- リセット警告のクエリは次のとおりです。

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    リセットクエリは、エラークエリの逆の処理を行います。 各コンピューターに対して、クエリは着信呼び出しと発信呼び出しの最後のカウンターを取得し、これら2つの値を合計します。 Sum 値が500より小さい場合は、1つのログを返します。それ以外の場合は何も返しません。

**アラートを作成する: "CPU 使用率 \> 90 または RTCMEDIARELAY がサーバーで停止されました" アラート**

この警告を作成するには、次のクエリを実行します。

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

このクエリは、すべてのコンピューターからすべてのプロセッサ使用率カウンターとサービス停止イベントを取得し、プロセッサの使用率が90% を超えた場合またはサービスが停止した場合に、1つのログを返します。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>ログ分析リポジトリのアラートを分析する

リポジトリ内のアラートを分析するには、アラート管理ソリューションを使用します。 詳細については、「 [Operations Management Suite (OMS)」の「Alert management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 」を参照してください。

## <a name="recommended-minimal-monitoring-set"></a>推奨される最小の監視セット

イベントログとパフォーマンスカウンターに関する問題を特定するには、次のようにします。 

- **イベントログ** 問題がある場合は、イベントのペアがあり、何らかのイベントが発生していることを示すイベントセットがあり、もう1つはすべてが適切であることを示します。 指定した任意の期間について、その期間に amiss があるかどうかを示す最後のイベントが記録されます。

- **パフォーマンスカウンター。** 監視対象のカウンターにはしきい値が必要です。

次の表に、停止イベントと開始イベントの Id を一覧表示することによって監視を推奨するサービスを示します。

|サービス名  <br/> |ターゲットサーバーの役割  <br/> |停止イベント ID  <br/> |開始イベント ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |仲介サーバー  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |エッジ サーバー  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |エッジ サーバー  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |エッジ サーバー  <br/> |22003  <br/> |22002  <br/> |

次の表に、Microsoft が監視を推奨するネットワークの問題を示します。


| モニター名  <br/>                                        | ターゲットサーバーの役割  <br/> | 成功イベント ID 式  <br/> | エラーイベント ID 式  <br/> | エラーの例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 仲介サーバーからゲートウェイへの接続エラー  <br/>    | 仲介サーバー  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 仲介サーバーからゲートウェイへの通話完了エラー  <br/> | 仲介サーバー  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重大なネットワークの問題  <br/>                           | エッジ サーバー  <br/>        | 14353                              |                                  | 12288  <br/>           |

以下に、監視する必要がある通話能力カウンターの一覧を示します。 これらの数値は、Cloud Connector standard edition の場合は500未満である必要があります。Cloud Connector の最小版の50未満。

- LS: MediationServer-着信呼び出し (_Total) \- Current 

- LS: MediationServer-送信呼び出し (_Total) \- Current 

- LS: MediationServer-着信呼び出し (_Total) \- アクティブメディアバイパス呼び出し

- LS: MediationServer-送信呼び出し (_Total) \- アクティブメディアバイパス呼び出し

## <a name="see-also"></a>関連項目

OMS の使用の詳細については、以下を参照してください。

- [ログ分析でログ検索を使用してデータを検索する](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics Language リファレンス](https://docs.loganalytics.io/docs/Language-Reference)

- [ログ分析の警告について](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Windows コンピューターを Azure の Log Analytics サービスに接続する](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


