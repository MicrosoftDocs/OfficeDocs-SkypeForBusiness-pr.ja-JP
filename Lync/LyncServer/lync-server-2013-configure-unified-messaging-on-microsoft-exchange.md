---
title: 'Lync Server 2013: Microsoft Exchange でユニファイドメッセージングを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

このトピックでは、エンタープライズ Voip で使用するために Microsoft Exchange Server で Exchange ユニファイドメッセージング (UM) を構成する方法について説明します。

<div>


> [!NOTE]  
> このトピックのコマンドレットの例では、exchange 管理シェルの Exchange 2007 バージョンの構文について説明します。 Exchange 2010 または Exchange 2013 を実行している場合は、参照されている適切なドキュメントを参照してください。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Exchange Server UM を実行しているサーバーを構成するには

1.  各エンタープライズボイスの場所プロファイルに対して、UM セッション開始プロトコル (SIP) の URI ダイヤルプランを作成します。 Exchange 管理コンソールを使用する場合は、セキュリティ設定がセキュリティ設定されている新しいダイヤルプランを作成します **(推奨)**。
    
    <div>
    

    > [!WARNING]  
    > セキュリティ設定の値を<STRONG>Sip セキュリティ</STRONG>に設定して、sip トラフィックのみの暗号化を必須にする場合は、前に説明したように、フロントエンドプールが暗号化を要求するように構成されている場合は、ダイヤルプランに対するこのセキュリティ設定は不十分であることに注意してください。つまり、プールは SIP と RTP の両方のトラフィックに ダイヤルプランとプールのセキュリティ設定に互換性がない場合は、フロントエンドプールからの Exchange UM へのすべての呼び出しが失敗し、"互換性のないセキュリティ設定" というエラーが表示されます。

    
    </div>
    
    Exchange 管理シェルを使用している場合は、次のように入力します。
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    詳細については、以下を参照してください。
    
      - Office Communications Server 2007 については、「at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and UMDialplan: Exchange 2007 のヘルプ」で[http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)「ユニファイドメッセージング SIP URI ダイヤルプランを作成する方法」を参照してください。
    
      - Exchange 2010 については、「at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)と "New-UMDialplan: exchange 2010 のヘルプ" の「UM ダイヤル[http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)プランを作成する」を参照してください。
    
      - Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>SIPSecured</STRONG>または secure のセキュリティレベルを選択するかどうかは、セキュリティで保護されたリアルタイムトランスポートプロトコル (srtp) がメディア暗号化に対してアクティブ化されているか、無効になっているか<STRONG>によって</STRONG>異なります。 Lync Server 2010 と Exchange UM との統合については、Lync Server メディア構成の暗号化レベルに対応している必要があります。 Lync Server のメディア構成を表示するには、 <STRONG>CsMediaConfiguration</STRONG>コマンドレットを実行します。 詳細については、「Lync Server 管理シェルドキュメントの CsMediaConfiguration」を参照してください。<BR>適切な VoIP セキュリティ設定を選ぶ方法について詳しくは、「<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」をご覧ください。

    
    </div>

2.  次のコマンドレットを実行して、各 UM ダイヤルプランの完全修飾ドメイン名 (FQDN) を取得します。
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    詳細については、以下を参照してください。
    
      - Exchange 2007 については、「UMDialplan: Exchange 2007 のヘルプ」 [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)を参照してください。
    
      - Exchange 2010 については、「UMDialplan: Exchange 2010 のヘルプ」 [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)を参照してください。
    
      - Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。

3.  各 UM ダイヤルプランのダイヤルプラン名を記録します。 使用している Exchange Server のバージョンによっては、ダイヤルプラン名が一致するように、各 UM ダイヤルプランの対応する Lync Server ダイヤルプランの名前として、後で各ダイヤルプラン名の FQDN を使用する必要がある場合があります。
    
    <div>
    

    > [!NOTE]  
    > UM ダイヤルプランが Exchange 2010 SP1 より<EM>前</EM>のバージョンの exchange で実行されている場合にのみ、Lync Server のダイヤルプラン名が um ダイヤルプラン名と一致する必要があります。

    
    </div>

4.  次のように、Exchange UM を実行しているサーバーにダイヤルプランを追加します。
    
      - Exchange 管理コンソールの使用を選択した場合は、サーバーのプロパティシートからダイヤルプランを追加できます。 具体的な手順については、Exchange Server の製品に関するドキュメントを参照してください。
        
        Exchange 2007 については、at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)の「ユニファイドメッセージングサーバーをダイヤルプランに追加する方法」を参照してください。
        
        Exchange 2010 については、「の UM サーバーのプロパティを表示または[http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)構成する」を参照してください。
        
        Exchange 2013 については、の「ユニファイ[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)ドメッセージング」を参照してください。
    
      - Exchange 管理シェルを使用している場合は、Exchange UM サーバーごとに次の操作を実行します。
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 次の手順を実行する前に、すべてのエンタープライズボイスユーザーが Exchange Server メールボックスで構成されていることを確認してください。<BR>Exchange 2007 の場合は、にある<A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>exchange Server 2007 TechNet ライブラリを参照してください。<BR>Exchange 2010 の場合は、にある<A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>exchange Server 2010 TechNet ライブラリを参照してください。<BR>手順1で作成したダイヤルプランごとにメールボックスポリシーを指定するときは、既定のポリシーまたは作成したポリシーのいずれかを選択します。

    
    </div>

5.  [Exchange \<インストールディレクトリ\>\\スクリプト] に移動し、exchange が単一フォレストに展開されている場合は、次のように入力します。
    ```console
    exchucutil.ps1
    ```
    または、複数のフォレストに Exchange が展開されている場合は、次のように入力します。
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    ここで、[フォレスト FQDN の指定は Lync Server が展開されているフォレストを指定します。
    
    複数の IP ゲートウェイに関連付けられている UM ダイヤルプランが1つ以上ある場合は、手順6に進みます。 ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、手順6をスキップします。
    
    <div>
    

    > [!IMPORTANT]  
    > Exchucutil を実行し<EM>た後</EM>、必ず<STRONG>Lync Server のフロントエンド</STRONG>サービス (rtcsrv) を再起動してください。 そうしないと、Lync Server では、ユニファイドメッセージングはトポロジで検出されません。

    
    </div>

6.  Exchange 管理シェルまたは Exchange 管理コンソールのいずれかを使用して、ダイヤルプランに関連付けられているすべての IP ゲートウェイ以外の発信通話を無効にします。
    
    <div>
    

    > [!NOTE]  
    > この手順は、外部ユーザーに対して Exchange Server ユニファイドメッセージングを実行しているサーバー (たとえば、再生中のシナリオの場合など) が企業ファイアウォールを確実に通過できるようにするために必要です。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 発信通話を許可する UM IP ゲートウェイを選択するときに、最も多くのトラフィックを処理する可能性が高いものを選択します。 Lync Server ディレクターのプールに接続する IP ゲートウェイ経由での送信トラフィックを許可しないでください。 また、別のセントラルサイトまたはブランチサイトのプールも避けてください。 次のいずれかの方法を使用して、発信した着信が IP ゲートウェイを通過するのをブロックすることができます。

    
    </div>
    
      - Exchange 管理シェルを使用している場合は、次のコマンドを実行して各 IP ゲートウェイを無効にします。
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Exchange 2007 については、「Set-UMIPGateway: Exchange 2007 の[http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)ヘルプ」を参照してください。
        
        Exchange 2010 については、「Set-UMIPGateway: Exchange 2010 の[http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)ヘルプ」を参照してください。
    
      - Exchange 管理コンソールを使用している場合は、[**この IP ゲートウェイ経由で発信する**] チェックボックスをオフにします。
    
    <div>
    

    > [!IMPORTANT]  
    > UM SIP URI ダイヤルプランが単一の IP ゲートウェイのみに関連付けられている場合は、このゲートウェイ経由での発信通話を許可しないでください。

    
    </div>

7.  各 Lync Server のダイヤルプランに UM 自動応答を作成します。
    
    <div>
    

    > [!IMPORTANT]  
    > 自動応答の名前にスペースを含めないでください。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    詳細については、以下を参照してください。
    
      - Exchange 2007 の場合は、「New-UMAutoAttendant: Exchange 2007 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)」を参照してください。
    
      - Exchange 2010 の場合は、「New-UMAutoAttendant: Exchange 2010 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)」を参照してください。
    
    エンタープライズ Voip の Lync Server ユーザーを有効にし、SIP Uri を知ったら、各ユーザーに対して次の手順を実行する必要があります。

8.  UM ダイヤルプランを使用して、Exchange UM ユーザー (Exchange メールボックスで構成する必要がある各ユーザー) を関連付け、各ユーザーの SIP URI を作成します。
    
    <div>
    

    > [!NOTE]  
    > 次のサンプルの<STRONG>SIPResourceIdentifier</STRONG>は、Lync Server ユーザーの SIP アドレスである必要があります。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    詳細については、以下を参照してください。
    
      - Exchange 2007 の場合は、「Enable-UMMailbox: Exchange 2007 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)」を参照してください。
    
      - Exchange 2010 の場合は、「Enable-UMMailbox: Exchange 2010 のヘルプ[http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

