---
title: 監視ノードのインストールと構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 代理トランザクションの監視ノードをインストールして構成します。'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640949"
---
# <a name="install-and-configure-watcher-nodes"></a>監視ノードのインストールと構成
 
**概要:** Skype for Business Server 代理トランザクションの監視ノードをインストールして構成します。
  
監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。 代理トランザクションは Windows PowerShell コマンドレットで、サインインまたは exchange インスタントメッセージへのサインイン機能など、主要なユーザーシナリオが期待どおりに動作していることを確認します。 Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、次の3つの代理トランザクションの種類が含まれます。
  
- **既定値**既定で監視ノードが実行する代理トランザクション。 新しい監視ノードを作成するときに、そのノードが実行する代理トランザクションを指定できます。 (これは、Set-cswatchernodeconfiguration コマンドレットで使用される Tests パラメーターの目的です。)監視ノードの作成時に Tests パラメーターを使用しない場合、既定の代理トランザクションがすべて自動的に実行され、既定以外の代理トランザクションは実行されません。 これは、たとえば、監視ノードが Test-CsAddressBookService テストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。
    
- **既定以外**監視ノードが既定で実行されないことをテストします。 (詳細については、既定の種類の説明を参照してください)。ただし、監視ノードを有効にして、既定以外の代理トランザクションを実行することができます。 これは、監視ノードを作成するとき (Set-cswatchernodeconfiguration コマンドレットを使用して)、または監視ノードが作成された後の任意の時点で行うことができます。 既定以外の代理トランザクションでは、多くの場合、特別なセットアップ手順が必要になることに注意してください。 これらの手順の詳細については、「[代理トランザクションの特別なセットアップ手順](test-users-and-settings.md#special_synthetictrans)」を参照してください。
    
- **拡張**特別な種類の既定以外の代理トランザクション。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証する場合に役立ちます。 これを構成するには、監視ノードに拡張テストの複数のインスタンスを追加するだけです。
    
他の代理トランザクションを監視ノードに追加するプロセスの詳細については、「[代理トランザクションを実行する監視ノードを構成する](watcher-nodes.md#enable_synthetic_trans)」を参照してください。 また、Skype for Business Server 管理シェルを使用して、監視ノードから代理トランザクションを削除することもできます。
  
監視ノードで使用できる代理トランザクションは以下のとおりです。
  
|**コマンドレット名 (テスト名)**|**説明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |ユーザーが自分の連絡先リストに含まれていないユーザーを検索できることを確認します。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |ユーザーが自分の連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。  <br/> |
|テスト-CsAVConference (AvConference)  <br/> |ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。  <br/> |
|テスト-CsGroupIM (IM 会議)  <br/> |ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。  <br/> |
|テスト-CsIM (P2P IM)  <br/> |ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。  <br/> |
|Test-csp2pav (P2PAV)  <br/> |ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。  <br/> |
|Test-CsPresence (Presence)  <br/> |ユーザーが他のユーザーのプレゼンスを表示できることを確認します。  <br/> |
|Test-CsRegistration (Registration)  <br/> |ユーザーが Skype for Business にサインインできることを確認します。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。  <br/> |
|テスト-CsASConference (Asコンファレンス)  <br/> |ユーザーがアプリケーション共有会議の作成と参加を行うことができることを確認します。  <br/> |
|Test-csavedgeconnectivity (AVEdgeConnectivity)  <br/> |音声ビデオエッジサーバーがピアツーピア通話と電話会議のための接続を受け入れることができることを確認します。  <br/> |
|Test-csdataconference (DataConference)  <br/> |ユーザーがデータコラボレーション会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。  <br/> |
|テスト-Csダイヤルイン会議 (ダイヤルイン会議)  <br/> |ユーザーが会議に参加するために電話番号をダイヤルできることを確認します。  <br/> |
|テスト-Csダイヤルイン会議 (ダイヤルイン会議)  <br/> |ユーザーが会議に参加するために電話番号をダイヤルできることを確認します。  <br/> |
|テスト-CsExumConnectivity (ExumConnectivity)  <br/> |ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。  <br/> |
|Test-CsGroupIM-TestJoinLauncher (Joinラウンチャー)  <br/> |ユーザーがスケジュールされた会議を作成し、(web アドレスリンクで) 参加できることを確認します。  <br/> |
|Test-csmcxp2pim (MCXP2PIM)  <br/> |モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。  <br/> |
|CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |ビデオ相互運用サーバーが稼働しており、ビデオ SIP トランク経由の受信接続を処理できることを確認します。  <br/> **注:** 従来のモバイルクライアントに対する MCX サポートは、Skype for Business Server 2019 では利用できなくなりました。 |
|Test-cspersistentchatmessage (PersistentChatMessage)  <br/> |ユーザーが常設チャットサービスを使用してメッセージを交換できることを確認します。  <br/> |
|Test-csucwaconference (UcwaConference)  <br/> |ユーザーが web 経由で会議に参加できることを確認します。  <br/> |
|Test-csunifiedcontactstore (UnifiedContactStore)  <br/> |統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアを使用すると、ユーザーは、Skype for Business Server 2015、Outlook メッセージングおよびコラボレーションクライアント、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理することができます。  <br/> |
|テスト-CsXmppIM (XmppIM)  <br/> |拡張メッセージングとプレゼンスプロトコル (XMPP) ゲートウェイを介してインスタントメッセージを送信できることを確認します。  <br/> XMPP ゲートウェイおよびプロキシは、Skype for business Server 2015 で利用できますが、Skype for business Server 2019 ではサポートされなくなりました。  |

System Center Operations Manager を使用するために監視ノードをインストールする必要はありません。 これらのノードをインストールしていない場合でも、問題が発生したときに Skype for Business Server 2015 のコンポーネントからリアルタイムで通知を受け取ることができます。 (コンポーネントおよびユーザー管理パックでは、監視ノードは使用されません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。
  
> [!NOTE]
> 管理者は、Operations Manager を使用したりインストールしたりせずに、代理トランザクションを手動で実行することもできます。 Skype for Business Server の展開の規模によっては、代理トランザクションが大量のコンピューターメモリとプロセッサ時間を使用することがあります。 このため、監視ノードとして専用のコンピューターを使用することをお勧めします。 たとえば、監視ノードとして動作するように Skype for Business Server フロントエンドサーバーを構成することはできません。 監視ノードは、Skype for Business Server トポロジの他のコンピュータと同じ基本的なハードウェア要件を満たす必要があります。 
  
> [!NOTE]
> Lync server 2013 と Skype for Business Server 2015 のコアシステムファイルを同じコンピューターにインストールできないため、従来の Lync Server 2013 監視ノードを Skype for Business Server 2015 監視ノードと同じコンピューターに併置することはできません。 ただし、Skype for Business Server 2015 監視ノードは、Skype for business Server 2015 および Lync Server 2013 を同時に監視できます。 両方の製品バージョンで既定の代理トランザクションがサポートされています。 
  
Lync Server 2013 監視ノードはエンタープライズの内部または外部に展開され、次の点を確認できます。
  
- 社内ユーザー用プールへの接続。
    
- 企業外で作業するリモートユーザーのための境界ネットワーク経由の接続。
    
- ブランチ オフィス アプライアンスへの接続。
    
- 企業内および境界ネットワークを介した Lync Server 2013 への接続。
    
管理を容易にするために、エンタープライズの内部と外部で異なる認証オプションを使用できます。 詳細については、「[代理トランザクションを実行する監視ノードを構成する](watcher-nodes.md#enable_synthetic_trans)」を参照してください。
  
監視ノードとして動作するようにコンピューターを構成するには、最初に以下の前提条件を満たす必要があります。 
  
- System Center Operations Manager をインストールして、Skype for Business Server 2015 管理パックをインポートします。 また、監視ノードコンピューターが Skype for Business Server 2015 をインストールするためのすべての前提条件を満たしていることを確認する必要があります。
    
- 監視ノードコンピューターに次のアイテムをインストールします。
    
  - 完全版の .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
前提条件が満たされたら、次の手順を実行して監視ノードを構成できます。
  
1. 監視ノードコンピューターに Skype for Business Server 2015 コアファイルをインストールします。
    
2. 監視ノードコンピューターに System Center Operations Manager エージェントをインストールします。
    
3. Watchernode.msi の実行可能ファイルを実行します。
    
4. 監視ノードによって使用されるテストユーザーアカウントを構成するには、 **set-cswatchernodeconfiguration**コマンドレットを使用します。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Skype for Business Server 2015 コアファイルおよび RTCLocal データベースをインストールする

Skype for Business Server 2015 のコアファイルをコンピューターにインストールするには、次の手順を実行します。 RTCLocal データベースは、コアファイルのインストール時に自動的にインストールされます。 監視ノードに SQL Server をインストールする必要はないことに注意してください。 SQL Server Express は自動的にインストールされます。
  
Skype for Business Server 2015 コアファイルおよび RTCLocal データベースをインストールするには、次のようにします。
  
1. 監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。
    
2. コンソールウィンドウで、次のコマンドを入力し、ENTER キーを押します。 Skype for Business Server のセットアップファイルへの適切なパスを入力してください。 D:\Setup.exe/BootstrapLocalMgmtTo コア Skype for Business Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **skype for business server 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。 Skype for Business Server 管理シェルで、次の Windows PowerShell コマンドを入力して enter キーを押します。
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> このコマンドを初めて実行したときは、監視ノードコンピューターがまだ構成されていないため、データは返されません。 コマンドがエラーを返さずに実行されている場合は、Skype for Business Server のセットアップが正常に完了したと見なすことができます。 
  
監視ノードコンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して、Skype for Business Server 2015 のインストールを確認できます。
  
CsPinPolicyYou は、組織で使用するように構成された PIN ポリシーの数に応じて、次のような情報を受け取ります。
  
Identity: Global
  
Description
  
MinPasswordLength: 5
  
Pinhistory Count: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts:
  
PIN ポリシーに関する情報が表示された場合は、コアコンポーネントが正常にインストールされています。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>操作マネージャーエージェントファイルを監視ノードにインストールする

レポートコンポーネント通知の Skype for Business Server のセットアップと同様に、Skype for Business Server 2015 監視ノードで System Center Operations Manager エージェントファイルをインストールする必要があります。 これにより、代理トランザクションが実行され、警告が System Center Operations Manager のルート管理サーバーに報告されるようになります。
  
エージェントファイルをインストールするには、「監視対象の[Skype For Business Server コンピューターを構成](configure-computers-to-monitor.md)する」に記載されている手順に従います。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>代理トランザクションを実行する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager エージェントファイルがインストールされたら、監視ノード自体を構成する必要があります。 監視ノードコンピューターが境界ネットワーク内にあるか境界ネットワーク外にあるかによって、これを実行する手順は異なります。 
  
監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Skype for Business Server 2015 では、信頼されたサーバーまたは資格情報認証という2つの認証方法のどちらかを選択できます。 次の表は、これら2つのメソッドの違いを示しています。
  
||**説明**|**サポートされる場所**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。  <br/> 各監視ノードで多数のユーザーパスワードではなく、1つの証明書を管理したいと考える管理者にとって便利です。  <br/> |エンタープライズの内側。  <br/> この方法では、監視ノードは監視対象のプールと同じドメイン内にある必要があります。 監視ノードとプールが異なるドメインにある場合は、資格情報認証を代わりに使用します。  <br/> |
|取り決め  <br/> |ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。  <br/> このモードでは、さらに多くのパスワードを管理する必要がありますが、エンタープライズ外部の監視ノードには唯一のオプションです。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。  <br/> |エンタープライズの外側。  <br/> エンタープライズの内側。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>信頼されたサーバー認証を使用するように監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

監視ノードコンピューターが境界ネットワーク内にある場合、信頼されたサーバー認証を使用すると、多数のユーザーアカウントパスワードを使用するのではなく、1つの証明書を保持することによって管理タスクを大幅に削減できます。
  
信頼されたサーバー認証を構成するには、最初に、監視ノードコンピューターをホストする信頼されたアプリケーションプールを作成する必要があります。 信頼済みアプリケーションプールを作成したら、その監視ノードで代理トランザクションを構成して、信頼されたアプリケーションとして実行する必要があります。
  
> [!NOTE]
> 信頼されたアプリケーションとは、信頼された状態で Skype for Business Server 2015 の一部として実行されるアプリケーションですが、製品の組み込みパーツではありません。 信頼済みステータスのアプリケーションは、実行のたびに認証でチャレンジされることはありません。
  
信頼されたアプリケーションプールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 上記のコマンドのパラメーターの詳細については、Skype for Business Server 管理シェルプロンプトから次のコマンドを入力してください。 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

信頼されたアプリケーションプールを作成したら、**次のよう**なコマンドを使用して、代理トランザクションを信頼されたアプリケーションとして実行するように監視ノードコンピューターを構成できます。
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

このコマンドが完了し、信頼されたアプリケーションが作成されたら、 **Enable-CsTopology**コマンドレットを実行して、変更が有効になるようにする必要があります。
  
```PowerShell
Enable-CsTopology
```

監視ノードのコンピューターアカウントでは、一部の代理トランザクションに対して CMS を照会する機能が必要です。 この機能を許可するには、監視ノードのコンピューターアカウントを RTCUniversalReadOnlyAdmins セキュリティグループに追加します。 AD レプリケーションが発生したら、コンピューターを再起動します。
  
新しい信頼済みアプリケーションが作成されたことを確認するには、Skype for Business Server 管理シェルプロンプトで次のように入力します。
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する
<a name="enable_synthetic_trans"> </a>

TrustedServer 認証を使用する各監視ノードには、Skype for Business Server 展開ウィザードを使用して割り当てられた既定の証明書が必要です。 
  
既定の証明書を割り当てるには、次のようにします。
  
1. [スタート]、[すべてのプログラム]、[Skype for Business Server 2015]、[Skype for Business Server 展開ウィザード] の順にクリックします。 
    
2. Skype for Business Server の展開ウィザードで、[Skype for business Server システムのインストールまたは更新] をクリックし、[タイトルの要求、インストール、または証明書の割り当て] の [実行] をクリックします。 
    
> [!NOTE]
> [実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。 
  
以下のいずれかの手順を実行します。
  
- 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。 証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
- 既定の証明書を使用するために証明書を要求する必要がある場合は、[要求] をクリックし、証明書の要求ウィザードの手順に従って証明書を要求します。 Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。
    
## <a name="install-and-configure-a-watcher-node"></a>監視ノードをインストールおよび構成する
<a name="enable_synthetic_trans"> </a>

監視ノードコンピューターを再起動し、証明書を構成した後、ファイル Watchernode.msi を実行する必要があります。 (Operations Manager エージェントファイルと Skype for Business Server 2015 コアコンポーネントの両方がインストールされているコンピューターで Watchernode.msi を実行する必要があります)。 
  
監視ノードをインストールおよび構成するには、次のようにします。
  
1. [スタート]、[すべてのプログラム]、[Skype for Business Server 2015] の順にクリックし、[Skype for Business Server 管理シェル] をクリックして、Skype for Business Server 管理シェルを開きます。 
    
2. 管理シェルで次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを確認してください)。
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> コマンドウィンドウから Watchernode.msi n を実行することもできます。 コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。 コマンドウィンドウが開いたら、上記と同じ手順2で示したコマンドを入力します。 
  
> [!IMPORTANT]
> 上記のコマンドで、名前と値のペアの Authentication = TrustedServer は大文字と小文字を区別します。 この値は、示されているとおりに入力する必要があります。 たとえば、次のコマンドは、適切な文字の大文字と小文字の区別を使用しないため、失敗します。 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer モードは、境界ネットワーク内に存在するコンピューターでのみ使用できます。 監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上でテストユーザーのパスワードを管理する必要はありません。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>ネゴシエーションを使用するように監視ノードを構成する
<a name="enable_synthetic_trans"> </a>

監視ノードコンピューターが境界ネットワークの外側にある場合は、次の手順に従って、代理トランザクションを実行するように監視ノードを構成する必要があります。特に、信頼されたアプリケーションプールまたは信頼されたアプリケーションを作成しないでください。 これは、次の2つのタスクを完了する必要があることを意味します。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC ローカルの読み取り専用の Administrators グループのメンバーシップを更新する

監視ノードが境界ネットワークの外側にある場合は、監視ノードで次の手順を実行して、ネットワークサービスアカウントを監視ノードコンピューターの RTC Local 読み取り専用管理者グループに追加する必要があります。
  
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

次の手順では、ファイル Watchernode.msi を実行します。 
  
1. Microsoft Skype for Business Server 2015 管理シェルを開きます。 [スタート]、[すべてのプログラム]、[Microsoft Skype for Business Server 2015]、[Skype for Business Server 管理シェル] の順にクリックします。 
    
2. Skype for Business Server 管理シェルで、次のコマンドを入力し、enter キーを押します (Watchernode.msi のコピーへの実際のパスを必ず指定してください)。
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 前述したように、Watchernode.msi はコマンドウィンドウから実行することもできます。 コマンド ウィンドウを開くには、[**スタート**] をクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。 コマンドウィンドウが開いたら、上記と同じ手順2で示したコマンドを入力します。 
  
ウォッチャー ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。 このモードでは、管理者がウォッチャー ノードのテスト ユーザー パスワードを管理する必要があります。
  

