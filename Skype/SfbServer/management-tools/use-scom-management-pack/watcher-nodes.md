---
title: 監視ノードのインストールと構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: をインストールし、Skype のビジネス サーバー代理トランザクションの監視ノードを構成します。'
ms.openlocfilehash: 6abaf800d2ef99f8b7a8a487f20529ad76fb996e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879428"
---
# <a name="install-and-configure-watcher-nodes"></a>監視ノードのインストールと構成
 
**の概要:** インストールし、Skype のビジネス サーバー代理トランザクションの監視ノードを構成します。
  
ウォッチャー ノードとは、Skype をビジネス サーバー代理トランザクションを定期的に実行しているコンピューターです。 代理トランザクションは、サインインする機能や、インスタント メッセージを交換する機能などの主要なユーザー シナリオが期待どおりに動作していることを確認する Windows PowerShell コマンドレットです。 ビジネス サーバー 2015 の Skype は、System Center Operations Manager は 3 つの合成のトランザクション タイプは、次の表に示すように代理トランザクションを実行できます。
  
- **既定**ウォッチャー ノードが既定で実行されるトランザクションを合成します。 (合成) するを指定することができます新しいウォッチャー ノードを作成するときにそのノードで実行するトランザクションです。 (新規 CsWatcherNodeConfiguration コマンドレットで使用されるテスト パラメーターの目的は) です。ウォッチャー ノードを作成するときにテスト パラメーターを使用しない場合は自動的にすべてのデフォルト代理トランザクションを実行し、いずれかの既定以外の代理トランザクションは実行されません。 つまりなどの監視ノード テスト CsAddressBookService テストを実行するように構成されますが、テスト CsExumConnectivity テストを実行するのには構成されません。
    
- **既定ではないです。** ウォッチャー ノードが既定では実行しないことをテストします。 (詳細については、既定の種類の説明を参照してください)。ただし、既定以外の代理トランザクションを実行するウォッチャー ノードを有効にすることができます。 (新規 CsWatcherNodeConfiguration コマンドレットを使用して) で、[監視] ノードを作成するまたはウォッチャー ノードの後に、いつでもが作成されたときに、これを行うことができます。 追加のセットアップ手順を必要とする既定以外の代理トランザクションの多くに注意してください。 これらの手順の詳細については、代理トランザクションの特殊なセットアップ手順を参照してください。 次の手順の詳細については、[代理トランザクションのセットアップの特別な指示](test-users-and-settings.md#special_synthetictrans)を参照してください。
    
- **拡張**代理トランザクションの既定以外の特別な種類です。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。 これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。
    
監視ノードに他の代理トランザクションを追加する方法については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。 ビジネス サーバー管理シェルの Skype は、監視ノードから代理トランザクションを削除するのにも使用できます。
  
監視ノードで使用できる代理トランザクションは以下のとおりです。
  
|**コマンドレット名 (テスト名)**|**説明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |ユーザーが連絡先リストに登録されていないユーザーを検索することを確認します。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |ユーザーが HTTP 経由で自分の連絡先リストに登録されていないユーザーを検索することを確認します。  <br/> |
|Test-CsAVConference (AvConference)  <br/> |ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。  <br/> |
|Test-CsGroupIM (IM Conferencing)  <br/> |ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。  <br/> |
|Test-CsIM (P2P IM)  <br/> |ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。  <br/> |
|Test-CsPresence (Presence)  <br/> |ユーザーが他のユーザーのプレゼンスを表示することを確認します。  <br/> |
|Test-CsRegistration (Registration)  <br/> |ユーザーは、Skype をビジネスのために、サインインすることを確認します。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。  <br/> |
|Test-CsASConference (ASConference)  <br/> |ユーザーがアプリケーション共有電話会議の作成と参加を行うことができることを確認します。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。  <br/> |
|Test-CsDataConference (DataConference)  <br/> |ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |ユーザーが Exchange ユニファイド メッセージング (UM) に接続できることを確認します。  <br/> |
|テスト-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクにより参加できることを確認します。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |ビデオの相互運用機能のサーバーが起動して、ビデオの SIP トランク経由で着信接続を処理できることを確認します。  <br/> **注:** 従来のモバイル クライアント用の MCX サポートはビジネス サーバー 2019 の Skype で利用可能ではありません。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |ユーザーが Web を介して電話会議に参加できることを確認します。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアには、ユーザーが単一のビジネス サーバー 2015、Outlook メッセージングおよびコラボレーション クライアントでは、または Outlook Web Access の Skype を使用してアクセスできるメンバーのセットを維持する方法が用意されています。  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |インスタント メッセージを Extensible Messaging and Presence Protocol (XMPP) ゲートウェイ経由で送信できることを確認します。  <br/> XMPP ゲートウェイとプロキシ サーバー 2015 のビジネス用の Skype では利用ビジネス サーバー 2019 の Skype でサポートされていません。  |

System Center Operations Manager を使用するウォッチャー ノードをインストールする必要はありません。 これらのノードをインストールしない場合でもから入手できますリアルタイム ・ アラート Skype サーバー 2015 のビジネス コンポーネントの問題が発生するたびにします。 (コンポーネントとユーザーの管理パックが使用ウォッチャー ノード)。ただし、監視ノードは、アクティブな監視管理パックを使用して、エンド ・ ツー ・ エンドのシナリオを監視する場合は、必要があります。
  
> [!NOTE]
> 管理者は、Operations Manager の使用やインストールを行わなくても、代理トランザクションを手動で実行することもできます。 サイズによっては、Skype をビジネス サーバーの展開の代理トランザクションは、大量のコンピューターのメモリとプロセッサ時間を使用できます。 このため、監視ノードとして専用のコンピューターを使用することをお勧めします。 など、Skype のビジネス サーバー フロント エンド サーバー監視ノードとして機能するように構成しないでください。 ウォッチャー ノードは、ビジネスのサーバー トポロジの場合、Skype での他のコンピューターと同じハードウェアの基本的な要件を満たす必要があります。 
  
> [!NOTE]
> 同じコンピューター上の Lync Server 2013 と Skype ビジネス サーバー 2015 のコア システム ファイルをインストールすることはできませんので、ビジネス サーバー 2015 ウォッチャー ノードを Skype と同じコンピューターにレガシーの Lync Server 2013 のウォッチャー ノードを共存させることはできません。 ただし、Skype のビジネス サーバー 2015 ウォッチャー ノードがビジネス サーバー 2015 と Lync Server 2013 の Skype を同時に監視することができます。 代理トランザクションの既定値は、両方の製品のバージョンでサポートされます。 
  
確認するためにエンタープライズの内外は、Lync Server 2013 のウォッチャー ノードを展開する場合があります。
  
- 社内ユーザー用プールへの接続。
    
- 社外で働くリモート ユーザー用の境界ネットワーク経由の接続。
    
- ブランチ オフィス アプライアンスへの接続。
    
- 企業の内部および境界領域のネットワークを介して Lync Server 2013 に接続します。
    
管理を容易にするため、社内および社外用の異なる認証オプションがあります。詳細については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。
  
監視ノードとして動作するようにコンピューターを構成するには、まず次の前提条件をすべて満たす必要があります。 
  
- System Center Operations Manager をインストールし、管理パックのビジネス サーバー 2015 の Skype をインポートします。 まず、監視ノード コンピューターがビジネス サーバー 2015 の Skype をインストールするためのすべての前提条件を満たしているを確認する必要があります。
    
- 監視ノード コンピューターに以下のアイテムをインストールします。
    
  - フル バージョンの.NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
これらの前提条件が満たされた後、次の操作を実行して監視ノードを構成できます。
  
1. ウォッチャー ノード コンピューター上のコア ファイルのビジネス サーバー 2015 の Skype をインストールします。
    
2. ウォッチャー ノード コンピューターの System Center Operations Manager エージェントをインストールします。
    
3. Watchernode.msi 実行可能ファイルの実行。
    
4. **CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザー アカウントの構成。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Skype for Business Server 2015 コア ファイルおよび RTCLocal データベースのインストール

ビジネス サーバー 2015 中核となるコンピューター上のファイル、Skype をインストールするには、次の手順を完了します。 RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。 ウォッチャー ノードで SQL Server をインストールする必要はありません注意してください。 SQL Server Express が自動的にインストールされます。
  
ビジネス サーバー 2015 のコア ファイルと RTCLocal データベースの Skype をインストールするには。
  
1. 監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。
    
2. コンソール ウィンドウで、次のコマンドを入力して Enter キーを押します。 Skype をビジネス サーバーのセットアップ ファイルを適切なパスを入力してください:/BootstrapLocalMgmtTo は、ビジネス サーバー コンポーネントのコア Skype が正常にインストールされていることを確認して D:\Setup.exe が [**スタート**] ボタン、[**すべてのプログラム**] をクリックして**ビジネス サーバー 2015 の Skype**をクリックし、 **Skype ビジネス サーバー管理シェル**] をクリックします。 ビジネス サーバー管理シェルの Skype では、次の Windows PowerShell コマンドを入力し、ENTER キーを押します。
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 最初にこのコマンドを実行したときは、まだ監視ノード コンピューターを構成していないので何もデータが表示されません。 エラーを返さずにコマンドを実行する場合は、ビジネス サーバーのセットアップの Skype が正常に完了したことを想定できます。 
  
監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。
  
Get CsPinPolicyYou 暗証番号 (pin) ポリシーを構成、組織で使用するための数によって、次のような情報が表示されます。
  
識別情報: グローバル
  
説明:
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>監視ノードの Operation Manager エージェント ファイルのインストール

同様に Skype ビジネス サーバーのセットアップ コンポーネントのアラートを報告するためのビジネス サーバー 2015 ウォッチャー ノードを Skype には、System Center Operations Manager エージェントのファイルをインストールするが必要です。 これにより、合成のトランザクションを実行して、システム センター操作マネージャー ルートの管理サーバーに報告する警告です。
  
エージェントのファイルをインストールするには、[構成 Skype ビジネス サーバーのコンピューターを監視するため](configure-computers-to-monitor.md)に記載されている手順に従います。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>代理トランザクションを実行する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager エージェントのファイルをインストールすると、ウォッチャー ノード自体を構成する必要があります。 監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。 
  
監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 ビジネス サーバー 2015 の Skype を使用すると、2 つの認証方法のいずれかを選択する: 信頼されたサーバーまたは認証の資格情報です。 この 2 つの方法の主な違いを次の表にまとめます。
  
||**説明**|**サポートされる場所**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。  <br/> 各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理したいと考える管理者にとって便利です。  <br/> |エンタープライズの内側。  <br/> この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があります。 監視ノードとプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。  <br/> |
|Negotiate  <br/> |ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。  <br/> このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。  <br/> |エンタープライズの外側。  <br/> エンタープライズの内側。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>信頼されたサーバー認証を使用する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。
  
信頼済みサーバー認証を構成するには、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。 信頼されたアプリケーション プールを作成した後は、信頼されたアプリケーションとして実行するウォッチャー ノードにし、代理トランザクションを構成しなければなりません。
  
> [!NOTE]
> 信頼されたアプリケーションは、ビジネス サーバー 2015 年の Skype の一部として実行するのには信頼される側のステータスが与えられますが、組み込み製品の一部ではないアプリケーションです。 Trusted status means that the application will not be challenged for authentication each time it runs.
  
信頼されたアプリケーション プールを作成するには、ビジネス サーバー管理シェルを開くには、Skype と次のようなコマンドを実行します。
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 上記のコマンドのパラメーターに関する詳細については、ビジネスのサーバー管理シェル プロンプトの Skype から以下を入力します。 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

信頼済みアプリケーション プールの作成後、これを行うには、**New-CsTrustedApplication** コマンドレットと次のようなコマンドを使用して、代理トランザクションが信頼済みアプリケーションとして実行されるように監視ノード コンピューターを構成します。
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

上記のコマンドが完了し、信頼済みアプリケーションが作成されたら、**Enable-CsTopology** コマンドレットを実行して変更を有効にします。
  
```
Enable-CsTopology
```

Enable-CsTopology を実行後、コンピューターを再起動します。
  
新しい信頼されたアプリケーションが作成されたことを確認するには、ビジネス サーバー管理シェル プロンプトの Skype で次を入力します。
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する
<a name="enable_synthetic_trans"> </a>

向こう側にある認証を使用する各監視ノードには、Skype ビジネス サーバーの展開ウィザードを使用して割り当てられている既定の証明書が必要です。 
  
既定の証明書を割り当てるには
  
1. [開始] をクリックしてすべてのプログラム] をクリックして、Skype ビジネス サーバー 2015 年の Skype をビジネス サーバーの展開ウィザードをクリックします。 
    
2. ビジネス サーバーの展開ウィザードの Skype、サーバーのビジネス システムのインストールまたは更新プログラムの Skype をクリックして.] の下の要求の実行、インストール、または証明書を割り当てる] をクリックし、 
    
> [!NOTE]
> [実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。 
  
次のいずれかの操作を行います。
  
- 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
- 既定の証明書として使用する証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。
    
## <a name="install-and-configure-a-watcher-node"></a>監視ノードをインストールおよび構成する
<a name="enable_synthetic_trans"> </a>

ウォッチャー ノードのコンピューターを再起動し、証明書を構成した後は、ファイル Watchernode.msi を実行する必要があります。 (必要がありますを実行する Watchernode.msi の任意のコンピューターのオペレーション マネージャー エージェントのファイルとサーバー 2015 のビジネスのコア ・ コンポーネントの Skype の両方がインストールされている) 
  
監視ノードをインストールおよび構成するには
  
1. ビジネス サーバー管理シェルの開始をクリックすると、すべてのプログラムをクリックすると、Skype ビジネス サーバー 2015 年をクリックし、Skype ビジネス サーバー管理シェルので、Skype を開きます。 
    
2. 管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> コマンド ウィンドウから Watchernode.msi を実行することもできます。コマンド ウィンドウを開くには、[スタート] をクリックし、[コマンド プロンプト] を右クリックして、[管理者として実行] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。 
  
> [!IMPORTANT]
> 上記のコマンドの名前/値ペア Authentication=TrustedServer は大文字と小文字が区別されるので、ここで示すとおりに正確に入力する必要があります。たとえば次のコマンドは、大文字と小文字が正しく使用されていないので失敗します。 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer モードは、境界ネットワーク内のコンピューターでのみ使用できます。監視ノードが TrustedServer モードで実行されている場合、管理者はコンピューター上のテスト ユーザー パスワードを管理する必要はありません。
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>ネゴシエートを使用する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワークの外側にある場合は、代理トランザクションを実行するように監視ノードを構成するために、少し異なる手順に従う必要があります。特に、信頼されたアプリケーション プールや信頼されたアプリケーションは作成しないでください。つまり、次に示す個別の 2 つのタスクを完了する必要があります。
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-Only Administrators グループのメンバーシップの更新

監視ノードが境界ネットワークの外側にある場合は、Network Service アカウントを監視ノード コンピューターの RTC Local Read-only Administrators グループに追加する必要があります。そのためには、監視ノードで以下の手順を完了します。
  
1. [スタート] メニューの [コンピューター] を右クリックし、[管理] をクリックします。
    
2. サーバー マネージャーで、[構成]、[ローカル ユーザーとグループ] の順に展開し、[グループ] をクリックします。
    
3. [グループ] ウィンドウで、[RTC Local Read-only Administrators] をダブルクリックします。
    
4. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[追加] をクリックします。
    
5. [ユーザー、コンピューター、サービス アカウント、またはグループの選択] ダイアログで、[場所] をクリックします。
    
6. [場所] ダイアログ ボックスで、監視ノード コンピューターの名前を選択し、[OK] をクリックします。
    
7. [選択するオブジェクト名を入力してください] ボックスに、「Network Service」と入力し、[OK] をクリックします。
    
8. [RTC Local Read-only Administrators のプロパティ] ダイアログ ボックスで、[OK] をクリックし、[サーバー マネージャー] を閉じます。
    
9. 監視ノード コンピューターを再起動します。
    
### <a name="install-the-watcher-node-configuration-files"></a>監視ノード構成ファイルのインストール

次に、Watchernode.msi ファイルを実行します。 
  
1. Microsoft Skype for Business Server 2015 管理シェルを以下の手順で起動します。[スタート]、[すべてのプログラム]、[Microsoft Skype for Business Server 2015]、[Skype for Business Server 管理シェル] の順にクリックします。 
    
2. Skype for Business Server 管理シェルで、次のコマンドを入力して、Enter キーを押します (Watchernode.msi のコピーへの実際のパスを指定)。
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 前述のように、Watchernode.msi はコマンド ウィンドウから実行することもできます。コマンド ウィンドウを開くには、[**スタート**] メニューをクリックし、[**コマンド プロンプト**] を右クリックして、[**管理者として実行**] をクリックします。コマンド ウィンドウが開いたら、上記の手順 2 と同じコマンドを入力します。 
  
監視ノードを信頼されたアプリケーション プールとしてセットアップできない場合はいつでも、ネゴシエート モードが使用されます。このモードでは、管理者が監視ノードのテスト ユーザー パスワードを管理する必要があります。
  

