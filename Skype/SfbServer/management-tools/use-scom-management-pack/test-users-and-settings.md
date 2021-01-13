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
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: '概要: Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。'
ms.openlocfilehash: 687aec65089939d2f4cb7b110b4139eca28433fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814837"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>監視ノードのテスト ユーザーと設定を構成する
 
**概要:** Skype for Business Server 代理トランザクションのテスト ユーザー アカウントと監視ノードの設定を構成します。
  
監視ノードとして機能するコンピューターを構成したら、次の手順を実行する必要があります。
  
1. [これらの監視ノードで使用](test-users-and-settings.md#testuser) するテスト ユーザー アカウントを構成します。 ネゴシエート認証方法を使用している場合は **、Set-CsTestUserCredential** コマンドレットを使用して、監視ノードで使用するためにこれらのテスト アカウントを有効にする必要があります。
    
2. 監視ノードの構成設定を更新します。
    
## <a name="configure-test-user-accounts"></a>テスト ユーザー アカウントを構成する
<a name="testuser"> </a>

テスト アカウントは、実際のユーザーを表す必要はありません。ただし、有効な Active Directory アカウントである必要があります。 さらに、これらのアカウントは Skype for Business Server に対して有効にし、有効な SIP アドレスを持っている必要があります。また、エンタープライズ VoIP に対して有効にする必要があります (Test-CsPstnPeerToPeerCall 代理トランザクションを使用する場合)。 
  
TrustedServer 認証方法を使用している場合は、これらのアカウントが存在し、これらのアカウントを構成する必要があります。 テストするプールごとに、少なくとも 2 人のテスト ユーザーを割り当てる必要があります。 ネゴシエート認証方法を使用している場合は、Set-CsTestUserCredential コマンドレットと Skype for Business Server 管理シェルも使用して、これらのテスト アカウントが代理トランザクションで機能する必要があります。 これを行うには、次のようなコマンドを実行します (これらのコマンドは、2 つの Active Directory ユーザー アカウントが作成され、これらのアカウントが Skype for Business Server に対して有効になっていると想定しています)。
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

SIP アドレスだけでなく、ユーザー名とパスワードも含める必要があります。 パスワードを含めない場合は、このコマンドレットSet-CsTestUserCredential情報の入力を求めるメッセージが表示されます。 ユーザー名は、前のコード ブロックに示したドメイン名\ユーザー名の形式を使用して指定できます。
  
テスト ユーザーの資格情報が作成されたのを確認するには、Skype for Business Server 管理シェルから次のコマンドを実行します。
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

次のような情報は、ユーザーごとに返されます。
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>既定の代理トランザクションを使用して基本監視ノードを構成する

テスト ユーザーを作成したら、次のようなコマンドを使用して監視ノードを作成できます。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

このコマンドは、既定の設定を使用する新しい監視ノードを作成し、代理トランザクションの既定のセットを実行します。 新しい監視ノードは、テスト ユーザーを使用してwatcher1@litwareinc.comし、watcher2@litwareinc.com。 監視ノードで TrustedServer 認証を使用する場合、2 つのテスト アカウントには、Active Directory と Skype for Business Server に対して有効な任意の有効なユーザー アカウントを指定できます。 監視ノードでネゴシエート認証方法を使用する場合は、これらのユーザー アカウントも監視ノードに対して有効にし、Set-CsTestUserCredentialがあります。
  
プールを直接対象にするのではなく、サインインするターゲット プールの自動検出が正しく構成されていることを検証するには、代わりに次の手順を使用します。
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>拡張テストの構成

公衆交換電話網との接続を確認する PSTN テストを有効にする場合は、監視ノードを設定するときに追加の構成を行う必要があります。 まず、Skype for Business Server 管理シェルから次のようなコマンドを実行して、テスト ユーザーを PSTN テストの種類に関連付ける必要があります。
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> このコマンドの結果は変数に格納する必要があります。 この例では、変数の名前は $pstnTest。 
  
次に **、New-CsWatcherNodeConfiguration** コマンドレットを使用して、テストの種類 (変数 $pstnTest に格納) を Skype for Business Server プールに関連付けできます。 たとえば、次のコマンドを実行すると、プール atl-cs-001.litwareinc.com の新しい監視ノード構成が作成され、前に作成した 2 人のテスト ユーザーが追加され、PSTN テストの種類が追加されます。
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

監視ノード コンピューターに Skype for Business Server のコア ファイルと RTCLocal データベースをインストールしていない場合、上記のコマンドは失敗します。 
  
複数の音声ポリシーをテストするには **、New-CsExtendedTest** コマンドレットを使用して、ポリシーごとに拡張テストを作成できます。 提供されるユーザーは、目的の音声ポリシーで構成する必要があります。 拡張テストは、次のようなコンマ区切り文字を使用して **New-CsWatcherNodeConfiguration** コマンドレットに渡されます。
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
**New-CsWatcherNodeConfiguration** コマンドレットは Tests パラメーターを使用せずに呼び出されたため、新しい監視ノードでは既定の代理トランザクション (および指定された拡張代理トランザクション) だけが有効になります。 したがって、監視ノードは次のコンポーネントをテストします。
  
- Registration
    
- IM
    
- GroupIM
    
- P2PAV (ピアツーピア音声/ビデオ セッション)
    
- AvConference (電話会議)
    
- プレゼンス
    
- ABS (アドレス帳サービス)
    
- ABWQ (アドレス帳 Web サービス)
    
次のコンポーネントは、既定ではテストされません。
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange ユニファイド メッセージング)
    
- JoinLauncher
    
- MCXP2PIM (従来のモバイル デバイス インスタント メッセージング)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (拡張テストとして指定された PSTN ゲートウェイ通話)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>代理トランザクションの追加と削除

監視ノードを構成した後、Set-CsWatcherNodeConfiguration コマンドレットを使用して、ノードに代理トランザクションを追加または削除できます。 たとえば、PersistentChatMessage テストを監視ノードに追加するには、Add メソッドと次のようなコマンドを使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

テスト名をコンマで区切って、複数のテストを追加できます。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

これらのテスト (DataConference など) の 1 つ以上が監視ノードで既に有効になっている場合は、エラーが発生します。 この場合、次のようなエラー メッセージが表示されます。
  
Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' キーまたは一意の ID 制約に重複するキー シーケンス 'DataConference' があります。
  
このエラーが発生した場合、変更は適用されません。 重複するテストを削除して、コマンドを再実行する必要があります。
  
代理トランザクションを監視ノードから削除するには、Remove メソッドを使用します。 たとえば、次のコマンドは監視ノードから ABWQ テストを削除します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace メソッドを使用すると、現在有効になっているすべてのテストを 1 つ以上の新しいテストに置き換できます。 たとえば、監視ノードで IM テストのみを実行する場合は、次のコマンドを使用して構成できます。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

このコマンドを実行すると、指定した監視ノード上のすべての代理トランザクションが IM を除いて無効になります。
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>監視ノード構成の表示とテスト

監視ノードに割り当てられているテストを表示するには、次のようなコマンドを使用します。
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

このコマンドは、ノードに割り当てられている代理トランザクションに応じて、次のような情報を返します。
  
登録 IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> 代理トランザクションをアルファベット順で表示するには、代わりに次のコマンドを使用します。 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

監視ノードが作成されたのを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

次のような情報が返されます。
  
ID : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test;Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
PortNumber : 5061<br/>

監視ノードが正しく構成されていることを確認するには、Skype for Business Server 管理シェルから次のコマンドを入力します。
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

このコマンドは、展開内の各監視ノードをテストし、次の操作が完了したかどうかを確認します。
  
- 必要なレジストラーの役割がインストールされている。
    
- 必要なレジストリ キーが作成されます (このコマンドレットを実行するとSet-CsWatcherNodeConfigurationされます。
    
- サーバーで正しいバージョンの Skype for Business Server を実行している。
    
- ポートが正しく構成されている。
    
- 割り当てられたテスト ユーザーは、必要な資格情報を持っています。
    
## <a name="managing-watcher-nodes"></a>監視ノードの管理
<a name="testuser"> </a>

監視ノードで実行される代理トランザクションの変更に加えて **、Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードの有効化と無効化、およびテストの実行中に内部 Web URL または外部 Web URL を使用する監視ノードの構成という 2 つの重要なタスクを実行することもできます。
  
既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。 ただし、これらのトランザクションを中断する必要がある場合があります。 たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。 ネットワーク接続がない場合、これらのトランザクションは失敗します。 監視ノードを一時的に無効にするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

このコマンドは、監視ノード atl ウォッチャー サーバー上での代理トランザクションの実行を001.litwareinc.com。 代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。 監視ノードを完全に削除する場合は、**Remove-CsWatcherNodeConfiguration** コマンドレットを使用します。
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

このコマンドを実行すると、指定したコンピューターからすべての監視ノード構成設定が削除され、そのコンピューターは代理トランザクションを自動的に実行できません。 ただし、System Center エージェント ファイルや Skype for Business Server システム ファイルはアンインストールされません。
  
既定では、監視ノードはテストを実行するときに組織の外部 Web URL を使用します。 ただし、監視ノードは、組織の内部 Web URL を使用するように構成することもできます。 これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。 外部 URL ではなく内部 URL を使用する監視ノードを構成するには、UseInternalWebURls プロパティを True ($True) に設定します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

このプロパティを既定値の False ($False) にリセットすると、ウォッチャーはもう一度外部 URL を使用します。
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>代理トランザクションの特別なセットアップ指示
<a name="special_synthetictrans"> </a>

ほとんどの代理トランザクションは監視ノードで実行できます。 ほとんどの場合、代理トランザクションが監視ノード構成設定に追加されたとすぐに、監視ノードはテスト パス中に代理トランザクションの使用を開始できます。 ただし、以下のセクションで説明したように、特別なセットアップ手順を必要とする代理トランザクションがいくつかある場合があります。
  
### <a name="data-conferencing-synthetic-transaction"></a>データ会議代理トランザクション

監視ノード コンピューターが境界ネットワークの外側にある場合は、次の手順を実行してネットワーク サービス アカウントの Windows Internet Explorer® インターネット ブラウザー プロキシ設定を最初に無効にしない限り、データ会議代理トランザクションを実行できません。
  
1. 監視ノード コンピューターで、[スタート]ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、コマンド プロンプトを右クリックして、[管理者として実行] をクリック **します**。 
    
2. コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    コマンド ウィンドウに次のメッセージが表示されます。

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    このメッセージは、ネットワーク サービス アカウントのプロキシInternet Explorer無効にしたかどうかを示します。
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange ユニファイド メッセージング代理トランザクション

Exchange ユニファイド メッセージング (UM) 代理トランザクションは、テスト ユーザーが Exchange にホームのボイスメール アカウントに接続できるのを確認します。
  
テスト ユーザーは、ボイスメール アカウントで事前構成する必要があります。 
  
### <a name="persistent-chat-synthetic-transaction"></a>常設チャット代理トランザクション

常設チャット代理トランザクションを使用するには、まずチャネルを作成し、テスト ユーザーにチャネルを使用するアクセス許可を付与する必要があります。
  
常設チャット代理トランザクションを使用して、このチャネルを構成できます。 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

このセットアップ タスクは、エンタープライズ内から実行する必要があります。
  
- サーバー以外のコンピューターから実行する場合、コマンドレットを実行するユーザーは、サーバー アクセス制御 (RBAC) の CsPersistentChatAdministrators 役割のメンバーRole-Based必要があります。
    
- サーバー自体から実行する場合、コマンドレットを実行するユーザーは RTCUniversalServerAdmins グループのメンバーである必要があります。
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN ピアツーピア通話代理トランザクション

代理Test-CsPstnPeerToPeerCallは、公衆交換電話網 (PSTN) 経由で通話を発信および受信する機能を確認します。
  
この代理トランザクションを実行するには、以下を構成する必要があります。
  
- UC が有効な 2 人のテスト ユーザー (発信者と受信者)。
    
- 各ユーザー アカウントのダイレクト インワード ダイヤリング (DID) 番号。
    
- 受信者の番号への通話が PSTN ゲートウェイに到達できる VoIP ポリシーとボイス ルート。
    
- 通話を受け付け、ダイヤルされた番号に基づいて受信者のホーム プールに通話を戻すメディアを受け入れる PSTN ゲートウェイ。
    
### <a name="unified-contact-store-synthetic-transaction"></a>統合連絡先ストア代理トランザクション

統合連絡先ストア代理トランザクションは、Skype for Business Server が Exchange からユーザーの代わりに連絡先を取得する機能を検証します。
  
この代理トランザクションを使用するには、次の条件を満たす必要があります。
  
- Lyss-Exchange対サーバー認証を構成する必要があります。
    
- テスト ユーザーは有効な Exchange メールボックスを持っている必要があります。
    
これらの条件が満たされた後、次のコマンドレットWindows PowerShell実行して、テスト ユーザーの連絡先リストを Exchange に移行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

テスト ユーザーの連絡先リストが Exchange に移行するには、時間がかかる場合があります。 移行の進行状況を監視するには、-Setup フラグを指定せずに同じコマンド ラインを実行できます。
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

移行が完了すると、このコマンド ラインは成功します。
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 代理トランザクション

XMPP (Extensible Messaging and Presence Protocol) IM 代理トランザクションでは、1 つ以上のフェデレーション ドメインで XMPP 機能を構成する必要があります。
  
XMPP 代理トランザクションを有効にするには、XmppTestReceiverMailAddress パラメーターに、ログアウト可能な XMPP ドメインのユーザー アカウントを指定する必要があります。 例:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

この例では、XMPP ゲートウェイにメッセージをルーティングするために Skype for Business Server litwareinc.com存在する必要があります。

> [!NOTE]
> XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>ビデオ相互運用サーバー (VIS) 代理トランザクション

ビデオ相互運用サーバー (VIS) 代理トランザクションでは、代理トランザクション サポート ファイル (VISSTSupportPackage.msi) をダウンロードしてインストール[ する必要があります ](https://www.microsoft.com/download/details.aspx?id=46921)。 
  
インストールするにはVISSTSupportPackage.msi msi の依存関係 ([システム要件] の下) が既にインストールされていることを確認します。 簡単VISSTSupportPackage.msiを実行するには、次のコマンドを実行します。 .msi は、"%ProgramFiles%\VIS Synthetic Transaction Support Package" というパスのすべてのファイルをインストールします。
  
VIS 代理トランザクションの実行方法の詳細については [、Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) コマンドレットのドキュメントを参照してください。
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>代理トランザクションの実行頻度の変更
<a name="special_synthetictrans"> </a>

既定では、代理トランザクションは構成済みのユーザーと 15 分ごとに実行されます。 代理トランザクションは、2 つの代理トランザクションが互いに競合しないように、一連のユーザー内で順番に実行されます。 すべての代理トランザクションが完了する時間を提供するには、より長い間隔が必要です。
  
代理トランザクションの実行頻度を高くすることが望ましい場合は、特定のユーザー セットで実行される代理トランザクションの数を減らして、ネットワーク遅延が発生する場合にバッファーを使用して目的の時間範囲内でテストを完了する必要があります。 より多くの代理トランザクションを実行することが望ましい場合は、追加の代理トランザクションを実行するユーザー セットを作成します。
  
代理トランザクションを実行する頻度を変更するには、次の手順を実行します。
  
1. System Center Operations Manager を開きます。 [作成] セクションをクリックします。 [ルール] セクション ([作成] の下) をクリックします。
    
2. [Rules] セクションで、"Main Synthetic Transaction Runner Performance Collection Rule" という名前のルールを探します。
    
3. ルールを右クリックし、[上書き] を選択し、[ルールの上書き] を選択し、[クラスのすべてのオブジェクトの場合: プール ウォッチャー] を選択します。
    
4. [プロパティの上書き] ウィンドウで、パラメーター名 "Frequency" を選択し、優先値を目的の値に設定します。
    
5. 同じウィンドウで、このオーバーライドを適用する必要がある管理パックを選択します。
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>代理トランザクションのリッチ ログの使用
<a name="special_synthetictrans"> </a>

代理トランザクションは、システムの問題を特定するのに非常に役立ちます。 たとえば、Test-CsRegistrationコマンドレットは、ユーザーが Skype for Business Server に登録する上で問題が発生しているという事実を管理者に警告できます。 ただし、エラーの実際の原因を特定するには、追加の詳細が必要になる場合があります。
  
このため、代理トランザクションは豊富なログを提供します。 リッチ ログでは、代理トランザクションが実行するアクティビティごとに、次の情報が記録されます。
  
- アクティビティが開始された時刻。
    
- アクティビティが終了した時刻。
    
- 実行されたアクション (会議の作成、参加、退出、Skype for Business Server へのサインイン、インスタント メッセージの送信など)。
    
- アクティビティの実行時に生成された情報メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ。
    
- SIP 登録メッセージ。
    
- アクティビティの実行時に生成された例外レコードまたは診断コード。
    
- アクティビティを実行した結果の結果。
    
この情報は、代理トランザクションが実行されるたび自動的に生成されますが、ログ ファイルに自動的に表示または保存されるのではありません。 代理トランザクションを手動で実行している場合は、OutLoggerVariable パラメーターを使用して、情報が格納される Windows PowerShell 変数を指定できます。 そこから、2 つの方法のいずれかを使用して、エラー メッセージを XML 形式または HTML 形式でリッチ ログに保存または表示することができます。 
  
トラブルシューティング情報を取得するには、OutLoggerVariable パラメーターを指定し、その後に変数名を指定します。
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 変数名の前に $ 記号を付けないでください。 RegistrationTest などの変数名を使用します ($RegistrationTest)。 
  
このコマンドを実行すると、次のような出力が表示されます。
  
ターゲット Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates. 診断 :このエラーに関する詳細な情報には、ここに示すエラー メッセージに加え、より詳細な情報にアクセスできます。

この情報に HTML 形式でアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に格納されている情報を HTML ファイルに保存します。
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

これらのファイルは、Windows Internet Explorer、Microsoft Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使用して表示できます。
  
System Center Operations Manager の内部から実行される代理トランザクションは、障害が発生した場合にこれらのログ ファイルを自動的に生成します。 これらのログは、Skype for Business Server PowerShell が代理トランザクションを読み込み、実行する前に実行が失敗した場合は生成されません。 
  
> [!IMPORTANT]
> 既定では、Skype for Business Server はログ ファイルを共有されていないフォルダーに保存します。 これらのログに簡単にアクセスするには、このフォルダーを共有する必要があります。 例: \\ atl-watcher-001.litwareinc.com\WatcherNode。 
