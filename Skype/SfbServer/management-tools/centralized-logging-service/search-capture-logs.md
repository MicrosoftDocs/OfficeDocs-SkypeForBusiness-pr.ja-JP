---
title: Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '概要: 検索し、ビジネス サーバー 2015 の Skype でのログ サービスの一元的なログを読み取る方法を説明します。'
ms.openlocfilehash: 9429ef0f2c14552c615e4d7f81c497ea9bb546f3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372220"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
 
**の概要:** 検索し、ビジネス サーバー 2015 の Skype でのログ サービスの一元的なログを読み取る方法について説明します。
  
集中ログ サービスの検索機能は、次のような便利で強力です。 
  
- 検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。
    
- 広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。 同じログに対して検索を実行し、検索条件が変更されたときにもう一度ログ セッションを実行する必要はありません。
    
- 検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。
    
個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューターあたり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。
  
検索後**同期 CsClsLogging**コマンドレットを実行しにではなく、CLSAgent が管理しているファイルをキャッシュと混同) の検索に使用するキャッシュをフラッシュします。 キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。
  
集中ログ サービスに最も大きなメリットを得るには、調査している問題に関連するコンピューターとプールのログからトレース メッセージのみを返す検索を構成する方法を十分に理解する必要があります。 問題
  
ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの一元的な検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要があります。これら 2 つのグループのいずれかが含まれています。 (自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>集中ログ サービスを使用して基本的な検索を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。 -OutputFilePath を使用して、検索結果をファイルに保存する場合は、_\<ファイルの絶対パスを文字列\>_。 -OutputFilePath パラメーターを定義するには、「パスとファイル名 (たとえば引用符で囲まれた文字列の形式でパラメーターの一部としての使用」を指定していますください。C:\LogFiles\SearchOutput.txt)。 この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。 出力は追加され、上書きはされません。 個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。 
  
次に例を示します。
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>集中ログ サービスを使用してプールやコンピューターの基本的な検索を実行するには

1. 特定のプールやコンピューターの検索を制限するを使用して、コンピューターのパラメーターを引用符で囲まれて、次のように、コンマで区切られたコンピューターの完全修飾名で定義されているコンピューターで。
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

次に例を示します。
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. 変更する 1 台のコンピューターではなくプール全体を検索する場合は、コンマで区切られた、プールまたは引用符で囲まれたプールで、プール、コンピューター名を削除および置換する-コンピューターのパラメーターです。
    
    例:
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 検索コマンドを使用して、プールのフロント エンド プール、エッジ プール、永続的なチャット サーバー プール、または、配置内のリソース プールとして定義されている他のユーザーなど、配置内のすべてのプールを使用できます。
    
    次に例を示します。
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>時間のパラメーターを使用して検索を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 25 分前です。 つまり、検索を 4:00:00 PM に開始する場合、検索の開始時間には 3:35:00 から 4:05:00 PM までと表示されます。 60 分または現在の時刻より前に 3 時間を検索する場合は、- 開始時刻パラメーターを使用し、検索を開始する時刻を示す日付と時刻の文字列を設定します。 
    
    などの日付と時刻の範囲を定義するための開始時刻と、終了時刻を使用するを定義できます午前 8 と 9 AM の間で検索 2012/11/20 に、プールに。 次に示すように、出力パスを設定して、c:\logfile.txt という名前のファイルに結果を書き込むことができます。
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 日時の文字列は、"日付 時間" と"時間 日付" のどちらででも指定できます。 "コマンドが文字列を解析し、適切な値を使用して、日付と時刻からコマンドレットを実行しているマシンでは、ロケールとカルチャの設定をします。 
  
3. 11/20/2012 11時 00分: 00 AM で始まるログを取得する場合の開始時刻を定義します。 検索の既定の時間範囲は、特定終了時刻を定義する場合を除き、30 分です。 検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。
    
次に例を示します。
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 特定の期間内には、ログの検索を行うの開始時刻と、終了時刻を定義します。 コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。 
    
次に例を示します。
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>他の条件および一致オプションを使用して高度な検索を行うには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

次に例を示します。
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。
    
3. Pool01.contoso.net をという名前のフロント エンド プールだけに同じコンポーネントを使用して検索を制限するには、次のように入力します。
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。 **MatchAll ・** パラメーターを指定することによって、この動作を変更できます。 これを行うには、次のように入力します。
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>集中ログ サービスからキャプチャしたログの閲覧

集中ログ サービスの本当の利益は、報告された問題を追跡するために使用できるファイルを使用して検索を実行した後に気付きました。 このファイルは、さまざまな方法で読むことができます。 出力ファイルは標準のテキスト形式なので、メモ帳など、テキスト ファイルを開いて読むことができる任意のプログラムを使用できます。 サイズの大きいファイルと複雑な問題については、読み取り、集中ログ サービスのログ出力を解析するように設計された Snooper.exe のようなツールを使用できます。 Snooper は、個別のダウンロードとして入手可能なデバッグ ツールに含まれています。 デバッグ ツールは、ここをダウンロードすることができます: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。 デバッグ ツールをインストールすると、ショート カットとメニュー項目は作成されません。 デバッグ ツールをインストールした後 Windows エクスプ ローラー、コマンド ライン ウィンドウ、または Skype ビジネス サーバー管理シェルを開きビジネス サーバー 2015\Debugging ツールの C:\Program Files\Skype ディレクトリ (既定の場所) に移動します。 Snooper.exe をダブルクリックして Snooper.exe を指定して、ビジネス サーバー管理シェルのコマンド ・ ラインまたは Skype を使用している場合、[ENTER キーを押します。
  
> [!IMPORTANT]
> このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。 トラブルシューティングとそれに関連するプロセスは、複雑な問題です。 基本的なトラブルシューティングおよび特定の作業負荷のトラブルシューティングに関する詳細を参照してください Microsoft Lync Server 2010 リソース キットでの[https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)。 プロセスと手順にも当てはまります Skype をビジネス サーバー 2015。 
  
### <a name="to-open-a-log-file-in-snooper"></a>Snooper でログ ファイルを開くには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。 
    
2. デバッグ ツール (LyncDebugTools.msi) のインストール後に、Windows エクスプローラーまたはコマンド ラインを使用して、Snooper.exe が存在するディレクトリに移動します。 既定では、デバッグ ツールは、ビジネス サーバー 2015\Debugging ツールの C:\Program Files\Skype に配置されます。 Snooper.exe をダブルクリックするか、実行します。
    
3. Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。
    
4. ログ ファイルの**トレース**メッセージが表示されるタブは**トレース**で収集されたトレースのメッセージの内容を表示するのには [**メッセージ**] タブをクリックします。
    
### <a name="to-display-a-call-flow-diagram"></a>通話フロー図を表示するには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。
    
2. ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。
    
3. [**通話フロー**] をクリックします。
    
> [!NOTE]
> メッセージまたは呼び出しの流れの一部ではないのトレース] をクリックする場合は、図は表示されず、できる Snooper は、「このメッセージは callfow の対象ではない」という内容下部にステータス メッセージが表示されます。 別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。 
  
4. メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。
    
5. 要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。