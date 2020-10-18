---
title: 'Lync Server 2013: Microsoft Exchange でのユニファイドメッセージングの構成'
description: 'Lync Server 2013: Microsoft Exchange のユニファイドメッセージングを構成します。'
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577523"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

このトピックでは、エンタープライズ Voip で使用するために Microsoft Exchange Server で Exchange ユニファイドメッセージング (UM) を構成する方法について説明します。

<div>


> [!NOTE]  
> このトピックのコマンドレットの例では、exchange 2007 バージョンの Exchange 管理シェルの構文について説明します。 Exchange 2010 または Exchange 2013 を実行している場合は、参照されている適切なドキュメントを参照してください。



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Exchange Server UM を実行しているサーバーを構成するには

1.  エンタープライズ Voip の場所のプロファイルごとに、UM セッション開始プロトコル (SIP) の URI (Uniform Resource Identifier) ダイヤルプランを作成します。 Exchange 管理コンソールを使用する場合は、セキュリティ設定をセキュリティで **保護 (推奨)** した新しいダイヤルプランを作成します。
    
    <div>
    

    > [!WARNING]  
    > セキュリティ設定の値を sip に対してセキュリティで <STRONG>保護</STRONG> された sip に設定した場合は、事前に推奨されているように、フロントエンドプールが暗号化を要求するように構成されている場合は、ダイヤルプランのこのセキュリティ設定が不十分であることに注意してください。 ダイヤルプランおよびプールのセキュリティ設定に互換性がない場合、フロントエンドプールからの Exchange UM へのすべての呼び出しが失敗し、"互換性のないセキュリティ設定" があることを示すエラーが発生します。

    
    </div>
    
    Exchange 管理シェルを使用する場合は、次のように入力します。
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    詳細については、以下を参照してください。
    
      - Office Communications Server 2007 については、「ユニファイドメッセージング SIP URI ダイヤルプランを作成する方法」 [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) および「set-umdialplan: Exchange 2007 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。
    
      - Exchange 2010 については、「UM ダイヤルプランを作成する」 [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) および「set-umdialplan: Exchange 2010 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。
    
      - Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>SIPSecured</STRONG>のセキュリティレベルを選択するか、セキュリティで<STRONG>保護</STRONG>するかは、メディア暗号化に対してセキュリティで保護されたリアルタイム転送プロトコル (srtp) をアクティブ化または非アクティブ化するかによって決まります。 Lync Server 2010 と Exchange UM との統合については、これは Lync Server メディア構成の暗号化レベルに対応している必要があります。 Lync Server メディア構成は、 <STRONG>get-csmediaconfiguration</STRONG> コマンドレットを実行すると表示できます。 詳細については、「Lync Server Management Shell」のドキュメントの「Get-CsMediaConfiguration」を参照してください。<BR>適切な VoIP セキュリティ設定の選択の詳細については、「 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」を参照してください。

    
    </div>

2.  次のコマンドレットを実行して、各 UM ダイヤルプランの完全修飾ドメイン名 (FQDN) を取得します。
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    詳細については、以下を参照してください。
    
      - Exchange 2007 については、「Set-umdialplan: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。
    
      - Exchange 2010 については、「Set-umdialplan: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。
    
      - Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。

3.  各 UM ダイヤルプランのダイヤルプラン名を記録します。 ご使用の Exchange Server のバージョンによっては、ダイヤルプランの名前が一致するように、各ダイヤルプラン名の FQDN を、各 UM ダイヤルプランの対応する Lync Server ダイヤルプランの名前として後で使用する必要がある場合があります。
    
    <div>
    

    > [!NOTE]  
    > Lync Server ダイヤルプラン名は、UM ダイヤルプランが Exchange 2010 SP1 より <EM>前</EM> のバージョンの exchange 上で実行されている場合にのみ、um ダイヤルプラン名と一致する必要があります。

    
    </div>

4.  Exchange UM を実行しているサーバーに、次のようにダイヤルプランを追加します。
    
      - Exchange 管理コンソールを使用することを選択した場合は、サーバーのプロパティシートからダイヤルプランを追加できます。 具体的な手順については、Exchange Server 製品のドキュメントを参照してください。
        
        Exchange 2007 については、「」の「ユニファイドメッセージングサーバーをダイヤルプランに追加する方法」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。
        
        Exchange 2010 については、「」の「UM サーバーのプロパティを表示または構成する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。
        
        Exchange 2013 については、「」の「ユニファイドメッセージング」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。
    
      - Exchange 管理シェルを使用する場合は、それぞれの Exchange UM サーバーに対して次のように実行します。
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > 次の手順を実行する前に、すべてのエンタープライズ Voip ユーザーが Exchange Server メールボックスで構成されていることを確認してください。<BR>Exchange 2007 については、Exchange Server 2007 TechNet ライブラリの「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。<BR>Exchange 2010 については、Exchange Server 2010 TechNet ライブラリの「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。<BR>手順1で作成した各ダイヤルプランのメールボックスポリシーを指定する場合は、既定のポリシーまたは作成したポリシーのいずれかを選択します。

    
    </div>

5.  \<Exchange installation directory\> \\ [スクリプト] に移動し、Exchange が単一のフォレストに展開されている場合は、次のように入力します。
    ```console
    exchucutil.ps1
    ```
    Exchange が複数のフォレストに展開されている場合は、次のように入力します。
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    フォレスト FQDN には、Lync Server を展開するフォレストを指定します。
    
    複数の IP ゲートウェイに関連付けられている1つまたは複数の UM ダイヤルプランがある場合は、手順6に進みます。 ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、手順6をスキップします。
    
    <div>
    

    > [!IMPORTANT]  
    > exchucutil.ps1 を実行した<EM></EM>後で、<STRONG>Lync サーバー フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。 それ以外の場合、Lync Server はトポロジ内のユニファイドメッセージングを検出しません。

    
    </div>

6.  Exchange 管理シェルまたは Exchange 管理コンソールのいずれかを使用して、各ダイヤルプランに関連付けられている1つを除くすべての IP ゲートウェイの発信呼び出しを無効にします。
    
    <div>
    

    > [!NOTE]  
    > この手順は、Exchange Server ユニファイドメッセージングを実行しているサーバーから外部ユーザーへの発信呼び出しを確実に行うために必要です (たとえば、電話で再生するシナリオの場合と同様)。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 送信呼び出しを許可する UM IP ゲートウェイを選択するときには、最も多くのトラフィックを処理する可能性があるものを選択します。 Lync Server director のプールに接続する IP ゲートウェイ経由の送信トラフィックを許可しません。 別の中央サイトまたはブランチサイトにあるプールも避けてください。 次のいずれかの方法を使用して、発信呼び出しが IP ゲートウェイを通過するのをブロックできます。

    
    </div>
    
      - Exchange 管理シェルを使用する場合は、次のコマンドを実行して各 IP ゲートウェイを無効にします。
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Exchange 2007 については、「Set-UMIPGateway: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。
        
        Exchange 2010 については、「Set-UMIPGateway: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。
    
      - Exchange 管理コンソールを使用する場合は、[ **この IP ゲートウェイ経由の送信呼び出しを許可** する] チェックボックスをオフにします。
    
    <div>
    

    > [!IMPORTANT]  
    > UM SIP URI ダイヤルプランが1つの IP ゲートウェイのみに関連付けられている場合は、このゲートウェイ経由の発信呼び出しを許可しません。

    
    </div>

7.  各 Lync Server ダイヤルプランに対して UM 自動応答を作成します。
    
    <div>
    

    > [!IMPORTANT]  
    > 自動応答の名前にスペースを含めないでください。

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    詳細については、以下を参照してください。
    
      - Exchange 2007 については、「New-UMAutoAttendant: Exchange 2007 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。
    
      - Exchange 2010 については、「New-UMAutoAttendant: Exchange 2010 Help」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。
    
    Lync Server ユーザーのエンタープライズ Voip を有効にし、その SIP Uri を認識した後、各ユーザーに対して次の手順を実行する必要があります。

8.  UM ダイヤルプランを使用して Exchange UM ユーザー (Exchange のメールボックスで構成する必要がある各ユーザー) を関連付け、各ユーザーの SIP URI を作成します。
    
    <div>
    

    > [!NOTE]  
    > 次の例の <STRONG>SIPResourceIdentifier</STRONG> は、Lync Server ユーザーの SIP アドレスである必要があります。

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    詳細については、以下を参照してください。
    
      - Exchange 2007 については、「Enable-UMMailbox: Exchange 2007 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。
    
      - Exchange 2010 については、「Enable-UMMailbox: Exchange 2010 Help」 () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

