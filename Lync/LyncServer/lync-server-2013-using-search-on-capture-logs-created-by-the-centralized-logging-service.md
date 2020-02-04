---
title: 一元管理サービスで作成されたキャプチャログでの検索の使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 の中央集中ログサービスで作成されたキャプチャログでの検索の使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

中央のログサービスの検索機能は、次のような理由で便利で強力です。

  - 検索と結果が、定義する条件に基づいて、1 台のコンピューター、プール、サイト、またはグローバル サイトで実行されます。

  - 広範囲での検索から始めて、時間、コンポーネント、コンピューターなど、検索の条件を絞り込むことができます。検索は同じログに対して行われるため、検索条件を変更したときにログ セッションを再実行する必要はありません。

  - 検索の結果は、スコープ内のすべてのコンピューターとプールから収集され、検索条件のすべての結果を表す 1 つの出力ファイルに集約されます (実行しているシナリオおよびシナリオによって取得されたデータに限定されます)。使い慣れた **Snooper**、**メモ帳**などのツールを使用して、出力ファイルおよび展開全体からのトレース メッセージを読み取ります。

個々の各コンピューター上の CLSAgent によって、1 つまたは複数のシナリオに基づいたログが作成されます (1 台のコンピューターあたり 2 つのシナリオをいつでも実行できます)。ログと関連するインデックス ファイルおよびキャッシュ ファイルは、CLSAgent によって管理されます。検索を定義して実行すると、その検索コマンドが CLSAgent に対して取得する情報を指示します。CLSAgent はログ ファイル、キャッシュ ファイル、およびインデックス ファイルに対してクエリを実行し、検索の結果を CLSContoller に返します。CLSController は、検索の範囲内のすべてのコンピューターおよびプールから、検索結果を受け取ります。次に、CLSController はログを集約 (結合) し、最も古いエントリが先頭で、最新のエントリが末尾になるように、時系列に配置します。

各検索の後、**Sync-CsClsLogging** コマンドレットが実行されて、検索で使用されるキャッシュ (CLSAgent が管理するキャッシュ ファイルで使用されるものではない) をフラッシュします。 キャッシュをフラッシュすることで、次の検索操作で CLSController はクリーンなログおよびトレース ファイルのキャプチャ バッファーを使用できます。

一元管理サービスを最大限に活用するには、検索の構成方法についてよく理解しておく必要があります。これは、コンピューターからのトレースメッセージだけを返し、調査中の問題に関連するプールログのみを返すようにするためです。 問題

Lync Server 管理シェルを使用して一元的なログサービスの検索機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、これら2つのグループのどちらかです。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧 (自分自身で作成したカスタム RBAC ロールを含む) を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの以降の部分では、トラブルシューティングを最適化するための検索の定義方法について説明します。

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>中央集中ログサービスを使用して基本的な検索を実行するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  AlwaysOn シナリオが展開内でグローバル スコープで実行していることを確認し、コマンド プロンプトで次のように入力します。
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > 既定では、Search-CsClsLogging は検索の結果をコンソールに送ります。 検索結果をファイルに保存する場合は、– OutputFilePath &lt;文字列の完全修飾ファイルパス&gt;を使用します。 -OutputFilePath パラメーターを定義するには、パラメーターにパスとファイル名を文字列形式で指定し、引用符で囲みます (たとえば、C:\LogFiles\SearchOutput.txt)。 この例では、ディレクトリ C:\LogFiles が存在し、フォルダー内のファイルに対して読み取りと書き込みのアクセス許可 (NTFS の場合は変更のアクセス許可) を持っている必要があります。 出力は追加され、上書きはされません。 個別のファイルが必要な場合は、検索ごとに個々のファイル名を定義します。

    
    </div>
    
    次に例を示します。
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>集中ログサービスを使用してプールまたはコンピューターで基本的な検索を実行するには

1.  検索を特定のプールまたはコンピューターに限定するには、-Computers パラメーターを使用し、コンピューターの完全修飾名で定義されるコンピューターを引用符で囲み、コンマで区切って指定します。
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    次に例を示します。
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  複数のコンピューターを検索するには、次に示すように、複数のコンピューター名をそれぞれ引用符で囲み、コンマで区切って入力します。
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  1 台のコンピューターではなくプール全体を検索する必要がある場合は、-Computers パラメーターを -Pools に変更し、コンピューター名を削除して、1 つまたは複数のプールに置き換えます。各プールは引用符で囲み、コンマで区切ります。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  検索コマンドを使用する場合、プールには、フロントエンドプール、エッジプール、常設チャットサーバープールなどの展開内の任意のプールを使うことができます。また、展開のプールとして定義されている他のプールにすることもできます。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>時間のパラメーターを使用して検索を実行するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  既定では、検索の時間固有のパラメーターの開始時刻は、検索を開始した時点から30分前になります。 つまり、4:00:00 PM で検索を開始すると、3:30:00 PM から 4:00:00 PM までに定義したコンピューターとプールのログが検索されます。 現在の時刻より 60 分または 3 時間前を検索する必要がある場合は、-StartTime パラメーターを使用して、検索を開始する時間を表す日時文字列を設定します。
    
    たとえば、-StartTime および -EndTime を使用して日時の範囲を定義することにより、2012/11/20 8 AM ～ 9 AM の間のプールでの検索を定義できます。 出力パスを設定して、次のように結果を c:\\logfile という名前のファイルに書き込むことができます。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > 日時の文字列は、"日付 時間" と"時間 日付" のどちらででも指定できます。 "コマンドは文字列を解析し、日付と時刻に適切な値を使用します。

    
    </div>

3.  2012/11/20 11:00:00 AM から始まるログを取得するには、-StartTime を定義します。既定の検索時間は、特定の -EndTime を定義しない限り、30 分です。検索の結果、定義したコンピューターまたはプールから、11:00:00 AM ～ 11:30:00 AM の範囲のログが返されます。
    
    次に例を示します。
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  特定の時間内でログの検索を行うには、-StartTime および -EndTime を定義します。コンピューター edge01.contoso.net における 1 PM から 2:45 PM までのログが必要です。
    
    次に例を示します。
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>他の条件および一致オプションを使用して高度な検索を行うには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  特定のコンポーネントのトレースを収集するコマンドを実行するには、次のように入力します。
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    次に例を示します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    検索の結果、過去 30 分の間に展開内のすべてのコンピューターおよびプールで、SIPStack、S4、および UserServices のトレース コンポーネントを持つすべてのログ エントリが返されます。

3.  同じコンポーネントを使用して、pool01.contoso.net という名前のフロントエンドプールに検索を限定するには、次のように入力します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  複数のパラメーターを使用するコマンドの既定の検索ロジックでは、定義された各パラメーターに対して論理 OR を使用します。この動作は、**-MatchAll** パラメーターを指定することで変更できます。これを行うには、次のように入力します。
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  AlwaysOn のように、シナリオが定期的に実行するように設定されている場合、または、長期にわたって実行するシナリオが定義されている場合、ログはローカル コンピューターではなくファイル共有に置かれることがあります。ファイル共有は、New-CsClsConfiguration で新しい構成を作成するとき、または Set-CsClsConfiguration で既存の構成を変更するときに、CacheFileNetworkFolder パラメーターを使用して定義します。検索のログ コレクションにファイル共有を含めない場合は、次に示すように、SkipNetworkLogs パラメーターを使用します。
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

