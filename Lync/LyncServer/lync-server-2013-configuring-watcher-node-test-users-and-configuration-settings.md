---
title: 監視ノードのテストユーザーと構成設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ecb6946bcbb7244ef3e5ef8504312063ab1bd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507524"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で監視ノードのテストユーザーと構成設定を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-29_

監視ノードとして動作するコンピューターを構成した後、次のことを行う必要があります。

1.  これらの監視ノードによって使用されるテストアカウントを作成します。 Negotiate の認証方法を使用している場合は、 [set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) コマンドレットを使用して、監視ノードで使用するためにこれらのテストアカウントを有効にする必要もあります。

2.  監視ノードの構成設定を更新します。

このセクションの内容は次のとおりです。

  - テストユーザーアカウントを構成する

  - 既定の代理トランザクションを使用した基本的な監視ノードの構成

  - 拡張テストの構成

  - 代理トランザクションの追加と削除

  - 監視ノード構成の表示とテスト

<div>

## <a name="configuring-test-user-accounts"></a>テストユーザーアカウントを構成する

テストユーザーは、実際の人物を表す必要はありませんが、有効な Active Directory ドメインサービスアカウントである必要があります。さらに、これらのアカウントは Lync Server 2013 に対して有効にする必要があり、有効な SIP アドレスを持っている必要があり、エンタープライズ Voip (Test-CsPstnPeerToPeerCall 代理トランザクションを使用するため) を有効にする必要があります。 TrustedServer の認証方法を使用する場合は、これらのアカウントが存在し、ここで指定したとおりに構成されていることを確認するだけで済みます。 テストする各プールについて、少なくとも3つのテストユーザーを割り当てる必要があります。

Negotiate の認証方法を使用している場合は、 **set-cstestusercredential** コマンドレットと Lync Server 管理シェルも使用して、これらのテストアカウントが代理トランザクションと連携できるようにする必要があります。 これを行うには、次のようなコマンドを実行します。 (これらのコマンドは、3つの Active Directory ユーザーアカウントが既に作成されており、これらのアカウントが Lync Server 2013 に対して有効になっていることを前提としています)。

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があることに注意してください。 パスワードを指定しない場合 Set-CsTestUserCredential はその情報を入力するように求められます。 ユーザー名を指定するには、上記のドメイン名のユーザー名の形式を使用する \\ か、またはユーザー name@domain 名の形式を使用します。たとえば、次のようにします。

    -UserName "watcher3@litwareinc.com"

テストユーザーの資格情報が作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを実行します。

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

次のような情報が各ユーザーに返されます。

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使用した基本的な監視ノードの構成

テストユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

このコマンドは、既定の設定を使用し、代理トランザクションの既定のセットを実行する新しい監視ノードを作成します。 新しい監視ノードは、テストユーザー watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com も使用します。 監視ノードが TrustedServer 認証を使用している場合、3つのテストアカウントは、Active Directory および Lync Server に対して有効になっている任意の有効なユーザーアカウントにすることができます。 監視ノードが Negotiate 認証方法を使用している場合は、 **set-cstestusercredential** コマンドレットを使用して、監視ノードに対してこれらのユーザーアカウントを有効にする必要もあります。

</div>

<div>

## <a name="configuring-extended-tests"></a>拡張テストの構成

公衆交換電話網との接続を確認する公衆交換電話網 (PSTN テスト) を有効にする場合は、監視ノードを設定するときに追加の構成を行う必要があります。 最初に、テストユーザーを PSTN テストの種類に関連付ける必要があります。 そのためには、Lync Server 管理シェルで次のようなコマンドを実行します。

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

このコマンドの結果は変数に格納する必要があることに注意してください。 この例では、$pstnTest という名前の変数です。

この時点で、 **set-cswatchernodeconfiguration** コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納されている) を Lync Server 2013 プールに関連付けることができます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しい監視ノード構成を作成し、以前に作成した3つのテストユーザーを追加し、さらに PSTN テストの種類も追加します。

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

なお、監視ノードコンピューターに Lync Server コアファイルと RTCLocal データベースをインストールしていない場合は、上記のコマンドは失敗します。

複数の音声ポリシーをテストするには、 **新しい-Csexthe dedtest** コマンドレットを使用して、各ポリシーの拡張テストを作成する必要があります。 このテストに割り当てられているユーザーは、目的の音声ポリシーを使用して構成する必要があります。 拡張テストは、次のようなコマンドを使用して、 **set-cswatchernodeconfiguration** コマンドレットに渡されます。

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

New-CsWatcherNodeConfiguration が Tests パラメーターを使用せずに呼び出された場合は、既定の代理トランザクション (および指定された拡張代理トランザクション) だけが新しい監視ノードに対して有効になることを意味します。 これは、監視ノードが次のコンポーネントをテストすることを意味します。

  - Registration

  - IM

  - GroupIM

  - P2PAV (ピアツーピアの音声ビデオセッション)

  - AvConference (音声/会議)

  - プレゼンス

  - ABS (アドレス帳サービス)

  - ABWQ (アドレス帳 web サービス)

  - PSTN (PSTN ゲートウェイ呼び出し。拡張テストとして指定されます。 既定では、PSTN は無効になっています。 この場合、このテストは、コマンドが ExtendedTests パラメーターを使用して PSTN を有効にしている場合にのみ有効になります。

これは、次のコンポーネントが既定ではテストされないことも意味します。

  - AVEdgeConnectivity

  - MCXP2PIM (モバイルデバイスインスタントメッセージング)

  - ExumConnectivity (Exchange ユニファイドメッセージング)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

監視ノードの構成後、 **set-cswatchernodeconfiguration** コマンドレットを使用して、ノードの代理トランザクションを追加または削除できます。 たとえば、監視ノードに PersistentChatMessage テストを追加するには、Add メソッドと次のようなコマンドを使用します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

テスト名をコンマで区切ることで、複数のテストを追加できます。 以下に例を示します。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

これらのテストの1つ以上 (たとえば、DataConference) が既に監視ノードで有効になっている場合は、エラーが発生することに注意してください。 この場合、次のようなエラーメッセージが表示されます。

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

このエラーが発生した場合、変更は適用されません。 重複するテストを削除してコマンドを再実行する必要があります。

監視ノードから代理トランザクションを削除するには、Add メソッドではなく Remove メソッドを使用します。 たとえば、次のコマンドを実行すると、監視ノードから ABWQ テストが削除されます。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Replace メソッドを使用して、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることもできます。 たとえば、監視ノードのみが IM テストを実行するようにする場合は、次のコマンドを使用してそれを構成できます。

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

上記のコマンドを実行すると、指定された監視ノードのすべての代理トランザクションは IM 以外は無効になります。

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
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。<BR>Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" |Select-Object-ExpandProperty テスト |Sort-Object



</div>

監視ノードが作成されたことを確認するには、Lync Server 管理シェルで次のコマンドを入力します。

    Get-CsWatcherNodeConfiguration

次のような情報が表示されます。

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

監視ノードが正しく構成されていることを確認するには、Lync Server 管理シェルで次のコマンドを入力します。

    Test-CsWatcherNodeConfiguration

上記のコマンドにより、展開内の各監視ノードがテストされ、次のような情報がわかります。

  - 必要なレジストラーの役割がインストールされている。

  - Set-cswatchernodeconfiguration を実行したときに必要なレジストリキーが作成されました。

  - サーバーで適切なバージョンの Lync Server が実行されている。

  - ポートが正しく構成されている。

  - 割り当てられたテストユーザーが必要な資格情報を持っている。

</div>

</div>

<span> </span>

</div>

</div>

</div>

