---
title: 'Lync Server 2013: キューの作成または変更'
TOCTitle: キューの作成または変更
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48273408
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのキューの作成または変更

 

_**トピックの最終更新日:** 2013-02-23_

キューを作成または変更するには、以下のいずれかの手順を使用します。

## Lync Server コントロール パネルを使用してキューを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    > [!NOTE]
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。


2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[ **応答グループ** \] をクリックし、\[ **キュー** \] をクリックします。

4.  \[ **キュー** \] ページで、次のいずれかの操作を実行します。
    
      - 新しいキューを作成するには、\[ **新規作成** \] をクリックします。\[ **サービスの選択** \] の検索フィールドに、キューを追加する **ApplicationServer** サービスの名前の一部またはすべてを入力します。表示されたサービスの一覧で、目的のサービスをクリックし、\[ **OK** \] をクリックします。
    
      - 既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、\[ **編集** \]、\[ **詳細の表示** \] の順にクリックします。

5.  \[ **名前** \] にキューの識別名を入力します。

6.  \[ **説明** \] に、キューの説明を入力します。

7.  \[ **グループ** \] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。
    
      - \[ **グループの選択** \] の検索フィールドに、キューに割り当てるエージェント グループの名前または名前の一部を入力します。 In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.
    
      - キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、\[ **削除** \] をクリックします。
    
      - エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。
        
        > [!NOTE]  
        > サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。


8.  エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、\[ **キューのタイムアウトを有効にする** \] チェック ボックスをオンにして次の操作を実行します。
    
    1.  \[ **タイムアウト時間 (秒)** \] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。
    
    2.  \[ **通話アクション** \] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。
    
    <!-- end list -->
    
      - タイムアウト後通話を終了するには、\[ **切断** \] をクリックします。
    
      - ボイス メールに通話を転送する場合は \[ **ボイス メールに転送** \] をクリックし、\[ **SIP アドレス** \] フィールドにボイス メール アドレスを入力します。形式は、sip: *\<ユーザー名\>* @ *\<ドメイン名\>* です (例: sip:bob@contoso.com)。
    
      - 別の電話番号に通話を転送する場合は \[ **電話番号に転送** \] をクリックし、\[ **SIP アドレス** \] フィールドに電話番号を入力します。形式は、sip: *\<番号\>* @ *\<ドメイン名\>* です (例: sip:+14255550121@contoso.com)。
    
      - 別のユーザーに通話を転送する場合は \[ **SIP アドレスに転送** \] をクリックし、\[ **SIP アドレス** \] フィールドにそのユーザーの URI を入力します。形式は、sip: *\<ユーザー名\>* @ *\<ドメイン名\>* です。
    
      - 別のキューに通話を転送する場合は \[ **別のキューに転送** \] をクリックし、使用するキューを参照します。

9.  キューに保持できる最大通話数を指定するには、\[ **キューのオーバーフローを有効にする** \] チェック ボックスをオンにして次の操作を実行します。
    
    1.  \[ **最大通話数** \] で、キューで保持する最大通話数を選択します。
    
    2.  \[ **通話の転送** \] で、キューが一杯になったときに転送する通話を、\[ **最新の通話** \] または \[ **最も古い通話** \] から選択します。
    
    3.  \[ **通話アクション** \] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。
    
    <!-- end list -->
    
      - タイムアウト後通話を終了するには、\[ **切断** \] をクリックします。
    
      - ボイス メールに通話を転送する場合は \[ **ボイス メールに転送** \] をクリックし、\[ **SIP アドレス** \] フィールドにボイス メール アドレスを入力します。形式は、sip: *\<ユーザー名\>* @ *\<ドメイン名\>* です (例: sip:bob@contoso.com)。
    
      - 別の電話番号に通話を転送する場合は \[ **電話番号に転送** \] をクリックし、\[ **SIP アドレス** \] フィールドに電話番号を入力します。形式は、sip: *\<番号\>* @ *\<ドメイン名\>* です (例: sip:+14255550121@contoso.com)。
    
      - 別のユーザーに通話を転送する場合は \[ **SIP アドレスに転送** \] をクリックし、\[ **SIP アドレス** \] フィールドにそのユーザーの URI を入力します。形式は、sip: *\<ユーザー名\>* @ *\<ドメイン名\>* です。
    
      - 別のキューに通話を転送する場合は \[ **別のキューに転送** \] をクリックし、使用するキューを参照します。

10. \[ **確定** \] をクリックします。

## Windows PowerShellを使用してキューを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    > [!NOTE]
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。


2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    次に例を示します。
    
        "All agents are currently busy. Please call back later."
    
    > [!NOTE]
    > プロンプトにオーディオ ファイルを使用するには、 <strong>Import-CsRgsAudioFile</strong> コマンドレットを使用します。詳細については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>」を参照してください。


4.  キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    > [!NOTE]
    > 使用可能なアクションとその構文の詳細については、「 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>」を参照してください。
    
    次に例を示します。
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    次に例を示します。
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    > [!NOTE]
    > プロンプトにオーディオ ファイルを使用するには、 <strong>Import-CsRgsAudioFile</strong> コマンドレットを使用します。詳細については、「 <a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>」を参照してください。


6.  キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    > [!NOTE]
    > 使用可能なアクションとその構文の詳細については、「 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</a>」を参照してください。
    
    次に例を示します。
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  キューに割り当てるエージェント グループの Identity を取得します。コマンド ラインで、次のコマンドを実行します。
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    > [!NOTE]
    > エージェント グループの作成の詳細については、「 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</a>」を参照してください。


9.  キューを作成します。コマンド ラインで、次のコマンドを実行します。
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    次に例を示します。
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. キューが作成されたことを確認します。次のコマンドレットを実行します。
    
        Get-CsRgsQueue -Name "Help Desk"

## 関連項目

#### その他のリソース

[New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsQueue)

