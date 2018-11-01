---
title: 集中ログ サービスの Start を使用したログのキャプチャー
TOCTitle: 集中ログ サービスの Start を使用したログのキャプチャー
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49886828
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービスの Start を使用したログのキャプチャー

 

_**トピックの最終更新日:** 2013-02-21_

集中ログ サービス を使用してトレース ログを取得するには、1 つ以上のコンピューターおよびプールでログの記録を開始するコマンドを実行します。また、コンピューターまたはプール、実行するシナリオ ("AlwaysOn" のような定義済みのシナリオ、または作成したシナリオ)、トレースする Lync Server コンポーネント (S4、SipStack など) を定義するパラメーターを指定します。

適切な情報を取得するには、問題に関連する情報を収集するための適切なシナリオを使用していることを確認する必要があります。集中ログ サービス では、サーバー コンポーネント、ログ レベル、およびフラグのコレクションに基づいてログ記録を有効にするという考え方のシナリオになっています。そのほうが、これらの要素をサーバーごとに定義する必要がある場合よりもずっと効率的で便利です。実行するシナリオを定義して指定すると、そのシナリオがインフラストラクチャのスコープ内にあるすべてのサーバーとプールで首尾一貫して実行されます。

既定のシナリオは、**AlwaysOn** です。AlwaysOn シナリオのねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。

集中ログ サービス には、コマンドを実行する方法が 2 つ用意されています。Lync Server 管理シェルから Windows PowerShell を使用する方法については、いくつかのトピックに明確な説明があります。集中ログ サービス を使用する場合には、複数の複雑な構成やコマンドを使用できる Windows PowerShell が適しています。Lync Server 管理シェルから Windows PowerShell を使用する方法は、Lync Server のあらゆる関数のあちこちに見られるので、ここでは Windows PowerShell コマンドについてのみ説明します。

> [!NOTE]
> コマンドラインから使用できる限られたコマンド セットを使用する場合は、「<code>ClsController.exe</code>」と入力すると、CLSController.exe に関するヘルプを参照できます。既定では、<strong>ClsController.exe</strong> のインストール先ディレクトリが C:\Program Files\Microsoft Lync Server 2013\ClsAgentになっています。


## 基本的なコマンドを使用して Windows PowerShell で Start-CsClsLogging を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドを入力して、集中ログ サービス によるログ記録シナリオを開始します。
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。このシナリオの実行は、<strong>Stop-CsClsLogging</strong> コマンドレットによって明示的に停止されるまで続きます。詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>」を参照してください。その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。


3.  Enter キーを押して、コマンドを実行します。
    
    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。
    
    ![Start-CsClsLogging の実行](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Start-CsClsLogging の実行")

4.  別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。
    
        Start-CsClsLogging -Scenario Authentication
    

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。実行中のシナリオの管理の詳細については、「<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">集中ログ サービスの Stop の使用</A>」と「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</A>」を参照してください。



## 高度なコマンドを使用して Windows PowerShell で Start-CsClsLogging を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  追加のパラメーターを使用して、このログ記録コマンドを管理できます。シナリオの実行期間を調整するには、–Duration を使用します。また、–Computers や –Pools を使用して、ログを有効にするコンピューターやプールの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを定義することもできます。
    
    UserReplicator というシナリオによるログ セッションをプール "pool01.contoso.net" で開始するとします。また、このログ セッションの期間を 8 時間に指定します。この場合、次のように入力します。
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    このシナリオが正常に実行されると、次のような結果が返されます。
    
    ![Start-CsClsLogging の実行](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Start-CsClsLogging の実行")
    
    この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。

## 関連項目

#### 概念

[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)

