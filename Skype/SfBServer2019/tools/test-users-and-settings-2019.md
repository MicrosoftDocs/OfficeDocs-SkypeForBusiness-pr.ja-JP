---
title: 監視ノードのテストユーザーと設定を構成する
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 代理トランザクションのテストユーザーアカウントと監視ノード設定を構成します。'
ms.openlocfilehash: f13680d16a248be339ee7cd4a085d7d0894146dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033676"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>監視ノードのテストユーザーと設定を構成する
 
**概要:** Skype for Business Server 代理トランザクションのテストユーザーアカウントと監視ノード設定を構成します。
  
監視ノードとして動作するコンピューターを構成した後、次のことを行う必要があります。
  
1. これらの監視ノードで使用される[テストユーザーアカウントを構成](test-users-and-settings-2019.md#testuser)します。 Negotiate の認証方法を使用している場合は、 **set-cstestusercredential**コマンドレットを使用して、監視ノードで使用するためにこれらのテストアカウントを有効にする必要もあります。
    
2. 監視ノードの構成設定を更新します。
    
## <a name="configure-test-user-accounts"></a>テストユーザーアカウントを構成する
<a name="testuser"> </a>

テストアカウントは、実際のユーザーを表す必要はありませんが、有効な Active Directory アカウントである必要があります。 さらに、これらのアカウントは Skype for Business Server に対して有効にする必要があり、有効な SIP アドレスを持っている必要があります。また、エンタープライズ Voip を有効にする必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使用する場合)。 
  
TrustedServer の認証方法を使用している場合は、これらのアカウントが存在していることを確認してから、前述のように構成する必要があります。 テストする各プールについて、少なくとも3つのテストユーザーを割り当てる必要があります。 Negotiate の認証方法を使用している場合は、これらのテストアカウントが代理トランザクションと連携できるようにするには、Set-cstestusercredential コマンドレットと Skype for Business Server 管理シェルも使用する必要があります。 これを行うには、次のようなコマンドを実行します (これらのコマンドは、3つの Active Directory ユーザーアカウントが作成されており、これらのアカウントが Skype for Business Server で有効になっていることを前提としています)。
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があります。 パスワードを指定しない場合は、Set-cstestusercredential コマンドレットによってその情報の入力を求められます。 ユーザー名は、前述のコードブロックに示されているドメインの name\user 名の形式を使用して指定できます。
  
テストユーザーの資格情報が作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

次のような情報が各ユーザーに返されます。
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.security.securestring  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使用した基本的な監視ノードの構成

テストユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

このコマンドは、既定の設定を使用し、代理トランザクションの既定のセットを実行する新しい監視ノードを作成します。 新しい監視ノードは、テストユーザー watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com も使用します。 監視ノードが TrustedServer 認証を使用する場合、3つのテストアカウントは、Active Directory と Skype for Business Server に対して有効になっている任意の有効なユーザーアカウントにすることができます。 監視ノードが Negotiate 認証方法を使用している場合は、Set-cstestusercredential コマンドレットを使用して、監視ノードについてもこれらのユーザーアカウントを有効にする必要があります。
  
サインインするターゲットプールの自動検出が適切に構成されているかどうかを検証するには、プールを直接対象とせずに、次の手順を実行します。
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>拡張テストの構成

PSTN テストを有効にして、公衆交換電話網との接続を確認する場合は、監視ノードを設定するときに追加の構成を行う必要があります。 最初に、Skype for Business Server 管理シェルから次のようなコマンドを実行して、テストユーザーを PSTN テストの種類に関連付けます。
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> このコマンドの結果は、変数に格納する必要があります。 この例では、変数に $pstnTest という名前が付けられています。 
  
次に、 **set-cswatchernodeconfiguration**コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納されている) を Skype For business Server プールに関連付けることができます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しい監視ノード構成を作成し、以前に作成した3つのテストユーザーを追加して、PSTN テストの種類を追加します。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Skype for Business Server のコアファイルおよび RTCLocal データベースを監視ノードコンピューターにインストールしていない場合、上記のコマンドは失敗します。 
  
複数の音声ポリシーをテストするには、**新しい-Csexthe dedtest**コマンドレットを使用して、各ポリシーの拡張テストを作成することができます。 提供されるユーザーは、目的の音声ポリシーを使用して構成する必要があります。 拡張テストは、次のようなコンマ区切り記号を使用して**set-cswatchernodeconfiguration**コマンドレットに渡されます。
  
-ExtendedTests @ {Add = $pstnTest 1、$pstnTest 2、$pstnTest 3}
  
**Set-cswatchernodeconfiguration**コマンドレットは、Tests パラメーターを使用せずに呼び出されたので、既定の代理トランザクション (および指定された拡張代理トランザクション) だけが新しい監視ノードで有効になります。 そのため、監視ノードは次のコンポーネントをテストします。
  
- レジスタ
    
- IM
    
- GroupIM
    
- P2PAV (ピアツーピアの音声ビデオセッション)
    
- AvConference (音声/会議)
    
- プレゼンス
    
- ABS (アドレス帳サービス)
    
- ABWQ (アドレス帳 web サービス)
    
既定では、次のコンポーネントはテストされません。
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- ダイヤルイン会議
    
- ExumConnectivity (Exchange ユニファイドメッセージング)
    
- JoinLauncher
    
- MCXP2PIM (従来のモバイルデバイスインスタントメッセージング)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (拡張テストとして指定された pstn ゲートウェイ通話)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

監視ノードの構成後、Set-cswatchernodeconfiguration コマンドレットを使用して、ノードの代理トランザクションを追加または削除できます。 たとえば、監視ノードに PersistentChatMessage テストを追加するには、Add メソッドと次のようなコマンドを使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

テスト名をコンマで区切ることで、複数のテストを追加できます。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

これらのテストの1つ以上 (たとえば、DataConference) が既に監視ノードで有効になっている場合は、エラーが発生します。 この場合、次のようなエラーメッセージが表示されます。
  
Set-cswatchernodeconfiguration: ' urn: schema: Watchernode.msi: TestName ' キーまたは一意の id 制約に対して、重複するキーシーケンス ' DataConference ' が存在しています。
  
このエラーが発生した場合、変更は適用されません。 重複するテストを削除した状態でコマンドを再度実行する必要があります。
  
監視ノードから代理トランザクションを削除するには、Remove メソッドを使用します。 たとえば、次のコマンドを実行すると、監視ノードから ABWQ テストが削除されます。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace メソッドを使用すると、現在有効になっているすべてのテストを1つまたは複数の新しいテストに置き換えることができます。 たとえば、監視ノードが IM テストのみを実行するように構成するには、次のコマンドを使用してそれを構成します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

このコマンドを実行すると、指定された監視ノードのすべての代理トランザクションは IM 以外は無効になります。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

このコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。
  
Registration IM GroupIM P2PAV AvConference プレゼンス PersistentChatMessage DataConference
> [!TIP]
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

監視ノードが作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

次のような情報が表示されます。
  
Identity: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...} ExtendedTests: {TestUsers = IList<System.string>;Name = PSTN テスト;Te...} TargetFqdn: atl-cs-001.litwareinc.com ポート: 5061To 監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

このコマンドは、展開内の各監視ノードをテストし、次の操作が完了したかどうかを確認します。
  
- 必要なレジストラーの役割がインストールされている
    
- 必要なレジストリキーが作成されます (Set-cswatchernodeconfiguration コマンドレットを実行したときに完了)。
    
- サーバーが正しいバージョンの Skype for Business Server を実行している
    
- ポートが正しく構成されている
    
- 割り当てられたテストユーザーが必要な資格情報を持っている
    
## <a name="managing-watcher-nodes"></a>監視ノードの管理
<a name="testuser"> </a>

監視ノードで実行される代理トランザクションの変更に加えて、 **set-cswatchernodeconfiguration**コマンドレットを使用して、監視ノードの有効化と無効化、およびテストの実行時に内部 web url または外部 web url のいずれかを使用する監視ノードの構成を実行することもできます。
  
既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。 ただし、これらのトランザクションを中断する必要がある場合もあります。 たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。 ネットワーク接続がない場合、これらのトランザクションは失敗します。 監視ノードを一時的に無効にするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

このコマンドは、監視ノードの atl 監視001.litwareinc.com で代理トランザクションの実行を無効にします。 代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。 監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

このコマンドは、指定されたコンピューターからすべての監視ノード構成設定を削除します。これにより、そのコンピューターは代理トランザクションを自動的に実行することができなくなります。 ただし、このコマンドを実行しても、System Center エージェントファイルまたは Skype for Business Server システムファイルはアンインストールされません。
  
既定では、監視ノードはテストを実施するときに組織の外部 Web Url を使用します。 ただし、監視ノードは、組織の内部 Web Url を使用するように構成することもできます。 これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。 外部 Url の代わりに内部 Url を使用するように監視ノードを構成するには、UseInternalWebURls プロパティを True ($True) に設定します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

このプロパティを既定値の False ($False) にリセットすると、ウォッチャーが再び外部 Url を使用するようになります。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>代理トランザクションの特別なセットアップ指示
<a name="special_synthetictrans"> </a>

ほとんどの代理トランザクションは、監視ノードでそのように実行できます。 ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテストパス中にすぐに開始できます。 ただし、以下のセクションで説明するように、特別なセットアップ手順を必要とする代理トランザクションがいくつかあります。
  
### <a name="data-conferencing-synthetic-transaction"></a>データ会議代理トランザクション

監視ノードコンピューターが境界ネットワークの外部に配置されている場合、最初にネットワークの Internet browser プロキシ設定® Windows Internet Explorer を無効にした場合を除き、データ会議の代理トランザクションを実行できないことがあります。サービスアカウントの場合は、次の手順を実行します。
  
1. 監視ノードコンピューターで、[**スタート**] ボタン、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンドプロンプト**] を右クリックし、[**管理者として実行**] をクリックします。
    
2. コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

コマンドウィンドウに次のメッセージが表示されます。
  
BITSAdmin は廃止され、今後のバージョンの Windows では使用できないことが保証されていません。 Bits サービスの管理ツールは、BITS PowerShell コマンドレットによって提供されるようになりました。
  
アカウント NetworkService のインターネットプロキシ設定が NO_PROXY に設定されています。 
  
(connection = default)
  
このメッセージは、ネットワークサービスアカウントの Internet Explorer プロキシ設定が無効になっていることを示しています。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange ユニファイドメッセージング代理トランザクション

Exchange ユニファイドメッセージング (UM) 代理トランザクションは、テストユーザーが Exchange に所属しているボイスメールアカウントに接続できることを確認します。
  
テストユーザーは、ボイスメールアカウントを使用して事前に構成する必要があります。 
  
### <a name="persistent-chat-synthetic-transaction"></a>常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、まずチャネルを作成し、それを使用するためのアクセス許可をテストユーザーに付与する必要があります。
  
常設チャット代理トランザクションを使用して、このチャネルを構成できます。 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

このセットアップタスクは、エンタープライズ内部から実行する必要があります。
  
- サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーである必要があります。
    
- サーバー自体から実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN ピアツーピア通話代理トランザクション

テスト-CsPstnPeerToPeerCall 代理トランザクションは、公衆交換電話網 (PSTN) を使用して通話を発信および受信できるかどうかを確認します。
  
この代理トランザクションを実行するには、次のものを構成する必要があります。
  
- 2つの UC 対応テストユーザー (発信者と受信者)。
    
- 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。
    
- 受信者の番号への通話が PSTN ゲートウェイに到達できるようにする VoIP ポリシーと音声ルート。
    
- 通話を受信し、ダイヤルされた番号に基づいて受信者のホームプールに通話を戻す PSTN ゲートウェイ。
    
### <a name="unified-contact-store-synthetic-transaction"></a>統合連絡先ストア代理トランザクション

統合連絡先ストア代理トランザクションは、Exchange からユーザーの代わりに、Skype for Business Server が連絡先を取得できるかどうかを確認します。
  
この代理トランザクションを使用するには、次の条件を満たす必要があります。
  
- 一 ss-Exchange サーバーからサーバーへの認証を構成する必要があります。
    
- テストユーザーは、有効な Exchange メールボックスを持っている必要があります。
    
これらの条件が満たされたら、次の Windows PowerShell コマンドレットを実行して、テストユーザーの連絡先リストを Exchange に移行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

テストユーザーの連絡先リストが Exchange に移行されるまでに時間がかかる場合があります。 移行の進行状況を監視するために、-Setup フラグを使用せずに、同じコマンドラインを実行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

このコマンドラインは、移行が完了した後に成功します。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 代理トランザクション

拡張メッセージングおよびプレゼンスプロトコル (XMPP) IM 代理トランザクションでは、XMPP 機能を1つ以上のフェデレーションドメインで構成する必要があります。
  
XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターに、ルーティング可能な XMPP ドメインのユーザーアカウントを指定する必要があります。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Skype for Business Server ルールが存在している必要があります。

> [!NOTE]
> XMPP ゲートウェイおよびプロキシは、Skype for business Server 2015 で使用できましたが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細については、「 [XMPP フェデレーションの移行](../migration/migrating-xmpp-federation.md)」を参照してください。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>ビデオ相互運用サーバー (VIS) 代理トランザクション

ビデオ相互運用サーバー (VIS) 代理トランザクションを使用するには、代理トランザクションサポートファイル ([VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921)) をダウンロードしてインストールする必要があります。 
  
VISSTSupportPackage をインストールするには、msi の依存関係 (システム要件の下) が既にインストールされていることを確認してください。 VISSTSupportPackage を実行して、単純なインストールを実行します。 .Msi は、次のパスにあるすべてのファイルをインストールします。 "%ProgramFiles%\VIS 代理トランザクションサポートパッケージ"。
  
VIS 代理トランザクションの実行方法の詳細については、 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx)コマンドレットのドキュメントを参照してください。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>代理トランザクションの実行頻度の変更
<a name="special_synthetictrans"> </a>

既定では、代理トランザクションは構成済みのユーザーと共に15分ごとに実行されます。 代理トランザクションは、2つの代理トランザクションが互いに競合しないように、一連のユーザーの間で順次実行されます。 すべての代理トランザクションの完了時間を提供するには、より長い間隔が必要です。
  
代理トランザクションをより頻繁に実行することが望ましい場合は、特定のユーザーセットで実行される代理トランザクションの数を減らす必要があります。これにより、一定の時間範囲内で、長時間のネットワーク遅延のためのバッファーを使用してテストを完了できるようになります。 代理トランザクションをさらに実行する必要がある場合は、追加の代理トランザクションを実行するために、より多くのユーザーセットを作成します。
  
代理トランザクションが実行される頻度を変更するには、次の手順を実行します。
  
1. System Center Operations Manager を開きます。 [作成] セクションをクリックします。 [ルール] セクションをクリックします (作成中)。
    
2. [ルール] セクションで、"Main 代理トランザクションランナー Performance Collection Rule" という名前のルールを見つけます。
    
3. ルールを右クリックして [上書き] を選択し、[ルールを上書きする] を選択して、[クラスのすべてのオブジェクト] で [プール監視] を選択します。
    
4. [プロパティのオーバーライド] ウィンドウで、[パラメーター名 "頻度"] を選択し、Override 値を目的の値に設定します。
    
5. 同じウィンドウで、この上書きを適用する必要がある管理パックを選択します。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>代理トランザクションのリッチ ログの使用
<a name="special_synthetictrans"> </a>

代理トランザクションは、システムの問題を特定するのに役立つように、非常に役に立ちます。 たとえば、ユーザーが Skype for Business Server に登録するのに苦労していたことを管理者に通知するには、Test-CsRegistration コマンドレットを使用します。 ただし、エラーの実際の原因を特定するには、追加の詳細が必要な場合があります。
  
このため、代理トランザクションには豊富なログ記録が用意されています。 リッチログを使用すると、代理トランザクションが undertakes するアクティビティごとに、次の情報が記録されます。
  
- アクティビティが開始された時刻。
    
- アクティビティが終了した時刻。
    
- 実行されたアクション (会議の作成、参加、または退室、Skype for Business Server へのサインオン、インスタントメッセージの送信など)。
    
- アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ
    
- SIP 登録メッセージ。
    
- アクティビティの実行時に生成された例外レコードまたは診断コード。
    
- アクティビティを実行した最終的な結果。
    
この情報は、代理トランザクションが実行されるたびに自動的に生成されますが、自動的に表示されたり、ログファイルに保存されたりすることはありません。 代理トランザクションを手動で実行している場合は、OutLoggerVariable パラメーターを使用して、情報を格納する Windows PowerShell 変数を指定できます。 そこから、2つの方法のいずれかを使用して、リッチログのエラーメッセージを XML 形式または HTML 形式で保存したり、表示したりすることができます。 
  
トラブルシューティング情報を取得するには、OutLoggerVariable パラメーターを指定し、その後に任意の変数名を指定します。
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : 変数名の先頭に $ 記号を付けないでください。 RegistrationTest ($RegistrationTest ではない) などの変数名を使用します。 
  
このコマンドを実行すると、次のような出力が表示されます。
  
ターゲット Fqdn: atl-cs-001.litwareinc.com Result: エラー待機時間: 00:00:00 エラーメッセージ: このコンピューターには、割り当てられた証明書がありません。 診断: このエラーの詳細については、ここに示すエラーメッセージだけではなく、さらに多くの情報にアクセスできます。 HTML 形式でこの情報にアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に格納されている情報を HTML ファイルに保存します。
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

これらのファイルを表示するには、Windows Internet Explorer、Microsoft Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使用します。
  
System Center Operations Manager の内部から実行される代理トランザクションは、エラーが発生したときにこれらのログファイルを自動的に生成します。 これらのログは、Skype for Business Server PowerShell が代理トランザクションを読み込んで実行できるようになる前に、実行が失敗した場合は生成されません。 
  
> [!IMPORTANT]
> 既定では、Skype for Business Server は、共有されていないフォルダーにログファイルを保存します。 これらのログに容易にアクセスできるようにするには、このフォルダーを共有する必要があります。 次に例\\を示します。 litwareinc。 com\WatcherNode. 
