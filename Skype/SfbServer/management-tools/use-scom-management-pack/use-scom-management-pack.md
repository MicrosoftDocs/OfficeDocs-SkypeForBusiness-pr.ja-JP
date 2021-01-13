---
title: SCOM 管理パックを使用して Skype for Business Server 2015 を管理する
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
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: '概要: System Center Operations Manager と一緒に動作する Skype for Business Server 2015 インフラストラクチャを構成する方法について学習します。'
ms.openlocfilehash: cfb48338d4022c1de7c5944f66d72e58dd8b403d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814847"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>SCOM 管理パックを使用して Skype for Business Server 2015 を管理する
 
**概要:** System Center Operations Manager と一緒に動作する Skype for Business Server 2015 インフラストラクチャを構成する方法について学習します。
  
理想的な世界では、Skype for Business Server 2015 に関する問題は発生しません。 ただし、Skype for Business Server は、ネットワーク クラッシュやハードウェア障害など、外部要因の影響を受ける可能性があります。 Skype for Business Server 2015 管理パックを使用すると、潜在的な問題を事前に特定して対処できます。 この方法で、Skype for Business Server 2015 管理パックは System Center Operations Manager の機能を拡張します。
  
この情報は、Skype for Business Server 2015 通信ソフトウェアの監視パックのバージョン 9319.0 に基づいて作成されました。
  
## <a name="configuration-overview"></a>構成の概要

 System Center Operations Manager と一緒に動作する Skype for Business Server 2015 インフラストラクチャを構成するには、次の 3 つの操作を行う必要があります。
  
プライマリ管理  [サーバーを識別して構成します](configure-the-primary.md)。 これを行うには、System Center Operations Manager 2012 SP1 または R2 をインストールする必要があります。 
  
 監視対象 [の Skype for Business Server コンピューターを識別して構成します](configure-computers-to-monitor.md)。 System Center Operations Manager を使用して Skype for Business Server コンピューターを監視するには、System Center Operations Manager エージェント ファイルをインストールし、各サーバーがプロキシとして機能する構成を行う必要があります。 
  
 監視ノード [を識別してインストールし、構成します](watcher-nodes.md)。 監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。システムにログオンする機能やインスタント メッセージを交換する機能など、主要な Skype for Business Server コンポーネントが期待通り動作しているのを確認する Windows PowerShell コマンドレットです。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager ルート管理サーバーとエージェントのサポート

管理パックは、System Center Operations Manager 2007 R2 (64 ビット) (移行専用) または System Center Operations Manager 2012 SP1 &amp; R2 (64 ビット) または System Center Operations Manager 2016 (64 ビット) で使用できます。 次の表に、Skype for Business Server 2015 の管理パックでサポートされている構成を示します。 
  
|構成|サポートの有無|
|:-----|:-----|
|Windows Server 2008 R2 オペレーティング システム  <br/> Windows Server 2012 R2 オペレーティング システム  <br/> |はい。 Skype for Business Server 2015 サーバーと代理トランザクション 監視ノードの両方。  <br/> |
|クラスター化されたサーバー  <br/> |サポートされていません。  <br/> |
|エージェントレス監視  <br/> |サポートされていません。  <br/> |
|仮想環境  <br/> |はい。  <br/> |
|ドメインに参加しているサーバーの役割  <br/> |すべての内部 Skype for Business Server 2015 サーバーの役割は、ドメインに参加している必要があります。  <br/> |
|スタンドアロン サーバーの役割  <br/> |Skype for Business Server 2015 エッジ サーバーは、ドメインに参加している必要はありません。  <br/> |
|トポロジの制限  <br/> |展開内のすべてのサーバーの役割は、同じ Operations Manager 管理グループから監視する必要があります。  <br/> |
|代理トランザクション監視ノード  <br/> |代理トランザクション監視ノードを使用した監視シナリオの可用性がサポートされています (追加の構成が必要)。 監視ノードは、ドメインに参加している必要はありません。  <br/> |
   
次の表に、代理トランザクション 監視ノードの容量とオペレーティング システムの要件を示します。
  
|ハードウェア コンポーネント|最小要件|
|:-----|:-----|
|CPU  <br/> |次のいずれかの要件:  <br/> 64 ビット プロセッサ、クアッド コア、2.33 GHz 以上  <br/> 64 ビット 2 way プロセッサ、デュアルコア、2.33 GHz 以上  <br/> |
|メモリ  <br/> |8 GB  <br/> |
|オペレーティング システム  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|ネットワーク  <br/> |1 Gbps で 1 つのネットワーク アダプター  <br/> |
   
## <a name="prerequisites"></a>前提条件

代理トランザクション 監視ノードを実行するには、まず次をインストールする必要があります。
  
- System Center Operations Manager エージェント 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server コア インストール ファイル (OcsCore.msi) および Unified Communications Managed API (UCMA) (バージョンは Skype for Business Server WatcherNode.msi バージョンと一致する必要があります)
    
## <a name="files-in-this-monitoring-pack"></a>この監視パック内のファイル

Skype for Business Server 2015 の監視パックには、次のファイルが含まれています。
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新機能

次の機能は、Skype for Business Server 2015 管理パックの新機能です。

- **[2019 年 9 月の更新プログラムの変更点](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** 一部のアラートでは特殊文字が削除されています。 特殊文字が SCOM コマンド チャネル通知機能に干渉する場合があります。

- **クライアント サインインの自動検出** 多くの場合、Skype for Business Server 2015 にサインインするクライアント アプリケーションは、サインインするサーバーを自動的に検出します。 代理トランザクションは、自動検出が正しく構成されていることを確認する機能をサポートするようになりました。
    
- **カスタマイズされた代理トランザクションの実行間隔** 監視ノードのセットアップ プロセスを簡略化するために、代理トランザクションはユーザー アカウントを共有できます。 これにより、テストをシリアル化して競合を回避するために、テストを実行する頻度が遅くなります。 既定では、代理トランザクションは 15 分ごとに実行されます。これにより、すべてのテストを実行する時間が確保されます。 1 ユーザーあたりのユーザー数またはテスト数を減らすことを選択した管理者も、実行間隔を短縮できる可能性があります。
    
- **ビデオ相互運用サービス代理トランザクション** 他のベンダー ソリューションから Skype for Business Server 2015 に移行しているお客様は、多くの場合、これらの他のベンダーからビデオ会議デバイス (VTC) を引き続き使用する必要があります。 ビデオ相互運用サーバーは、新しい Skype for Business Server 2015 サーバーの役割で、お客様はビデオ SIP トランクを介して Cisco CUCM に接続することで、会議室で Cisco VTC を引き続き使用できます。 この機能では、代理トランザクションも追加され、ビデオ相互運用サーバーが開始され、ビデオ SIP トランクを使用した着信接続を処理できます。
    
- **アプリケーション共有会議代理トランザクション** アプリケーション共有会議のエンドツーエンド シナリオ検証がサポートされました。
    
## <a name="monitoring-scenarios"></a>監視シナリオ

Skype for Business Server 2015 管理パックは、問題の検出と診断に役立つさまざまな機能を活用します。 これらの機能を使用すると、Skype for Business Server 2015 環境の正常性をリアルタイムで確認できます。
  
|監視シナリオ|説明|
|:-----|:-----|
|代理トランザクション  <br/> | Windows PowerShellをテストし、ユーザーのサインイン、プレゼンス、IM、会議などのシナリオの高可用性をテストし、確認します。 <br/> 代理トランザクションは、企業内、社外、ブランチ オフィスなど、地理的に任意の場所から実行できます。  <br/> 代理トランザクションが失敗すると、エラーの正確な性質を判断するために HTML ログが作成されます。 これには、失敗したアクション、各アクションの待機時間、テストの実行に使用されたコマンド ライン、発生した特定のエラーが含まれます。  <br/> |
|通話の信頼性の警告  <br/> |Skype for Business Server 2015 サーバーによって書き込まれた通話詳細記録 (CDRs) には、ユーザーが通話に接続できるかどうか、または通話が終了する理由が反映されます。 通話信頼性アラートは CDR データベースにクエリを実行して、多数のユーザーがピアツーピア通話または基本的な会議機能の接続の問題が発生した場合を示すアラートを生成します。  <br/> シナリオ範囲には、音声通話、ピアツーピア インスタント メッセージング (IM)、その他の会議機能が含まれます。  <br/> |
|メディア品質のアラート  <br/> |各通話の最後に Skype for Business Server 2015 クライアントによって公開された QoE (Quality of Experience) レポートを確認するデータベース クエリ。 これらのクエリは、ユーザーが通話や会議中にメディア品質の低下を経験する可能性が最も高いシナリオを特定するアラートを生成します。 データは、パケットの待機時間や損失などの主要な指標に基いて構築され、ユーザー エクスペリエンスの品質に直接影響します。  <br/> |
|コンポーネント正常性アラート  <br/> |個々のサーバー コンポーネントは、イベント ログとパフォーマンス カウンターを介してアラートを発生し、ユーザー シナリオに大きな影響を与える可能性があるエラー状態を示します。 これらのアラートは、サービスが実行されていない、エラー率が高い、メッセージの待機時間が長い、接続の問題など、さまざまな条件を示します。  <br/> |
|依存関係の正常性の監視  <br/> |Skype for Business Server は、さまざまな外部の理由で失敗することがあります。 管理パックは、重大な問題を示す可能性がある重要な外部依存関係のデータを監視および収集します。 これらの依存関係には、インターネット インフォメーション サービス (IIS) の可用性と、Skype for Business Server に使用されるサーバーの CPU が含まれます。  <br/> |
|||
   
### <a name="alert-prioritization"></a>アラートの事前設定

アラートは、次のカテゴリに分類されます。 
  
 **優先度の高いアラート:** これらのアラートは、大規模なユーザー グループのサービス停止を引き起こす状態を示し、直ちに対応する必要があります。 代理トランザクションおよびオフライン サービス (Skype for Business Server の音声ビデオ会議など) によって検出された停止は、優先度の高いアラートとして機能します。 一方、1 台のコンピューターでのコンポーネントのエラーは、優先度の高いアラートではありません。 Skype for Business Server 2015 には、ロード バランサーの背後に複数のフロント エンド サーバーなど、このような状況に対応する組み込みの高可用性機能があります。
  
 **中程度の優先度のアラート:** これらのアラートは、ユーザーのサブセットに影響する条件を示したり、通話品質の問題 (コンポーネントの障害、通話確立の待機時間、通話の音質の低下など) を示します。 このカテゴリのアラートはステートフルです (つまり、ネットワーク接続の状態に基づいてアラートの性質が変化します)。たとえば、通話の確立時間が待機時間を示し、通常のしきい値に戻った場合、この中程度の優先度の警告は System Center Operations Manager で自動解決され、管理者はアクションを実行する必要はありません。 自動解決できないアラートは、通常、管理者が同じ営業日に対処します。
  
 **その他のアラート:** これらのアラートは、特定のユーザーまたはユーザーのサブセットに影響を与える可能性があるコンポーネントから生成されます。 たとえば、通常、アドレス帳サービスがユーザーの Active Directory® ドメイン サービス (AD DS) エントリを解析できないという警告が表示testuser@contoso.com。 管理者は、利用可能な時間があるときにいつでもこれらのアラートに対処できます。
  
### <a name="synthetic-transactions"></a>代理トランザクション

Skype for Business Server 2015 管理パックは、代理トランザクションを通じてアラートの対象範囲を拡大します。 代理トランザクションは、Windows PowerShellエンド ユーザー シナリオをテストするために Operations Manager 管理パックに統合されたコマンドレットです。 代理トランザクションを実行するサーバーを指定すると、これらのコマンドレットは管理パックによって定期的にトリガーされます。 代理トランザクションによって発生したエラーは、ステートフルアラートを生成します。 Skype for Business Server 2015 でサポートされている代理トランザクションを次に示します。
  


|登録、プレゼンス、および連絡先でサポートされる代理トランザクション|||
|:-----|:-----|:-----|
|1   <br/> |登録 (ユーザー ログイン)  <br/> |使用可能な Lync Server 2010 以降  <br/> |
|2   <br/> |アドレス帳サービス (ファイルのダウンロード)  <br/> |使用可能な Lync Server 2010 以降  <br/> |
|3   <br/> |アドレス帳 Web クエリ  <br/> |使用可能な Lync Server 2010 以降  <br/> |
|4   <br/> |プレゼンス  <br/> |使用可能な Lync Server 2010 以降  <br/> |
|5   <br/> |統合連絡先ストア  <br/> |使用可能な Lync Server 2013 以降  <br/> |
||||   

|ピアツーピア サービスでサポートされる代理トランザクション|||
|:-----|:-----|:-----|
|6   <br/> |ピアツーピア インスタント メッセージング  <br/> |Lync Server 2010 以降で使用可能  <br/> |
|7   <br/> |ピアツーピア オーディオ ビデオ  <br/> |Lync Server 2010 以降で使用可能  <br/> |
|8   <br/> |MCX ピアツーピア インスタント メッセージ (モバイル)  <br/> |Lync Server 2010 から Skype for Business 2015 の 2011 年 9 月リリースで利用可能  <br/> |
 
> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。


|電話会議および常設チャットでサポートされる代理トランザクション|||
|:-----|:-----|:-----|
|9   <br/> |音声ビデオ会議  <br/> |Lync Server 2010 以降で使用可能  <br/> |
|10   <br/> |データ会議  <br/> |Lync Server 2013 以降で使用可能  <br/> |
|11   <br/> |インスタント メッセージ会議  <br/> |Lync Server 2010 以降で使用可能  <br/> |
|12   <br/> | 常設チャット <br/> |Lync Server 2013 以降で使用可能  <br/> |
|13   <br/> |会議に起動ツールする (スケジュールされた会議)  <br/> |Lync Server 2013 以降で使用可能  <br/> |
|14   <br/> |ダイヤルイン会議  <br/> |Skype for Business Server 2015 の新機能  <br/> |
|15   <br/> |アプリケーション共有会議  <br/> |Skype for Business Server 2015 の新機能  <br/> |
|16   <br/> |UCWA 会議 (Web 会議参加)  <br/> |Skype for Business Server 2015 の新機能  <br/> |
||||

|ネットワークとパートナーの依存関係でサポートされる代理トランザクション|||
|:-----|:-----|:-----|
|17   <br/> |AV エッジ接続  <br/> |Lync Server 2013 以降で使用可能  <br/> |
|18   <br/> |AV エッジ接続 Exchange 統合メッセージ接続 (ボイスメール)  <br/> |Lync Server 2013 以降で使用可能  <br/> |
|19  <br/> |PSTN ピアツーピア通話  <br/> |Lync Server 2010 以降で使用可能  <br/> |
|20  <br/> |XMPP インスタント メッセージング (フェデレーション)  <br/> |Lync Server 2013 および Skype for Business 2015 で使用可能  <br/> |
| 21  <br/> |ビデオ相互運用サーバー  <br/> |Skype for Business Server 2015 の新機能  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>正常性のロール アップ方法

次の表に、Skype for Business Server 監視パックのオブジェクトの正常性状態を示します。
  
|Management Pack オブジェクト|説明|
|:-----|:-----|
|Skype for Business Server の展開  <br/> |組織での Skype for Business Server 2015 の展開を表します。  <br/> |
|Skype for Business Server サイト  <br/> |サービスが展開される地理的に異なる場所を表します。  <br/> |
|Skype for Business Server プール  <br/> |インスタント メッセージングや会議などの通信サービスをユーザーに提供するプール (サイト内)。 特定のプールにコンピューターが 1 台しかなくても、フロント エンド プール、エッジ プール、およびディレクター プールに適用できます。  <br/> |
|Skype for Business Server の役割  <br/> |Skype for Business Server サービスをホストするサーバーの役割。  <br/> |
|Skype for Business Server サービス  <br/> |特定のコンピューターに展開された機能を表します (たとえば、特定のコンピューター上のユーザー サービスfp01.contoso.com。  <br/> |
|Skype for Business Server コンポーネント  <br/> |サービスのコンポーネント (たとえば、アドレス帳のダウンロード コンポーネントは Web サービスの一部です)。  <br/> |
|Skype for Business Server プール ウォッチャー  <br/> |1 つのプールに対して実行されている代理トランザクションのインスタンス。  <br/> |
|Skype for Business Server レジストラー ウォッチャー  <br/> |1 つのレジストラー プールに対して実行される代理トランザクションのインスタンス。  <br/> |
|Skype for Business Server User Services プール ウォッチャー  <br/> |1 つの User Services プールに対して実行される代理トランザクションのインスタンス。  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |1 つの音声プールに対して実行される代理トランザクションのインスタンス。  <br/> |
|Skype for Business Server ポート ウォッチャー  <br/> |1 つのプールに対して実行されているポート チェックのインスタンス。  <br/> |
|簡易 URL ウォッチャー  <br/> |展開で構成済みの簡易 URL の HTTPS の処理を実行します。  <br/> |
   
![SCOM ロールアップ](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Skype for Business Server プールには、複数の個別の Skype for Business Server システム (複数の Skype for Business Server の役割、Skype for Business Server サービス、および Skype for Business Server コンポーネント) を含めできます。 したがって、個々のサーバーまたはコンポーネントの障害は、同じプール内の他のサーバーがクライアントにアプリケーション サービスを提供する可能性があるため、Skype for Business Server プールの全体的な正常性にとってそれほど重要ではありません。 正常性は、割合レベルで Skype for Business Server プールにロールアップされます。 
  
Skype for Business Server プール ウォッチャーは、Skype for Business Server プールに対して代理トランザクションを実行します。 次の図に示すように、1 つ以上の代理トランザクション (連続ポーリング間隔と呼ばれるプロセス) が連続して失敗すると、重大な正常性状態がプール レベル (代理トランザクションの最悪の状態) にロールアップされます。 
  
![SCOM ロールアップの連続ポーリング](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>ベスト プラクティス: カスタマイズ用の管理パックを作成する

既定では、Operations Manager は、既定の管理パックへの上書きなど、すべてのカスタマイズを保存します。 ベスト プラクティスとして、カスタマイズするシール管理パックごとに個別の管理パックを作成する必要があります。 
  
シールされた管理パックのカスタマイズされた設定を格納するための管理パックを作成する場合は、新しい管理パックに適切な名前を付ける (「Skype for Business Server 2015 Customizations」など) することをお勧めします。 
  
シールされた各管理パックのカスタマイズを保存するための新しい管理パックを作成すると、カスタマイズをテスト環境から実稼働環境に簡単にエクスポートできます。 これにより、管理パックを削除する前に依存関係を削除する必要が生じ、管理パックを簡単に削除できます。 すべての管理パックのカスタマイズが既定の管理パックに保存され、1 つの管理パックを削除する必要がある場合は、最初に既定の管理パックを削除する必要があります。この場合、他の管理パックへのカスタマイズも削除されます。 
  
## <a name="links"></a>リンク

次のリンクをクリックすると、System Center 2012 監視パックに関連付けられている一般的なタスクに関する情報にアクセスできます。
  
- [管理パックのライフ サイクル](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Operations Manager 2012 で管理パックをインポートする方法](https://technet.microsoft.com/library/hh212691.aspx)
    
- [ルールまたはモニターを上書きする方法](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Operations Manager 2012 で実行アカウントを作成する方法](https://technet.microsoft.com/library/hh321655.aspx)
    
- [実行アカウントとプロファイルの管理](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Operations Manager 管理パックをエクスポートする方法](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Operations Manager 管理パックを削除する方法](https://technet.microsoft.com/library/hh230746.aspx)
    
次のリンクを使用すると、System Center 2007 監視パックに関連付けられている一般的なタスクに関する情報にアクセスできます。
  
- [管理パックのライフ サイクルの管理](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Operations Manager 2007 で管理パックをインポートする方法](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [上書きを使用して監視する方法](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Operations Manager 2007 で実行アカウントを作成する方法](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [既存の実行プロファイルを変更する方法](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [管理パックのカスタマイズをエクスポートする方法](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [管理パックを削除する方法](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Operations Manager と監視パックに関する質問については、System Center Operations Manager コミュニティ フォーラム [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
役に立つリソースは [、System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) ブログです。このブログには、特定の監視パックに関する「例」の投稿が含まれています。
  
Operations Manager の詳細については、次のブログを参照してください。 
  
- [Operations Manager チームブログ](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman の OpsMgr ブログ](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr に関する考え](https://thoughtsonopsmgr.blogspot.com/)
    
- [Rahael Burri のブログ](https://rburri.wordpress.com/)
    
- [BWren の管理スペース](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Microsoft 以外のサイトのすべての情報とコンテンツは、その Web サイトの所有者またはユーザーが提供しています。 Microsoft は、この Web サイトの情報に関して、明示、黙示、法的な保証を一切行いません。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 管理ツール](../../management-tools/management-tools.md)
