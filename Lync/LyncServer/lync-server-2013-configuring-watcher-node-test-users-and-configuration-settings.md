---
title: 監視ノードのテスト ユーザーおよび構成設定の構成
TOCTitle: 監視ノードのテスト ユーザーおよび構成設定の構成
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48273231
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視ノードのテスト ユーザーおよび構成設定の構成

 

_**トピックの最終更新日:** 2013-07-29_

監視ノードとして動作するコンピューターを構成したら、次のことを行う必要があります。

1.  これらの監視ノードによって使用されるテスト アカウントを作成します。Negotiate の認証方法を使用している場合は、[Set-CsTestUserCredential](https://docs.microsoft.com/en-us/powershell/module/skype/) コマンドレットを使用し、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要もあります。

2.  監視ノード構成設定を更新します。

このセクションでは、以下の内容について説明します。

  - テスト ユーザー アカウントの構成

  - 既定の代理トランザクションを使用した基本的な監視ノードの構成

  - 拡張テストの構成

  - 代理トランザクションの追加と削除

  - 監視ノード構成の表示とテスト

## テスト ユーザー アカウントの構成

テスト ユーザーは実在するユーザーである必要はありませんが、有効な Active Directory ドメイン サービス アカウントである必要があります。また、これらのアカウントは Lync Server 2013 で有効になっていて、有効な SIP アドレスがあり、(Test-CsPstnPeerToPeerCall 代理トランザクションを使用するため) エンタープライズ VoIP が有効になっている必要もあります。TrustedServer 認証方法を使用する場合は、これらのアカウントが存在し、ここで指定されているように構成されていることを確認するだけです。テストする各プールには、少なくとも 3 人のテスト ユーザーを割り当てる必要があります。

また、Negotiate 認証方法を使用している場合、**Set-CsTestUserCredential** コマンドレッドと Lync Server 管理シェルを使用して、これらのテスト アカウントが代理トランザクションを操作できるようにする必要もあります。これは、次のようなコマンドを実行することで実行できます (これらのコマンドでは、3 つの Active Directory ユーザー アカウントが既に作成されていて、これらのアカウントが Lync Server 2013 で有効になっていることを前提としています)。

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

SIP アドレスだけでなくユーザー名とパスワードも含める必要があることに注意してください。パスワード Set-CsTestUserCredential を含めない場合は、この情報の入力が求められます。ユーザー名は、上記のようにドメイン名\\ユーザー名の形式を使用するか、次の例のようにユーザー名@ドメイン名の形式を使用して指定できます。

    -UserName "watcher3@litwareinc.com"

テスト ユーザーの資格情報が作成されたことを確認するには、Lync Server 管理シェルから次のコマンドを実行します。

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

次のような情報が各ユーザーに返されます。

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

## 既定の代理トランザクションを使用した基本的な監視ノードの構成

テスト ユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

このコマンドでは、既定の設定を使用し、既定の代理トランザクションのセットを実行する新しい監視ノードが作成されます。新しい監視ノードでは、 watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com のテスト ユーザーを使用します。監視ノードが TrustedServer 認証を使用している場合、3 つのテスト アカウントは Active Directory および Lync Server で有効なユーザー アカウントにすることができます。監視ノードが Negotiate 認証方法を使用している場合は、**Set-CsTestUserCredential** コマンドレットを使用してこれらのユーザー アカウントを監視ノードで有効にする必要もあります。

## 拡張テストの構成

公衆交換電話網との接続を検証する公衆交換電話網 (PSTN) テストを有効にする場合、監視ノードのセットアップ時に追加の構成を行う必要があります。最初に、テスト ユーザーを PSTN のテストの種類に関連付ける必要があります。これを行うには、Lync Server 管理シェルから次のようなコマンドを実行します。

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

このコマンドの結果は変数に格納する必要があります。この例では、$pstnTest という名前の変数です。

この時点で **New-CsWatcherNodeConfiguration** コマンドレットを使用すると、テストの種類 (変数 $pstnTest に格納されている) を Lync Server 2013 プールに関連付けることができます。たとえば、次のコマンドでは、前に作成した 3 つのテスト ユーザーを追加し、PSTN のテストの種類も追加する新しい監視ノード構成をプール atl-cs-001.litwareinc.com に対し作成します。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Lync Server の中核となるファイルと RTCLocal データベースを監視ノード コンピューターにインストールしていない場合、上記のコマンドは失敗することに注意してください。

複数の音声ポリシーをテストするには、**New-CsExtendedTest** コマンドレットを使用して各ポリシーに拡張テストを作成する必要があります。このテストに割り当てられたユーザーは、目的の音声ポリシーを使用して構成する必要があります。次のようなコマンドを使用すると、拡張テストは **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Tests パラメーターを使用しないで New-CsWatcherNodeConfiguration を呼び出す場合、既定の代理トランザクション (および指定された拡張代理トランザクション) のみが新しい監視ノードで有効になります。このため、監視ノードは次のコンポーネントをテストします。

  - Registration

  - IM

  - GroupIM

  - P2PAV (ピアツーピアの音声ビデオ セッション)

  - AvConference (音声/会議)

  - プレゼンス

  - ABS (アドレス帳サービス)

  - ABWQ (アドレス帳 Web サービス)

  - PSTN (拡張テストとして指定される PSTN ゲートウェイ通話。既定では PSTN は無効です。ここでは、コマンドで ExtendedTests パラメーターを使用して PSTN を有効にしたためにこのテストが有効になっています。)

また、次のコンポーネントは既定ではテストされません。

  - AVEdgeConnectivity

  - MCXP2PIM (モバイル デバイス インスタント メッセージング)

  - ExumConnectivity (Exchange ユニファイド メッセージング)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

## 代理トランザクションの追加と削除

監視ノードを構成した後は、**Set-CsWatcherNodeConfiguration** コマンドレットを使用してノードから代理トランザクションを追加または削除できます。たとえば、監視ノードに PersistentChatMessage テストを追加するには Add メソッドと次のようなコマンドを使用します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

テスト名をカンマで区切ることにより、複数のテストを追加することができます。次に例を示します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

これらのテストの 1 つまたは複数 (たとえば DataConference) が既に監視ノードで有効になっていた場合、エラーが発生します。この場合、次のようなエラー メッセージが表示されます。

    Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' キー、または一意の Identity 制約に対して、重複するキー シーケンス 'DataConference' が存在します。

このエラーが発生した場合、変更は一切適用されません。重複するテストを削除してコマンドを再実行する必要があります。

監視ノードから代理トランザクションを削除するには、Add メソッドの代わりに Remove メソッドを使用します。たとえば、次のコマンドでは、監視ノードから ABWQ テストを削除します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

また、Replace メソッドを使用すると、現在有効になっているすべてのテストを 1 つ以上の新しいテストに置き換えることができます。たとえば、1 つの監視ノードが IM テストを実行するようにする場合、次のコマンドを使用してこれを構成することができます。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

上記のコマンドを実行する場合、指定された監視ノードのすべての代理トランザクションは IM 以外無効になります。

## 監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて次のような情報を返します。

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference


> [!TIP]
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。<BR>Get-CsWatcherNodeConfiguration ?Identity "atl-cs-001.litwareinc.com" | Select-Object ?ExpandProperty Tests | Sort-Object



監視ノードが作成されていることを確認するには、Lync Server 管理シェルから次のコマンドを入力します。

    Get-CsWatcherNodeConfiguration

次のような情報が表示されます。

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

監視ノードが正しく構成されていることを確認するには、Lync Server 管理シェルから次のコマンドを入力します。

    Test-CsWatcherNodeConfiguration

上記のコマンドでは、展開内の監視ノードをそれぞれテストし、次のような情報を提供します。

  - 必要なレジストラーの役割がインストールされているかどうか

  - Set-CsWatcherNodeConfiguration を実行したときに必要なレジストリ キーが作成されたかどうか

  - サーバーで適切なバージョンの Lync Server。を実行しているかどうか

  - ポートが正しく構成されているかどうか

  - 割り当てられたテスト ユーザーが必要な資格情報を持っているかどうか

