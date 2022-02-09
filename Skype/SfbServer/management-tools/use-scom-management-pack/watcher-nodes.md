---
title: 監視ノードをインストールして構成する方法
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 代理トランザクションの監視ノードをインストールおよび構成するプロセスSkype for Business Server説明します。
ms.openlocfilehash: 34ab33bb486e3bc9973632c108e6eccf33bec481
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396680"
---
# <a name="learn-to-install-configure-watcher-nodes"></a>監視ノードのインストール、構成の詳細
 
**概要:** 代理トランザクションの監視ノードをインストールSkype for Business Server構成します。
  
監視ノードは、代理トランザクションを定期的に実行Skype for Business Serverコンピューターです。 代理トランザクションはWindows PowerShell、サインインやインスタント メッセージの交換などの主要なユーザー シナリオが期待通り動作しているのを確認するコマンドレットです。 2015 Skype for Business Server、Operations Manager System Center次の表に示す代理トランザクションを実行できます。これには、次の 3 種類の代理トランザクションが含まれます。
  
- **既定** 監視ノードが既定で実行する代理トランザクション。 新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定できます。 (これは、このコマンドレットで使用される Tests パラメーターNew-CsWatcherNodeConfigurationです)。監視ノードの作成時に Tests パラメーターを使用しない場合、既定の代理トランザクションはすべて自動的に実行され、既定以外の代理トランザクションは実行されません。 つまり、たとえば、監視ノードは Test-CsAddressBookService テストを実行するように構成されますが、Test-CsExumConnectivity テストを実行するように構成されません。
    
- **既定以外** 監視ノードが既定で実行されないテスト。 (詳細については、Default 型の説明を参照してください。ただし、監視ノードを有効にすると、既定以外の代理トランザクションを実行できます。 監視ノードを作成する場合 (New-CsWatcherNodeConfiguration コマンドレットを使用して)、監視ノードの作成後にいつでも実行できます。 既定以外の代理トランザクションの多くは、追加のセットアップ手順を必要とします。 これらの手順の詳細については、「代理トランザクションの [特別なセットアップ手順」を参照してください](test-users-and-settings.md#special_synthetictrans)。
    
- **拡張** 既定以外の代理トランザクションの特殊な種類。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールの複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を確認する場合に便利です。 これを構成するには、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。
    
監視ノードに他の代理トランザクションを追加するプロセスの詳細については、「代理トランザクションを実行する監視ノードを構成する [」を参照してください](watcher-nodes.md#enable_synthetic_trans)。 また、管理シェルSkype for Business Server使用して、監視ノードから代理トランザクションを削除することもできます。
  
監視ノードで使用できる代理トランザクションは以下のとおりです。
  
|**コマンドレット名 (テスト名)**|**説明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |ユーザーが連絡先リストに含めなかったユーザーを参照できると確認します。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |ユーザーが HTTP 経由で連絡先リストに登録されていないユーザーを参照できる状態を確認します。  <br/> |
|Test-CsAVConference (AvConference)  <br/> |ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。  <br/> |
|Test-CsGroupIM (IM 会議)  <br/> |ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。  <br/> |
|Test-CsIM (P2P IM)  <br/> |ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。  <br/> |
|Test-CsPresence (Presence)  <br/> |ユーザーが他のユーザーのプレゼンスを表示できる状態を確認します。  <br/> |
|Test-CsRegistration (Registration)  <br/> |ユーザーがユーザーにサインインできるSkype for Business。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。  <br/> |
|Test-CsASConference (ASConference)  <br/> |ユーザーがアプリケーション共有会議を作成して参加できると確認します。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |オーディオ ビデオ エッジ サーバーがピアツーピア通話と電話会議の接続を受け入れ可能なと確認します。  <br/> |
|Test-CsDataConference (DataConference)  <br/> |ユーザーがデータコラボレーション会議 (ホワイトボードやポーリングなどのアクティビティを含むオンライン会議) に参加できると確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話会議に参加するために電話番号をダイヤルできると確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話会議に参加するために電話番号をダイヤルできると確認します。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |ユーザーがユニファイド メッセージング (UM) Exchange接続できると確認します。  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |ユーザーがスケジュールされた会議を作成して参加できる (Web アドレス リンクによって) 確認します。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |ビデオ相互運用サーバーがアップし、ビデオ SIP トランクを使用して受信接続を処理できると確認します。  <br/> **注:** 従来のモバイル クライアントの MCX サポートは、2019 年Skype for Business Serverで使用できなくなりました。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |ユーザーが常設チャット サービスを使用してメッセージを交換できると確認します。  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |ユーザーが Web 経由で会議に参加できると確認します。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアは、Skype for Business Server 2015、Outlook メッセージングおよびコラボレーション クライアント、および/または Outlook Web Access を使用してアクセスできる単一の連絡先セットをユーザーが維持する方法を提供します。  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |インスタント メッセージが拡張可能メッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイを通して送信可能な状態を確認します。  <br/> XMPP ゲートウェイとプロキシは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。  |

Operations Manager で使用する監視ノードをインストールするSystem Centerはありません。 これらのノードをインストールしない場合でも、問題が発生するたびに、Skype for Business Server 2015 コンポーネントからリアルタイムのアラートを取得できます。 (コンポーネントとユーザー管理パックでは監視ノードは使用されません)。ただし、Active Monitoring Management パックを使用してエンド to エンドのシナリオを監視する場合は、監視ノードが必要です。
  
> [!NOTE]
> 管理者は、Operations Manager を使用またはインストールせずに、代理トランザクションを手動で実行することもできます。 展開のサイズに応じてSkype for Business Server、代理トランザクションで大量のコンピューター メモリとプロセッサ時間を使用できます。 そのため、監視ノードとして専用のコンピューターを使用することをお勧めします。 たとえば、監視ノードとして機能Skype for Business Serverフロントエンド サーバーを構成する必要があります。 監視ノードは、ネットワーク トポロジ内の他のコンピューターと同じ基本的なハードウェア要件Skype for Business Server必要があります。 
  
> [!NOTE]
> 従来の Lync Server 2013 監視ノードは、Lync Server 2013 および Skype for Business Server 2015 のコア システム ファイルを同じコンピューターにインストールできないので、Skype for Business Server 2015 ウォッチャー ノードと同じコンピューターに接続できません。 ただし、2015 Skype for Business Server監視ノードは、2015 と Lync Server 2013 Skype for Business Server同時に監視できます。 既定の代理トランザクションは、両方の製品バージョンでサポートされています。 
  
Lync Server 2013 監視ノードは、次の点を確認するために、企業の内部または外部に展開できます。
  
- 社内ユーザー用プールへの接続。
    
- 企業外で作業しているリモート ユーザーの境界ネットワークを介した接続。
    
- ブランチ オフィス アプライアンスへの接続。
    
- 企業内および境界ネットワークを介した Lync Server 2013 への接続。
    
管理を簡略化するために、企業の内部と外部で異なる認証オプションを使用できます。 詳細については、「 [代理トランザクションを実行する監視ノードを構成する」を参照してください](watcher-nodes.md#enable_synthetic_trans)。
  
監視ノードとして機能するコンピューターを構成するには、まず次の前提条件を満たす必要があります。 
  
- Operations Manager System Centerインストールし、2015 Skype for Business Serverパックをインポートします。 また、監視ノード コンピューターが 2015 年にインストールするためのすべての前提条件を満たしていることをSkype for Business Serverがあります。
    
- 監視ノード コンピューターに次の項目をインストールします。
    
  - 4.5 .NET Frameworkバージョン
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
前提条件が満たされた後、次の手順に従って監視ノードを構成できます。
  
1. 監視ノード Skype for Business Server 2015 コア ファイルをインストールします。
    
2. 監視System Centerコンピューターに Operations Manager エージェントをインストールします。
    
3. 実行可能ファイルWatchernode.msi実行します。
    
4. **New-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードで使用するテスト ユーザー アカウントを構成します。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>2015 Skype for Business Serverファイルと RTCLocal データベースのインストール

コンピューターに Skype for Business Server 2015 コア ファイルをインストールするには、次の手順を実行します。 コア ファイルをインストールすると、RTCLocal データベースが自動的にインストールされます。 監視ノードにインストールする必要SQL Server注意してください。 SQL Server Express自動的にインストールされます。
  
2015 コア Skype for Business Server RTCLocal データベースをインストールするには、次の手順を実行します。
  
1. 監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。
    
2. コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。 Skype for Business Server セットアップ ファイルへの適切なパスを入力してください:D:\Setup.exe /BootstrapLocalMgmt コア Skype for Business Server コンポーネントが正常にインストールされていることを確認するには、[スタート] をクリックし、[すべてのプログラム] をクリックし、**Skype for Business Server 2015 をクリック** し、[管理 **シェルSkype for Business Serverクリックします**。 [管理シェルSkype for Business Serverに、次のコマンドを入力Windows PowerShell Enter キーを押します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> このコマンドを初めて実行すると、監視ノード コンピューターがまだ構成されていないため、データは返されません。 コマンドがエラーを返さずに実行される場合は、セットアップがSkype for Business Server完了したと仮定できます。 
  
監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して、2015 のインストールSkype for Business Serverできます。
  
Get-CsPinPolicyYou、組織で使用するように構成されている PIN ポリシーの数に応じて、次のような情報を受信します。
  
ID : グローバル
  
説明 :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>監視ノードに Operation Manager エージェント ファイルをインストールする

レポート コンポーネントSkype for Business Serverの設定と同様に、Skype for Business Server 2015 監視ノードには、System Center Operations Manager エージェント ファイルをインストールする必要があります。 これにより、代理トランザクションを実行し、アラートを Operations Manager ルート管理サーバー System Centerレポートできます。
  
エージェント ファイルをインストールするには、「監視対象のコンピューターの構成Skype for Business Server[手順に従います](configure-computers-to-monitor.md)。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>代理トランザクションを実行する監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

Operations Manager System Centerファイルがインストールされた後、監視ノード自体を構成する必要があります。 これを行う手順は、監視ノード コンピューターが境界ネットワーク内か境界ネットワーク外かによって異なります。 
  
監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Skype for Business Server 2015 では、信頼できるサーバー認証または資格情報認証の 2 つの認証方法のいずれかを選択できます。 次の表に、これら 2 つの方法の違いを示します。
  
|&nbsp;|**説明**|**サポートされている場所**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。  <br/> 各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理する管理者に役立ちます。  <br/> |エンタープライズの内側。  <br/> この方法では、監視ノードは監視対象のプールと同じドメイン内にある必要があります。 監視ノードとプールが異なるドメインにある場合は、代わりに資格情報認証を使用します。  <br/> |
|ネゴシエート  <br/> |ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。  <br/> このモードでは、より多くのパスワード管理が必要ですが、企業外の監視ノードの唯一のオプションです。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。  <br/> |エンタープライズの外側。  <br/> エンタープライズの内側。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>信頼されたサーバー認証を使用する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証を使用すると、多数のユーザー アカウント パスワードを使用するのではなく、単一の証明書を維持することで管理タスクを大幅に削減できます。
  
信頼済みサーバー認証を構成するには、最初に監視ノード コンピューターをホストする信頼できるアプリケーション プールを作成する必要があります。 信頼済みアプリケーション プールを作成したら、その監視ノードで代理トランザクションを構成して、信頼できるアプリケーションとして実行する必要があります。
  
> [!NOTE]
> 信頼済みアプリケーションとは、Skype for Business Server 2015 の一部として実行する信頼できる状態が与えられるアプリケーションですが、製品の組み込みの一部ではありません。 信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。
  
信頼できるアプリケーション プールを作成するには、管理シェルSkype for Business Server開き、次のようなコマンドを実行します。
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 前のコマンドのパラメーターの詳細については、管理シェル プロンプトから次Skype for Business Server入力します。 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

信頼されたアプリケーション プールを作成したら、 **New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションを信頼できるアプリケーションとして実行する監視ノード コンピューターを構成できます。
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

このコマンドが完了し、信頼できるアプリケーションが作成されると、 **Enable-CsTopology** コマンドレットを実行して、変更が有効になります。
  
```PowerShell
Enable-CsTopology
```

監視ノードのコンピューター アカウントでは、一部の代理トランザクションについて CMS を照会する機能が必要です。 この機能を許可するには、監視ノードのコンピューター アカウントを RTCUniversalReadOnlyAdmins セキュリティ グループに追加します。 レプリケーションADしたら、コンピューターを再起動します。
  
新しい信頼済みアプリケーションが作成されたと確認するには、管理シェルのプロンプトに次Skype for Business Server入力します。
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する
<a name="enable_synthetic_trans"> </a>

TrustedServer 認証を使用する各監視ノードには、展開ウィザードを使用して割り当てられた既定の証明書Skype for Business Server必要があります。 
  
既定の証明書を割り当てるには、
  
1. [スタート] ボタン、[すべてのプログラム] をクリックし、[Skype for Business Server 2015] をクリックし、[展開ウィザードSkype for Business Serverクリックします。 
    
2. [展開ウィザードSkype for Business Server、[ システムのインストール] または [更新] Skype for Business Serverし、[要求]、[インストール]、または [証明書の割り当て] という見出しの下にある [実行] をクリックします。 
    
> [!NOTE]
> [実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。 
  
次のいずれかの操作を行います。
  
- 既定の証明書として使用できる証明書が既にある場合は、[証明書] ウィザードで [既定] をクリックし、[割り当て] をクリックします。 証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
- 既定の証明書の使用を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従って証明書を要求します。 Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。
    
## <a name="install-and-configure-a-watcher-node"></a>監視ノードのインストールと構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターを再起動し、証明書を構成したら、ファイル を実行する必要Watchernode.msi。 (Operations Manager エージェント ファイルWatchernode.msi 2015 コア コンポーネントの両方がインストールされているコンピューターで、Skype for Business Serverを実行する必要があります。 
  
監視ノードをインストールして構成するには、次の手順を実行します。
  
1. [スタート] Skype for Business Serverをクリックし、[すべてのプログラム] をクリックし、[2015 年 2015 年Skype for Business Server] をクリックし、[管理シェル] Skype for Business Serverクリックします。 
    
2. 管理シェルで、次のコマンドを入力し、Enter キーを押します (必ず、コピーの実際のパスを指定Watchernode.msi。
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> コマンド ウィンドウから Watchernode.msi n を実行することもできます。 コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。 コマンド ウィンドウが開いたら、上記の手順 2 に示したのと同じコマンドを入力します。 
  
> [!IMPORTANT]
> 前のコマンドでは、名前/値のペア Authentication=TrustedServer では大文字と小文字が区別されます。 これは、示されているとおりに正確に入力する必要があります。 たとえば、次のコマンドは正しい文字の大文字小文字を使用しないので失敗します。 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer モードは、境界ネットワーク内にあるコンピューターでのみ使用できます。 監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上でテスト ユーザー パスワードを維持する必要はありません。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>ネゴシエートを使用する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワークの外側にある場合、代理トランザクションを実行する監視ノードを構成するには、少し異なる手順に従う必要があります。特に、信頼できるアプリケーション プールや信頼できるアプリケーションを作成する必要があります。 つまり、次の 2 つのタスクを完了する必要があります。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC ローカル 管理者グループRead-Only更新する

監視ノードが境界ネットワークの外側にある場合は、監視ノードで次の手順を実行して、監視ノード コンピューターの RTC ローカル読み取り専用 Administrators グループにネットワーク サービス アカウントを追加する必要があります。
  
1. [スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。
    
2. サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。
    
3. [グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。
    
4. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。
    
5. [ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。
    
6. [場所] ダイアログ ボックスで、ウォッチャー ノード コンピューターの名前を選択し、[OK] をクリックします。
    
7. [選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。
    
8. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。
    
9. ウォッチャー ノード コンピューターを再起動します。
    
### <a name="install-the-watcher-node-configuration-files"></a>監視ノード構成ファイルのインストール

次の手順では、次の手順でファイルを実行Watchernode.msi。 
  
1. Microsoft Skype for Business Server 2015 管理シェルを開きます。 [スタート] ボタン、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server 2015] をクリックし、[管理シェルSkype for Business Serverクリックします。 
    
2. [Skype for Business Server管理シェル] で、次のコマンドを入力し、Enter キーを押します (必ず、コピーへの実際のパスをWatchernode.msi。
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 前述したように、Watchernode.msiウィンドウから実行することもできます。 コマンド ウィンドウを開くには、[**スタート**] をクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。 コマンド ウィンドウが開いたら、上記の手順 2 に示したのと同じコマンドを入力します。 
  
ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。 このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。
  

