---
title: 集中ログ サービスが作成したキャプチャ ログ検索の使用
TOCTitle: 集中ログ サービスが作成したキャプチャ ログ検索の使用
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49886861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービスが作成したキャプチャ ログ検索の使用

 

_**トピックの最終更新日:** 2013-02-21_

集中ログ サービス の検索機能は、次に示す理由で、便利かつ強力だといえます。

  - 検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。

  - 広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。検索は同じログに対して行われるため、検索条件を変更したときにログ セッションを再実行する必要はありません。

  - 検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。

個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューター当たり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。

各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。

集中ログ サービス を最大限に活用するには、調べている問題に関係するコンピューターとプールからのトレース メッセージのみを返すように、検索を構成する方法を理解している必要があります。

Lync Server 管理シェルを使用して 集中ログ サービス の検索機能を実行するには、CsAdministrator または CsServerAdministrator 役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーであるか、この 2 つのグループのどちらかが含まれるカスタムの RBAC の役割である必要があります。このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。

## 集中ログ サービス を使用して基本的な検索を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    > [!NOTE]
    > 既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。検索結果をファイルに保存する場合は、–OutputFilePath &lt;完全修飾ファイル パス文字列&gt; を使用します。–OutputFilePath パラメーターを定義するには、パラメーターにパスとファイル名を文字列形式で指定し、引用符で囲みます (たとえば、C:\LogFiles\SearchOutput.txt)。この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。出力は追加され、上書きはされません。個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。
    
    次に例を示します。
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

## 集中ログ サービス を使用してプールまたはコンピューターで基本的な検索を行うには

1.  検索を特定のプールまたはコンピューターに限定するには、–Computers パラメーターを使用し、コンピューターの完全修飾名で定義されるコンピューターを引用符で囲み、コンマで区切って指定します。
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    次に例を示します。
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  1 台のコンピューターではなくプール全体を検索する必要がある場合は、–Computers パラメーターを –Pools に変更し、コンピューター名を削除して、1 つまたは複数のプールに置き換えます。各プールは引用符で囲み、コンマで区切ります。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  検索コマンドを使用するとき、プールは、フロント エンド プール、エッジ プール、常設チャット サーバー プールなど、展開内でプールとして定義されている任意のプールを指定できます。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

## 時間のパラメーターを使用して検索を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  既定では、検索の時間固有のパラメーターの開始時間は、検索を開始する時間の 30 分前です。つまり、検索を 4:00:00 PM に開始する場合、定義するコンピューターおよびプールのログは 3:30:00 PM から 4:00:00 PM まで検索されます。現在の時刻より 60 分または 3 時間前を検索する必要がある場合は、–StartTime パラメーターを使用して、検索を開始する時間を表す日時文字列を設定します。
    
    たとえば、–StartTime および –EndTime を使用して日時の範囲を定義することにより、11/20/2012 8 AM ～ 9 AM の間のプールでの検索を定義できます。次に示すように、出力パスを設定して、c:\\logfile.txt という名前のファイルに結果を書き込むことができます。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    > [!NOTE]
    > 日時の文字列は、&quot;日付 時間&quot; と&quot;時間 日付&quot; のどちらででも指定できます。コマンドの解析により、日付と時間に適した値が使用されます。


3.  11/20/2012 11:00:00 AM から始まるログを取得するには、–StartTime を定義します。既定の検索時間は、特定の –EndTime を定義しない限り、30 分です。検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  特定の時間内でログの検索を行うには、–StartTime および –EndTime を定義します。コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。
    
    次に例を示します。
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

## 他の条件および一致オプションを使用して高度な検索を行うには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    次に例を示します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。

3.  同じコンポーネントの検索を、pool01.contoso.net という名前のフロント エンド プールにのみ限定するには、次のように入力します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。この動作は、**–MatchAll** パラメーターを指定することで変更できます。これを行うには、次のように入力します。
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

