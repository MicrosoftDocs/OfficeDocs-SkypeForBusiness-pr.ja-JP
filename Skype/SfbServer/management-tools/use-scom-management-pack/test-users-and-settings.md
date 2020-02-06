---
title: 監視ノードのテスト ユーザーおよび設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '概要: Skype for Business Server の代理トランザクションのテストユーザーアカウントとウォッチャーノード設定を構成します。'
ms.openlocfilehash: ce0c82f6f850c7a2b632c828f938979747d99e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816116"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>監視ノードのテスト ユーザーおよび設定の構成
 
**概要:** Skype for Business Server の代理トランザクションのテストユーザーアカウントとウォッチャーノード設定を構成します。
  
監視ノードとして動作するコンピューターを構成したら、次のことを行う必要があります。
  
1. これらのウォッチャーノードによって使用される[テストユーザーアカウントを構成](test-users-and-settings.md#testuser)します。 Negotiate の認証方法を使用している場合は、**Set-CsTestUserCredential** コマンドレットを使用し、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要もあります。
    
2. 監視ノード構成設定を更新します。
    
## <a name="configure-test-user-accounts"></a>テスト ユーザー アカウントの構成
<a name="testuser"> </a>

テストアカウントは、実際のユーザーを表す必要はありませんが、有効な Active Directory アカウントである必要があります。 また、これらのアカウントは、Skype for Business Server で有効にしておく必要があります。また、有効な SIP アドレスが必要であり、エンタープライズ Voip に対して有効になっている必要があります (テスト-CsPstnPeerToPeerCall 代理トランザクションを使う場合)。 
  
TrustedServer の認証方法を使用している場合に実行する必要があるのは、これらのアカウントが存在していることを確認し、説明に従って構成することのみです。 テスト対象の各プールについて、少なくとも2つのテストユーザーを割り当てる必要があります。 Negotiate 認証方法を使用している場合は、CsTestUserCredential コマンドレットと Skype for Business Server の管理シェルも使用して、これらのテストアカウントで代理トランザクションを操作できるようにする必要があります。 この操作を実行するには、次のようなコマンドを実行します (これらのコマンドは、2つの Active Directory ユーザーアカウントが作成され、これらのアカウントが Skype for Business Server に対して有効になっていることを前提としています)。
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

SIP アドレスだけでなくユーザー名とパスワードも含める必要があります。パスワードを含めない場合は、Set-CsTestUserCredential コマンドレットを実行したときに、この情報の入力が求められます。ユーザー名は、上記のコード ブロックのようにドメイン名\ユーザー名の形式を使用して指定できます。
  
テストユーザーの資格情報が作成されたことを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

次のような情報が各ユーザーに返されます。
  
|**Chap**|**パスワード**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |「  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使用した基本的な監視ノードの構成

テスト ユーザーが作成されたら、次のようなコマンドを使用して監視ノードを作成できます。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

このコマンドでは、既定の設定を使用し、既定の代理トランザクションのセットを実行する新しい監視ノードが作成されます。 新しいウォッチャーノードでは、テストユーザー watcher1@litwareinc.com と watcher2@litwareinc.com も使用されます。 ウォッチャーノードが TrustedServer 認証を使用している場合は、2つのテストアカウントで Active Directory と Skype for Business Server に対して有効なユーザーアカウントを有効にすることができます。 監視ノードが Negotiate 認証方法を使用している場合は、Set-CsTestUserCredential コマンドレットを使用してこれらのユーザー アカウントを監視ノードで有効にする必要もあります。
  
これらのステップでプールを直接ターゲット指定する代わりに、サインインするターゲット プールの自動検出が正しく構成されていることを確認するには
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>拡張テストの構成

公衆交換電話網との接続を検証する公衆交換電話網 (PSTN) テストを有効にする場合、監視ノードのセットアップ時に追加の構成を行う必要があります。最初に、テスト ユーザーを PSTN のテストの種類に関連付ける必要があります。これを行うには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> このコマンドの結果は変数に格納する必要があります。この例では、$pstnTest という名前の変数です。 
  
次に、 **CsWatcherNodeConfiguration**コマンドレットを使用して、テストの種類 (可変 $pstnTest) を Skype For business Server プールに関連付けます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しいウォッチャーノード構成を作成し、前に作成した2つのテストユーザーを追加して、PSTN テストの種類を追加します。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Skype for Business Server の中核となるファイルと RTCLocal データベースを監視ノード コンピューターにインストールしていない場合、上記のコマンドは失敗します。 
  
複数の音声ポリシーをテストするには、**New-CsExtendedTest** コマンドレットを使用して各ポリシーに拡張テストを作成する必要があります。このテストに割り当てられたユーザーは、目的の音声ポリシーを使用して構成する必要があります。次のようなコマンドを使用すると、拡張テストは **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。
  
-ExtendedTests @ {Add = $pstnTest 1、$pstnTest 2、$pstnTest 3}
  
Tests パラメーターを使用しないで **New-CsWatcherNodeConfiguration** コマンドレットを呼び出す場合、既定の代理トランザクション (および指定された拡張代理トランザクション) のみが新しい監視ノードで有効になります。このため、監視ノードは次のコンポーネントをテストします。
  
- Registration
    
- IM
    
- GroupIM
    
- P2PAV (ピアツーピアの音声/ビデオ セッション)
    
- AvConference (音声/会議)
    
- Presence
    
- ABS (アドレス帳サービス)
    
- ABWQ (アドレス帳 Web サービス)
    
また、次のコンポーネントは既定ではテストされません。
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange ユニファイド メッセージング)
    
- JoinLauncher
    
- MCXP2PIM (従来のモバイルデバイスのインスタントメッセージング)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (拡張テストとして指定された PSTN ゲートウェイ通話)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

監視ノードを構成した後は、Set-CsWatcherNodeConfiguration コマンドレットを使用してノードから代理トランザクションを追加または削除できます。たとえば、監視ノードに PersistentChatMessage テストを追加するには Add メソッドと次のようなコマンドを使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

テスト名をコンマで区切ることにより、複数のテストを追加することができます。次に例を示します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

これらのテストの 1 つまたは複数 (たとえば DataConference) が既に監視ノードで有効になっていた場合、エラーが発生します。この場合、次のようなエラー メッセージが表示されます。
  
Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.
  
このエラーが発生した場合、変更は一切適用されません。 重複するテストを削除してコマンドを再実行する必要があります。
  
監視ノードから代理トランザクションを削除するには、Remove メソッドを使用します。たとえば、次のコマンドでは、監視ノードから ABWQ テストを削除します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

また、Replace メソッドを使用すると、現在有効になっているすべてのテストを 1 つ以上の新しいテストに置き換えることができます。たとえば、1 つの監視ノードが IM テストを実行するようにする場合、次のコマンドを使用してこれを構成することができます。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

上記のコマンドを実行する場合、指定された監視ノードのすべての代理トランザクションでは IM 以外無効になります。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

上記のコマンドは、ノードに割り当てられている代理トランザクションに応じて次のような情報を返します。
  
登録 IM GroupIM AvConference プレゼンス PersistentChatMessage DataConference
> [!TIP]
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

監視ノードが作成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

次のような情報が表示されます。
  
Id: atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}<br/>
ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
ポート番号: 5061<br/>

監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

上記のコマンドでは、展開内の監視ノードをそれぞれテストし、次のような情報を提供します。
  
- 必要なレジストラー役割がインストールされています。
    
- 必要なレジストリキーが作成されます (CsWatcherNodeConfiguration コマンドレットを実行すると完了します)。
    
- お使いのサーバーで、正しいバージョンの Skype for Business Server が実行されています。
    
- ポートが正しく構成されています。
    
- 割り当てられたテストユーザーには、必要な資格情報があります。
    
## <a name="managing-watcher-nodes"></a>監視ノードの管理
<a name="testuser"> </a>

監視ノードで実行される代理トランザクションの変更に加え、管理者は **Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードを有効化または無効化すること、およびテストの実行時に内部 Web URL または外部 Web URL を使用するように監視ノードを構成すること、という他の 2 つの重要なタスクも実行できます。
  
既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。ただし、これらのトランザクションの中断が必要な場合があります。たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。ネットワーク接続がなければ、これらのトランザクションは失敗します。監視ノードを一時的に無効にする場合は、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

このコマンドは、監視ノード atl-watcher- 001.litwareinc.com での代理トランザクションの実行を無効にします。代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

このコマンドは、指定されたコンピューターからすべてのウォッチャーノードの構成設定を削除します。これにより、そのコンピューターは代理トランザクションを自動的に実行できなくなります。 ただし、このコマンドを実行しても、System Center agent ファイルまたは Skype for Business Server システムファイルはアンインストールされません。
  
既定では、監視ノードは、テストを実行するときに組織の外部 Web URL を使用します。ただし、監視ノードは、組織の内部 Web URL を使用するように構成することもできます。これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。監視ノードを外部 URL ではなく内部 URL を使用するように構成するには、UseInternalWebUrls プロパティを True ($True) に設定します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

このプロパティを既定値である False ($False) にリセットすると、監視ノードは外部 URL を使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>代理トランザクションの特別なセットアップ指示
<a name="special_synthetictrans"> </a>

大半の代理トランザクションは、監視ノード上でそのまま実行できます。ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されると、監視ノードはその代理トランザクションの使用をテスト パス中に直ちに開始できます。ただし、以降のセクションで説明するように、一部の代理トランザクションでは特別なセットアップが必要です。
  
### <a name="data-conferencing-synthetic-transaction"></a>データ会議代理トランザクション

監視ノード コンピューターが境界ネットワークの外部に配置されている場合は、以下の手順を実行してネットワーク サービス アカウントの Windows Internet Explorer® Internet ブラウザーでのプロキシ設定を最初に無効にしない限り、データ会議代理トランザクションはほぼ実行できません。
  
1. 監視ノード コンピューターで、[**スタート**] ボタン、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。
    
2. コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。 
    
```console
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

コマンド ウィンドウに次のようなメッセージが表示されます。
  
BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
Internet proxy settings for account NetworkService set to NO_PROXY. 
  
(connection = default)
  
このメッセージは、ネットワーク サービス アカウントの Internet Explorer プロキシ設定が無効になったことを意味します。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange ユニファイド メッセージング代理トランザクション

Exchange Unified Messaging (UM) 代理トランザクションは、テスト ユーザーが Exchange に属するボイスメール アカウントに接続できることを検証します。
  
これらのテスト ユーザーは、ボイスメール アカウントを使用して事前に構成しておく必要があります。 
  
### <a name="persistent-chat-synthetic-transaction"></a>常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、管理者は、まずチャネルを作成し、テスト ユーザーにチャネルを使用する許可を与える必要があります。
  
常設チャット代理トランザクションを使用して、このチャネルを構成できます。 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

このセットアップ タスクは、社内から実行する必要があります。
  
- サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、役割ベースのアクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーである必要があります。
    
- サーバー自体から実行する場合、コマンドレットを実行するユーザーは、RTCUniversalServerAdmins グループのメンバーである必要があります。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN ピアツーピア通話代理トランザクション

Test-CsPstnPeerToPeerCall 代理トランザクションは、公衆交換電話網 (PSTN) 経由で通話を発信および受信できるかどうか検証します。
  
この代理トランザクションを実行するには、管理者は以下を構成する必要があります。
  
- UC 用に有効化された 2 つのテスト ユーザー (発信者と受信者)。
    
- 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。
    
- 受信者の電話番号への通話を許可する VoIP ポリシーとボイスルーティング。 PSTN ゲートウェイに到達できます。
    
- PSTN ゲートウェイは、ダイヤル先のホームプールに着信を転送する通話とメディアを受信します。
    
### <a name="unified-contact-store-synthetic-transaction"></a>統合連絡先ストア代理トランザクション

統合連絡先ストアの代理トランザクションでは、Skype for Business Server が Exchange のユーザーの代わりに連絡先を取得できるかどうかを確認します。
  
この代理トランザクションを使用するには、次の条件を満たす必要があります。
  
- Lyss-Exchange サーバーからのサーバー認証が構成済みであることが必要です。
    
- テスト ユーザーが有効な Exchange メールボックスを持っている必要があります。
    
これらの条件が満たされた後、次の Windows PowerShell コマンドレットを実行して、テストユーザーの連絡先リストを Exchange に移行することができます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

テスト ユーザーの連絡先リストを Exchange に移行するには、ある程度の時間を要することがあります。 移行の進行状況を監視するために、次のコマンドラインは、セットアップフラグなしで実行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

移行が完了した後、このコマンドが成功するようになります。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 代理トランザクション

XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、XMPP 機能を 1 つ以上のフェデレーション ドメインで構成する必要があります。
  
XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターにルーティング可能な XMPP ドメインのユーザー アカントを指定する必要があります。 次に例を示します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

この例では、litwareinc.com のメッセージを XMPP ゲートウェイにルーティングするために、Skype for Business Server ルールが存在している必要があります。

> [!NOTE]
> XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Video Interop Server (VIS) 代理トランザクション

ビデオ相互運用機能サーバー (VIS) の代理トランザクションでは、代理トランザクションサポートファイル ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921)) をダウンロードしてインストールする必要があります。 
  
VISSTSupportPackage をインストールするには、msi の依存関係 (システム要件の下) が既にインストールされていることを確認します。 簡単なインストールを実行するには、VISSTSupportPackage を実行します。 .Msi は、次のパスにあるすべてのファイルをインストールします。 "%ProgramFiles%\VIS の代理トランザクションサポートパッケージ"。
  
VIS の代理トランザクションの実行方法の詳細については、 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx)コマンドレットのマニュアルを参照してください。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>代理トランザクションの実行頻度の変更
<a name="special_synthetictrans"> </a>

既定では、代理トランザクションは構成済みのユーザーに対して 15 分ごとに実行されます。 2 つの代理トランザクションが互いに競合することを防止するために、代理トランザクションはユーザー セットを対象にして順に実行されます。 すべての代理トランザクションが完了するように、より長い間隔が必要とされます。
  
定期的なトランザクションをより頻繁に実行する必要がある場合は、特定のユーザーのセットを使って実行される代理トランザクションの数を減らして、一定の時間帯にテストを完了できるようにします。これにより、ネットワークの遅延が発生する可能性があります。 代理トランザクションをさらに実行することが望ましい場合は、さらに多くの代理トランザクションを実行するためにユーザーセットを作成します。
  
代理トランザクションを実行する頻度を変更するには、次の手順を実行します。
  
1. System Center Operations Manager を開きます。 [Authoring] セクションをクリックします。 [ルール] セクション ([作成] の下) をクリックします。
    
2. [ルール] セクションで、"メインの代理トランザクションランナーパフォーマンスコレクションルール" という名前のルールを見つけます。
    
3. ルールを右クリックし、[上書き] を選択して、[ルールの上書き] を選択し、[クラスのすべてのオブジェクト] で [プールウォッチャー] を選びます。
    
4. [プロパティの上書き] ウィンドウで、[パラメーター名 "頻度"] を選び、[Override] の値を目的の値に設定します。
    
5. 同じウィンドウで、上書きを適用する必要がある管理パックを選びます。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>代理トランザクションのリッチ ログの使用
<a name="special_synthetictrans"> </a>

代理トランザクションは、システムの問題を特定する際に非常に役立つことが実証されてきました。 たとえば、Test-CsRegistration コマンドレットを使用して、ユーザーが Skype for Business Server に登録しようとするときに問題が発生していることを管理者に警告できます。 ただし、障害の実際の原因を突き止めるには、付加的な詳細が必要になることがあります。
  
この理由で、代理トランザクションはリッチ ログを提供しています。リッチ ログを使用すると、代理トランザクションが実行するアクティビティごとに次の情報が記録されます。
  
- アクティビティが開始した時間
    
- アクティビティが終了した時間
    
- 実行されたアクション (たとえば、電話会議の作成、参加、または終了、Skype for Business Server へのサインオン、インスタント メッセージの送信など)
    
- アクティビティの実行時に生成される情報、詳細、警告、またはエラーメッセージ。
    
- SIP 登録メッセージ
    
- アクティビティが行われたときに生成された例外レコードまたは診断コード
    
- アクティビティを実行した全体的な結果
    
代理トランザクションが実行されるたびに、この情報は自動的に生成されます。しかし、この情報は、自動的に表示されることや、ログ ファイルに保存されることはありません。手動で代理トランザクションを実行中の管理者は、OutLoggerVariable パラメーターを使用して、情報を保存する Windows PowerShell 変数を指定できます。次に、管理者は、2 つの方法のいずれかを使用して、リッチ ログのエラー メッセージを XML または HTML 形式で保存または表示できます。 
  
トラブルシューティング情報を収集するには、OutLoggerVariable パラメーターと、それに続く任意の変数名を指定します。
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 変数名の先頭に $ 文字を付けないでください。 $RegistrationTest ではなく、RegistrationTest のような変数名を使用します。 
  
このコマンドを実行すると、次のような出力が表示されます。
  
ターゲット Fqdn: atl-cs-001.litwareinc.com Result: エラー待ち時間: 00:00:00 エラーメッセージ: このコンピューターには、割り当てられている証明書がありません。 診断: このエラーの詳細情報にアクセスするには、ここに示すエラーメッセージだけでなく、さらに詳しい情報にアクセスできます。

この情報に HTML 形式でアクセスするには、以下のようなコマンドを使用して、変数 RegistrationTest に格納された情報を HTML ファイルに保存します。
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

これらのファイルは、Windows Internet Explorer、Microsoft Visual Studio、またはその他すべての HTML/XML ファイルを開けるアプリケーションで表示できます。
  
System Center Operations Manager の内部で実行される代理トランザクションでは、エラーのログファイルが自動的に生成されます。 しかし、Skype for Business Server PowerShell が読み込まれて代理トランザクションを行う前に、実行が失敗した場合、これらのログは生成されません。 
  
> [!IMPORTANT]
> 既定では、Skype for Business Server は共有されていないフォルダーにログファイルを保存します。 これらのログを簡単にアクセスできるようにするには、このフォルダーを共有する必要があります。 たとえば、litwareinc \\のようになります。 com\WatcherNode. 
