---
title: 'Lync Server 2013: ハント グループ ワークフローの作成または変更'
TOCTitle: ハント グループ ワークフローの作成または変更
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48273838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのハント グループ ワークフローの作成または変更

 

_**トピックの最終更新日:** 2013-09-11_

次のいずれかの手順を使用して、ハント グループ ワークフローを作成または変更します。

> [!NOTE]
> Lync Server 管理シェルまたは 応答グループ構成ツールを使用して、ハント グループ ワークフローを作成および変更できます。 Lync Server コントロール パネルから 応答グループ構成ツールにアクセスするか、次の URL を入力して Web ブラウザーから Web ページを直接開くことができます。 <strong>https://</strong> <em>&lt;webPoolFqdn&gt;</em> <strong>/RgsConfig</strong>


## 応答グループ構成ツール を使用して、ハント グループ ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**応答グループ**\] をクリックし、\[**ワークフロー**\] をクリックします。

4.  \[**ワークフロー**\] ページで、\[**ワークフローの作成または編集**\] をクリックします。

5.  \[**サービスの選択**\] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前または名前の一部を入力します。表示されたサービスの一覧で、目的のサービスをクリックし、\[**OK**\] をクリックします。
    
    > [!NOTE]
    > 応答グループ構成ツールが開きます。次の URL を入力して、Web ブラウザーから 応答グループ構成ツールを直接開くこともできます。 <strong>https://</strong> <em>&lt;webPoolFqdn&gt;</em> <strong>/RgsConfig</strong>


6.  次のいずれかの操作を行います。
    
      - \[**新規ワークフローの作成**\] で、\[**ハント グループ**\] の横にある \[作成\] をクリックします。
    
      - \[**既存ワークフローの管理**\] で変更するワークフローを見つけて、\[**アクション**\] の \[**編集**\] をクリックします。

7.  ユーザーがワークフローへの通話を開始する準備ができている場合は、\[**ワークフローのアクティブ化**\] を選択します。
    
    > [!NOTE]
    > 管理ワークフローを作成する場合は、[<strong>ワークフローのアクティブ化</strong>] を選択する必要があります。アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。


8.  フェデレーション ユーザーにグループへの通話を許可するには、\[**フェデレーションを有効にする**\] チェック ボックスをオンにします。また、フェデレーション用に構成されている 応答グループ アプリケーションに適用される外部アクセス ポリシーを保持する必要があります。
    
    > [!NOTE]
    > グローバル外部アクセス ポリシーは、 応答グループ アプリケーションに適用されます。 Lync Server コントロール パネルを使用するか、 <strong>Set-CsExternalAccessPolicy</strong> コマンドレットを使用して、EnableOutsideAccess パラメーターを True に設定することにより、応答グループ フェデレーション用のグローバル ポリシーを構成することができます。グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。ポリシーをユーザーに適用する方法の詳細については、「<a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 での組織の外部アクセス ポリシーの管理</a>」を参照してください。フェデレーション設定の詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</a>」を参照してください。
    
    > [!NOTE]
    > Lync Online でホストされているユーザーは、社内展開でホストされている応答グループに通話を発信できません。これは、ハイブリッド展開でも、社内展開が Lync Online 展開とフェデレーションされている場合でも同じです。


9.  通話中、エージェントの ID を非表示にするには、\[**エージェントの匿名性を有効にする**\] チェック ボックスをオンにします。
    
    > [!NOTE]
    > 匿名の通話は、インスタント メッセージング (IM) やビデオから開始することはできません。ただし、通話の確立後、エージェントまたは発信者が IM やビデオを追加することはできます。匿名のエージェントは、通話の保留、通話の転送 (無条件転送と取次転送)、および通話の保留と保留解除を行うこともできます。匿名の通話では、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータのグループ作業、および通話の記録はサポートされません。Lync VDI プラグインを使用するエージェントは、着信通話を匿名で受信できますが、発信通話を匿名で行うことはできません。


10. \[**通話を受けるグループのアドレスを入力します**\] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。
    
    > [!NOTE]
    > ワークフローのプライマリ URI は、ワークフローをどのように識別および参照するかを表します。入力した SIP URI は、連絡先オブジェクトとして Active Directory ドメイン サービス に作成されます。URI を作成するには、オブジェクトが Active Directory 内で一意である必要があります。


11. ワークフローで表示する名前を \[**表示名**\] に入力します (例: 販売 応答グループ)。
    
    > [!NOTE]
    > 表示名に「&lt;」または「&gt;」という文字を含めないでください。次の表示名は予約されているため、使用しないでください。 <strong>RGS Presence Watcher</strong> または <strong>Announcement Service</strong>。


12. \[**電話番号**\] に、応答グループの回線 URI を入力します (入力例 +14255550165)。

13. \[**表示番号**\] に、応答グループを表示する番号を入力します (入力例 +1 (425) 555-0165)。

14. (オプション) \[**説明**\] に、 Lync クライアントの連絡先カードに表示するワークフローの説明を入力します。

15. このワークフローを応答グループのマネージャーが管理する場合は、\[**ワークフローの種類**\] で \[**管理**\] を選択します。ワークフローを 応答グループのマネージャーに割り当てるには、次の操作を実行します。
    
    1.  このワークフローのマネージャーの SIP URI を入力して、\[**追加**\] をクリックします。
    
    2.  ワークフローに追加するマネージャーの SIP URI を入力して、\[**追加**\] をクリックします。
    

    > [!IMPORTANT]
    > 応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。



16. \[**ステップ 2 言語の選択**\] で、音声認識と音声合成で使用する言語をクリックします。

17. 開始メッセージを構成する場合は、\[**ステップ 3 開始メッセージの構成**\] で \[**開始メッセージを再生する**\] チェック ボックスをオンにして、次のいずれかの操作を行います。
    
      - 発信者用の音声に変換される開始メッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスに開始メッセージを入力します。
        
        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。
    
      - 開始メッセージに Wave (.wav) または Windows Media オーディオ (.wma) ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するオーディオ ファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。


18. \[**ステップ 4 営業時間の指定**\] の \[**タイム ゾーン**\] で、ワークフローのタイム ゾーンをクリックします。
    
    > [!NOTE]
    > このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。これを使用して、始業時間と終業時間が計算されます。たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が午後 11:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります (時間は 24 時間表記で入力する必要があります)。


19. 次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。
    
      - 事前に定義した営業時間スケジュールを使用するには、\[**事前設定したスケジュールを使用する**\] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。
        
        > [!NOTE]  
        > このオプションを選択できるようにするには、あらかじめ少なくとも 1 つの事前設定スケジュールを定義しておく必要があります。 <strong>New-CSRgsHoursOfBusiness</strong> コマンドレットを使用して事前設定スケジュールを定義します。詳細については、「<a href="lync-server-2013-optional-define-response-group-business-hours.md">(オプション) Lync Server 2013 での応答グループの営業時間の定義</a>」を参照してください。
        
        > [!NOTE]  
        > 事前設定したスケジュールを選択すると、応答グループの対応日時で、[<strong>曜日</strong>]、[<strong>始業</strong>]、[<strong>終業</strong>] が自動的に設定されます。
    
      - このワークフローのみに適用するカスタム スケジュールを使用するには、\[**カスタム スケジュールを使用する**\] をクリックします。

20. このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。

21. カスタム スケジュールを作成する場合は、応答グループが対応可能な各曜日の \[**始業**\] 時間と \[**終業**\] 時間を入力します。
    
    > [!NOTE]
    > [<strong>始業</strong>] 時間と [<strong>終業</strong>] 時間は 24 時間表記で入力する必要があります。たとえば、職場の営業時間が営業日の 9 ～ 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [<strong>始業</strong>] 9:00、[<strong>終業</strong>] 12:00、[<strong>始業</strong>] 13:00、[<strong>終業</strong>] 17:00 として指定します。


22. 営業時間外にメッセージを再生するには、\[**応答グループの営業時間外にメッセージを再生する**\] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスにメッセージを入力します。
        
        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。
    
      - メッセージにオーディオ ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。


23. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、\[**終話**\] をクリックします。
    
      - 通話をボイス メールに転送するには、\[**ボイス メールに転送**\] をクリックして、ボイス メール アドレスを入力します。ボイス メール アドレスの形式は *\<user name\>*@ *\<domain name\>* (例: bob@contoso.com) です。
    
      - 通話を別のユーザーに転送するには、\[**SIP URI に転送**\] をクリックして、ユーザー アドレスを入力します。ユーザー アドレスの形式は *\<user name\>*@ *\<domain name\>* です。
    
      - 通話を別の電話番号に転送するには、\[**電話番号に転送**\] をクリックして、電話番号を入力します。電話番号の形式は *\<number\>*@ *\<domain name\>* (例: +14255550121@contoso.com) です。発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

24. \[**ステップ 5 休日の指定**\] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。
    
    > [!NOTE]
    > ワークフローを構成する前に、休日および休日セットを定義する必要があります。休日および休日セットを定義するには、 <strong>New-CsRgsHoliday</strong> コマンドレットおよび <strong>New-CsRgsHolidaySet</strong> コマンドレットを使用します。詳細については、「<a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(オプション) 応答グループ休日セットの定義</a>」を参照してください。


25. 休日にメッセージを再生するには、\[**休日にメッセージを再生する**\] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスにメッセージを入力します。
        
        > [!NOTE]  
        > 入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。
    
      - メッセージにオーディオ ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        > [!NOTE]  
        > ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。


26. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、\[**終話**\] をクリックします。
    
      - 通話をボイス メールに転送するには、\[**ボイス メールに転送**\] をクリックして、ボイス メール アドレスを入力します。ボイス メール アドレスの形式は *\<user name\>*@ *\<domain name\>* (例: bob@contoso.com) です。
    
      - 通話を別のユーザーに転送するには、\[**SIP URI に転送**\] をクリックして、ユーザー アドレスを入力します。ユーザー アドレスの形式は *\<user name\>*@ *\<domain name\>* です。
    
      - 通話を別の電話番号に転送するには、\[**電話番号に転送**\] をクリックして、電話番号を入力します。電話番号の形式は *\<number\>*@ *\<domain name\>* (例: +14255550121@contoso.com) です。発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

27. \[**ステップ 6 キューの構成**\] の \[**通話を受け取るキューを選択します**\] で、エージェントが応答可能になるまで発信者を保留するキューを選択します。

28. \[**ステップ 7 保留音の構成**\] で次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。
    
      - 既定の保留音の録音を使用するには、\[**既定値を使用する**\] をクリックします。
    
      - 保留音にオーディオ ファイルの録音を使用するには、\[**音楽ファイルを選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**音楽ファイル**\] リンクをクリックします。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        > [!NOTE]  
        > ユーザーが指定するすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。


29. \[**展開**\] をクリックします。

## Windows PowerShell を使用して、ハント グループ ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  開始メッセージで再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    次に例を示します。
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    > [!NOTE]
    > プロンプトにオーディオ ファイルを使用するには、 <strong>Import-CsRgsAudioFile</strong> コマンドレットを使用します。詳細については、「<a href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</a>」を参照してください。


4.  通話が転送されることになるキューまたは質問の ID を取得します。コマンド ラインで、次のコマンドを実行します。
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    キューの作成に関する詳細については、「[New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue)」を参照してください。

5.  営業時間中にワークフローを開いたときに実行される既定のアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    > [!NOTE]
    > ハント グループ ワークフローでは、既定のアクションにより通話がキューに転送される必要があります。アクティブなワークフローでは、このパラメーターが必要です。非アクティブなワークフローでは不要です。
    
    次に例を示します。
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  営業時間と休日を定義する場合は、ワークフローを作成または変更する前に、営業時間と休日を作成する必要があります。詳細については、「[(オプション) Lync Server 2013 での応答グループの営業時間の定義](lync-server-2013-optional-define-response-group-business-hours.md)」および「[(オプション) 応答グループ休日セットの定義](lync-server-2013-optional-define-response-group-holiday-sets.md)」を参照してください。

7.  営業時間外または休日に受信する通話用のプロンプトを保持する場合は、 **New-CsRgsPrompt** コマンドレットを使用してプロンプトを定義し、 **New-CsRgsCallAction** を使用して、プロンプトの後に実行するアクションを定義します。詳細については、「[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)」および「[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)」を参照してください。

8.  Lync Server 応答グループ サービスのサービス名を取得して変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  ワークフローを作成または変更します。ワークフローを作成するには、 **New-CsRgsWorkflow** を使用します。ワークフローを変更するには、 **Set-CsRgsWorkflow** を使用します。コマンドラインで、次のように入力します。
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    次に例を示します。
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    

    > [!IMPORTANT]
    > ワークフローのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。

    
    > [!NOTE]
    > オプションの追加パラメーターの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</a>」または「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</a>」を参照してください。


## 関連項目

#### タスク

[(オプション) 応答グループ休日セットの定義](lync-server-2013-optional-define-response-group-holiday-sets.md)  

#### 概念

[(オプション) Lync Server 2013 での応答グループの営業時間の定義](lync-server-2013-optional-define-response-group-business-hours.md)  

#### その他のリソース

[New-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)

