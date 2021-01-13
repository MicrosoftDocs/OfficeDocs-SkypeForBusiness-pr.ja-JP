---
title: 監視ノードのインストールと構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: Skype for Business Server 代理トランザクションの監視ノードをインストールおよび構成します。'
ms.openlocfilehash: f6d3db973291b8a41647a3c4a4d3c3530c7af019
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812752"
---
# <a name="install-and-configure-watcher-nodes"></a>監視ノードのインストールと構成
 
**概要:** Skype for Business Server 代理トランザクションの監視ノードをインストールおよび構成します。
  
監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。 代理トランザクションはWindows PowerShellユーザーの主要なシナリオ (サインインやインスタント メッセージの交換など) が期待通り動作しているのを確認するコマンドレットです。 Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、次の 3 種類の代理トランザクションが含まれます。
  
- **既定値** 監視ノードが既定で実行される代理トランザクション。 新しい監視ノードを作成するときに、そのノードを実行する代理トランザクションを指定できます。 (これは、テスト コマンドレットで使用される Tests パラメーターNew-CsWatcherNodeConfigurationです)。監視ノードの作成時に Tests パラメーターを使用しない場合は、すべての既定の代理トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。 つまり、たとえば、監視ノードは Test-CsAddressBookService テストを実行するように構成されますが、Test-CsExumConnectivity テストを実行するように構成されません。
    
- **既定以外** 監視ノードが既定で実行されないテスト。 (詳細については、Default 型の説明を参照してください)。ただし、監視ノードを有効にすると、既定以外の代理トランザクションを実行できます。 これは、監視ノードを作成するときに (New-CsWatcherNodeConfiguration コマンドレットを使用して)、または監視ノードの作成後にいつでも実行できます。 既定以外の代理トランザクションの多くは、追加のセットアップ手順を必要とします。 これらの手順の詳細については、「代理トランザクションの [特別なセットアップ手順」を参照してください](test-users-and-settings.md#special_synthetictrans)。
    
- **拡張** 特殊な種類の既定以外の代理トランザクション。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールの複数の公衆交換電話網 (PSTN) ボイス ルートなどの動作を確認する場合に役立ちます。 これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。
    
監視ノードに他の代理トランザクションを追加するプロセスの詳細については [、「Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。 Skype for Business Server 管理シェルを使用して監視ノードから代理トランザクションを削除することもできます。
  
監視ノードで使用できる代理トランザクションは以下のとおりです。
  
|**コマンドレット名 (テスト名)**|**説明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |ユーザーが自分の連絡先リストに含されていないユーザーを参照できるのを確認します。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |ユーザーが HTTP 経由で連絡先リストに登録されていないユーザーを参照できる状態を確認します。  <br/> |
|Test-CsAVConference (AvConference)  <br/> |ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。  <br/> |
|Test-CsGroupIM (IM 会議)  <br/> |ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。  <br/> |
|Test-CsIM (P2P IM)  <br/> |ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。  <br/> |
|Test-CsPresence (Presence)  <br/> |ユーザーが他のユーザーのプレゼンスを表示できる状態を確認します。  <br/> |
|Test-CsRegistration (Registration)  <br/> |ユーザーが Skype for Business にサインイン可能なユーザーを確認します。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。  <br/> |
|Test-CsASConference (ASConference)  <br/> |ユーザーがアプリケーション共有会議を作成して参加可能なユーザーを確認します。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |音声ビデオ エッジ サーバーが、ピアツーピア通話と電話会議の接続を受け入れ可能に設定します。  <br/> |
|Test-CsDataConference (DataConference)  <br/> |ユーザーがデータ コラボレーション会議 (ホワイトボードや投票などのアクティビティを含むオンライン会議) に参加できるのを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話会議に参加するために電話番号をダイヤルできるのを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話会議に参加するために電話番号をダイヤルできるのを確認します。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |ユーザーが Exchange ユニファイド メッセージング (UM) に接続可能なのを確認します。  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |ユーザーが (Web アドレス リンクを使用して) スケジュールされた会議を作成して参加可能なユーザーを確認します。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |ビデオ相互運用サーバーが立ち上がり、ビデオ SIP トランクを使用した着信接続を処理できるのを確認します。  <br/> **注:** 従来のモバイル クライアントの MCX サポートは、Skype for Business Server 2019 では使用できなくなりました。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |ユーザーが常設チャット サービスを使用してメッセージを交換できるのを確認します。  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |ユーザーが Web 経由で会議に参加可能なのを確認します。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアを使用すると、ユーザーは Skype for Business Server 2015、Outlook メッセージングおよびコラボレーション クライアント、Outlook Web Access を使用してアクセスできる連絡先の単一セットを維持できます。  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |インスタント メッセージが XMPP (Extensible Messaging and Presence Protocol) ゲートウェイを通して送信可能な状態を確認します。  <br/> XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。  |

System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。 これらのノードをインストールしない場合でも、問題が発生するたびに Skype for Business Server 2015 コンポーネントからリアルタイムのアラートを取得できます。 (コンポーネントおよびユーザー管理パックでは監視ノードは使用されません)。ただし、アクティブ監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。
  
> [!NOTE]
> 管理者は、Operations Manager を使用またはインストールせずに、代理トランザクションを手動で実行することもできます。 Skype for Business Server 展開のサイズによっては、代理トランザクションで大量のコンピューター メモリとプロセッサ時間を使用できます。 そのため、監視ノードとして専用のコンピューターを使用することをお勧めします。 たとえば、監視ノードとして機能する Skype for Business Server フロント エンド サーバーを構成する必要があります。 監視ノードは、Skype for Business Server トポロジ内の他のコンピューターと同じ基本的なハードウェア要件を満たしている必要があります。 
  
> [!NOTE]
> Lync Server 2013 と Skype for Business Server 2015 のコア システム ファイルは同じコンピューターにインストールできないので、従来の Lync Server 2013 監視ノードを Skype for Business Server 2015 監視ノードと同じコンピューターに同じコンピューターに同時に設置することはできません。 ただし、Skype for Business Server 2015 監視ノードは、Skype for Business Server 2015 と Lync Server 2013 を同時に監視できます。 既定の代理トランザクションは、両方の製品バージョンでサポートされています。 
  
Lync Server 2013 監視ノードは、次の点を確認するために、企業の内部または外部に展開できます。
  
- 社内ユーザー用プールへの接続。
    
- 社外で作業するリモート ユーザー向け境界ネットワーク経由の接続。
    
- ブランチ オフィス アプライアンスへの接続。
    
- 企業内部および境界ネットワークを介した Lync Server 2013 への接続。
    
管理を簡素化するために、企業の内部と外部で異なる認証オプションを使用できます。 詳細については、「代理トランザクション [を実行する監視ノードを構成する」を参照してください](watcher-nodes.md#enable_synthetic_trans)。
  
監視ノードとして機能するコンピューターを構成するには、まず次の前提条件を満たす必要があります。 
  
- System Center Operations Manager をインストールし、Skype for Business Server 2015 管理パックをインポートします。 また、最初に監視ノード コンピューターが Skype for Business Server 2015 をインストールするためのすべての前提条件を満たしていることを確認する必要があります。
    
- 監視ノード コンピューターに次の項目をインストールします。
    
  - .NET Framework 4.5 のフル バージョン
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
前提条件を満たした後、次の手順に従って監視ノードを構成できます。
  
1. 監視ノード コンピューターに Skype for Business Server 2015 コア ファイルをインストールします。
    
2. System Center Operations Manager エージェントを監視ノード コンピューターにインストールします。
    
3. 実行可能ファイルWatchernode.msi実行します。
    
4. **New-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードで使用するテスト ユーザー アカウントを構成します。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Skype for Business Server 2015 コア ファイルと RTCLocal データベースをインストールする

Skype for Business Server 2015 のコア ファイルをコンピューターにインストールするには、次の手順を実行します。 RTCLocal データベースは、コア ファイルをインストールすると自動的にインストールされます。 監視ノードに新しいSQL Serverする必要はありません。 SQL Server Express は自動的にインストールされます。
  
Skype for Business Server 2015 のコア ファイルと RTCLocal データベースをインストールするには、次の手順を実行します。
  
1. 監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。
    
2. コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。 Skype for Business Server セットアップ ファイルへの適切なパスを入力してください:D:\Setup.exe /BootstrapLocalMgmt。コア Skype for Business Server コンポーネントが正常にインストールされていることを確認し、[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。 Skype for Business Server 管理シェルで、次のコマンドを入力Windows PowerShell Enter キーを押します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> このコマンドを初めて実行する場合、監視ノード コンピューターをまだ構成していないので、データは返されません。 コマンドがエラーを返さずに実行される場合は、Skype for Business Server のセットアップが正常に完了したと想定できます。 
  
監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。
  
Get-CsPinPolicyYou、組織で使用するように構成されている PIN ポリシーの数に応じて、次のような情報を受信します。
  
Identity : Global
  
説明 :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>監視ノードに Operation Manager エージェント ファイルをインストールする

コンポーネントの警告を報告する Skype for Business Server のセットアップと同様に、Skype for Business Server 2015 監視ノードには System Center Operations Manager エージェント ファイルをインストールする必要があります。 これにより、代理トランザクションを実行し、System Center Operations Manager ルート管理サーバーに警告を報告できます。
  
エージェント ファイルをインストールするには、「監視対象の Skype for Business Server コンピューターを構成する」に記載されている [手順に従います](configure-computers-to-monitor.md)。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>代理トランザクションを実行する監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager エージェント ファイルをインストールしたら、監視ノード自体を構成する必要があります。 これを行う手順は、監視ノード コンピューターが境界ネットワーク内にあるか、境界ネットワークの外側にあるかによって異なります。 
  
監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Skype for Business Server 2015 では、信頼済みサーバー認証と資格情報認証の 2 つの認証方法のいずれかを選択できます。 次の表に、これら 2 つの方法の違いを示します。
  
||**説明**|**サポートされる場所**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。  <br/> 各監視ノードで多数のユーザー パスワードを管理するのではなく、1 つの証明書を管理することを希望する管理者に役立ちます。  <br/> |エンタープライズの内側。  <br/> この方法では、監視ノードは監視対象のプールと同じドメインに含まれる必要があります。 監視ノードとプールが異なるドメインにある場合は、代わりに資格情報認証を使用します。  <br/> |
|ネゴシエート  <br/> |ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。  <br/> このモードでは、より多くのパスワード管理が必要ですが、企業外の監視ノードの唯一のオプションです。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。  <br/> |エンタープライズの外側。  <br/> エンタープライズの内側。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>信頼済みサーバー認証を使用する監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証を使用すると、多数のユーザー アカウント パスワードを使用するのではなく、単一の証明書を維持することで管理タスクを大幅に削減できます。
  
信頼済みサーバー認証を構成するには、最初に監視ノード コンピューターをホストする信頼されたアプリケーション プールを作成する必要があります。 信頼されたアプリケーション プールを作成したら、その監視ノードで代理トランザクションを構成して、信頼されたアプリケーションとして実行する必要があります。
  
> [!NOTE]
> 信頼済みアプリケーションとは、Skype for Business Server 2015 の一部として実行する信頼できる状態が与えられるアプリケーションですが、製品の組み込みの一部ではありません。 信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。
  
信頼されたアプリケーション プールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 前のコマンドのパラメーターの詳細については、Skype for Business Server 管理シェル プロンプトから次を入力します。 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

信頼されたアプリケーション プールを作成した後 **、New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションを信頼されたアプリケーションとして実行する監視ノード コンピューターを構成できます。
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

このコマンドが完了し、信頼されたアプリケーションが作成されると **、Enable-CsTopology** コマンドレットを実行して、変更が有効になつながっている必要があります。
  
```PowerShell
Enable-CsTopology
```

監視ノード コンピューター アカウントでは、一部の代理トランザクションについて CMS を照会する機能が必要です。 この機能を許可するには、監視ノードのコンピューター アカウントを RTCUniversalReadOnlyAdmins セキュリティ グループに追加します。 レプリケーションADしたら、コンピューターを再起動します。
  
新しい信頼済みアプリケーションが作成されたのを確認するには、Skype for Business Server 管理シェル プロンプトで次を入力します。
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する
<a name="enable_synthetic_trans"> </a>

TrustedServer 認証を使用する各監視ノードには、Skype for Business Server 展開ウィザードを使用して割り当てられた既定の証明書が必要です。 
  
既定の証明書を割り当てるには、
  
1. [スタート] ボタン、[すべてのプログラム] の順にクリックし、Skype for Business Server 2015 をクリックして、Skype for Business Server 展開ウィザードをクリックします。 
    
2. Skype for Business Server 展開ウィザードで、[Skype for Business Server システムのインストールまたは更新] をクリックし、[要求、インストール、または証明書の割り当て] という見出しの下の [実行] をクリックします。 
    
> [!NOTE]
> [実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。 
  
次のいずれかの操作を行います。
  
- 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。 証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
- 既定の証明書を使用するための証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従って証明書を要求します。 Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。
    
## <a name="install-and-configure-a-watcher-node"></a>監視ノードのインストールと構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターを再起動し、証明書を構成した後、次のコマンドでファイルを実行Watchernode.msi。 (Operations Manager エージェント Watchernode.msi Skype for Business Server 2015 コア コンポーネントの両方がインストールされている任意のコンピューターで、このコマンドを実行する必要があります)。 
  
監視ノードをインストールして構成するには:
  
1. [スタート] ボタン、[すべてのプログラム] の順にクリックし、[Skype for Business Server 2015] をクリックし、[Skype for Business Server 管理シェル] をクリックして、Skype for Business Server 管理シェルを開きます。 
    
2. 管理シェルで次のコマンドを入力し、Enter キーを押します (このコマンドのコピーへの実際のパスを指定Watchernode.msi)。
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> コマンド ウィンドウから Watchernode.msi n を実行することもできます。 コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。 コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。 
  
> [!IMPORTANT]
> 前のコマンドでは、名前と値のペア Authentication=TrustedServer では大文字と小文字が区別されます。 次に示すとおりに入力する必要があります。 たとえば、次のコマンドは正しい大文字小文字を使用しないので失敗します。 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer モードは、境界ネットワーク内にあるコンピューターでのみ使用できます。 監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上でテスト ユーザー パスワードを保持する必要はありません。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>ネゴシエートを使用する監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワークの外側にある場合、代理トランザクションを実行するために監視ノードを構成するには、少し異なる手順に従う必要があります。特に、信頼されたアプリケーション プールや信頼されたアプリケーションを作成する必要があります。 つまり、次の 2 つのタスクを完了する必要があります。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-Only Administrators グループのメンバーシップを更新する

監視ノードが境界ネットワークの外側にある場合は、監視ノードで次の手順を実行して、監視ノード コンピューターの RTC Local Read-only Administrators グループにネットワーク サービス アカウントを追加する必要があります。
  
1. [スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。
    
2. サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。
    
3. [グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。
    
4. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。
    
5. [ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。
    
6. [場所] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[OK] をクリックします。
    
7. [選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。
    
8. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。
    
9. ウォッチャー ノード コンピューターを再起動します。
    
### <a name="install-the-watcher-node-configuration-files"></a>監視ノード構成ファイルをインストールする

次の手順では、次の手順でファイルを実行Watchernode.msi。 
  
1. Microsoft Skype for Business Server 2015 管理シェルを開きます。 [スタート] ボタン、[すべてのプログラム] の順にクリックし、[Microsoft Skype for Business Server 2015] をクリックして、[Skype for Business Server 管理シェル] をクリックします。 
    
2. Skype for Business Server 管理シェルで、次のコマンドを入力し、Enter キーを押します (必ず、サーバーのコピーへの実際のパスをWatchernode.msi。
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 前述したように、Watchernode.msiウィンドウから実行することもできます。 コマンド ウィンドウを開くには、[**スタート**] をクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。 コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。 
  
ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。 このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。
  

