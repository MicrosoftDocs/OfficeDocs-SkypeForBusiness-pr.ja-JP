---
title: Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '概要: Skype for Business Server 2015 で一元管理されたログサービスキャプチャログの検索と読み取りを行う方法について説明します。'
ms.openlocfilehash: 234bcdcda4fbf4a0fa7cec364b9a8dbb7b757dc7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816576"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で集中ログ サービスが作成したキャプチャ ログを検索する
 
**概要:** Skype for Business Server 2015 で一元管理されたログサービスのキャプチャログの検索と読み取りを行う方法について説明します。
  
中央のログサービスの検索機能は、次のような理由で便利で強力です。 
  
- 検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。
    
- 広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。 検索条件が変更されたときに、ログセッションをもう一度実行する必要はありません。
    
- 検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。
    
個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューターあたり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。
  
各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。 キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。
  
一元管理サービスを最大限に活用するには、検索の構成方法についてよく理解しておく必要があります。これは、コンピューターからのトレースメッセージだけを返し、調査中の問題に関連するプールログのみを返すようにするためです。 問題
  
Skype for Business Server 管理シェルを使用して集中ログサービスの検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループ、またはカスタム RBAC ロールのいずれかのメンバーである必要があります。この2つのグループのいずれかが含まれます。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>中央集中ログサービスを使用して基本的な検索を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。 検索結果をファイルに保存する場合は、-outputfilepath _ \<文字列の完全修飾ファイルパス\>_ を使用します。 -OutputFilePath パラメーターを定義するには、パスとファイル名を引用符で囲まれた文字列形式でパラメーターの一部として指定します (例:C:\LogFiles\SearchOutput.txt). この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。 出力は追加され、上書きはされません。 個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。 
  
次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>集中ログサービスを使用してプールまたはコンピューターで基本的な検索を実行するには

1. 検索を特定のプールまたはコンピューターに限定するには、コンピューターのパラメーターを、引用符で囲まれ、次のようにコンマで区切って、コンピューターの完全修飾名で指定します。
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. 1台のコンピューターではなくプール全体を検索する必要がある場合は、-Computers のパラメーターを [プール] に変更し、コンピューター名を削除して、そのプールまたはプールをコンマで区切って引用符で囲みます。
    
    次に例を示します。
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 検索コマンドを使用する場合、プールには、フロントエンドプール、エッジプール、常設チャットサーバープールなどの展開内の任意のプールを使うことができます。また、展開のプールとして定義されている他のプールにすることもできます。
    
    次に例を示します。
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>時間のパラメーターを使用して検索を実行するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 25 分前です。 つまり、検索を 4:00:00 PM に開始する場合、検索の開始時間には 3:35:00 から 4:05:00 PM までと表示されます。 現在の時刻の前に60分または3時間を検索する必要がある場合は、-StartTime パラメーターを使用し、日付と時刻の文字列を設定して、検索を開始する時刻を指定します。 
    
    たとえば、-StartTime と-EndTime を使用して時刻と日付の範囲を定義することによって、プールの11/20/2012 で、午前8時から9時までの間に検索を定義できます。 次に示すように、出力パスを設定して、c:\logfile.txt という名前のファイルに結果を書き込むことができます。
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 日時の文字列は、"日付 時間" と"時間 日付" のどちらででも指定できます。 "コマンドは文字列を解析し、コマンドレットを実行しているコンピューター上の、日付と時刻の適切な値、およびロケールとカルチャの設定を使います。 
  
3. 11/20/2012 の 11:00:00 AM から始まるログを取得する場合は、-StartTime を定義します。 特定の終了日を定義しない限り、検索の既定の時間範囲は30分です。 検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。
    
次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 指定した期間内にログの検索を実行するには、-StartTime と-EndTime の定義を行います。 コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。 
    
次に例を示します。
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>他の条件および一致オプションを使用して高度な検索を行うには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。
    
3. 同じコンポーネントを使用して、pool01.contoso.net という名前のフロントエンドプールに検索を限定するには、次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。 この動作を変更するには、 **-matchall**パラメーターを指定します。 これを行うには、次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>集中ログ サービスからキャプチャしたログの閲覧

検索を実行した後で一元管理サービスの実際の利点を実感し、報告された問題を追跡するために使用できるファイルを用意しています。 このファイルは、さまざまな方法で読むことができます。 出力ファイルは標準のテキスト形式なので、メモ帳など、テキスト ファイルを開いて読むことができる任意のプログラムを使用できます。 大規模なファイルとより複雑な問題については、一元管理サービスからのログ出力の読み取りと解析のために設計された Snooper などのツールを使うことができます。 Snooper は、個別のダウンロードとして入手可能なデバッグ ツールに含まれています。 デバッグツールは、次[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)のページからダウンロードできます。 デバッグツールをインストールすると、ショートカットとメニュー項目は作成されません。 デバッグツールをインストールしたら、Windows エクスプローラー、コマンドラインウィンドウ、または Skype for Business Server Management Shell を開いて、ディレクトリ (既定の場所) C:\Program Files\Skype for Business Server 2015 \ デバッグツールを開きます。 Snooper をダブルクリックするか、Snooper を入力して、コマンドラインまたは Skype for Business Server Management Shell を使用している場合は、ENTER キーを押します。
  
> [!IMPORTANT]
> このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。 トラブルシューティングとそれに関連するプロセスは、複雑な問題です。 基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、「 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 リソースキット」を参照してください。 プロセスと手順は、引き続き Skype for Business Server 2015 にも適用されます。 
  
### <a name="to-open-a-log-file-in-snooper"></a>Snooper でログ ファイルを開くには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。 
    
2. デバッグ ツール (LyncDebugTools.msi) のインストール後に、Windows エクスプローラーまたはコマンド ラインを使用して、Snooper.exe が存在するディレクトリに移動します。 既定では、デバッグツールは、C:\Program Files\Skype for Business Server 2015 \ デバッグツールにあります。 Snooper.exe をダブルクリックするか、実行します。
    
3. Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。
    
4. ログファイルの**トレース**メッセージが [**トレース**] タブに表示されます。収集されたトレースのメッセージの内容を表示するには、[**メッセージ**] タブをクリックします。
    
### <a name="to-display-a-call-flow-diagram"></a>通話フロー図を表示するには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。
    
2. ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。
    
3. [**通話フロー**] をクリックします。
    
> [!NOTE]
> コールフローの一部ではないメッセージまたはトレースをクリックすると、図面が表示されず、Snooper の下部に状態メッセージが表示されます。 "このメッセージは、呼び出しの対象になりません" と表示されます。 別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。 
  
4. メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。
    
5. 要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。
