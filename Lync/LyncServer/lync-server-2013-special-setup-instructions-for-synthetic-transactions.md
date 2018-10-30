---
title: 代理トランザクションの特別なセットアップ指示
TOCTitle: 代理トランザクションの特別なセットアップ指示
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49886986
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 代理トランザクションの特別なセットアップ指示

 

_**トピックの最終更新日:** 2015-11-16_

大半の代理トランザクションは、監視ノード上でそのまま実行できます。つまり、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテスト パス中に直ちに開始できます。ただし、これは、すべての代理トランザクションに当てはまるわけではありません。以降のセクションで、特別なセットアップが必要な代理トランザクションについて説明します。

## データ会議代理トランザクション

監視ノード コンピューターが境界ネットワークの外部に配置されている場合は、ネットワーク サービス アカウントの Internet Explorer プロキシ設定を無効にしない限り、データ会議代理トランザクションはほぼ実行できません。このサービスのプロキシ設定を無効にするには、次の手順に従います。

1.  監視ノード コンピューターで、\[**スタート**\] ボタン、\[**すべてのプログラム**\]、\[**アクセサリ**\] の順にクリックし、\[**コマンド プロンプト**\] を右クリックし、\[**管理者として実行**\] をクリックします。

2.  コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

コマンド ウィンドウに次のようなメッセージが表示されます。

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

このメッセージは、ネットワーク サービス アカウントの Internet Explorer プロキシ設定が無効になったことを意味します。

## Exchange ユニファイド メッセージング代理トランザクション

Exchange ユニファイド メッセージング (UM)代理トランザクションは、テスト ユーザーが Exchange に属するボイスメール アカウントに接続できることを検証します。これらのテスト ユーザーは、Exchange UM テストを使用する前に、ボイスメール アカウントを使用して事前に構成しておく必要があります。

## 常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、管理者は、まずチャネルを作成し、テスト ユーザーにチャネルを使用する許可を与える必要があります。これらのテスト ユーザーは、[Test-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPersistentChatMessage) コマンドレットを使用して適切に構成できます。

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

このセットアップ タスクは、社内から実行する必要があります。

  - サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の PersistentChatAdministrators 役割のメンバーである必要があります。

  - サーバーから実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。

上のコマンドには Setup パラメーターが含まれ、True ($True) が設定されています。Setup パラメーターを指定した場合、Test-CsPersistentChatMessage は、特別な常設チャット ルームを作成し、そのルームにテスト ユーザーを割り当てます。これにより、テスト目的で使用できるチャット ルームが実際に存在することが保証されます。Setup パラメーターは、フロント エンド サーバーからのみ実行する必要があります。

Test-CsPersistentChatMessage を使用して作成されたチャット ルームは、管理者のみが削除できます。

## PSTN ピアツーピア通話代理トランザクション

[Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnPeerToPeerCall)代理トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうか検証します。

この代理トランザクションを実行するには、管理者は以下を構成する必要があります。

  - エンタープライズ VoIP用に有効化された 2 名のテスト ユーザー (発信者と受信者)。

  - 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。

  - 受信者の番号への通話が PSTN ゲートウェイに到達できるようにする音声ポリシーと音声ルート。

  - 通話を受ける PSTN ゲートウェイと、ダイヤルされた番号に基づいて受信者のホーム プールに通話を戻すメディア。

## 統合連絡先ストア代理トランザクション

統合連絡先ストア代理トランザクションは、Lync Server 2013 が Microsoft Exchange Server 2013 からユーザーに代わって連絡先を取得できることを検証します。

この代理トランザクションを使用するには、次の条件を満たす必要があります。

  - Lync Server 2013 と Exchange 2013 の間に、[Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)を構成する必要があります。

  - テスト ユーザーが有効な Exchange 2013 メールボックスを持っている必要があります。

これらの条件が満たされた後、管理者は、次のコマンドを実行して、SIP アドレスが kenmyer@litwareinc.com であるユーザーが自分の連絡先を統合連絡先ストアから取得できることを検証できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

上のコマンドでの Setup パラメーターの使い方に注意してください。Test-CsUnifiedContactStore の実行時に Setup パラメーターが含まれている場合、指定されたユーザーの連絡先 (この例では sip:kenmyer@litwareinc.com) が統合連絡先ストアに移動されます (もちろん、ユーザーの連絡先が統合連絡先ストア内にすでに存在する場合、連絡先は移動されません)。通常、Setup パラメーターは、一度だけ使用され (Test-CsUnifiedContactStore の初回の実行時)、テスト ユーザー、つまり Lync Server に実際にログオンすることがないユーザー アカウントでのみ使用する必要があります。テスト ユーザーが統合連絡先ストアに移行された後、Setup パラメーターなしで Test-CsUnifiedContactStore を呼び出すことで、ユーザーの連絡先を取得できます。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

## XMPP 代理トランザクション

XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、XMPP 機能を 1 つ以上のフェデレーション ドメインで構成する必要があります。

XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターにルーティング可能な XMPP ドメインのユーザー アカントを指定して使用する必要があります。次に例を示します。

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

この例では、litwareinc.com 用のメッセージを XMPP ゲートウェイにルーティングするために、Lync Server 2013 ルールが存在する必要があります。

