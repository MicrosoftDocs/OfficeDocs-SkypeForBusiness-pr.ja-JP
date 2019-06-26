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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '概要: Skype for Business Server の代理トランザクション用にウォッチャーノードをインストールして構成します。'
ms.openlocfilehash: f95803f61d527196c97c7a6a17b8e0bfcfdfbc7a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221519"
---
# <a name="install-and-configure-watcher-nodes"></a>監視ノードのインストールと構成
 
**概要:** Skype for Business Server の代理トランザクション用にウォッチャーノードをインストールして構成します。
  
ウォッチャーノードは、Skype for Business Server の代理トランザクションを定期的に実行するコンピューターです。 代理トランザクションは、Windows PowerShell コマンドレットであり、サインインや exchange のインスタントメッセージなどの主要なユーザーシナリオが期待どおりに機能していることを確認します。 Skype for Business Server 2015 の場合、System Center Operations Manager は、次の表に示す代理トランザクションを実行できます。これには、3つの組み込みトランザクションの種類が含まれます。
  
- **既定値**ウォッチャーノードが既定で実行する代理トランザクション。 新しいウォッチャーノードを作成するときに、そのノードが実行する代理トランザクションを指定できます。 (これは、CsWatcherNodeConfiguration コマンドレットで使用されるテストパラメーターの目的です。)ウォッチャーノードが作成されたときに Tests パラメーターを使用しないと、既定のすべての合成トランザクションが自動的に実行され、既定以外の代理トランザクションは実行されません。 つまり、たとえば、watcher ノードは、CsAddressBookService のテストを実行するように構成されていますが、テスト-CsExumConnectivity テストを実行するように構成されていないことを意味します。
    
- **既定以外の**場合ウォッチャーノードが既定で実行されていないことをテストします。 (詳しくは、「既定の型の説明」をご覧ください)。ただし、ウォッチャーノードを有効にして、既定以外の代理トランザクションのいずれかを実行することができます。 これは、(CsWatcherNodeConfiguration コマンドレットを使用して) ウォッチャーノードを作成するとき、またはウォッチャーノードを作成した後であれば、いつでも行うことができます。 既定以外の代理トランザクションの多くには、追加のセットアップ手順が必要であることに注意してください。 これらの手順の詳細については、「[代理トランザクション用の特別なセットアップ手順](test-users-and-settings.md#special_synthetictrans)」を参照してください。
    
- **拡張**特別な種類の既定以外の代理トランザクション。 他の代理トランザクションとは異なり、拡張テストは、1 回のパスで複数回実行できます。 これは、プールに対する複数の公衆交換電話網 (PSTN) 音声ルートなどの動作を検証するときに便利です。 これは、拡張テストの複数のインスタンスを監視ノードに追加するだけで構成できます。
    
監視ノードに他の代理トランザクションを追加する方法については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。 また、Skype for Business Server 管理シェルを使って、ウォッチャーノードから合成トランザクションを削除することもできます。
  
監視ノードで使用できる代理トランザクションは以下のとおりです。
  
|**コマンドレット名 (テスト名)**|**説明**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |ユーザーが連絡先リストに含まれていないユーザーを検索できることを確認します。  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |ユーザーが、連絡先リストに含まれていないユーザーを HTTP 経由で検索できることを確認します。  <br/> |
|Test-CsAVConference (AvConference)  <br/> |ユーザーが音声/ビデオ会議で作成と参加が可能なことを確認します。  <br/> |
|Test-CsGroupIM (IM Conferencing)  <br/> |ユーザーが会議中にインスタント メッセージを送信でき、3 人以上のユーザーとインスタント メッセージでの会話に参加できることを確認します。  <br/> |
|Test-CsIM (P2P IM)  <br/> |ユーザーがピアツーピア インスタント メッセージを送信できることを確認します。  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |ユーザーがピアツーピア音声通話を開始できることを確認します (シグナリングのみ)。  <br/> |
|Test-CsPresence (Presence)  <br/> |ユーザーが他のユーザーのプレゼンスを表示できることを確認します。  <br/> |
|Test-CsRegistration (Registration)  <br/> |ユーザーが Skype for Business にサインインできることを確認します。  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |ユーザーが企業の外部のユーザー (PSTN 番号) と通話できることを確認します。  <br/> |
|Test-CsASConference (ASConference)  <br/> |ユーザーがアプリケーション共有電話会議の作成と参加を行うことができることを確認します。  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |音声ビデオ エッジ サーバーがピアツーピア通話と会議通話を行うための接続を受け入れることができることを確認します。  <br/> |
|Test-CsDataConference (DataConference)  <br/> |ユーザーが、データ グループ作業電話会議 (ホワイトボードや投票などのアクティビティが含まれるオンライン会議) に参加できることを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |ユーザーが電話番号をダイヤルして電話会議に参加できることを確認します。  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |ユーザーが Exchange ユニファイドメッセージング (UM) に接続できることを確認します。  <br/> |
|テスト-CsGroupIM-TestJoinLauncher (Joinランチャー)  <br/> |ユーザーがミーティングを作成でき、予定されたミーティングに Web アドレス リンクにより参加できることを確認します。  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |モバイル デバイス ユーザーがインスタント メッセージの登録と送信を実行できることを確認します。  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |ビデオ相互運用機能サーバーが起動していて、ビデオ SIP トランク経由の着信接続を処理できることを確認します。  <br/> **注:** 従来のモバイルクライアントに対する MCX のサポートは、Skype for Business Server 2019 では利用できなくなりました。 |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |ユーザーが常設チャット サービスを使用してメッセージを交換できることを確認します。  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |ユーザーが Web を介して電話会議に参加できることを確認します。  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |統合連絡先ストアを通じてユーザーの連絡先にアクセスできることを確認します。 統合連絡先ストアでは、Skype for Business Server 2015、Outlook メッセージングおよびコラボレーションクライアント、または Outlook Web Access を使用してアクセスできる単一の連絡先セットを管理することができます。  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |インスタント メッセージを Extensible Messaging and Presence Protocol (XMPP) ゲートウェイ経由で送信できることを確認します。  <br/> XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。  |

System Center Operations Manager を使用するためにウォッチャーノードをインストールする必要はありません。 これらのノードをインストールしていない場合でも、問題が発生するたびに Skype for Business Server の2015コンポーネントからリアルタイムの通知を受け取ることができます。 (コンポーネントとユーザー管理パックはウォッチャーノードを使用しません)。ただし、アクティブな監視管理パックを使用してエンドツーエンドのシナリオを監視する場合は、監視ノードが必要です。
  
> [!NOTE]
> 管理者は、Operations Manager の使用やインストールを行わなくても、代理トランザクションを手動で実行することもできます。 統合トランザクションでは、Skype for Business Server の展開のサイズに応じて、大量のコンピューターメモリとプロセッサ時間を使うことができます。 このため、監視ノードとして専用のコンピューターを使用することをお勧めします。 たとえば、Skype for Business Server フロントエンドサーバーを監視ノードとして機能するように構成することはできません。 ウォッチャーノードは、Skype for Business Server トポロジの他のコンピューターと同じ基本的なハードウェア要件を満たしている必要があります。 
  
> [!NOTE]
> Lync server 2013 と Skype for Business Server 2015 のコアシステムファイルを同じコンピューターにインストールできないため、従来の Lync Server 2013 ウォッチャーノードは、Skype for Business 2015 Server の [ウォッチャー] ノードと同じコンピューター上に併置できません。 ただし、Skype for Business Server 2015 監視ノードでは、Skype for Business Server 2015 と Lync Server 2013 を同時に監視できます。 既定の代理トランザクションは、両方の製品バージョンでサポートされています。 
  
Lync Server 2013 ウォッチャーノードは、確認のために企業内外に展開することができます。
  
- 社内ユーザー用プールへの接続。
    
- 社外で働くリモート ユーザー用の境界ネットワーク経由の接続。
    
- ブランチ オフィス アプライアンスへの接続。
    
- 企業内および境界ネットワーク経由での Lync Server 2013 への接続。
    
管理を容易にするため、社内および社外用の異なる認証オプションがあります。詳細については、「[Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans)」を参照してください。
  
監視ノードとして動作するようにコンピューターを構成するには、まず次の前提条件をすべて満たす必要があります。 
  
- System Center Operations Manager をインストールして、Skype for Business Server 2015 管理パックをインポートします。 また、ウォッチャーノードコンピューターが Skype for Business Server 2015 をインストールするための前提条件をすべて満たしていることを確認する必要があります。
    
- 監視ノード コンピューターに以下のアイテムをインストールします。
    
  - .NET Framework 4.5 の完全バージョン
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
これらの前提条件が満たされた後、次の操作を実行して監視ノードを構成できます。
  
1. ウォッチャーノードコンピューターに Skype for Business Server 2015 コアファイルをインストールします。
    
2. Watcher ノードコンピューターに System Center Operations Manager エージェントをインストールします。
    
3. Watchernode.msi 実行可能ファイルの実行。
    
4. **CsWatcherNodeConfiguration** コマンドレットによる監視ノードで使用されるテスト ユーザー アカウントの構成。
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Skype for Business Server 2015 コア ファイルおよび RTCLocal データベースのインストール

Skype for Business Server 2015 のコアファイルをコンピューターにインストールするには、次の手順を実行します。 RTCLocal データベースは、コア ファイルをインストールするときに自動的にインストールされます。 監視ノードに SQL Server をインストールする必要はないことに注意してください。 SQL Server Express が自動的にインストールされます。
  
Skype for Business Server 2015 コアファイルと RTCLocal データベースをインストールするには、次の操作を行います。
  
1. 監視ノード コンピューターで、[スタート] ボタン、[すべてのプログラム]、[アクセサリ] の順にクリックし、[コマンド プロンプト] を右クリックし、[管理者として実行] をクリックします。
    
2. コンソール ウィンドウで、次のコマンドを入力して Enter キーを押します。 Skype for Business Server セットアップファイルへの適切なパスを入力してください: D:\Setup.exe/BootstrapLocalMgmtTo コア Skype for Business Server コンポーネントが正常にインストールされたことを確認するには、[**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。[ **skype For Business server 2015**] をクリックし、[skype For Business **server 管理シェル**] をクリックします。 Skype for Business Server 管理シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 最初にこのコマンドを実行したときは、まだ監視ノード コンピューターを構成していないので何もデータが表示されません。 このコマンドを実行してもエラーが返されない場合は、Skype for Business Server のセットアップが正常に完了したと見なすことができます。 
  
監視ノード コンピューターが境界ネットワーク内にある場合は、次のコマンドを実行して Skype for Business Server 2015 のインストールを確認できます。
  
CsPinPolicyYou は、組織で使用するように構成されている PIN ポリシーの数に応じて、次のような情報を受け取ります。
  
Identity: グローバル
  
説明
  
MinPasswordLength: 5
  
Pinhistory カウント: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
PIN ポリシーに関する情報が表示された場合は、コア コンポーネントが正常にインストールされています。
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>監視ノードの Operation Manager エージェント ファイルのインストール

Skype for business Server のセットアップと同じように、レポートコンポーネントの通知を設定するには、Skype for Business Server 2015 ウォッチャーノードで System Center Operations Manager エージェントファイルをインストールする必要があります。 これにより、代理トランザクションが実行され、警告が System Center Operations Manager ルート管理サーバーに報告されます。
  
エージェントファイルをインストールするには、「監視対象の[Skype For Business サーバーコンピューターを構成](configure-computers-to-monitor.md)する」の手順に従ってください。
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>代理トランザクションを実行する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager エージェントファイルがインストールされたら、ウォッチャーノード自体を構成する必要があります。 監視ノードを構成する手順は監視ノードを境界ネットワークの内側に置くか、外側に置くかによって異なります。 
  
監視ノードの構成時には、そのノードが使用する認証方法の種類も選択する必要があります。 Skype for Business Server 2015 では、2つの認証方法のいずれかを選択できます。信頼されたサーバーまたは資格情報認証。 この 2 つの方法の主な違いを次の表にまとめます。
  
||**説明**|**サポートされる場所**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |内部サーバーを偽装する証明書を使用し、認証チャレンジをバイパスします。  <br/> 各監視ノードで多数のユーザー パスワードではなく、1 つの証明書を管理したいと考える管理者にとって便利です。  <br/> |エンタープライズの内側。  <br/> この方法では、監視ノードが監視対象のプールと同じドメイン内に存在する必要があります。 監視ノードとプールが別のドメインに存在する場合は、この方法ではなく、資格情報認証を使用します。  <br/> |
|Negotiate  <br/> |ユーザー名とパスワードを各監視ノードの Windows 資格情報マネージャーに保管します。  <br/> このモードは、パスワード管理の手間を必要としますが、エンタープライズの外側に位置する監視ノードの場合には唯一の選択肢となります。 このような外側に位置する監視ノードを認証の際に信頼済みのエンドポイントとして扱うことはできません。  <br/> |エンタープライズの外側。  <br/> エンタープライズの内側。  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>信頼されたサーバー認証を使用する監視ノードの構成
<a name="enable_synthetic_trans"> </a>

監視ノード コンピューターが境界ネットワーク内にある場合、信頼済みサーバー認証によって 1 つの証明書を管理するだけでよくなるので、管理負荷が大幅に軽減されます。膨大な数のユーザー アカウント パスワードを管理する必要はありません。
  
信頼済みサーバー認証を構成するには、まず監視ノード コンピューターをホストする信頼済みアプリケーション プールを作成します。 信頼されたアプリケーションプールを作成したら、そのウォッチャーノードの代理トランザクションを構成して、信頼できるアプリケーションとして実行する必要があります。
  
> [!NOTE]
> 信頼されたアプリケーションとは、Skype for Business Server 2015 の一部として実行される信頼された状態を提供するアプリケーションですが、製品の組み込みの一部ではありません。 Trusted status means that the application will not be challenged for authentication each time it runs.
  
信頼されたアプリケーションプールを作成するには、Skype for Business Server 管理シェルを開き、次のようなコマンドを実行します。
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 上記のコマンドのパラメーターの詳細については、「Skype for Business Server 管理シェルのプロンプトで次のように入力します。 
  
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
  
新しい信頼済みアプリケーションが作成されたことを確認するには、Skype for Business Server 管理シェルプロンプトで次のように入力します。
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>監視ノードで既定の証明書を構成する
<a name="enable_synthetic_trans"> </a>

TrustedServer 認証を使用する各ウォッチャーノードには、Skype for Business Server Deployment wizard を使って既定の証明書を割り当てる必要があります。 
  
既定の証明書を割り当てるには
  
1. [スタート] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business server 2015] をクリックして、[Skype for Business Server Deployment ウィザード] をクリックします。 
    
2. Skype for Business Server の展開ウィザードで、[Skype for Business Server システムのインストールまたは更新] をクリックし、[タイトルの要求]、[インストール]、または [証明書の割り当て] の [実行] をクリックします。 
    
> [!NOTE]
> [実行] ボタンをが無効になっている場合は、[ローカル構成ストアのインストール] で [実行] を最初にクリックしなければならないことがあります。 
  
次のいずれかの操作を行います。
  
- 既定の証明書として使用できる証明書が既にある場合は、証明書ウィザードで [既定] をクリックし、[割り当て] をクリックします。証明書の割り当てウィザードの手順に従って、証明書を割り当てます。
    
- 既定の証明書として使用する証明書を要求する必要がある場合は、[要求] をクリックし、証明書要求ウィザードの手順に従ってその証明書を要求します。Web サーバー証明書の既定値を使用すると、既定の証明書として割り当てることができる証明書を取得できます。
    
## <a name="install-and-configure-a-watcher-node"></a>監視ノードをインストールおよび構成する
<a name="enable_synthetic_trans"> </a>

ウォッチャーノードのコンピューターを再起動して証明書を構成したら、Watchernode ファイルを実行する必要があります。 (Operations Manager エージェントファイルと Skype for Business Server 2015 コアコンポーネントの両方がインストールされているコンピューターであれば、Watchernode を実行する必要があります)。 
  
監視ノードをインストールおよび構成するには
  
1. [スタート] をクリックし、[すべてのプログラム]、[Skype for Business Server 2015]、[Skype for business Server 管理シェル] の順にクリックして、Skype for Business Server 管理シェルを開きます。 
    
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
  

