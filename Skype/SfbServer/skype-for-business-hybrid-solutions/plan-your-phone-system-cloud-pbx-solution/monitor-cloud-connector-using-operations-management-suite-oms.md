---
title: Operations Management Suite (OMS) を使用したクラウド コネクタの監視
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
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン 2.1 以降のデプロイを監視する方法については、このトピックを参照してください。
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676509"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Operations Management Suite (OMS) を使用したクラウド コネクタの監視

> [!Important]
> Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。 組織がTeamsにアップグレードしたら、[ダイレクト ルーティング](/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミステレフォニー ネットワークをTeamsに接続する方法について説明します。

Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン 2.1 以降のデプロイを監視する方法については、このトピックを参照してください。

Microsoft クラウド IT 管理ソリューションである Operations Management Suite (OMS) を使用して、Cloud Connector バージョン 2.1 以降のデプロイを監視できるようになりました。 OMS Log Analytics を使用すると、物理マシンや仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析できます。 OMS と Log Analytics の詳細については、「[Operations Management Suite (OMS) とは」](/azure/operations-management-suite/operations-management-suite-overview)を参照してください。

このトピックは、以下のセクションで構成されています。

- 前提条件

- OMS を使用するようにクラウド コネクタを構成する

- OMS を構成する

- Log Analytics リポジトリのアラートを分析する

- 推奨される監視セット

## <a name="prerequisites"></a>前提条件

OMS を使用して Cloud Connector のデプロイを監視するには、次のものが必要です。

- **Azure アカウントと OMS ワークスペース。** Azure アカウントをまだ持っていない場合は、OMS Log Analytics を使用するアカウントを作成する必要があります。 Azure アカウントを作成し、OMS ワークスペースを設定する方法については、「[Log Analytics ワークスペースを使用した概要](/azure/log-analytics/log-analytics-get-started)」を参照してください。

- **Cloud Connector バージョン 2.1 以降**

- Cloud Connector の監視には **、Log Analytics の新しいログ検索** が必要です。 詳細については、「 [Azure Log Analytics ワークスペースを新しいログ検索にアップグレードする](/azure/log-analytics/log-analytics-log-search-upgrade)」を参照してください。

## <a name="configure-cloud-connector-to-use-oms"></a>OMS を使用するようにクラウド コネクタを構成する

OMS を使用するようにクラウド コネクタのオンプレミス環境を構成する必要があります。 これを行うには、OMS ワークスペース ID とキーが必要です。これには、OMS ポータルを使用して次のように確認できます:設定 --\>接続されたソース -\> Windows サーバー:

![Cloud Connector OMS のスクリーン ショット。](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

OMS を使用するように Cloud Connector を構成する方法は、シナリオによって異なります。

- **新しい Cloud Connector アプライアンスをインストールする場合、またはアプライアンスを再デプロイする場合は**、Install-CcAppliance を実行する前に次の手順に従います。

  1. CloudConnector.ini ファイル [Common] セクションで、OMSEnabled パラメーターを True に設定します。

     Cloud Connector がデプロイまたはアップグレードされるたびに、OMS エージェントを VM に自動的にインストールしようとします。 OMS エージェントが Cloud Connector の自動更新を存続できるように、この機能を有効にします。

  2. OMS ID とキーを構成するには、-AccountType OMSWorkspace Set-CcCredential実行します。

- **既存の Cloud Connector アプライアンスに OMS エージェントをインストールする場合は**、次の手順に従います。

  1. CloudConnector.ini ファイル [Common] セクションで、OMSEnabled=true を設定します。

  2. Import-CcConfiguration を実行します。

  3. Install-CcOMSAgent を実行します。

     > [!NOTE]
     > OMSWorkspace 資格情報が設定されていない場合は、install-CcOMSAgent を実行するときに資格情報の入力を求めるメッセージが表示されます。

- **OMS エージェントが既にインストールされている Cloud Connector アプライアンスで OMS ワークスペース ID またはキーを更新する場合は、次のようにします。**

  1. OMS ID とキーを構成するには、-AccountType OMSWorkspace Set-CcCredential実行します。

  2. 更新プログラムを適用するには、Install-CcOMSAgent を実行します。

- **すべてのシナリオで、エージェントが次のように接続されていることを確認します。**

    OMS ポータルで、設定 - 接続されたソース -\>\> Windows サーバーに移動します。 接続されているマシンの一覧が表示されます。

## <a name="configure-oms"></a>OMS を構成する

次に、OMS ポータルを使用して OMS 構成を指定する必要があります。 具体的には、次のことを行う必要があります。

- イベント ログとパフォーマンス カウンターに関する情報を指定します。

- 通知を作成します。

### <a name="specify-information-about-event-logs-and-performance-counters"></a>イベント ログとパフォーマンス カウンターに関する情報を指定する

OMS ポータルでは、次のようにイベント ログとパフォーマンス カウンターに関する情報を指定する必要があります。

1. 設定-Data-Windows\>\> イベント ログに移動し、次のイベント ログを追加します。

   - Lync Server

   - アプリケーション

     > [!NOTE]
     > テキスト ボックスに Lync Server を手動で入力する必要があります。 ドロップダウン リストにはオプションとして表示されません。

     詳細については、[Log Analytics のイベント ログ データ ソースWindows](/azure/log-analytics/log-analytics-data-sources-windows-events)を参照してください。

2. 設定-\>Data-\> Windows パフォーマンス カウンターに移動し、次のパフォーマンス カウンターを追加します。

   - **OS レベルのカウンター**。 プロセッサ使用量、メモリ使用量、ネットワーク使用量などの OS レベル カウンターを追加することも、カウンターを明示的に追加せずに、容量やパフォーマンス、ネットワーク パフォーマンス モニターなどの既存のソリューションを使用することもできます。 監視方法に関係なく、これらの OS カウンターを監視することをお勧めします。

   - **カウンターをSkype for Business** します。 Skype for Businessによって提供されるカウンターは多数あります。 これらのカウンターを見つけるには、任意の仲介サーバーにログオンし、パフォーマンス モニターを開きます。 これらのカウンターは、"LS:" で始まる。 Microsoft では、少なくとも次の容量カウンターから始めて、関心のある他の容量カウンターを追加することをお勧めします。

     アクティブな呼び出しの合計:

     - LS:MediationServer - 受信呼び出し(_Total)\- 現在

     - LS:MediationServer - 発信呼び出し(_Total)\- 現在

     アクティブ メディア バイパス呼び出しの合計数:

     - LS:MediationServer - 受信呼び出し(_Total)\- アクティブ メディア バイパス呼び出し

     - LS:MediationServer - 発信呼び出し (_Total)\- アクティブ メディア バイパス呼び出し

     > [!NOTE]
     > テキスト ボックスにパフォーマンス カウンターを手動で入力する必要があります。 ドロップダウン リストにオプションとして表示されません。

     詳細については、[Log Analytics のWindowsおよび Linux パフォーマンス データ ソースに関するページを](/azure/log-analytics/log-analytics-data-sources-performance-counters)参照してください。

### <a name="create-alerts"></a>アラートを作成する

OMS には、結果アラートの数とメトリック測定アラートの 2 種類のアラートがあります。 アラートの作成の詳細については、「 [Log Analytics でのアラート ルールの操作](/azure/log-analytics/log-analytics-alerts-creating)」を参照してください。

アラートを作成するときは、次のことを考慮する必要があります。

- アラートが結果の数アラート (既定の選択) であることを確認します。

- デモ クエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。

- タイム ウィンドウとアラート頻度の両方を 5 分に設定することをお勧めします。

- デモ アラートに対して "アラートの抑制" を有効にしないことをお勧めします。

- 一般的なアラート シナリオでは、1 つのエラー アラートと 1 つのリセット アラートというアラートのペアを作成することをお勧めします。 エラー アラートの重大度レベル [重大] を選択します。リセット アラートの場合は、重大度レベル Informational を選択します。

次のセクションでは、サンプル アラートを作成する方法について説明します。

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>アラート ペアを作成する: "RTCMEDSRV は仲介サーバーで実行されていません"と "RTCMEDSRV は仲介サーバーで実行に戻っています"

このアラート ペアを作成するには:

- エラー アラートのクエリは次のとおりです。

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    クエリでは、コンピューターに  *"MediationServer" が含まれているコンピューター フィルターが使用されます*  。 フィルターは、名前に "MediationServer" という文字列が含まれているコンピューターのみを選択します。

     フィルターを独自のコンピューター フィルターに置き換えるか、単に削除します。 正規表現を使用せずに複雑な文字列フィルターを作成できます。 正規表現を使用することもできます。 さらに、検索クエリを保存し、そのグループをアラート クエリのコンピューター フィルターとして使用することで、コンピューター グループを作成できます。 詳細については、 [Log Analytics ログ検索のコンピューター グループに関する](/azure/log-analytics/log-analytics-computer-groups)ページを参照してください。

    各コンピューターについて、エラー クエリは RTCMEDSRV サービスの開始とサービス停止の両方の最後のイベント ログを取得します。 最後のイベントがサービス停止イベントの場合は、1 つのログが返されます。最後のイベントがサービス開始イベントの場合、何も返されません。 つまり、クエリは、RTCMEDSRV が時間枠で停止されているサーバーの一覧を返します。

- リセット アラートのクエリは次のとおりです。

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    リセット クエリは、エラー クエリとは正反対の処理を行います。 各コンピューターに対して、最後のイベントがサービス開始イベントの場合は 1 つを返します。最後のイベントがサービス停止イベントの場合、何も返されません。

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>アラート ペアを作成する: "仲介サーバーでの同時呼び出しが多すぎます"と "同時呼び出しは通常の読み込みにフォールバックします"

このアラートを作成するには:

- エラー アラートのクエリは次のとおりです。

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    各コンピューターについて、クエリは受信呼び出しと送信呼び出しの最後のカウンターを取得し、これら 2 つの値を合計します。 合計値が 500 を超えると、1 つのログが返されます。返さない場合は何も返されません。 つまり、クエリは、同時呼び出しが時間枠内に多すぎるサーバーの一覧を返します。

- リセット アラートのクエリは次のとおりです。

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    リセット クエリは、エラー クエリとは正反対の処理を行います。 各コンピューターについて、クエリは受信呼び出しと送信呼び出しの最後のカウンターを取得し、これら 2 つの値を合計します。 合計値が 500 未満の場合、1 つのログが返されます。それ以外の場合は何も返しません。

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>アラートの作成: "CPU 使用率 \> 90 または RTCMEDIARELAY がサーバーで停止しました" アラート

このアラートを作成するには、クエリは次のとおりです。

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

クエリは、すべてのコンピューターからすべてのプロセッサ使用率カウンターとサービス停止イベントを取得し、プロセッサ使用率が 90% を超えるか、サービスが停止した場合に 1 つのログを返します。

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Log Analytics リポジトリのアラートを分析する

リポジトリ内のアラートを分析するには、Alert Management ソリューションを使用します。 詳細については、「[Operations Management Suite (OMS) のアラート管理ソリューション](/azure/log-analytics/log-analytics-solution-alert-management)」を参照してください。

## <a name="recommended-minimal-monitoring-set"></a>推奨される最小限の監視セット

イベント ログとパフォーマンス カウンターに関する問題を特定するには、

- **イベント ログ。** 問題の場合はイベントペアが存在する必要があります。一方のイベントセットは何かが間違っていることを示し、もう一方はすべてが正常であることを示します。 特定の期間は、記録された最後のイベントであり、その期間に何かが間違っているかどうかを示します。

- **パフォーマンス カウンター。** 監視対象のカウンターのしきい値が必要です。

次の表に、停止イベント ID と開始イベント ID を一覧表示して監視を推奨するサービスを示します。

|サービス名  <br/> |ターゲット サーバー ロール  <br/> |イベント ID の停止  <br/> |Start イベント ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |仲介サーバー  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |エッジ サーバー  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |エッジ サーバー  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |エッジ サーバー  <br/> |22003  <br/> |22002  <br/> |

次の表に、Microsoft が監視を推奨するネットワークの問題を示します。


| モニター名  <br/>                                        | ターゲット サーバー ロール  <br/> | 成功イベント ID 式  <br/> | エラー イベント ID 式  <br/> | エラーの例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 仲介サーバーからゲートウェイへの接続エラー  <br/>    | 仲介サーバー  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 仲介サーバーからゲートウェイへの呼び出しの完了エラー  <br/> | 仲介サーバー  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重大なネットワークの問題  <br/>                           | エッジ サーバー  <br/>        | 14353                              |                                  | 12288  <br/>           |

監視する必要がある呼び出し容量カウンターを次に示します。 これらの数値は、Cloud Connector 標準エディションの場合は 500 以下にする必要があります。Cloud Connector の最小エディションの場合は 50 未満です。

- LS:MediationServer - 受信呼び出し(_Total)\- 現在

- LS:MediationServer - 発信呼び出し(_Total)\- 現在

- LS:MediationServer - 受信呼び出し(_Total)\- アクティブ メディア バイパス呼び出し

- LS:MediationServer - 発信呼び出し (_Total)\- アクティブ メディア バイパス呼び出し

## <a name="see-also"></a>関連項目

OMS の操作の詳細については、次を参照してください。

- [Log Analytics でログ検索を使用してデータを検索する](/azure/log-analytics/log-analytics-log-searches)

- [Log Analytics のアラートについて](/azure/log-analytics/log-analytics-alerts)

- [コンピューターを Azure の Log Analytics サービスにConnect Windowsする](/azure/log-analytics/log-analytics-windows-agents)