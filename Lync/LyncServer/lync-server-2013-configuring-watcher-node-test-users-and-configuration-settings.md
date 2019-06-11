---
title: ウォッチャーノードのテストユーザーと構成設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d446934e8d84a12a6eecd84fbc94a956d8ae95e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-29_

監視ノードとして動作するコンピューターを構成したら、次のことを行う必要があります。

1.  これらのウォッチャーノードで使用するテストアカウントを作成します。 Negotiate の認証方法を使用している場合は、[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) コマンドレットを使用し、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要もあります。

2.  監視ノード構成設定を更新します。

このセクションの内容:

  - テストユーザーアカウントを構成する

  - 既定の代理トランザクションを使った基本的なウォッチャーノードの構成

  - 拡張テストの構成

  - 代理トランザクションの追加と削除

  - 監視ノード構成の表示とテスト

<div>

## <a name="configuring-test-user-accounts"></a>テストユーザーアカウントを構成する

テストユーザーは、実際のユーザーを表す必要はありませんが、有効な Active Directory ドメインサービスアカウントである必要があります。さらに、これらのアカウントは Lync Server 2013 で有効にしておく必要があります。また、有効な SIP アドレスがある必要があります。また、エンタープライズ Voip を有効にする必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使う場合)。 TrustedServer 認証方法を使用する場合は、これらのアカウントが存在し、ここで指定したように構成されていることを確認する必要があります。 テストしようとする各プールに対して、少なくとも 3 つのテスト ユーザーを割り当てる必要があります。

Negotiate 認証方法を使用している場合は、 **CsTestUserCredential**コマンドレットと Lync Server Management Shell を使って、これらのテストアカウントで代理トランザクションを操作できるようにする必要もあります。 これを行うには、次のようなコマンドを実行します。 (これらのコマンドは、3つの Active Directory ユーザーアカウントが既に作成されていて、それらのアカウントが Lync Server 2013 用に有効になっていることを前提としています)。

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があることに注意してください。 パスワードを指定しない場合、CsTestUserCredential によって情報の入力を求めるメッセージが表示されます。 ユーザー名は、上記のドメイン名\\のユーザー名形式、またはユーザー名 @ ドメイン名の形式を使用して指定できます。例えば：

    -UserName "watcher3@litwareinc.com"

テストユーザーの資格情報が作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを実行します。

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

このような情報は、ユーザーごとに返されます。

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使った基本的なウォッチャーノードの構成

テストユーザーが作成された後、次のようなコマンドを使用してウォッチャーノードを作成できます。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

このコマンドでは、既定の設定を使用し、既定の代理トランザクションのセットを実行する新しい監視ノードが作成されます。 新しい監視ノードでは、watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com のテスト ユーザーを使用します。 ウォッチャーノードが TrustedServer 認証を使用している場合、3つのテストアカウントは Active Directory と Lync Server で有効になっている有効なユーザーアカウントにすることができます。 ウォッチャーノードが Negotiate 認証方法を使用している場合は、 **CsTestUserCredential**コマンドレットを使用して、ウォッチャーノードに対してもこれらのユーザーアカウントを有効にする必要があります。

</div>

<div>

## <a name="configuring-extended-tests"></a>拡張テストの構成

公衆交換電話網 (PSTN テスト) を有効にして、公衆交換電話網との接続を確認する場合は、ウォッチャーノードを設定するときに追加の構成を行う必要があります。 最初に、テストユーザーに PSTN テストの種類を関連付ける必要があります。 そのためには、Lync Server 管理シェルで次のようなコマンドを実行します。

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

このコマンドの結果は、変数に格納する必要があることに注意してください。 この例では、$pstnTest という名前の変数です。

この時点で、 **CsWatcherNodeConfiguration**コマンドレットを使用して、テストの種類 (可変 $pstnTest) を Lync Server 2013 プールに関連付けることができます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しいウォッチャーノード構成を作成し、前に作成した3つのテストユーザーを追加して、PSTN テストタイプも追加します。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Communicator ノードコンピューターに Lync Server core ファイルと RTCLocal データベースをインストールしていない場合は、上記のコマンドが失敗します。

複数のボイスポリシーをテストするには、**新しい-Csex・ Deddedtest**コマンドレットを使用して、各ポリシーの拡張テストを作成する必要があります。 このテストに割り当てられているユーザーは、目的の音声ポリシーで構成する必要があります。 その後、次のようなコマンドを使用して、拡張テストを**新しい-CsWatcherNodeConfiguration**コマンドレットに渡します。

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

CsWatcherNodeConfiguration が Tests パラメーターを使用せずに呼び出された場合は、既定の代理トランザクション (および指定された拡張合成トランザクション) だけが新しいウォッチャーノードに対して有効になることを意味します。 これは、ウォッチャーノードが次のコンポーネントをテストすることを意味します。

  - Registration

  - IM

  - GroupIM

  - P2PAV (ピアツーピアの音声/ビデオ セッション)

  - AvConference (音声/会議)

  - Presence

  - ABS (アドレス帳サービス)

  - ABWQ (アドレス帳 Web サービス)

  - PSTN (拡張テストとして指定された pstn ゲートウェイ通話)。 既定では、PSTN は無効になっています。 この場合、テストは、コマンドによって ExtendedTests パラメーターを使って PSTN が有効になっている場合にのみ有効になります。

これは、既定では次のコンポーネントがテストされないことを意味します。

  - AVEdgeConnectivity

  - MCXP2PIM (モバイル デバイス インスタント メッセージング)

  - ExumConnectivity (Exchange ユニファイド メッセージング)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

ウォッチャーノードが構成されると、 **CsWatcherNodeConfiguration**コマンドレットを使用して、ノードの合成トランザクションを追加または削除できます。 たとえば、監視ノードに PersistentChatMessage テストを追加するには Add メソッドと次のようなコマンドを使用します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

テスト名をコンマで区切ることにより、複数のテストを追加することができます。 次に例を示します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

このようなテスト (たとえば、DataConference) がウォッチャーノードで既に有効になっている場合は、エラーが発生します。 この場合、次のようなエラー メッセージが表示されます。

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

このエラーが発生した場合、変更は一切適用されません。 重複したテストを削除してコマンドを再実行する必要があります。

ウォッチャーノードから合成トランザクションを削除するには、Add メソッドの代わりに Remove メソッドを使います。 たとえば、次のコマンドでは、監視ノードから ABWQ テストを削除します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

また、Replace メソッドを使用して、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることもできます。 たとえば、watcher ノードで IM テストを実行する場合は、次のコマンドを使用してそれを構成できます。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

上のコマンドを実行すると、指定したウォッチャーノードのすべての代理トランザクションが、IM 以外は無効になります。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。<BR>Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" |選択-オブジェクト– ExpandProperty テスト |Sort-Object



</div>

ウォッチャーノードが作成されたことを確認するには、Lync Server 管理シェル内から次のコマンドを入力します。

    Get-CsWatcherNodeConfiguration

次のような情報が表示されます。

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

ウォッチャーノードが正しく構成されていることを確認するには、Lync Server 管理シェルで次のコマンドを入力します。

    Test-CsWatcherNodeConfiguration

上のコマンドを実行すると、展開の各ウォッチャーノードがテストされ、次のような情報がわかります。

  - 必要なレジストラー役割がインストールされました。

  - CsWatcherNodeConfiguration を実行したときに必要なレジストリキーが作成されました。

  - サーバーで、正しいバージョンの Lync Server が実行されている。

  - ポートが正しく構成されています。

  - 割り当てられたテストユーザーには、必要な資格情報があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

