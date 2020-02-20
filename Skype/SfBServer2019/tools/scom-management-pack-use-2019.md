---
title: SCOM 管理パックを使用して Skype for Business Server 2019 を管理する
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 インフラストラクチャを System Center Operations Manager と連携するように構成する方法について説明します。'
ms.openlocfilehash: 54c9f3dadb73df45ddc21cfc40ff83711032a4c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150544"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>SCOM 管理パックを使用して Skype for Business Server 2019 を管理する
 
**概要:** System Center Operations Manager と連携するように Skype for Business Server 2019 インフラストラクチャを構成する方法について説明します。
  
理想的な世界では、Skype for Business Server 2019 で問題が発生することはありません。 ただし、Skype for Business Server は、ネットワーククラッシュやハードウェア障害などの外部要因の影響を受ける場合があります。 Skype for Business Server 2019 管理パックを使用すると、潜在的な問題を事前に識別して対処することができます。 このようにして、Skype for Business Server 2019 管理パックは System Center Operations Manager の機能を拡張します。
  
この情報は、Skype for Business Server 2019 communications software 用の監視パックのバージョン9319.0 に基づいて作成されました。
  
## <a name="configuration-overview"></a>構成の概要

 System Center Operations Manager と連携するように Skype for Business Server 2019 インフラストラクチャを構成するには、次の3つの作業を行う必要があります。
  
[プライマリ管理サーバーを](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md)識別して構成します。 これを行うには、System Center Operations Manager 2012 SP1 または R2 をインストールする必要があります。 
  
 監視対象の[Skype For Business Server コンピューターを](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md)識別して構成します。 System Center Operations manager を使用して Skype for Business Server コンピューターを監視するには、System Center Operations Manager エージェントファイルをインストールし、プロキシとして動作するように各サーバーを構成する必要があります。 
  
 監視ノードを識別し、[インストールして構成](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md)します。 監視ノードは、Skype for business Server 代理トランザクションを定期的に実行するコンピューターです。 Windows PowerShell コマンドレットを使用すると、システムにログオンしたり、exchange を利用したりするなど、主要な Skype for Business Server コンポーネントを確認できます。メッセージは期待どおりに動作しています。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager のルート管理サーバーとエージェントのサポート

管理パックは、System Center Operations Manager 2007 R2 (64 ビット) (移行のためにのみサポートされます) または System Center Operations Manager 2012 &amp; SP1 R2 (64 ビット) と組み合わせて使用できます。 次の表に、Skype for Business Server 2019 の管理パックでサポートされている構成を示します。 
  
|**構成**|**サポートの有無**|
|:-----|:-----|
|Windows Server 2008 R2 オペレーティング システム  <br/> Windows Server 2012 R2 オペレーティングシステム  <br/> |はい。 Skype for Business Server 2019 server および代理トランザクション監視ノードの両方。  <br/> |
|クラスター化されたサーバー  <br/> |サポートされていません。  <br/> |
|エージェントレスの監視  <br/> |サポートされていません。  <br/> |
|仮想環境  <br/> |はい。  <br/> |
|ドメインに参加しているサーバーの役割  <br/> |すべての内部 Skype for Business Server 2019 のサーバーの役割は、ドメインに参加している必要があります。  <br/> |
|スタンドアロンサーバーの役割  <br/> |Skype for Business Server 2019 エッジサーバーはドメインに参加する必要はありません。  <br/> |
|トポロジの制限事項  <br/> |展開内のすべてのサーバーの役割は、同じ Operations Manager 管理グループから監視する必要があります。  <br/> |
|代理トランザクション監視ノード  <br/> |代理トランザクション監視ノードでの監視シナリオの可用性がサポートされています (追加の構成が必要です)。 監視ノードはドメインに参加する必要はありません。  <br/> |
   
次の表は、代理トランザクション監視ノードの容量とオペレーティングシステムの要件を示しています。
  
|**ハードウェア コンポーネント**|**最小要件**|
|:-----|:-----|
|CPU  <br/> |次のいずれかの要件:  <br/> 64ビットプロセッサ、クアッドコア、2.33 GHz またはそれ以上  <br/> 64ビット2ウェイプロセッサ、デュアルコア、2.33 GHz またはそれ以上  <br/> |
|メモリ  <br/> |8 GB  <br/> |
|オペレーティング システム  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|ネットワーク  <br/> |1 Gbps のネットワークアダプター1つ  <br/> |
   
## <a name="prerequisites"></a>前提条件

代理トランザクション監視ノードを実行するには、最初に次のものをインストールする必要があります。
  
- System Center Operations Manager エージェント 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server のコアインストールファイル (OcsCore) および統合コミュニケーションマネージ API (UCMA) (バージョンは、Skype for Business Server Watchernode.msi のバージョンと一致する必要があります)
    
## <a name="files-in-this-monitoring-pack"></a>この監視パックのファイル

Skype for Business Server 2019 の監視パックには、次のファイルが含まれています。
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- Watchernode.msi
    
## <a name="whats-new"></a>新機能

次の機能は、Skype for Business Server 2019 管理パックの新機能です。

- **2019 年[9 月の更新プログラム](https://www.microsoft.com/download/details.aspx?id=57511)の変更点**特殊文字が削除された通知があります。 場合によっては、特殊文字が SCOM コマンドチャネル通知機能に干渉することがあります。

- **クライアントサインインの自動検出**多くの場合、Skype for Business Server 2019 にサインインするクライアントアプリケーションは、にサインインするサーバーを自動的に検出します。 代理トランザクションは、自動検出が正しく構成されているかどうかの検証をサポートするようになりました。
    
- **代理トランザクションの実行間隔のカスタマイズ**監視ノードのセットアッププロセスを簡単にするために、代理トランザクションはユーザーアカウントを共有できます。 テストがシリアル化されて競合が発生しないように、テストが実行される頻度が遅くなります。 既定では、代理トランザクションは15分ごとに実行され、すべてのテストの実行時間があることを確認します。 ユーザーごとにより多くのユーザーまたはより少ないテストを使用することを選択した管理者は、実行の間隔も短縮できるようになります。
    
- **ビデオ相互運用サービス代理トランザクション**他のベンダーからの Skype for Business Server 2019 に移行しているお客様は、多くの場合、これらの他のベンダーからのビデオ会議デバイス (VTCs) を引き続き使用することを望んでいます。 ビデオ相互運用サーバーは新しい Skype for Business Server 2019 のサーバーの役割で、ユーザーは、ビデオ SIP トランク経由で Cisco CUCM に接続することにより、自分の会議室で Cisco VTCs を引き続き使用できます。 また、この機能は、ビデオ相互運用サーバーが稼働しており、ビデオ SIP トランク経由の受信接続を処理できることを確認するための代理トランザクションを追加します。
    
- **アプリケーション共有会議代理トランザクション**アプリケーション共有会議のエンドツーエンドのシナリオの検証がサポートされるようになりました。
    
## <a name="monitoring-scenarios"></a>監視シナリオ

Skype for Business Server 2019 管理パックは、問題の検出と診断に役立つさまざまな機能を活用しています。 これらの機能は、Skype for Business Server 2019 環境の正常性をリアルタイムで確認できるようにします。
  
|**監視シナリオ**|**説明**|
|:-----|:-----|
|代理トランザクション  <br/> | Windows PowerShell コマンドレットをテストして、ユーザー用のサインイン、プレゼンス、IM、会議などのシナリオの高可用性を実現します。 <br/> 代理トランザクションは、企業内のすべての地理的な場所 (企業内やブランチオフィスの外部) から実行できます。  <br/> 代理トランザクションが失敗した場合は、エラーの正確な性質を判断するために HTML ログが作成されます。 これには、失敗したアクション、各アクションの待機時間、テストの実行に使用されたコマンドライン、発生した特定のエラーについての説明が含まれます。  <br/> |
|通話の信頼性のアラート  <br/> |Skype for Business Server 2019 サーバーによって書き込まれた通話詳細記録 (Cdr) ユーザーが通話に接続できるかどうか、または通話が終了した理由を示します。 呼び出しの信頼性のアラートは、CDR データベースを照会して、多数のユーザーがピアツーピア通話または基本的な会議機能の接続に関する問題を発生したことを示す警告を生成します。  <br/> シナリオカバレッジには、音声通話、ピアツーピアインスタントメッセージング (IM)、その他の会議機能が含まれます。  <br/> |
|メディア品質のアラート  <br/> |各呼び出しの終了時に Skype for Business Server 2019 クライアントによって発行された QoE (Quality of Experience) レポートを参照するデータベースクエリ。 これらのクエリは、通話と電話会議中にユーザーが侵害されたメディア品質を発生させる可能性のあるシナリオを特定するアラートを生成します。 データは、パケットの遅延や損失などの重要な指標に基づいて構築されており、ユーザーにとっての品質に直接影響します。  <br/> |
|コンポーネントの正常性アラート  <br/> |個々のサーバーコンポーネントは、イベントログとパフォーマンスカウンターを使用して警告を発生させ、ユーザーのシナリオに大きな影響を与える可能性があるエラー状態を示します。 これらのアラートは、サービスが実行されていない、高エラー率、高メッセージ遅延、または接続の問題など、さまざまな条件を示しています。  <br/> |
|依存関係の正常性の監視  <br/> |Skype for Business Server は、外部のさまざまな理由で失敗する可能性があります。 管理パックは、重大な問題を示している可能性のある重大な外部依存関係のデータを監視し、収集します。 これらの依存関係には、インターネットインフォメーションサービス (IIS) の可用性、および Skype for Business Server で使用されるサーバーの CPU が含まれます。  <br/> |
   
### <a name="alert-prioritization"></a>アラートの優先度設定

通知は、次のカテゴリに分類されます。 
  
 **高優先度のアラート:** これらのアラートは、大規模なユーザーグループのサービスが停止し、直ちにアクションを必要とする条件を示します。 代理トランザクションとオフラインサービス (Skype for Business Server の音声ビデオ会議など) によって検出された停止は、優先度の高いアラートとして評価されます。 一方、コンポーネントが1台のコンピューターで失敗した場合は、優先度の高いアラートにはなりません。 Skype for Business Server 2019 には、これらの状況で高可用性機能が組み込まれています。たとえば、ロードバランサーの背後に複数のフロントエンドサーバーがあります。
  
 **中優先度の警告:** これらのアラートは、ユーザーのサブセットに影響を与えたり、通話品質の問題 (コンポーネント障害、通話確立の待機時間、通話の音声品質低下など) を示したりする条件を示します。 このカテゴリの通知はステートフルです (つまり、ネットワーク接続の状態に基づいて通知の性質が変わります)。たとえば、呼び出しの確立時間が遅延を示していて、通常のしきい値に戻ると、この中優先度警告は System Center Operations Manager では自動解決され、管理者はアクションを実行する必要はありません。 自動解決できない通知は、通常、同じ営業日の管理者によって処理されます。
  
 **その他のアラート:** これらのアラートは、特定のユーザーまたはユーザーのサブセットに影響を与える可能性のあるコンポーネントから生成されます。 たとえば、一般的な警告は、アドレス帳サービスが user: testuser@contoso.com の Active Directory® Domain Services (AD DS) エントリを解析できなかったことです。 管理者は、使用可能な時間があるときにこれらのアラートに対処できます。
  
### <a name="synthetic-transactions"></a>代理トランザクション

Skype for Business Server 2019 の管理パックを使用すると、代理トランザクションによる通知の範囲が拡大されます。 代理トランザクションは、エンドツーエンドのユーザーシナリオをテストするために Operations Manager 管理パックに統合された Windows PowerShell コマンドレットです。 代理トランザクションを実行するようにサーバーを指定すると、これらのコマンドレットは管理パックによって定期的にトリガーされます。 代理トランザクションによって発生したエラーは、ステートフルな警告を生成します。 Skype for Business Server 2019 でサポートされている代理トランザクションは次のとおりです。
  
**登録、プレゼンス、および連絡先のサポートされている代理トランザクション**

||||
|:-----|:-----|:-----|
|1-d  <br/> |登録 (ユーザーログイン)  <br/> |利用可能な Lync Server 2010 以降  <br/> |
|pbm-2  <br/> |アドレス帳サービス (ファイルのダウンロード)  <br/> |利用可能な Lync Server 2010 以降  <br/> |
|1/3  <br/> |アドレス帳 Web クエリ  <br/> |利用可能な Lync Server 2010 以降  <br/> |
|2/4  <br/> |プレゼンス  <br/> |利用可能な Lync Server 2010 以降  <br/> |
|5  <br/> |統合連絡先ストア  <br/> |利用可能な Lync Server 2013 以降  <br/> |
   
**ピアツーピアサービスに対してサポートされている代理トランザクション**

||||
|:-----|:-----|:-----|
|6   <br/> |ピアツーピアのインスタントメッセージング  <br/> |Lync Server 2010 以降で利用可能  <br/> |
|7   <br/> |ピアツーピア音声ビデオ  <br/> |Lync Server 2010 以降で利用可能  <br/> |
|8   <br/> |MCX ピアツーピアインスタントメッセージ (モバイル)  <br/> |Lync Server 2010 の2011年9月リリース以降の Skype for Business 2019 で利用可能  <br/> |
 
> [!NOTE]
> 従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。 現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。
  
**会議および常設チャットでサポートされている代理トランザクション**

||||
|:-----|:-----|:-----|
|9   <br/> |音声ビデオ会議  <br/> |Lync Server 2010 以降で利用可能  <br/> |
|10   <br/> |データ会議  <br/> |Lync Server 2013 以降で利用可能  <br/> |
|11   <br/> |インスタントメッセージ会議  <br/> |Lync Server 2010 以降で利用可能  <br/> |
|12  <br/> | 常設チャット <br/> |Lync Server 2013 以降で利用可能  <br/> |
|スリー  <br/> |参加起動ツール (スケジュールされた会議)  <br/> |Lync Server 2013 以降で利用可能  <br/> |
|14   <br/> |ダイヤルイン会議  <br/> |Skype for Business Server 2015 以降で利用可能 <br/> |
|15   <br/> |アプリケーション共有会議  <br/> |Skype for Business Server 2015 以降で利用可能 <br/> |
|16   <br/> |UCWA 会議 (web 会議参加)  <br/> |Skype for Business Server 2015 以降で利用可能 <br/> |
   
**ネットワークとパートナーの依存関係に対してサポートされている代理トランザクション**

||||
|:-----|:-----|:-----|
|17   <br/> |AV エッジ接続  <br/> |Lync Server 2013 以降で利用可能  <br/> |
|18   <br/> |AV エッジ接続 Exchange ユニファイドメッセージ接続 (ボイスメール)  <br/> |Lync Server 2013 以降で利用可能  <br/> |
|年  <br/> |PSTN ピアツーピア通話  <br/> |Lync Server 2010 以降で利用可能  <br/> |
|1280  <br/> |XMPP インスタントメッセージング (フェデレーション)  <br/> |Lync Server 2013 以降で利用可能  <br/> |
|21  <br/> |ビデオ相互運用サーバー  <br/> |Skype for Business Server 2015 以降で利用可能  <br/> |
   
## <a name="how-health-rolls-up"></a>正常性ロールアップのしくみ

次の表に、Skype for Business Server の監視パックのオブジェクトの正常性状態を示します。
  
|**管理パックオブジェクト**|**説明**|
|:-----|:-----|
|Skype for Business Server の展開  <br/> |組織内の Skype for Business Server 2019 の展開を表します。  <br/> |
|Skype for Business Server サイト  <br/> |サービスが展開されている地理的な場所を表します。  <br/> |
|Skype for Business Server プール  <br/> |インスタントメッセージングや会議などの通信サービスをユーザーに提供する (サイト内の) プール。 特定のプールに1台のコンピューターしかない場合でも、フロントエンドプール、エッジプール、およびディレクタープールに適用されます。  <br/> |
|Skype for Business Server の役割  <br/> |Skype for Business Server サービスをホストするサーバーの役割。  <br/> |
|Skype for Business Server サービス  <br/> |特定のコンピューター (たとえば、fp01.contoso.com 上の user service) に展開されている機能を表します。  <br/> |
|Skype for Business Server コンポーネント  <br/> |サービスのコンポーネント (たとえば、アドレス帳のダウンロードコンポーネントは Web サービスの一部です)。  <br/> |
|Skype for Business Server プール監視  <br/> |1つのプールに対して実行されている代理トランザクションのインスタンスです。  <br/> |
|Skype for Business Server レジストラーウォッチャー  <br/> |1つのレジストラープールに対して実行される代理トランザクションのインスタンスです。  <br/> |
|Skype for Business Server ユーザーサービスプール監視  <br/> |1つのユーザーサービスプールに対して実行される代理トランザクションのインスタンスです。  <br/> |
|Skype for Business Server 音声プール監視  <br/> |1つの音声プールに対して実行される代理トランザクションのインスタンスです。  <br/> |
|Skype for Business Server のポート監視  <br/> |1つのプールに対して実行されているポートチェックのインスタンス。  <br/> |
|簡易 URL ウォッチャー  <br/> |展開で構成された簡易 Url の HTTPS プローブを実行します。  <br/> |
   
![SCOM Rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype for Business Server プールには、複数の個別の Skype for business Server システムを含めることができます (複数の Skype for Business server の役割、Skype for business Server service、および Skype for Business Server コンポーネントを含む)。 そのため、同じプール内の他のサーバーがアプリケーションサービスをクライアントに提供できるため、個々のサーバーまたはコンポーネントの障害は、Skype for Business Server プールの全体的な正常性にとって重要ではありません。 稼働状態は、比率レベルで Skype for Business Server プールにロールアップされます。 
  
Skype for Business Server プール監視は、Skype for Business Server プールに対して代理トランザクションを実行します。 次の図に示すように、1つまたは複数の代理トランザクション (連続したポーリング間隔と呼ばれるプロセス) が連続して失敗すると、次の図に示すように、重大な状態がプールレベル (すべての代理トランザクションの最低) にロールアップされます。 
  
![SCOM ロールアウト連続ポーリング](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>ベストプラクティス: カスタマイズ用の管理パックを作成する

既定では、Operations Manager は、既定の管理パックへの上書きなど、すべてのカスタマイズを保存します。 ベストプラクティスとして、カスタマイズする封印された管理パックごとに個別の管理パックを作成する必要があります。 
  
封印された管理パックのカスタマイズされた設定を格納する管理パックを作成する場合、「Skype for Business Server 2019 のカスタマイズ」などの新しい管理パックに適切な名前を付けることをお勧めします。
  
各封印された管理パックのカスタマイズを保存するための新しい管理パックを作成することにより、カスタマイズをテスト環境から運用環境に簡単にエクスポートすることができます。 これにより、管理パックを削除する前に依存関係を削除する必要があるので、管理パックの削除も容易になります。 すべての管理パックのカスタマイズが既定の管理パックに保存されていて、1つの管理パックを削除する必要がある場合は、最初に既定の管理パックを削除する必要があります。これにより、他の管理パックへのカスタマイズも削除されます。 
  
## <a name="links"></a>リンク

次のリンクを使用すると、System Center 2012 の監視パックに関連付けられている一般的なタスクに関する情報にアクセスできます。
  
- [管理パックのライフサイクル](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Operations Manager 2012 で管理パックをインポートする方法](https://technet.microsoft.com/library/hh212691.aspx)
    
- [ルールまたはモニターを上書きする方法](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Operations Manager 2012 で実行アカウントを作成する方法](https://technet.microsoft.com/library/hh321655.aspx)
    
- [実行アカウントと実行プロファイルの管理](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Operations Manager 管理パックをエクスポートする方法](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Operations Manager 管理パックを削除する方法](https://technet.microsoft.com/library/hh230746.aspx)
    
次のリンクを使用すると、System Center 2007 の監視パックに関連付けられている一般的なタスクに関する情報にアクセスできます。
  
- [管理パックのライフサイクルを管理する](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Operations Manager 2007 で管理パックをインポートする方法](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [オーバーライドを使用して監視する方法](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Operations Manager 2007 で実行アカウントを作成する方法](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [既存の実行プロファイルを変更する方法](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [管理パックのカスタマイズをエクスポートする方法](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [管理パックを削除する方法](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Operations Manager と監視パックに関する質問については、 [System Center Operations manager コミュニティフォーラム](https://go.microsoft.com/fwlink/p/?LinkID=179635)を参照してください。
  
有用なリソースとしては、 [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/)ブログがあります。これには、特定の監視パックの「例」の投稿が含まれています。
  
Operations Manager の詳細については、次のブログを参照してください。 
  
- [Operations Manager チームブログ](https://blogs.technet.com/momteam/default.aspx)
    
- [加山 Holman の OpsMgr ブログ](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr での考え](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael の気流のブログ](https://rburri.wordpress.com/)
    
- [BWren の管理スペース](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Microsoft 以外のサイトのすべての情報とコンテンツは、その Web サイトの所有者またはユーザーが提供しています。 Microsoft は、この web サイトの情報に関して、明示的、黙示的、または法律上の保証を行いません。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2019 管理ツール](../management-tools-2019.md)
