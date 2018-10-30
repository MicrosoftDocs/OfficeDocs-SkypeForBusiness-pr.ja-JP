---
title: Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成
TOCTitle: Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48271168
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成

 

_**トピックの最終更新日:** 2016-12-08_

ここでは、エンタープライズ VoIP で使用する Exchange ユニファイド メッセージング (UM) を Microsoft Exchange Server 上で構成する方法を説明します。

> [!NOTE]
> このトピックのコマンドレット例では、Exchange 2007 バージョンの Exchange 管理シェルの構文を記載しています。Exchange 2010 または Exchange 2013 を実行する場合は、該当するドキュメントを参照してください。


## Exchange Server UM を実行するサーバーを構成するには

1.  エンタープライズ VoIP の場所のプロファイルごとに UM SIP (セッション開始プロトコル) URI (Uniform Resource Identifier) ダイヤル プランを作成します。Exchange 管理コンソールを使用する場合は、**セキュリティで保護 (推奨)** のセキュリティ設定を使用して新しいダイヤル プランを作成します。
    

    > [!WARNING]
    > SIP トラフィックの暗号化のみを要求するようにセキュリティ設定値を <STRONG>セキュリティで保護された SIP</STRONG> (以前の推奨) に設定した場合は、フロントエンド プールが暗号化を要求するように構成されていても、プールで SIP と RTP の両方のトラフィックの暗号化が要求されるため、ダイヤル プランのこのセキュリティ設定では不十分です。ダイヤル プランとプールのセキュリティ設定に互換性がないと、フロントエンド プールから Exchange UM への通話はすべて失敗し、"セキュリティ設定に互換性がない" ことを示すエラーが表示されます。

    
    Exchange 管理シェルを使用する場合は、次のように入力します。
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    詳細については、以下を参照してください。
    
      - Office Communications Server 2007 の場合は、「ユニファイド メッセージング SIP URI ダイヤル プランを作成する方法」 ([http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0x411)) および「New-UMDialplan: Exchange 2007 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0x411)) を参照してください。
    
      - Exchange 2010 の場合は、「UM ダイヤル プランの作成」 ([http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0x411)) および「New-UMDialplan: Exchange 2010 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0x411)) を参照してください。
    
      - Exchange 2013 の場合は、「ユニファイド メッセージング」 ([http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411)) を参照してください。
    
    > [!NOTE]  
    > セキュリティ レベルとして <strong>SIPSecured</strong> と <strong>Secured</strong> のどちらを選択するかは、メディア暗号化でセキュア リアルタイム転送プロトコル (SRTP) がアクティブになっているか、非アクティブになっているかによって異なります。Lync Server 2010 が Exchange UM と統合されている場合は、Lync Server メディア構成の暗号化レベルに対応している必要があります。Lync Server メディア構成は、<strong>Get-CsMediaConfiguration</strong> コマンドレットを実行すると表示できます。詳細については、「Lync Server 管理シェル」のドキュメントの「Get-CsMediaConfiguration」を参照してください。<br />
    > 適切な VoIP セキュリティ設定の選択方法の詳細については、「<a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス</a>」を参照してください。


2.  次のコマンドレットを実行して、各 UM ダイヤル プランの完全修飾ドメイン名 (FQDN) を取得します。
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    詳細については、以下を参照してください。
    
      - Exchange 2007 の場合は、「Get-UMDialplan: Exchange 2007 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268678\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268678%26clcid=0x411)) を参照してください。
    
      - Exchange 2010 の場合は、「Get-UMDialplan: Exchange 2010 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0x411)) を参照してください。
    
      - Exchange 2013 の場合は、「ユニファイド メッセージング」 ([http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411)) を参照してください。

3.  各 UM ダイヤル プランのダイヤル プラン名を記録します。Exchange Server のバージョンによっては、ダイヤル プラン名が一致するように、各 UM ダイヤル プランの対応する Lync Server ダイヤル プランの名前として後で各ダイヤル プラン名の FQDN を使用する場合があります。
    
    > [!NOTE]
    > Lync Server ダイヤル プラン名と UM ダイヤル プラン名が一致する必要があるのは、Exchange 2010 SP1 より前のバージョンの Exchange で UM ダイヤル プランを実行する場合だけです。


4.  次のようにして、Exchange UM を実行しているサーバーにダイヤル プランを追加します。
    
      - Exchange 管理コンソールを使用する場合は、サーバーのプロパティ シートからダイヤル プランを追加します。 具体的な手順については、Exchange Server 製品のドキュメントを参照してください。
        
        Exchange 2007 の場合は、「ユニファイド メッセージング サーバーをダイヤル プランに追加する方法」 ([http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0x411)) を参照してください。
        
        Exchange 2010 の場合は、「UM サーバーのプロパティの表示または構成」 ([http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0x411)) を参照してください。
        
        Exchange 2013 の場合は、「ユニファイド メッセージング」 ([http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0x411)) を参照してください。
    
      - Exchange 管理シェルを使用する場合は、Exchange UM サーバーごとに以下を実行します。
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    
    > [!NOTE]  
    > 次のステップを実行する前に、すべてのエンタープライズ VoIP ユーザーに Exchange Server のメールボックスが構成されていることを確認してください。<br />
    > Exchange 2007 の場合は、Exchange Server 2007 TechNet ライブラリ (<a href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0x411</a>) を参照してください。<br />
    > Exchange 2010 の場合は、Exchange Server 2010 TechNet ライブラリ (<a href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0x411</a>) を参照してください。<br />
    > ステップ 1. で作成した各ダイヤル プランのメールボックス ポリシーを指定する場合は、既定のポリシーと作成したポリシーのどちらかを選択します。


5.  \<Exchange インストール ディレクトリ\>\\Scripts に移動します。Exchange を単一のフォレストに展開する場合は、次のように入力します。
    
        exchucutil.ps1
    
    Exchange を複数のフォレストに展開する場合は、次のように入力します。
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    forest FQDN には、Lync Server を展開するフォレストを指定します。
    
    複数の IP ゲートウェイに関連付けられた UM ダイヤル プランが複数ある場合は、ステップ 6 に進んでください。ダイヤル プランをそれぞれ 1 つの IP ゲートウェイに関連付けている場合は、ステップ 6 を省略してください。
    

    > [!IMPORTANT]
    > exchucutil.ps1 を実行した後で、<STRONG>Lync サーバー フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。 再起動しないと、Lync Server でトポロジのユニファイド メッセージングが検出されません。



6.  Exchange 管理シェルまたは Exchange 管理コンソールを使用して、ダイヤル プランに関連付けられた IP ゲートウェイを除くすべての IP ゲートウェイで発信を無効にします。
    
    > [!NOTE]
    > このステップは、Exchange Server ユニファイド メッセージングを実行しているサーバーから外部ユーザーに対する発信通話 (電話で再生を使用する場合など) が確実に企業ファイアウォールを通過できるようにするために必要です。
    

    > [!IMPORTANT]
    > 発信通話に使用できる UM IP ゲートウェイを選択するときには、処理するトラフィックが最も多くなる可能性の高いゲートウェイを選択します。Lync Server ディレクターのプールに接続する IP ゲートウェイでは、送信トラフィックを許可しないでください。また、別のセントラル サイト内やブランチ サイト内のプールは避けてください。次のどちらかの方法で、IP ゲートウェイを通過する発信通話をブロックできます。

    
      - Exchange 管理シェルを使用する場合は、次のコマンドを実行して各 IP ゲートウェイを無効にします。
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Exchange 2007 の場合は、「Set-UMIPGateway: Exchange 2007 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0x411)) を参照してください。
        
        Exchange 2010 の場合は、「Set-UMIPGateway: Exchange 2010 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0x411)) を参照してください。
    
      - Exchange 管理コンソールを使用する場合は、\[**この IP ゲートウェイからの発信を許可する**\] チェック ボックスをオフにします。
    

    > [!IMPORTANT]
    > UM SIP URI ダイヤル プランを 1 つの IP ゲートウェイだけに関連付けている場合は、そのゲートウェイからの発信を無効にしないでください。



7.  Lync Server ダイヤル プランごとに UM 自動応答を作成します。
    

    > [!IMPORTANT]
    > 自動応答の名前の中にスペースを含めないでください。

    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    詳細については、以下を参照してください。
    
      - Exchange 2007 の場合は、「New-UMAutoAttendant: Exchange 2007 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0x411)) を参照してください。
    
      - Exchange 2010 の場合は、「New-UMAutoAttendant: Exchange 2010 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0x411)) を参照してください。
    
    以下の手順は、Lync Server ユーザーをエンタープライズ VoIP に対して有効にし、各ユーザーの SIP URI を把握した後で、ユーザーごとに実行します。

8.  Exchange UM ユーザー (Exchange メールボックスを各ユーザーに構成する必要があります) を UM ダイヤル プランに関連付け、各ユーザーの SIP URI を作成します。
    
    > [!NOTE]
    > 次に示すサンプルの <strong>SIPResourceIdentifier</strong> には、Lync Server ユーザーの SIP アドレスを指定する必要があります。
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    詳細については、以下を参照してください。
    
      - Exchange 2007 の場合は、「Enable-UMMailbox: Exchange 2007 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0x411)) を参照してください。
    
      - Exchange 2010 の場合は、「Enable-UMMailbox: Exchange 2010 ヘルプ」 ([http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0x411)) を参照してください。

