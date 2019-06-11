---
title: 一元的なログサービスのために Start を使用してログをキャプチャする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

一元ログサービスを使ってトレースログをキャプチャするには、1つ以上のコンピューターとプールでログの記録を開始するコマンドを実行します。 また、どのコンピューターまたはプール、実行するシナリオ (AlwaysOn、別の定義済みシナリオ、作成したシナリオ)、どの Lync Server コンポーネント (S4、SipStack など) を追跡するかを定義するパラメーターを発行することもできます。

適切な情報を取得するには、適切なシナリオを使用して、問題に関連する情報を収集していることを確認する必要があります。 一元化されたログサービスでは、サーバーコンポーネント、ログレベル、フラグなどのコレクションに基づいてログ記録を有効にするという概念があります。これは、サーバーごとにこれらの要素を定義するよりも効率的で便利です。 実行するシナリオを定義して指定すると、インフラストラクチャの範囲内のすべてのサーバーとプールでシナリオが一貫して実行されます。

既定のシナリオは、**AlwaysOn** です。AlwaysOn のねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。

中央集中ログサービスでは、2つの方法でコマンドを発行できます。 Lync Server 管理シェルを介して Windows PowerShell を使用することに正方形て、いくつかのトピックを重点的に説明しました。 多数の複雑な構成とコマンドを使う機能は、Windows PowerShell を使用して一元的なログサービスを使うことができます。 Lync Server 管理シェル経由での Windows PowerShell は、Lync Server のすべての機能に対して広く普及しているため、Windows PowerShell コマンドのみについて説明します。

<div>


> [!NOTE]
> コマンドラインから利用できる限定的なコマンドセットを使用する場合は、「」と入力<CODE>ClsController.exe</CODE>して、clscontroller に関するヘルプを表示することができます。 既定では、 <STRONG>Clscontroller</STRONG>がディレクトリ C:\Program の Lync Server 2013 \ clscontroller にインストールされています。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>基本的なコマンドを使用して Windows PowerShell で CsClsLogging を実行するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のように入力して、集中化されたログサービスでログシナリオを開始します。
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。 このシナリオの実行は、<STRONG>Stop-CsClsLogging</STRONG> コマンドレットによって明示的に停止するまで続きます。 詳細については、「<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>」を参照してください。 その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。

    
    </div>

3.  Enter キーを押して、コマンドを実行します。
    
    <div>
    

    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。

    
    </div>
    
    ![開始-CsClsLogging を実行しています。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "開始-CsClsLogging を実行しています。")

4.  別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。 コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。 3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。 グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。 実行されているシナリオを管理する方法の詳細については、「 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Lync Server 2013 の集中ログサービスで Stop を使用する</A>」および「 <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">csclslogging</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>詳細なコマンドを使用して、Windows PowerShell での Start CsClsLogging を実行するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  追加のパラメーターを使用して、このログ記録コマンドを管理できます。シナリオの実行期間を調整するには、-Duration を使用します。また、-Computers や -Pools を使用して、ログを有効にするコンピューターやプールの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを定義することもできます。
    
    *UserReplicator* というシナリオによるログ セッションをプール “pool01.contoso.net” で開始するとします。 また、このログ セッションの期間を 8 時間に指定します。 この場合、次のように入力します。
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    このシナリオが正常に実行されると、次のような結果が返されます。
    
    ![開始-CsClsLogging を実行しています。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "開始-CsClsLogging を実行しています。")
    
    この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の一元管理されたログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

