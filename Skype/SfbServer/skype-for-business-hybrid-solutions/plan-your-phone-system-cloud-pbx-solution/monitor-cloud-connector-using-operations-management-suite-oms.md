---
title: 運用管理スイート (OMS) を使用してクラウドのコネクタを監視します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 運用管理スイート (OMS) を使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 5e03504f27eadbb235c1b5c84e8c7a19d66aea7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>運用管理スイート (OMS) を使用してクラウドのコネクタを監視します。
 
運用管理スイート (OMS) を使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視する方法の詳細については、このトピックを参照してください。
  
運用管理スイート (OMS)、マイクロソフトのクラウド IT 管理ソリューションを使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視できます。 OMS のログ分析機能を使用すると、監視し、可用性となどの物理リソースと仮想マシンのパフォーマンスを分析できます。 OMS とログ分析の詳細についてを参照してください[操作の管理スイート (OMS) とは何ですか?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)。
  
このトピックには次のセクションが含まれます。
  
- 前提条件
    
- OMS を使用するクラウドのコネクタを構成します。
    
- OMS を構成します。
    
- ログ分析リポジトリ内のアラートを分析します。
    
- 推奨される監視の設定
    
## <a name="prerequisites"></a>前提条件

OMS を使用するには、コネクタのクラウドの展開を監視するため、前に、以下が必要。
  
- **Azure アカウントと、OMS のワークスペースです。** 既に Azure アカウントをお持ちでない場合は、OMS のログ分析機能を使用する 1 つを作成する必要があります。 Azure アカウントを作成し、OMS のワークスペースを設定する方法の詳細については、[ログ分析機能のワークスペースを使い始める](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started)を参照してください。
    
- **クラウド コネクタ 2.1 またはそれ以降のバージョン**
    
- **ログ分析の新しいログの検索**では、クラウドのコネクタを監視する必要があります。 詳細については、[新しいログの検索対象に Azure のログ分析ワークスペースのアップグレード](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade)を参照してください。
    
## <a name="configure-cloud-connector-to-use-oms"></a>OMS を使用するクラウドのコネクタを構成します。

OMS を使用するクラウド コネクタ、オンプレミス環境を構成する必要があります。 これを行うには、する必要があります、OMS ワークスペース ID とキーが、OMS のポータルを使用して次のように、検索することができます: 設定 -\>ソースの接続 -\> Windows サーバー。
  
![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
OMS を使用するクラウドのコネクタを構成する方法は、シナリオによって異なります。
  
- **クラウド コネクタの新しいアプライアンスをインストールするか、アプライアンスを再配置する場合**、インストール CcAppliance を実行する前にこれらの手順に従います。
    
1. CloudConnector.ini ファイルの [共通] セクションに OMSEnabled パラメーターを True に設定します。
    
    クラウド コネクタを展開またはアップグレードするたびにしようと、Vm 上に自動的に OMS のエージェントをインストールします。 OMS のエージェントは、クラウド コネクタの自動更新を生き残ることができますので、この機能を有効にします。
    
2. OMS の ID とキーを構成するには、セット CcCredential AccountType の OMSWorkspace を実行します。 
    
- **既存のコネクタのクラウド アプライアンスに OMS エージェントをインストールするかどうかは**、次の手順に従います。
    
1. CloudConnector.ini [共通] セクションで、ファイル内の設定 OMSEnabled = true です。 
    
2. インポート-CcConfiguration を実行します。 
    
3. インストール CcOMSAgent を実行します。 
    
    > [!NOTE]
    > OMSWorkspace の資格情報が設定されていることはない場合は、インストール CcOMSAgent を実行すると、資格情報の求められます。 
  
- **OMS ワークスペース ID またはコネクタのクラウド アプライアンス内のキーを更新する場合、OMS エージェントを既にインストールされているには。**
    
1. OMS の ID とキーを構成するには、セット CcCredential AccountType の OMSWorkspace を実行します。 
    
2. 更新プログラムを適用するには、インストール CcOMSAgent を実行します。 
    
- **すべてのシナリオでは、エージェントが次のように接続されていることを確認します。**
    
    OMS ポータルで、[設定] -\> - [ソースの接続されている\>Windows サーバーです。 接続されているマシンの一覧が表示されます。 
    
## <a name="configure-oms"></a>OMS を構成します。

次に、OMS のポータルを使用して、OMS の構成を指定する必要があります。 具体的には、する必要があります。
  
- イベント ログおよびパフォーマンス カウンターに関する情報を指定します。
    
- アラートを作成します。 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a>イベント ログおよびパフォーマンス カウンターに関する情報を指定します。

OMS ポータルでは、次のように、イベント ログおよびパフォーマンス カウンターに関する情報を指定する必要があります。
  
1. 設定 - を参照して\>データ ・\>Windows イベント ログのイベント ログを追加し、。 
    
  - Lync Server
    
  - アプリケーション
    
    > [!NOTE]
    > テキスト ボックスに、Lync Server を手動で入力する必要があります。 ドロップ ダウン リストでオプションとして表示されません。 
  
    詳細については、[ログの分析では、Windows イベント ログ データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)を参照してください。
    
2. 設定 -\>データ -\> 、Windows パフォーマンス カウンターのパフォーマンス カウンターを追加し、。 
    
  - **OS レベルのカウンター**です。 プロセッサ使用率、メモリ使用量、ネットワークの使用率など、OS レベルのカウンターを追加することができますや容量などのパフォーマンス、ネットワークのパフォーマンス モニター カウンターを明示的に追加することがなく既存のソリューションを使用することができます。 それらを監視するを決定する方法に関係なく、これらの OS のカウンターを監視することをお勧めします。
    
  - **Skype ビジネスのカウンター**です。 ビジネス用の Skype によって提供される多数のカウンターがあります。 任意の仲介サーバーにログオンするいると、パフォーマンス モニターを開くには、これらのカウンターがあります。 これらのカウンターが始まる"LS:"です。 マイクロソフトでは、最低限、次の容量のカウンターを使用して開始し、興味のある他のユーザーを追加することをお勧めします。
    
    アクティブな呼び出しの合計:
    
  - LS:MediationServer - 受信 Calls(_Total)\-現在 
    
  - LS:MediationServer - 送信 Calls(_Total)\-現在 
    
    アクティブなメディアの合計は、呼び出しを使用しません。
    
  - LS:MediationServer - 受信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。 
    
  - LS:MediationServer - 送信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。 
    
    > [!NOTE]
    > テキスト ボックスに、パフォーマンス カウンターを手動で入力する必要があります。 ドロップ ダウン リストでオプションとして表示されません。 
  
    詳細については、[ログ分析機能で、Windows と Linux のパフォーマンス データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)を参照してください。
    
### <a name="create-alerts"></a>アラートを作成します。

OMS のアラートの 2 種類があります: 結果の通知とメートル法の警告の数。 警告の作成の詳細については、[ログ分析の警告ルールの操作](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating)を参照してください。
  
アラートを作成するときは、以下を考慮してください。
  
- アラートは、デフォルトの選択、数値の結果のアラートを確認します。 
    
- デモのクエリは、「結果の数」を"よりも長く 0"に設定されている必要があります。 
    
- 5 分のタイム ・ ウィンドウおよび [通知の頻度を設定することをお勧めします。 
    
- デモのアラートの「警告を抑制する」を有効にするいることをお勧めします。 
    
- 一般的には、アラートのアラートのペアの作成をお勧めします。: 1 つのエラー メッセージと警告の 1 つのリセットします。 エラーのアラートの重大度レベル重大な; を選択しますリセット警告の重大度レベルの情報を選択します。
    
次のセクションでは、サンプルの通知を作成する方法について説明します。
  
 **アラートのペアを作成:「RTCMEDSRV は仲介サーバーで実行されていない」と「RTCMEDSRV は、仲介サーバーで実行するのには」**
  
このアラートのペアを作成します。
  
- エラー メッセージのクエリは次のとおりです。
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    クエリを使用して、コンピューターのフィルターで*コンピューターに"MediationServer"が含まれている場合*。 フィルターは、名前に文字列"MediationServer"が含まれているコンピューターのみを選択します。
    
     コンピューター フィルターでフィルターを交換してか、削除するだけとします。 正規表現のない複雑な文字列のフィルターを作成できます。 詳細については、[文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)を参照してください。 正規表現を使用することもできます。 さらに、検索クエリを保存し、そのグループを使用して、警告のクエリで、コンピューターのフィルターとしてコンピューター グループを作成することができます。 詳細については、[コンピューター グループのログの分析ログの検索](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups)を参照してください。
    
    各コンピューターでは、クエリのエラーは RTCMEDSRV の両方のサービス開始の最後のイベント ログを取得して、サービスの停止。 いずれかが返されます場合は、最後のイベントは、サービスの停止イベントをログに記録nothing が返されます場合は、最後のイベントは、サービスの開始イベントです。 つまり、クエリが RTCMEDSRV を停止する時間帯にサーバーのリストが返されます。 
    
- リセット警告のクエリは次のとおりです。
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    リセットのクエリは、まったく逆クエリ エラーのことです。 各コンピューターの場合を返しますいずれかの最後のイベントは、サービスを開始するイベントです。nothing が返されます場合、最後のイベントは、サービスの停止イベントです。
    
 **アラートのペアを作成:"が仲介サーバーでの同時通話の数」「同時通話に戻る通常の負荷」と**
  
この警告を作成します。
  
- エラー メッセージのクエリは次のとおりです。
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    各コンピューターのクエリが表示されます着信呼び出しおよび発信呼び出しの合計の最後のカウンター、2 つの値。 いずれかが返されますを合計した値が 500 を超えている場合にログを記録nothing が返されますされていない場合。 つまり、クエリ サーバーの同時呼び出しを時間帯に多くのリストが返されます。
    
- リセット警告のクエリは次のとおりです。
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    リセットのクエリは、まったく逆クエリ エラーのことです。 各コンピューターのクエリが表示されます着信呼び出しおよび発信呼び出しの合計の最後のカウンター、2 つの値。 500 未満の場合は、合計値は 1 つのログが返されますそれ以外は何も返されます。
    
 **警告を作成する:"CPU 使用率\>90 または RTCMEDIARELAY は、サーバーで停止している"アラート**
  
この警告を作成するには、クエリは次のとおりです。
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

クエリは、すべてのコンピューターと戻り値のいずれかのプロセッサ使用率が 90%、またはサービスを超えた場合、1 つのログが停止したことから、すべてのプロセッサの使用状況カウンターとサービスの停止イベントが表示されます。 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>ログ分析リポジトリ内のアラートを分析します。

リポジトリ内の警告を分析するには、アラートの管理ソリューションを使用します。 詳細については、[警告の管理ソリューションで操作管理スイート (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)を参照してください。
  
## <a name="recommended-minimal-monitoring-set"></a>推奨される最低限監視

イベント ログおよびパフォーマンス カウンターと問題を特定します。 
  
- **イベント ログです。** すべての問題のすべてが適切であることを示します、他の何かが間違っている場合は、通知するイベントの 1 つのセットを使用して、イベントのペアがあります。 最後には、一定期間、その期間はまずい何かがあるかどうかを示すイベントが記録します。
    
- **パフォーマンス カウンターです。** 監視対象のカウンターのしきい値が存在する必要があります。
    
次の表に、マイクロソフトは、停止と開始のイベント Id をリストすることによって監視することをお勧めするサービスを示します。
  
|||||
|:-----|:-----|:-----|:-----|
|サービス名  <br/> |ターゲット サーバーの役割  <br/> |イベント ID を停止します。  <br/> |イベント ID を開始します。  <br/> |
|RTCMEDSRV  <br/> |仲介サーバー  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |エッジ サーバー  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |エッジ サーバー  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |エッジ サーバー  <br/> |22003  <br/> |22002  <br/> |
   
監視をお勧めするネットワークの問題を次の表に一覧します。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|モニター名  <br/> |ターゲット サーバーの役割  <br/> |成功のイベント ID の式  <br/> |エラー イベント ID 式  <br/> |障害の例  <br/> |
|ゲートウェイの接続障害が発生する仲介サーバー  <br/> |仲介サーバー  <br/> |25062 || 25002  <br/> |25061  <br/> |MS PING (オプション) をゲートウェイが失敗しました。  <br/> |
|ゲートウェイに仲介サーバーの呼び出し完了障害  <br/> |仲介サーバー  <br/> |25064 || 25002  <br/> |25063  <br/> |MS のゲートウェイへの呼び出しを作成しようとして失敗しました。  <br/> |
|重要なネットワークの問題  <br/> |エッジ サーバー  <br/> |14353 || 12288  <br/> |14624  <br/> |TLS をトランスポートは、ローカル IP アドレス ポート 5061 で 192.168.231.14 の開始に失敗しました  <br/> |
   
呼び出し容量のカウンターを監視する必要がありますを次に示します。 これらの数値は、以下をする必要があります 500 のクラウドのコネクタの標準的なエディションです。クラウド コネクタの最小のエディションの 50 よりも小さい。
  
- LS:MediationServer - 受信 Calls(_Total)\-現在 
    
- LS:MediationServer - 送信 Calls(_Total)\-現在 
    
- LS:MediationServer - 受信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。
    
- LS:MediationServer - 送信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。
    
## <a name="see-also"></a>関連項目

OMS を使用して操作の詳細については、以下を参照してください。
  
- [ログ分析でログの検索を使用してデータを検索します。](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [Azure のログ分析の言語リファレンス](https://docs.loganalytics.io/docs/Language-Reference)
    
- [ログ分析機能で通知を理解します。](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [Azure のログ分析サービスを Windows コンピューターに接続します。](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

