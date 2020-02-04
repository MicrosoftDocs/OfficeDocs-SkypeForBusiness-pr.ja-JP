---
title: 'Lync Server 2013: 代理トランザクション用の特別なセットアップ手順'
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
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 での代理トランザクションの特別なセットアップ手順

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-11-16_

ほとんどの代理トランザクションは、のようにウォッチャーノードで実行できます。つまり、代理トランザクションがウォッチャーノードの構成設定に追加されるとすぐに、ウォッチャーノードは、テストパス中に合成トランザクションの使用を開始できます。 ただし、すべての代理トランザクションでこれは当てはまりません。 例外 (特殊なセットアップ手順を必要とする代理トランザクション) については、次のセクションで説明します。

<div>

## <a name="dealing-with-server-timeout-errors"></a>サーバータイムアウトエラーを処理する

場合によっては、エラーコード504で、代理トランザクションがサーバータイムアウトエラーで失敗することがあります。 通常、これらのエラーは、ファイアウォールの問題が原因で発生します。 代理トランザクションが実行されると、そのトランザクションは MonitoringHost .exe プロセスで実行されます。さらに、MonitoringHost は、PowerShell の .exe プロセスのインスタンスを開始します。 ファイアウォールによって、MonitoringHost または PowerShell がブロックされている場合、代理トランザクションは失敗し、504エラーが生成されます。

この問題を解決するには、ローカルコンピューター上の MonitoringHost と PowerShell の両方に対して、受信ファイアウォール規則を手動で作成する必要があります。 この操作は、サーバーの既存の構成に応じて、Windows ファイアウォールまたはサードパーティのローカルファイアウォールソフトウェアを使用して行うことができます。

代理トランザクションホストマシンと監視しようとしている Lync サーバーの間でネットワークファイアウォールデバイスを使用している場合は、ホストをクライアントコンピューターとして扱う必要があります。これには、 [Lync Server 2013 の内部サーバーのポートとプロトコル](lync-server-2013-ports-and-protocols-for-internal-servers.md)からすべてのファイアウォールポート要件を考慮する必要があります。

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>データ会議の代理トランザクション

ウォッチャーノードのコンピューターが境界ネットワークの外部にある場合は、ネットワークサービスアカウントの Internet Explorer プロキシ設定を無効にしない限り、データ会議の代理トランザクションを実行できない可能性があります。 このサービスのプロキシ設定を無効にするには、次の手順を実行します。

1.  ウォッチャーノードのコンピューターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。

2.  コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

コマンドウィンドウに次のメッセージが表示されます。

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

このメッセージは、ネットワークサービスアカウントの Internet Explorer のプロキシ設定を無効にしていることを意味します。

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange ユニファイドメッセージングの代理トランザクション

Exchange Unified Messaging (UM) 代理トランザクションは、テスト ユーザーが Exchange に属するボイスメール アカウントに接続できることを検証します。 これらのテストユーザーは、Exchange UM テストを使用する前に、ボイスメールアカウントで事前に構成する必要があります。

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>常設チャットの代理トランザクション

常設チャットの代理トランザクションを使用するには、最初にチャネルを作成し、それを使用するための権限をテストユーザーに付与する必要があります。 [CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage)コマンドレットを使用して、これらのテストユーザーを適切に構成できます。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

このセットアップタスクは、エンタープライズ内から実行する必要があります。

  - Nonserver コンピューターから実行する場合、コマンドレットを実行するユーザーは、ロールベースのアクセス制御 (RBAC) の PersistentChatAdministrators ロールのメンバーである必要があります。

  - サーバー自体から実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。

上記のコマンドでは、Setup パラメーターが含まれており、True ($True) に設定されています。 Setup パラメーターを含める場合は、CsPersistentChatMessage によって特別な常設チャットルームが作成され、そのルームにテストユーザーが設定されます。 これにより、実際にはテスト目的でチャットルームが用意されていることを確認できます。 Setup パラメーターは、フロントエンドサーバーからのみ実行する必要があることに注意してください。

CsPersistentChatMessage によって作成されたチャットルームは、管理者のみが削除できます。

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN ピアツーピア通話の代理トランザクション

[テスト-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)合成トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうかを確認します。

この代理トランザクションを実行するには、管理者が次のように構成する必要があります。

  - エンタープライズ Voip の2つのテストユーザー (発信者と受信者) が有効になっています。

  - 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。

  - PSTN ゲートウェイに到達するために受信者の電話番号への通話を可能にする音声ポリシーと音声ルート。

  - 着信を受け付ける PSTN ゲートウェイ。通話をルーティングするメディアは、ダイヤルした番号に基づいて受信者のホームプールにバックバックします。

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>統合連絡先ストアの代理トランザクション

統合連絡先ストアの代理トランザクションは、Lync Server 2013 が Microsoft Exchange Server 2013 からユーザーの代わりに連絡先を取得できることを確認します。

この代理トランザクションを使用するには、次の条件を満たす必要があります。

  - Lync server [2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理するに](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)は、lync server 2013 と Exchange 2013 の間で構成する必要があります。

  - テストユーザーは、有効な Exchange 2013 メールボックスを持っている必要があります。

これらの条件が満たされた後、管理者は次のコマンドを実行して、SIP アドレス kenmyer@litwareinc.com を持つユーザーが、ユニファイド連絡先ストアから連絡先を取得できるかどうかを確認できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

前のコマンドで使用した Setup パラメーターを使用することに注意してください。 CsUnifiedContactStore の実行中に Setup パラメーターが含まれている場合は、指定したユーザーの連絡先 (この場合は sip:kenmyer@litwareinc.com) が統合連絡先ストアに移動されます。 (もちろん、ユーザーの連絡先が既にユニファイド連絡先ストアにある場合は、それを移動する必要はありません)。通常、Setup パラメーターは1回のみ使用され (初回のテスト CsUnifiedContactStore が実行されます)、テストユーザーでのみ使用する必要があります。つまり、Lync Server に実際にはログオンしないユーザーアカウントを使用しています。 テストユーザーがユニファイド連絡先ストアに移行されたら、セットアップパラメーターを指定せずに CsUnifiedContactStore を呼び出してユーザーの連絡先を取得できることを確認できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP の代理トランザクション

XMPP (拡張メッセージングとプレゼンスプロトコル) IM の代理トランザクションでは、1つ以上のフェデレーションドメインで XMPP 機能が構成されている必要があります。

XMPP の代理トランザクションを有効にするには、ルーティング可能な XMPP ドメインのユーザーアカウントで XmppTestReceiverMailAddress パラメーターを指定する必要があります。 次に例を示します。

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Lync Server 2013 ルールが存在している必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

