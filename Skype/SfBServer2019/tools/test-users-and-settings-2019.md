---
title: 監視ノードのテスト ユーザーと設定を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。'
ms.openlocfilehash: fc581b5f9624d28e8cbeb906832dfcfba3fd19dd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120366"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>監視ノードのテスト ユーザーと設定を構成する
 
**概要:** Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。
  
監視ノードとして機能するコンピューターを構成したら、次の手順を実行する必要があります。
  
1. [これらの監視ノードで](test-users-and-settings-2019.md#testuser) 使用するテスト ユーザー アカウントを構成します。 ネゴシエート認証方法を使用している場合は **、Set-CsTestUserCredential** コマンドレットを使用して、監視ノードでこれらのテスト アカウントを使用する必要があります。
    
2. 監視ノードの構成設定を更新します。
    
## <a name="configure-test-user-accounts"></a>テスト ユーザー アカウントの構成
<a name="testuser"> </a>

テスト アカウントは実際のユーザーを表す必要はありません。ただし、有効な Active Directory アカウントである必要があります。 さらに、これらのアカウントは Skype for Business Server で有効にする必要があります。有効な SIP アドレスを持っている必要があります。エンタープライズ VoIP (代理トランザクションを使用するには) Test-CsPstnPeerToPeerCall に対して有効にする必要があります。 
  
TrustedServer 認証方法を使用している場合は、これらのアカウントが存在し、これらのアカウントを構成する必要があります。 テストするプールごとに、少なくとも 3 人のテスト ユーザーを割り当てる必要があります。 ネゴシエート認証方法を使用している場合は、Set-CsTestUserCredential コマンドレットと Skype for Business Server 管理シェルを使用して、これらのテスト アカウントが代理トランザクションで動作する必要があります。 これを行うには、次のようなコマンドを実行します (これらのコマンドは、3 つの Active Directory ユーザー アカウントが作成され、これらのアカウントが Skype for Business Server で有効になっていると仮定します)。
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があります。 パスワードを含めない場合は、Set-CsTestUserCredentialを入力するように求められます。 ユーザー名は、前のコード ブロックに示されているドメイン名\ユーザー名形式を使用して指定できます。
  
テスト ユーザー資格情報が作成されたと確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

このような情報は、ユーザーごとに返されます。
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使用して基本監視ノードを構成する

テスト ユーザーが作成された後、次のようなコマンドを使用して監視ノードを作成できます。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

このコマンドは、既定の設定を使用し、代理トランザクションの既定のセットを実行する新しい監視ノードを作成します。 新しい監視ノードでは、テスト ユーザーが watcher1@litwareinc.com、watcher2@litwareinc.com、および watcher3@litwareinc.com。 監視ノードが TrustedServer 認証を使用する場合、3 つのテスト アカウントには、Active Directory および Skype for Business Server で有効な任意の有効なユーザー アカウントを指定できます。 監視ノードでネゴシエート認証方法を使用する場合は、監視ノードに対してこれらのユーザー アカウントも有効にするSet-CsTestUserCredentialがあります。
  
プールを直接対象とするのではなく、サインインするターゲット プールの自動検出が正しく構成されていることを検証するには、代わりに次の手順を使用します。
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>拡張テストの構成

公衆交換電話網との接続を確認する PSTN テストを有効にする場合は、監視ノードをセットアップするときに追加の構成を行う必要があります。 最初に、Skype for Business Server 管理シェルから次のようなコマンドを実行して、テスト ユーザーを PSTN テストの種類に関連付ける必要があります。
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> このコマンドの結果は変数に格納する必要があります。 この例では、変数の名前は $pstnTest。 
  
次に **、New-CsWatcherNodeConfiguration** コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納されている) を Skype for Business Server プールに関連付けできます。 たとえば、次のコマンドは、プール atl-cs-001.litwareinc.com の新しい監視ノード構成を作成し、前に作成した 3 人のテスト ユーザーを追加し、PSTN テストの種類を追加します。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

監視ノード コンピューターに Skype for Business Server コア ファイルと RTCLocal データベースをインストールしていない場合、上記のコマンドは失敗します。 
  
複数の音声ポリシーをテストするには **、New-CsExtendedTest** コマンドレットを使用して、ポリシーごとに拡張テストを作成できます。 提供されるユーザーは、目的の音声ポリシーで構成する必要があります。 拡張テストは、次のようなコンマ区切り文字を使用して **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
**New-CsWatcherNodeConfiguration** コマンドレットは Tests パラメーターを使用せずに呼び出されたため、新しい監視ノードでは既定の代理トランザクション (および指定した拡張代理トランザクション) だけが有効になります。 したがって、監視ノードは次のコンポーネントをテストします。
  
- 登録
    
- IM
    
- GroupIM
    
- P2PAV (ピアツーピアのオーディオ/ビデオ セッション)
    
- AvConference (電話/会議)
    
- プレゼンス
    
- ABS (アドレス帳サービス)
    
- ABWQ (アドレス帳 Web サービス)
    
既定では、次のコンポーネントはテストされません。
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange ユニファイド メッセージング)
    
- JoinLauncher
    
- MCXP2PIM (従来のモバイル デバイス インスタント メッセージング)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN ゲートウェイ呼び出し、拡張テストとして指定)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

監視ノードが構成された後、Set-CsWatcherNodeConfiguration コマンドレットを使用して、ノードに代理トランザクションを追加または削除できます。 たとえば、PersistentChatMessage テストを監視ノードに追加するには、Add メソッドと次のようなコマンドを使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

複数のテストを追加するには、コンマを使用してテスト名を区切ります。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

これらのテストの 1 つ以上 (DataConference など) が監視ノードで既に有効になっている場合、エラーが発生します。 この場合、次のようなエラー メッセージが表示されます。
  
Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' キーまたは一意の ID 制約の重複キー シーケンス 'DataConference' があります。
  
このエラーが発生すると、変更は適用されません。 このコマンドは、重複するテストを削除して再実行する必要があります。
  
監視ノードから代理トランザクションを削除するには、Remove メソッドを使用します。 たとえば、このコマンドは監視ノードから ABWQ テストを削除します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace メソッドを使用すると、現在有効なすべてのテストを 1 つ以上の新しいテストに置き換できます。 たとえば、監視ノードで IM テストのみを実行する場合は、次のコマンドを使用して構成できます。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

このコマンドを実行すると、指定された監視ノード上のすべての代理トランザクションは、IM を除いて無効になります。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示する場合は、次のようなコマンドを使用します。
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

このコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。
  
登録 IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> 代理トランザクションをアルファベット順に表示するには、代わりに次のコマンドを使用します。 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

監視ノードが作成されたと確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

次のような情報を取得します。
  
Id : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com、sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test;Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061 監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

このコマンドは、展開内の各監視ノードをテストし、次のアクションが完了したかどうかを確認します。
  
- 必要なレジストラーの役割がインストールされている
    
- 必要なレジストリ キーが作成されます (このコマンドレットを実行Set-CsWatcherNodeConfiguration完了)
    
- サーバーが正しいバージョンの Skype for Business Server を実行している
    
- ポートが正しく構成されている
    
- 割り当てられたテスト ユーザーが必要な資格情報を持っている
    
## <a name="managing-watcher-nodes"></a>監視ノードの管理
<a name="testuser"> </a>

監視ノードで実行される代理トランザクションの変更に加えて **、Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードの有効化と無効化、テストの実行中に内部 Web URL または外部 Web URL を使用する監視ノードの構成という 2 つの重要なタスクを実行することもできます。
  
既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。 ただし、これらのトランザクションを中断する場合があります。 たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。 ネットワーク接続がない場合、これらのトランザクションは失敗します。 監視ノードを一時的に無効にするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

このコマンドを実行すると、監視ノード atl 監視ノードでの代理トランザクションの実行が 001.litwareinc.com。 代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。 監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

このコマンドを実行すると、指定したコンピューターから監視ノード構成設定すべてが削除され、そのコンピューターが代理トランザクションを自動的に実行できません。 ただし、このコマンドは System Center エージェント ファイルや Skype for Business Server システム ファイルをアンインストールしません。
  
既定では、監視ノードはテストを実行するときに組織の外部 Web URL を使用します。 ただし、監視ノードは、組織の内部 Web URL を使用するように構成することもできます。 これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。 外部 URL の代わりに内部 URL を使用する監視ノードを構成するには、UseInternalWebURls プロパティを True ($True) に設定します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

このプロパティを既定値の False ($False) にリセットすると、ウォッチャーは再び外部 URL を使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>代理トランザクションの特別なセットアップ指示
<a name="special_synthetictrans"> </a>

ほとんどの代理トランザクションは監視ノードで実行できます。 ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されたとすぐに、監視ノードはテスト パス中に代理トランザクションの使用を開始できます。 ただし、次のセクションで説明したように、特別なセットアップ手順が必要な代理トランザクションがあります。
  
### <a name="data-conferencing-synthetic-transaction"></a>データ会議代理トランザクション

監視ノード コンピューターが境界ネットワークの外側にある場合、次の手順を実行してネットワーク サービス アカウントの Windows Internet Explorer® インターネット ブラウザー プロキシ設定を最初に無効にしない限り、データ会議代理トランザクションを実行できない可能性があります。
  
1. 監視ノード コンピューターで、[**スタート**] をクリックし、[すべてのプログラム] をクリックし、[アクセサリ] をクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行]**をクリックします**。 
    
2. コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

コマンド ウィンドウに次のメッセージが表示されます。
  
BITSAdmin は非推奨であり、将来のバージョンの Windows で使用できるとは保証されません。 BITS サービスの管理ツールは、BITS PowerShell コマンドレットによって提供されます。
  
アカウント NetworkService のインターネット プロキシ設定が [ネットワーク サービス] にNO_PROXY。 
  
(connection = default)
  
このメッセージは、ネットワーク サービス アカウントInternet Explorerプロキシ設定を無効にしたかどうかを示します。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange ユニファイド メッセージング代理トランザクション

Exchange ユニファイド メッセージング (UM) 代理トランザクションは、Exchange に含むボイスメール アカウントにテスト ユーザーが接続できると確認します。
  
テスト ユーザーは、ボイスメール アカウントで事前構成する必要があります。 
  
### <a name="persistent-chat-synthetic-transaction"></a>常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、まずチャネルを作成し、テスト ユーザーに使用許可を与える必要があります。
  
常設チャット代理トランザクションを使用して、次のチャネルを構成できます。 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

このセットアップ タスクは、エンタープライズ内から実行する必要があります。
  
- サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、Role-Based アクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーである必要があります。
    
- サーバー自体から実行する場合、コマンドレットを実行するユーザーは RTCUniversalServerAdmins グループのメンバーである必要があります。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN ピアツーピア通話代理トランザクション

代理Test-CsPstnPeerToPeerCallは、公衆交換電話網 (PSTN) を介して通話を発信および受信する機能を確認します。
  
この代理トランザクションを実行するには、以下を構成する必要があります。
  
- UC が有効な 2 人のテスト ユーザー (発信者と受信者)。
    
- 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。
    
- VoIP ポリシーと音声ルートにより、受信者の番号への通話が PSTN ゲートウェイに到達できます。
    
- ダイヤルされた番号に基づいて、通話を受信者のホーム プールにルーティングする通話とメディアを受け入れる PSTN ゲートウェイ。
    
### <a name="unified-contact-store-synthetic-transaction"></a>統合連絡先ストア代理トランザクション

統合連絡先ストア代理トランザクションは、Skype for Business Server が Exchange からユーザーに代わって連絡先を取得する機能を検証します。
  
この代理トランザクションを使用するには、次の条件を満たす必要があります。
  
- Lyss-Exchangeサーバー間認証を構成する必要があります。
    
- テスト ユーザーは、有効な Exchange メールボックスを持っている必要があります。
    
これらの条件が満たされた後、次のコマンドレットをWindows PowerShellして、テスト ユーザーの連絡先リストを Exchange に移行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

テスト ユーザー連絡先リストが Exchange に移行するには、時間がかかる場合があります。 移行の進行状況を監視するには、-Setup フラグなしで同じコマンド ラインを実行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

移行が完了すると、このコマンド ラインは成功します。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 代理トランザクション

拡張メッセージングとプレゼンス プロトコル (XMPP) IM 代理トランザクションでは、1 つ以上のフェデレーション ドメインを使用して XMPP 機能を構成する必要があります。
  
XMPP 代理トランザクションを有効にするには、ROUTABLE XMPP ドメインのユーザー アカウントに XmppTestReceiverMailAddress パラメーターを指定する必要があります。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

この例では、Skype for Business litwareinc.com Server ルールが存在する必要があります。

> [!NOTE]
> XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細 [については、「XMPP フェデレーションの移行](../migration/migrating-xmpp-federation.md) 」を参照してください。
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>ビデオ相互運用サーバー (VIS) 代理トランザクション

ビデオ相互運用サーバー (VIS) 代理トランザクションでは、代理トランザクション サポート ファイル (VISSTSupportPackage.msi) をダウンロードして[ インストールする必要があります ](https://www.microsoft.com/download/details.aspx?id=46921)。 
  
インストールするにはVISSTSupportPackage.msi msi の依存関係 ([システム要件] の下) が既にインストールされていることを確認します。 簡単VISSTSupportPackage.msiを実行するには、次の手順を実行します。 .msi は、"%ProgramFiles%\VIS 代理トランザクション サポート パッケージ" というパス内のすべてのファイルをインストールします。
  
VIS 代理トランザクションを実行する方法の詳細については [、Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) コマンドレットのドキュメントを参照してください。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>代理トランザクションの実行頻度の変更
<a name="special_synthetictrans"> </a>

既定では、代理トランザクションは構成済みのユーザーと 15 分ごとに実行されます。 代理トランザクションは、2 つの代理トランザクションが互いに競合しないように、一連のユーザー内で順次実行されます。 すべての代理トランザクションが完了する時間を提供するには、より長い間隔が必要です。
  
代理トランザクションを頻繁に実行することが望ましい場合は、特定の一連のユーザーと一緒に実行される代理トランザクションの数を減らして、ネットワークの遅延が発生する可能性のあるバッファーを使用して、目的の時間範囲でテストを完了できる必要があります。 より多くの代理トランザクションを実行することが望ましい場合は、追加の代理トランザクションを実行するために、より多くのユーザー セットを作成します。
  
代理トランザクションを実行する頻度を変更するには、次の手順を実行します。
  
1. System Center Operations Manager を開きます。 [作成] セクションをクリックします。 [ルール] セクション ([作成] の下) をクリックします。
    
2. [ルール] セクションで、"Main Synthetic Transaction Runner Performance Collection Rule" という名前のルールを見つける
    
3. ルールを右クリックし、[上書き] を選択し、[ルールの上書き] を選択し、[クラスのすべてのオブジェクト: プール ウォッチャー] を選択します。
    
4. [プロパティの上書き] ウィンドウで、[パラメーター名] "Frequency" を選択し、[上書き値] を目的の値に設定します。
    
5. 同じウィンドウで、この上書きを適用する必要がある管理パックを選択します。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>代理トランザクションのリッチ ログの使用
<a name="special_synthetictrans"> </a>

代理トランザクションは、システムの問題を特定するのに非常に役立ちます。 たとえば、このコマンドレットTest-CsRegistration、ユーザーが Skype for Business Server への登録が困難であるという事実を管理者に通知できます。 ただし、エラーの実際の原因を特定するために、追加の詳細が必要になる場合があります。
  
このため、代理トランザクションは豊富なログを提供します。 リッチ ログでは、代理トランザクションが実行する各アクティビティに対して、次の情報が記録されます。
  
- アクティビティが開始した時刻。
    
- アクティビティが終了した時刻。
    
- 実行されたアクション (会議の作成、参加、退出、Skype for Business Server へのサインイン、インスタント メッセージの送信など)。
    
- アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ
    
- SIP 登録メッセージ。
    
- アクティビティの実行時に生成される例外レコードまたは診断コード。
    
- アクティビティを実行した結果。
    
この情報は、代理トランザクションが実行されるごとに自動的に生成されますが、ログ ファイルに自動的に表示または保存されません。 代理トランザクションを手動で実行している場合は、OutLoggerVariable パラメーターを使用して、情報が格納される Windows PowerShell変数を指定できます。 そこから、2 つの方法のいずれかを使用して、XML 形式または HTML 形式のリッチ ログにエラー メッセージを保存または表示できます。 
  
トラブルシューティング情報を取得するには、OutLoggerVariable パラメーターを指定し、その後に変数名を指定します。
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : 変数名の前に $文字を付け込む必要があります。 RegistrationTest などの変数名を使用します ($RegistrationTest)。 
  
このコマンドを実行すると、次のような出力が表示されます。
  
ターゲット Fqdn : atl-cs-001.litwareinc.com 結果 : エラー待機時間 : 00:00:00 エラー メッセージ : このコンピューターには、割り当てられた証明書が存在しない。 診断 :このエラーに関する詳細情報は、ここに示すエラー メッセージに比してはるかに詳細な情報にアクセスできます。 この情報に HTML 形式でアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に格納されている情報を HTML ファイルに保存します。
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

これらのファイルは、Windows Internet Explorer、Microsoft Visual Studio、または HTML/XML ファイルを開くことができる他のアプリケーションを使用して表示できます。
  
System Center Operations Manager の内部から実行される代理トランザクションは、エラーに対してこれらのログ ファイルを自動的に生成します。 これらのログは、Skype for Business Server PowerShell が代理トランザクションを読み込み、実行できる前に実行が失敗した場合は生成されません。 
  
> [!IMPORTANT]
> 既定では、Skype for Business Server はログ ファイルを共有されていないフォルダーに保存します。 これらのログに簡単にアクセスするには、このフォルダーを共有する必要があります。 例: \\ atl-watcher-001.litwareinc.com\WatcherNode。