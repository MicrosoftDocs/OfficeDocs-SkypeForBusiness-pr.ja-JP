---
title: SCOM Skype for Business Serverパックを使用して 2019 年を管理する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 年 2019 年のインフラストラクチャを構成して、System Centerします。'
ms.openlocfilehash: e0e5f7c090c51fbe3b7b022f890fd3fc8f254aa3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844890"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>SCOM Skype for Business Serverパックを使用して 2019 年を管理する
 
**概要:** 2019 年 2019 年のインフラストラクチャを、Skype for Business Server Operations Manager で動作System Centerします。
  
理想的な世界では、2019 年に問題が発生Skype for Business Serverです。 ただし、Skype for Business Server、ネットワーククラッシュやハードウェア障害など、外部要因の影響を受ける可能性があります。 2019 Skype for Business Serverパックを使用すると、潜在的な問題を事前に特定して対処できます。 この方法で、2019 Skype for Business Server 2019 管理パックは、Operations Manager のSystem Center拡張します。
  
この情報は、2019 年の通信ソフトウェアの監視パックのバージョン 9319.0 に基Skype for Business Server書き込まれます。
  
## <a name="configuration-overview"></a>構成の概要

 2019 年 2019 Skype for Business Serverを Operations Manager で動作System Centerするには、次の 3 つの操作を実行する必要があります。
  
プライマリ管理 [サーバーを識別して構成します](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md)。 これを行うには、Operations Manager 2012 SP1 または R2 System Centerインストールする必要があります。 
  
 監視する[コンピューター Skype for Business Serverを識別して構成します](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md)。 System Center Operations Manager を使用して Skype for Business Server コンピューターを監視するには、System Center Operations Manager エージェント ファイルをインストールし、プロキシとして動作する各サーバーを構成する必要があります。 
  
 監視ノードを [識別してインストールし、構成します](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md)。 監視ノードは、Skype for Business Server 代理トランザクションを定期的に実行するコンピューターです。Windows PowerShell コマンドレットは、システムにログオンする機能やインスタント メッセージを交換する機能など、主要な Skype for Business Server コンポーネントが期待通り動作しているのを確認します。 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System CenterOperations Manager ルート管理サーバーとエージェントのサポート

管理パックは、System Center Operations Manager 2007 R2 (64 ビット) (移行目的でのみサポート) または System Center Operations Manager 2012 SP1 &amp; R2 (64 ビット) で使用できます。 次の表に、2019 年の管理パックでサポートされている構成Skype for Business Server示します。 
  
|構成|サポートの有無|
|:-----|:-----|
|Windows Server 2008 R2 オペレーティング システム  <br/> Windows Server 2012R2 オペレーティング システム   |はい。 2019 Skype for Business Server代理トランザクション 監視ノードの両方。   |
|クラスター化されたサーバー   |サポートされていません。   |
|エージェントレス監視   |サポートされていません。   |
|仮想環境   |はい。   |
|ドメインに参加しているサーバーの役割   |すべての内部Skype for Business Server 2019 サーバーの役割は、ドメインに参加している必要があります。   |
|スタンドアロン サーバーの役割   |Skype for Business Server 2019 エッジ サーバーは、ドメインに参加する必要はありません。   |
|トポロジの制限   |展開内のすべてのサーバーの役割は、同じ Operations Manager 管理グループから監視する必要があります。   |
|代理トランザクション監視ノード   |代理トランザクション監視ノードによるシナリオの可用性の監視がサポートされています (追加の構成が必要)。 監視ノードは、ドメインに参加する必要はありません。   |
   
次の表に、代理トランザクション 監視ノードの容量とオペレーティング システムの要件を示します。
  
|ハードウェア コンポーネント|最小要件|
|:-----|:-----|
|CPU   |次のいずれかの要件:  <br/> 64 ビット プロセッサ、クアッド コア、2.33 GHz 以上  <br/> 64 ビット 2 ウェイ プロセッサ、デュアル コア、2.33 GHz 以上   |
|メモリ   |8 GB   |
|オペレーティング システム   |WindowsServer 2008 R2 Windows Server 2012 R2   |
|ネットワーク   |1 Gbps の 1 つのネットワーク アダプター   |
   
## <a name="prerequisites"></a>前提条件

代理トランザクション 監視ノードを実行するには、最初に以下をインストールする必要があります。
  
- System CenterOperations Manager エージェント 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server インストール ファイル (OcsCore.msi) およびユニファイド コミュニケーションマネージ API (UCMA) (バージョンは、Skype for Business Server WatcherNode.msi バージョンと一致する必要があります)
    
## <a name="files-in-this-monitoring-pack"></a>この監視パック内のファイル

2019 年 2019 Skype for Business Server監視パックには、次のファイルが含まれています。
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>新機能

次の機能は、2019 管理パックSkype for Business Server新機能です。

- **[2019 年 9 月の更新プログラムの変更点](https://www.microsoft.com/download/details.aspx?id=57511)** 一部のアラートでは、特殊文字が削除されています。 特殊文字が SCOM コマンド チャネル通知機能に干渉する場合があります。

- **クライアント サインインの自動検出** 2019 年 2019 年にサインインするクライアント アプリケーションSkype for Business Server、サインインするサーバーが自動的に検出されます。 代理トランザクションでは、自動検出が正しく構成されているという検証がサポートされるようになりました。
    
- **カスタマイズされた代理トランザクションの実行間隔** 監視ノードのセットアップ プロセスを簡略化するために、代理トランザクションはユーザー アカウントを共有できます。 これにより、テストのシリアル化時にテストを実行する頻度が低下し、競合を回避できます。 既定では、代理トランザクションは 15 分ごとに実行し、すべてのテストの実行時間が確保されます。 ユーザー数を多くするか、ユーザーごとのテスト数を減らすことを選択した管理者は、実行間隔も短縮できます。
    
- **ビデオ相互運用サービス代理トランザクション** 他のベンダー ソリューションから Skype for Business Server 2019 に移行する顧客は、多くの場合、これらの他のベンダーからビデオ電話会議デバイス (VTC) を使用し続けたいという望みがあります。 ビデオ相互運用サーバーは、ビデオ SIP トランクを介して Cisco CUCM に接続することで、お客様が会議室で引き続き Cisco VTC を使用できる新しい Skype for Business Server 2019 サーバーの役割です。 また、この機能は、ビデオ相互運用サーバーがアップし、ビデオ SIP トランク上の着信接続を処理できる確認に役立つ代理トランザクションを追加します。
    
- **アプリケーション共有会議代理トランザクション** アプリケーション共有会議のエンドツーエンドシナリオ検証がサポートされました。
    
## <a name="monitoring-scenarios"></a>監視シナリオ

2019 Skype for Business Server 2019 管理パックでは、さまざまな機能を活用して、問題の検出と診断に役立ちます。 これらの機能は、2019 年の環境の正常性をリアルタイムでSkype for Business Serverします。
  
|監視シナリオ|説明|
|:-----|:-----|
|代理トランザクション   | Windows PowerShell、サインイン、プレゼンス、IM、ユーザーの会議などのシナリオの高可用性をテストし、確認するためのコマンドレットを提供します。 <br/> 代理トランザクションは、企業内、企業外、ブランチ オフィスなど、地理的な場所から実行できます。  <br/> 代理トランザクションが失敗すると、エラーの正確な性質を判断するために HTML ログ s が作成されます。 これには、失敗したアクション、各アクションの待機時間、テストの実行に使用されるコマンド ライン、発生した特定のエラーが含まれます。   |
|通話の信頼性に関する通知   |Skype for Business Server 2019 サーバーによって作成された通話詳細レコード (CDRs) は、ユーザーが通話に接続できるかどうか、または通話が終了する理由を反映します。 通話の信頼性アラートは、CDR データベースにクエリを実行して、ピアツーピア通話または基本的な会議機能に対して接続の問題が発生したユーザーの数が多い場合を示すアラートを生成します。  <br/> シナリオ範囲には、音声通話、ピアツーピア インスタント メッセージング (IM)、その他の会議機能が含まれます。   |
|メディア品質のアラート   |各呼び出しの最後に、Skype for Business Server 2019 クライアントによって発行された QoE (Quality of Experience) レポートを参照するデータベース クエリ。 これらのクエリは、ユーザーが通話や会議中にメディア品質の低下を経験する可能性が最も高いシナリオを特定するアラートを生成します。 データは、パケット遅延や損失などの主要な指標に基いて構築され、ユーザー エクスペリエンスの品質に直接貢献します。   |
|コンポーネントの正常性アラート   |個々のサーバー コンポーネントは、イベント ログとパフォーマンス カウンターを介してアラートを発生し、ユーザー シナリオに大きな影響を与える可能性がある障害状態を示します。 これらのアラートは、サービスが実行されていない、エラー率が高い、メッセージの待ち時間が長い、接続の問題など、さまざまな条件を示します。   |
|依存関係の正常性の監視   |Skype for Business Server、さまざまな外部の理由でエラーが発生する可能性があります。 管理パックは、重大な問題を示す可能性がある重要な外部依存関係のデータを監視および収集します。 これらの依存関係には、インターネット インフォメーション サービス (IIS) 可用性、およびサーバーに使用されるサーバーの CPU がSkype for Business Server。   |
   
### <a name="alert-prioritization"></a>アラートの事前設定

アラートは、次のカテゴリに分類されます。 
  
 **優先度の高いアラート:** これらのアラートは、大規模なユーザー グループのサービス停止を引き起こす条件を示し、すぐに対応する必要があります。 代理トランザクションおよびオフライン サービス (音声ビデオ会議など) によって検出された停止は、Skype for Business Server優先度の高いアラートとして機能します。 これに対し、1 台のコンピューターでコンポーネントに障害が発生した場合は、優先度の高いアラートではありません。 Skype for Business Server 2019 には、ロード バランサーの背後にある複数のフロントエンド サーバーなど、このような状況に対応する高可用性機能が組み込まれています。
  
 **中優先度アラート:** これらのアラートは、ユーザーのサブセットに影響を与える条件、または通話品質の問題 (コンポーネントの障害、通話の確立の待機時間、通話の音質の低下など) を示します。 このカテゴリのアラートはステートフルです (つまり、ネットワーク接続の状態に基づいてアラートの性質が変わります)。たとえば、通話の確立時間が待機時間を示し、通常のしきい値に戻った場合、この中優先度アラートは System Center Operations Manager および管理者がアクションを実行する必要はありません。 自動解決できないアラートは、通常、同じ営業日に管理者が対処します。
  
 **その他のアラート:** これらのアラートは、特定のユーザーまたはユーザーのサブセットに影響を与える可能性があるコンポーネントから生成されます。 たとえば、一般的なアラートは、アドレス帳サービスがユーザーの Active Directory® Domain Services (AD DS) エントリを解析できない testuser@contoso.com。 管理者は、利用可能な時間がある場合はいつでも、これらのアラートに対処できます。
  
### <a name="synthetic-transactions"></a>代理トランザクション

Skype for Business Server 2019 管理パックは、代理トランザクションを通じてアラートの適用範囲を拡大します。 代理トランザクションは、Windows PowerShellユーザー シナリオをテストするために Operations Manager 管理パックに統合されたコマンドレットです。 代理トランザクションを実行するサーバーを指定すると、これらのコマンドレットは管理パックによって定期的にトリガーされます。 代理トランザクションに起因するエラーは、ステートフルアラートを生成します。 2019 年にサポートされる代理Skype for Business Server次に示します。
  
**登録、プレゼンス、連絡先でサポートされる代理トランザクション**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|1   |登録 (ユーザー ログイン)   |利用可能な Lync Server 2010 以降   |
|2   |アドレス帳サービス (ファイルのダウンロード)   |利用可能な Lync Server 2010 以降   |
|3   |アドレス帳 Web クエリ   |利用可能な Lync Server 2010 以降   |
|4   |プレゼンス   |利用可能な Lync Server 2010 以降   |
|5   |統合連絡先ストア   |利用可能な Lync Server 2013 以降   |
   
**ピアツーピア サービスでサポートされる代理トランザクション**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|6    |ピアツーピア インスタント メッセージング   |Lync Server 2010 以降で利用可能   |
|7    |ピアツーピア オーディオ ビデオ   |Lync Server 2010 以降で利用可能   |
|8    |MCX ピアツーピア インスタント メッセージ (モバイル)   |Lync Server 2010 の 2011 年 9 月リリースから 2019 年Skype for Business利用可能   |
 
> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
**電話会議と常設チャットでサポートされる代理トランザクション**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|9    |音声ビデオ会議   |Lync Server 2010 以降で利用可能   |
|10   |データ会議   |Lync Server 2013 以降で利用可能   |
|11   |インスタント メッセージ会議   |Lync Server 2010 以降で利用可能   |
|12    | 常設チャット  |Lync Server 2013 以降で利用可能   |
|13   |会議に起動ツール (スケジュールされた会議)   |Lync Server 2013 以降で利用可能   |
|14    |会議でのダイヤル   |2015 Skype for Business Server以降で利用可能  |
|15    |アプリケーション共有会議   |2015 Skype for Business Server以降で利用可能  |
|16   |UCWA 会議 (Web 会議への参加)   |2015 Skype for Business Server以降で利用可能  |
   
**ネットワークとパートナーの依存関係でサポートされる代理トランザクション**

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|17    |AV Edge Connectivity   |Lync Server 2013 以降で利用可能   |
|18    |AV Edge Connectivity Exchangeユニファイド メッセージ接続 (ボイスメール)   |Lync Server 2013 以降で利用可能   |
|19   |PSTN ピアツーピア通話   |Lync Server 2010 以降で利用可能   |
|20   |XMPP インスタント メッセージング (フェデレーション)   |Lync Server 2013 以降で利用可能   |
| 21   |ビデオ相互運用サーバー   |2015 Skype for Business Server以降で利用可能   |
   
## <a name="how-health-rolls-up"></a>正常性のロールアップの方法

次の表に、監視パックのオブジェクトの正常性Skype for Business Server示します。
  
|管理パック オブジェクト|説明|
|:-----|:-----|
|Skype for Business Server展開   |組織での 2019 Skype for Business Serverの展開を表します。   |
|Skype for Business Serverサイト   |サービスが展開されるさまざまな地理的な場所を表します。   |
|Skype for Business Serverプール   |インスタント メッセージングや会議などの通信サービスをユーザーに提供するプール (サイト内)。 特定のプールにコンピューターが 1 台だけある場合でも、フロント エンド プール、エッジ プール、ディレクター プールに適用されます。   |
|Skype for Business Server役割   |サービスをホストするSkype for Business Server役割。   |
|Skype for Business Serverサービス   |特定のコンピューターに展開された機能を表します (たとえば、コンピューター上のユーザー サービス fp01.contoso.com。   |
|Skype for Business Serverコンポーネント   |サービスのコンポーネント (たとえば、アドレス帳のダウンロード コンポーネントは Web サービスの一部です)。   |
|Skype for Business Serverプール ウォッチャー   |1 つのプールに対して実行されている代理トランザクションのインスタンス。   |
|Skype for Business Serverレジストラー ウォッチャー   |1 つのレジストラー プールに対して実行される代理トランザクションのインスタンス。   |
|Skype for Business ServerUser Services Pool Watcher   |1 つの User Services プールに対して実行される代理トランザクションのインスタンス。   |
|Skype for Business Server音声プールウォッチャー   |1 つの Voice プールに対して実行される代理トランザクションのインスタンス。   |
|Skype for Business Serverポート ウォッチャー   |1 つのプールに対して実行されているポート チェックのインスタンス。   |
|簡易 URL ウォッチャー   |展開で構成済みの単純な URL の HTTPS プロビリングを実行します。   |
   
![SCOM のロールアップ。](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
1 Skype for Business Serverには、複数の個々のSkype for Business Serverシステム (複数の Skype for Business Server、Skype for Business Server サービス、およびSkype for Business Serverコンポーネント)。 したがって、個々のサーバーまたはコンポーネントの障害は、同じプール内の他のサーバーがアプリケーション サービスをクライアントに提供する可能性があるため、Skype for Business Server プールの全体的な正常性にとってそれほど重要ではありません。 正常性は、パーセンテージ レベルでプールにSkype for Business Serverされます。 
  
プール 監視Skype for Business Serverは、プールに対して代理トランザクションSkype for Business Serverします。 次の図に示すように、1 つ以上の代理トランザクション (連続ポーリング間隔と呼ばれるプロセス) が連続して失敗すると、重大な正常性状態がプール レベル (代理トランザクションの最悪) にロールアップされます。 
  
![SCOM ロールアップの連続ポーリング。](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>ベスト プラクティス: カスタマイズ用の管理パックを作成する

既定では、Operations Manager は、オーバーライドなど、すべてのカスタマイズを既定の管理パックに保存します。 ベスト プラクティスとして、カスタマイズするシールされた管理パックごとに個別の管理パックを作成する必要があります。 
  
シールされた管理パックのカスタマイズされた設定を格納するための管理パックを作成する場合は、新しい管理パックに適切な名前を付ける (「Skype for Business Server 2019 カスタマイズ」など) をお勧めします。
  
シールされた各管理パックのカスタマイズを保存するための新しい管理パックを作成すると、テスト環境から実稼働環境にカスタマイズを簡単にエクスポートできます。 これにより、管理パックを削除する前に依存関係を削除する必要が生じ、管理パックを簡単に削除できます。 すべての管理パックのカスタマイズが既定の管理パックに保存され、1 つの管理パックを削除する必要がある場合は、最初に既定の管理パックを削除する必要があります。また、他の管理パックのカスタマイズも削除します。 
  
## <a name="links"></a>リンク

次のリンクは、2012 年の監視パックに関連付けられている一般的System Centerに接続します。
  
- [管理パックのライフ サイクル](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Operations Manager 2012 で管理パックをインポートする方法](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [ルールまたはモニターを上書きする方法](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [Operations Manager 2012 で実行アカウントを作成する方法](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [実行アカウントとプロファイルの管理](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [Operations Manager 管理パックをエクスポートする方法](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [Operations Manager 管理パックを削除する方法](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
次のリンクは、2007 監視パックに関連付けられている一般的なタスクSystem Center接続します。
  
- [管理パックのライフ サイクルの管理](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Operations Manager 2007 で管理パックをインポートする方法](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [上書きを使用して監視する方法](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [Operations Manager 2007 で実行アカウントを作成する方法](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [既存の実行プロファイルを変更する方法](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [管理パックのカスタマイズをエクスポートする方法](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [管理パックを削除する方法](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Operations Manager と監視パックに関する質問については[、「System Center」を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=179635)。
  
便利なリソースは、特定System Centerの "例" の投稿を含む、Operations [Manager Unleashed](https://opsmgrunleashed.wordpress.com/)ブログの一覧です。
  
Operations Manager の詳細については、次のブログを参照してください。 
  
- [Operations Manager チーム ブログ](https://blogs.technet.com/momteam/default.aspx)
    
- [OpsMgr に関する考え](https://thoughtsonopsmgr.blogspot.com/)
    
    
> [!IMPORTANT]
> Microsoft 以外のサイトのすべての情報とコンテンツは、その Web サイトの所有者またはユーザーが提供しています。 Microsoft は、この Web サイトの情報に関して、明示的、黙示的、または法的な保証を行いません。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2019 管理ツール](../management-tools-2019.md)