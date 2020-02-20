---
title: 'Lync Server 2013: 代理トランザクションの特別なセットアップ手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92786b50bc0b29fe5bc7f6b5b8ac978a17085aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 での代理トランザクションの特別なセットアップ手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-11-16_

大半の代理トランザクションは、監視ノード上でそのまま実行できます。つまり、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテスト パス中に直ちに開始できます。ただし、これは、すべての代理トランザクションに当てはまるわけではありません。以降のセクションで、特別なセットアップが必要な代理トランザクションについて説明します。

<div>

## <a name="dealing-with-server-timeout-errors"></a>サーバーのタイムアウトエラーを処理する

場合によっては、代理トランザクションがサーバータイムアウトエラーで失敗することがあります (エラーコード 504)。 これらのエラーは、通常、ファイアウォールの問題によって発生します。 代理トランザクションが実行されると、そのトランザクションは MonitoringHost .exe プロセスの下で実行されます。その後、MonitoringHost は PowerShell プロセスのインスタンスを開始します。 MonitoringHost または PowerShell がファイアウォールによってブロックされている場合、代理トランザクションは失敗し、504エラーが生成されます。

この問題を解決するには、ローカルコンピューター上の MonitoringHost と PowerShell の両方に対して、受信ファイアウォール規則を手動で作成する必要があります。 この操作は、サーバーの既存の構成に応じて、Windows ファイアウォールまたはサードパーティのローカルファイアウォールソフトウェアを使用して行うことができます。

代理トランザクションホストマシンと、監視しようとしている Lync サーバーとの間でネットワークファイアウォールデバイスを使用する場合は、ホストをクライアントコンピューターとして扱い、 [Lync Server 2013 の内部サーバーのポートとプロトコル](lync-server-2013-ports-and-protocols-for-internal-servers.md)に関するすべてのファイアウォールポート要件をオブザーバーする必要があります。

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>データ会議代理トランザクション

監視ノードコンピューターが境界ネットワークの外部に配置されている場合は、ネットワークサービスアカウントの Internet Explorer プロキシ設定を最初に無効にしない限り、データ会議の代理トランザクションを実行できない可能性があります。 このサービスのプロキシ設定を無効にするには、次の手順に従います。

1.  ウォッチャー ノード コンピューターで、[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックします。次に、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

コマンド ウィンドウに次のようなメッセージが表示されます。

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

このメッセージは、ネットワークサービスアカウントの Internet Explorer プロキシ設定が無効になっていることを意味します。

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange ユニファイド メッセージング代理トランザクション

Exchange ユニファイドメッセージング (UM) 代理トランザクションは、テストユーザーが Exchange に所属しているボイスメールアカウントに接続できることを確認します。 これらのテスト ユーザーは、Exchange UM テストを使用する前に、ボイスメール アカウントを使用して事前に構成しておく必要があります。

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、管理者はまずチャネルを作成し、それを使用するためのアクセス許可をテストユーザーに付与する必要があります。 これらのテストユーザーを適切に構成するには、 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage)コマンドレットを使用できます。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

このセットアップ タスクは、社内から実行する必要があります。

  - サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の PersistentChatAdministrators 役割のメンバーである必要があります。

  - サーバーから実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。

上のコマンドには Setup パラメーターが含まれ、True ($True) が設定されています。 Setup パラメーターを指定すると、Test-cspersistentchatmessage は特別な常設チャットルームを作成し、そのルームにテストユーザーを設定します。 これにより、テスト目的で使用できるチャット ルームが実際に存在することが保証されます。 Setup パラメーターは、フロントエンドサーバーからのみ実行する必要があることに注意してください。

Test-CsPersistentChatMessage を使用して作成されたチャット ルームは、管理者のみが削除できます。

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN ピアツーピア通話代理トランザクション

[テスト-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)代理トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうかを確認します。

この代理トランザクションを実行するには、管理者は以下を構成する必要があります。

  - エンタープライズ Voip に対して有効になっている2つのテストユーザー (発信者と受信者)。

  - 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。

  - 受信者の番号への通話が PSTN ゲートウェイに到達できるようにする音声ポリシーと音声ルート。

  - 通話を受ける PSTN ゲートウェイと、ダイヤルされた番号に基づいて受信者のホーム プールに通話を戻すメディア。

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>統合連絡先ストア代理トランザクション

統合連絡先ストア代理トランザクションは、Lync Server 2013 が、ユーザーの代わりに Microsoft Exchange Server 2013 から連絡先を取得できることを確認します。

この代理トランザクションを使用するには、次の条件を満たす必要があります。

  - Lync server [2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)は、lync server 2013 と Exchange 2013 の間で行う必要があります。

  - テストユーザーは、有効な Exchange 2013 メールボックスを持っている必要があります。

これらの条件が満たされた後、管理者は、次のコマンドを実行して、SIP アドレスが kenmyer@litwareinc.com であるユーザーが自分の連絡先を統合連絡先ストアから取得できることを検証できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

前述のコマンドで使用した Setup パラメーターの使用に注意してください。 Test-csunifiedcontactstore の実行中に Setup パラメーターが含まれる場合、指定されたユーザーの連絡先 (この場合は sip:kenmyer@litwareinc.com) が統合連絡先ストアに移動されます。 (もちろん、ユーザーの連絡先が既に統合連絡先ストアにある場合は、それらを移動する必要はありません)。Setup パラメーターは、通常、1回だけ使用され (初回は Test-csunifiedcontactstore が実行されます)、テストユーザーのみが使用されます。つまり、実際には Lync Server にログオンしていないユーザーアカウントを使用します。 テストユーザーが統合連絡先ストアに移行されたら、次のように、セットアップパラメーターを使用せずに Test-csunifiedcontactstore を呼び出して、ユーザーの連絡先を取得できることを確認できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 代理トランザクション

XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、XMPP 機能を 1 つ以上のフェデレーション ドメインで構成する必要があります。

XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターにルーティング可能な XMPP ドメインのユーザー アカントを指定して使用する必要があります。 次に例を示します。

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Lync Server 2013 ルールが存在している必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

