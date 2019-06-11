---
title: 'Lync Server 2013: キューを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Lync Server 2013 でキューを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

キューを作成または変更するには、以下のいずれかの手順を使用します。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Lync Server コントロールパネルを使用してキューを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    <div>
    

    > [!NOTE]  
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。

    
    </div>

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。

4.  [**キュー**] ページで、次のいずれかの操作を実行します。
    
      - 新しいキューを作成するには、[**新規作成**] をクリックします。 [**サービスの選択**] の検索フィールドに、キューを追加する **ApplicationServer** サービスの名前の一部またはすべてを入力します。 表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。
    
      - 既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**名前**] にキューの識別名を入力します。

6.  [**説明**] に、キューの説明を入力します。

7.  [**グループ**] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。
    
      - キューにグループを追加するには、[**選択**] をクリックします。[**グループの選択**] の検索フィールドに、キューに割り当てるエージェント グループの名前または名前の一部を入力し、一覧で目的のエージェント グループをクリックして、[**OK**] をクリックします。
    
      - キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、[**削除**] をクリックします。
    
      - エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。
        
        <div>
        

        > [!NOTE]  
        > サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。

        
        </div>

8.  エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、[**キューのタイムアウトを有効にする**] チェック ボックスをオンにして次の操作を実行します。
    
    1.  [**タイムアウト時間 (秒)**] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。
    
    2.  [**通話アクション**] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。
    
    <!-- end list -->
    
      - タイムアウト後通話を終了するには、[**切断**] をクリックします。
    
      - 通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**\<] フィールドに、「sip: username\>@\<domainname\> (sip:)」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。
    
      - 別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックして、[ **sip アドレス**] フィールドに電話番号を\<「\>@\<sip\> : 番号のドメイン名」という形式で入力します (例 sip:+14255550121@contoso.com)。
    
      - 通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip\<:\>@\<username\>domainname」という形式で入力します。
    
      - 別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。

9.  キューに保持できる最大通話数を指定するには、[**キューのオーバーフローを有効にする**] チェック ボックスをオンにして次の操作を実行します。
    
    1.  [**最大通話数**] で、キューで保持する最大通話数を選択します。
    
    2.  [**通話の転送**] で、キューが一杯になったときに転送する通話を、[**最新の通話**] または [**最も古い通話**] から選択します。
    
    3.  [**通話アクション**] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。
    
    <!-- end list -->
    
      - タイムアウト後通話を終了するには、[**切断**] をクリックします。
    
      - 通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**\<] フィールドに、「sip: username\>@\<domainname\> (sip:)」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。
    
      - 別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックして、[ **sip アドレス**] フィールドに電話番号を\<「\>@\<sip\> : 番号のドメイン名」という形式で入力します (例 sip:+14255550121@contoso.com)。
    
      - 通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip\<:\>@\<username\>domainname」という形式で入力します。
    
      - 別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。

10. [**確定**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Windows PowerShell を使用してキューを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    <div>
    

    > [!NOTE]  
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。

    
    </div>

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    次に例を示します。
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > プロンプトにオーディオ ファイルを使用するには、 <STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。 詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">インポート-CsRgsAudioFile</A>」を参照してください。

    
    </div>

4.  キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 可能なアクションとその構文の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新しい-CsRgsCallAction</A>」を参照してください。

    
    </div>
    
    次に例を示します。
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    次に例を示します。
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > プロンプトにオーディオ ファイルを使用するには、 <STRONG>Import-CsRgsAudioFile</STRONG> コマンドレットを使用します。 詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">インポート-CsRgsAudioFile</A>」を参照してください。

    
    </div>

6.  キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 可能なアクションとその構文の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新しい-CsRgsCallAction</A>」を参照してください。

    
    </div>
    
    次に例を示します。
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  キューに割り当てるエージェント グループの Identity を取得します。コマンド ラインで、次のコマンドを実行します。
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > エージェントグループの作成の詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">新しい-CsRgsAgentGroup</A> 」を参照してください。

    
    </div>

9.  キューを作成します。コマンド ラインで、次のコマンドを実行します。
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    例:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. キューが作成されたことを確認します。次のコマンドレットを実行します。
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>関連項目


[新規-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[新規-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[新規-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[インポート-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[削除-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

