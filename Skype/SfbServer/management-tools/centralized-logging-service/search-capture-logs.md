---
title: Skype for Business Server 2015 の集中ログ サービスによって作成された検索キャプチャ ログ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server 2015 で集中ログ サービスキャプチャ ログを検索および読み取る方法について学習します。'
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835127"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の集中ログ サービスによって作成された検索キャプチャ ログ
 
**概要:** Skype for Business Server 2015 で集中ログ サービスキャプチャ ログを検索して読み取る方法について学習します。
  
集中ログ サービスの検索機能は、次の理由から役立ち、強力です。 
  
- 検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。
    
- 広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。 同じログに対して検索し、検索条件が変更された場合にログ セッションを再度実行する必要はありません。
    
- 検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳** などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。
    
個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューター当たり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。
  
各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。 キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。
  
集中ログ サービスを最も有効に利用するには、調査中の問題に関連するコンピューターログとプール ログからのトレース メッセージのみを返す検索を構成する方法を理解している必要があります。 issues
  
Skype for Business Server 管理シェルを使用して集中ログ サービスの検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーか、これら 2 つのグループのどちらかを含むカスタム RBAC の役割のメンバーである必要があります。 このコマンドレットが割り当てられているすべての RBAC の役割 (自身が作成したカスタムの RBAC の役割を含む) の一覧を戻す場合は、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>集中ログ サービスを使用して基本的な検索を実行するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
2. AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。 検索結果をファイルに保存する場合は、-OutputFilePath を使用します  _\<string fully qualified file path\>_ 。 -OutputFilePath パラメーターを定義するには、パラメーターの一部としてパスとファイル名を引用符で囲まれた文字列形式で指定します (例: C:\LogFiles\SearchOutput.txt)。 この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。 出力は追加され、上書きはされません。 個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。 
  
次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>集中ログ サービスを使用してプールまたはコンピューターで基本検索を実行するには

1. 検索を特定のプールまたはコンピューターに限定するには、-Computers パラメーターを使用し、コンピューターの完全修飾名で定義されたコンピューターを引用符で囲み、コンマで区切ります。
    
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

3. 1 台のコンピューターではなくプール全体を検索する必要がある場合は、-Computers パラメーターを -Pools に変更し、コンピューター名を削除して、コンマで区切られた二重引用符で囲まれたプールまたはプールに置き換える必要があります。
    
    例:
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 検索コマンドを使用する場合、プールは、フロント エンド プール、エッジ プール、常設チャット サーバー プールなど、展開内の任意のプールにできます。
    
    次に例を示します。
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>時間のパラメーターを使用して検索を実行するには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
2. 既定では、検索の時間固有のパラメーターの開始時刻は、検索を開始した 5 分前の 25 分前です。 つまり、午後 4:00:00 に検索すると、検索の開始時刻は午後 3:35:00 から午後 4:05:00 と表示されます。 現在の時刻より 60 分または 3 時間前に検索する必要がある場合は、-StartTime パラメーターを使用して、検索を開始する時刻を示す日付と時刻の文字列を設定します。 
    
    たとえば、-StartTime と -EndTime を使用して時間と日付の範囲を定義すると、プールで 2012 年 11 月 20 日の午前 8 時から午前 9 時までの検索を定義できます。 次に示すように、出力パスを設定して、c:\logfile.txt という名前のファイルに結果を書き込むことができます。
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 指定する時刻と日付の文字列は、"date time" または "time date" です。 " コマンドは文字列を解析し、日付と時刻の適切な値と、コマンドレットを実行しているコンピューター上のロケールとカルチャの設定を使用します。 
  
3. 2012 年 11 月 20 日の午前 11:00:00 からログを取得する場合は、-StartTime を定義します。 特定の -EndTime を定義しない限り、検索の既定の時間範囲は 30 分です。 検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。
    
次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 特定の時間内にログの検索を実行するには、-StartTime と -EndTime を定義します。 コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。 
    
次に例を示します。
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>他の条件および一致オプションを使用して高度な検索を行うには

1. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
2. 特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

次に例を示します。
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。
    
3. 同じコンポーネントを持つ検索を、同じ名前のフロントエンド プールに限定するには、次pool01.contoso.net入力します。
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。 この動作は **、-MatchAll** パラメーターを指定することで変更できます。 これを行うには、次のように入力します。
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>集中ログ サービスからキャプチャ ログを読み取る

検索を実行し、報告された問題の追跡に使用できるファイルを作成すると、集中ログ サービスの真のメリットを実感できます。 ファイルを読み取る方法は複数あります。 出力ファイルは標準のテキスト形式で、Notepad.exe またはテキスト ファイルを開いて読み取りできる他のプログラムを使用できます。 ファイルのサイズが大きく、問題が複雑な場合は、集中ログ サービスからのログ出力を読み取って解析するように設計された Snooper.exe などのツールを使用できます。 Snooper は、個別のダウンロードとして利用できるデバッグ ツールに含まれています。 デバッグ ツールは、次の場所からダウンロードできます [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) 。 デバッグ ツールをインストールすると、ショートカットとメニュー項目は作成されません。 デバッグ ツールをインストールした後、エクスプローラー、コマンド ライン ウィンドウ、または Skype for Business Server 管理シェルを開き、ディレクトリ (既定の場所) C:\Program Files\Skype for Business Server 2015\Debugging Tools に移動します。 コマンド ラインSnooper.exe Skype for Business Server 管理シェルを使用している場合は、Snooper.exeをダブルクリックするか、「Snooper.exe」と入力し、Enter キーを押します。
  
> [!IMPORTANT]
> このトピックの目的は、トラブルシューティングの手法を詳細に説明したり議論したりすることではありません。 トラブルシューティングとそれに関連するプロセスは、複雑な問題です。 基本的なトラブルシューティングと特定のワークロードのトラブルシューティングの詳細については、Microsoft Lync Server 2010 リソース キットのブックを参照してください [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) 。 プロセスと手順は引き続き Skype for Business Server 2015 に適用されます。 
  
### <a name="to-open-a-log-file-in-snooper"></a>Snooper でログ ファイルを開くには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。 
    
2. デバッグ ツール (LyncDebugTools.msi) のインストール後、エクスプローラーまたはコマンド ラインを使用して、Snooper.exe の場所にディレクトリを変更します。 既定では、デバッグ ツールは C:\Program Files\Skype for Business Server 2015\Debugging Tools にあります。 Snooper.exe をダブルクリックするか、実行します。
    
3. Snooper を開いたら、[**ファイル**] を右クリックして [**OpenFile**] をクリックします。ログ ファイルを探し、[**開く**] ダイアログ ボックスでファイルを選択して [**開く**] をクリックします。
    
4. ログ ファイルのトレース メッセージ **が** [トレース] タブに **表示** されます。収集された **トレースの** メッセージ コンテンツを表示するには、[メッセージ] タブをクリックします。
    
### <a name="to-display-a-call-flow-diagram"></a>通話フロー図を表示するには

1. Snooper を使用してログ ファイルを開くためには、ログ ファイルへの読み取りアクセス権が必要です。Snooper を使用してログ ファイルにアクセスするためには、役割ベースのアクセス制御 (RBAC) のセキュリティ グループである CsAdministrator または CsServerAdministrator のメンバーであるか、これらの 2 グループのいずれかを含むカスタムの RBAC の役割のメンバーである必要があります。
    
2. ログ ファイルを開いて [**メッセージ**] タブをクリックし、メッセージ ビューで会話を選択するか、[**トレース**] タブでトレース コンポーネントを選択します。
    
3. [**通話フロー**] をクリックします。
    
> [!NOTE]
> 通話フローの一部ではないメッセージまたはトレースをクリックすると、図は表示されません。Snooper の下部に"This message is not eligible for callfow" というステータス メッセージが表示されます。 別のメッセージまたはトレースを選択すると、そのメッセージまたはトレースが通話フローに含まれている場合は通話フローが表示されます。 
  
4. メッセージ間またはトレース線を移動して、通話フロー図が更新されるか変化して、新しい図が表示されるかどうかに注目してください。
    
5. 要素にマウスをポイントすると、通話メッセージ、エンドポイント、その他のコンポーネントに関する情報を表示されます。
