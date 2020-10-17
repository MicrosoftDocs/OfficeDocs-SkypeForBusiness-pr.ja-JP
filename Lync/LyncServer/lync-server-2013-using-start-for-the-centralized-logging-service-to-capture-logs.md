---
title: 集中ログサービスの Start を使用してログをキャプチャする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f43a2c86dcbd88f8e9af4ae54f302b4abc943fc0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529974"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Lync Server 2013 でログをキャプチャするための集中ログサービスの Start の使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

集中ログサービスを使用してトレースログをキャプチャするには、1つ以上のコンピューターおよびプールでログ記録を開始するコマンドを発行します。 また、どのコンピューターまたはプールを実行するか、どのシナリオ (たとえば、AlwaysOn、別の定義済みのシナリオ、または作成したシナリオ)、どの Lync Server コンポーネント (たとえば、S4、SipStack) をトレースするかを定義するパラメーターを発行します。

適切な情報を取得するには、適切なシナリオを使用して、問題に関連する情報を収集する必要があります。 集中ログサービスでは、1つのシナリオとして、サーバーコンポーネント、ログレベル、およびフラグの集合に基づいてログをオンにする概念があります。これは、サーバーごとにこれらの要素を定義するよりも効率的で便利です。 実行するシナリオを定義して指定し、インフラストラクチャの範囲内のすべてのサーバーとプールでシナリオが一貫して実行されるようにします。

既定のシナリオは、**AlwaysOn** です。AlwaysOn シナリオのねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。

集中ログサービスは、2つのコマンドを発行する方法を提供します。 Lync Server 管理シェルを使用して Windows PowerShell を使用することに重点を squarely ているトピックがいくつかあります。 複数の複雑な構成とコマンドを使用する機能により、集中ログサービスを使用するために Windows PowerShell が採用されています。 Lync server 管理シェルを使用した Windows PowerShell は、Lync Server のすべての機能についてほぼ広く普及しているため、Windows PowerShell コマンドのみについて説明しています。

<div>


> [!NOTE]
> コマンドラインから使用できる制限付きのコマンドセットを使用する場合は、「」と入力することによって CLSController.exe に関するヘルプが表示され <CODE>ClsController.exe</CODE> ます。 既定では、 <STRONG>ClsController.exe</STRONG> がインストールされているディレクトリは C:\Program C:\Program Lync Server 2013 \ clsagent です。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>基本的なコマンドを使用して Windows PowerShell で Start-CsClsLogging を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のように入力して、集中ログサービスでログシナリオを開始します。
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn シナリオには、既定の実行期間がありません。 このシナリオの実行は、<STRONG>Stop-CsClsLogging</STRONG> コマンドレットによって明示的に停止されるまで続きます。 詳細については、「<A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>」を参照してください。 その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。

    
    </div>

3.  Enter キーを押して、コマンドを実行します。
    
    <div>
    

    > [!NOTE]
    > このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。

    
    </div>
    
    ![Start-CsClsLogging を実行しています。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Start-CsClsLogging を実行しています。")

4.  別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。 コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。 3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。 グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。 実行されているシナリオの管理の詳細については、「 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Lync Server 2013 での集中ログサービスの stop の使用</A> 」および「 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-csclslogging</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>詳細なコマンドを使用して Windows PowerShell で Start-CsClsLogging を実行するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  追加のパラメーターを使用して、このログ記録コマンドを管理できます。 シナリオの実行期間を調整するには、–Duration を使用します。 また、–Computers や–Pools を使用して、ログを有効にするコンピューターやプールの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを定義することもできます。
    
    プール "pool01.contoso.net" に対して *Userreplicator* シナリオのログセッションを開始します。 また、このログ セッションの期間を 8 時間に指定します。 この場合、次のように入力します。
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    このシナリオが正常に実行されると、次のような結果が返されます。
    
    ![Start-CsClsLogging を実行しています。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Start-CsClsLogging を実行しています。")
    
    この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

