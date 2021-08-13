---
title: 2015 年の新機能Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: '概要: このトピックを参照して、2015 年の新機能Skype for Business Serverしてください。 新しいクライアント エクスペリエンスの詳細については、「Lync は現在使用Skype for Business -- 新機能」を参照してください。'
ms.openlocfilehash: e32b55c6eb41a5800f4bceb1e213a44efed5d2292ccd57766dbf56c1c0cd6e4b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344516"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>2015 年の新機能Skype for Business Server

**概要:** このトピックでは、2015 年の新機能についてSkype for Business Serverしてください。 新しいクライアント エクスペリエンスの詳細については[、「Lync is now」を参照Skype for Business新機能を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync はSkype for Business、Skype にインスパイアされたエクスペリエンスと、エンタープライズ レベルのセキュリティ、コンプライアンス、および Lync の制御を統合するコミュニケーションおよびコラボレーション プラットフォームです。 Skype for Business、IM、音声およびビデオ通話、オンライン会議などの機能を提供します。 Skype for Business、新しいクライアント エクスペリエンス、新しいサーバー リリース、およびサービスの更新プログラムを、Microsoft 365またはOffice 365。 組織内のユーザーが既に Skype に精通している場合、同僚を簡単に見つけて接続できる Skype for Business の機能とシンプルさを理解できます。 組織内のユーザーが Lync から Skype for Business にアクセスする場合、ユーザーは既に使用しているすべての機能を認識しますが、簡略化されたコントロールと新しい追加機能を備え、新しいインターフェイスで認識されます。 新しいクライアント エクスペリエンスに加えて、Skype for Business Server 2015 には、オンプレミス サーバーとハイブリッド ソリューションの管理性を向上させるいくつかの新機能が提供されています。
  
2015 年 2015 Skype for Business Serverの新機能には、以下の機能強化が含まれます。
  
- ユーザー エクスペリエンス  
- 音声とビデオのサポート
- モバイル サポート
- オンプレミス サーバーの管理
- ハイブリッド ソリューションの展開と管理
- 多要素認証のサポート
    
## <a name="user-experience"></a>ユーザー エクスペリエンス

このSkype for Businessクライアントは、コンシューマー バージョンの Skypeに非常に似ていて、同じボタンとアイコンを使用します。 メニューが少なく、タスク階層がフラット化された場合、ユーザーは必要なコントロールとコマンドをすばやく見つけやすくできます。 
  
Skype for Business、前述の新しいユーザー エクスペリエンスと、以前にリリースされた Lync 2013 ユーザー エクスペリエンスが含まれます。 両方のエクスペリエンスを組み込むと、企業は新しいクライアント ロールアウトのプロセスとタイミングを制御することで、ユーザーの変更を管理できます。既定のユーザー エクスペリエンスは、使用しているサーバーのバージョンによって異なります。 管理者は、EnableSkypeUI パラメーターで **Set-CsClientPolicy** コマンドレットを使用して、優先するエクスペリエンスを選択します。 クライアント エクスペリエンスの構成の詳細については、「クライアント[](deploy/deploy-clients/configure-the-client-experience.md)エクスペリエンスを構成する」および「Skype for Business デスクトップ クライアント機能の比較」を[参照](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)Skype for Business。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、2016 クライアント バージョンSkype for Businessオプションではありません。 Lync 2013 クライアントを使用するクライアント環境を構成する前に、クライアントのバージョンを確認して、番号 16 で始まるのを確認してください。たとえば、16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>音声とビデオの機能強化

Skype for Business Server 2015 には、通話データの収集と分析、サードパーティのビデオ電話会議システムとの相互運用性の向上など、音声およびビデオ機能の改善が含まれています。
  
### <a name="call-data-collection-and-analysis"></a>データの収集と分析を呼び出す

[通話率] 機能を使用すると、2015 Skype for Business Serverユーザーが通話データを収集できます。 この機能は、オンプレミス展開でのみ使用できます。 ユーザーは、通話が完了した後にアンケートを受け取るメッセージが表示されます。 詳細については、「Rate [my Call in Skype for Business Server 2015」を参照](manage/health-and-monitoring/rate-my-call.md)してください。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>サードパーティ製ビデオ電話会議システムとの相互運用性の向上

ビデオ相互運用サーバー (VIS) は、Skype for Business Serverビデオ電話会議 (VTC) システム間の仲介として機能します。 会議に参加すると、ユーザーは Cisco VTC システムを選択できます。 ビデオ相互運用サーバー (VIS) は、オンプレミス展開のスタンドアロン サーバーの役割として実装されます。 詳細については[、「Plan for Video Interop Server in Skype for Business Server 2015」を参照](plan-your-deployment/video-interop-server.md)してください。
  
### <a name="call-via-work"></a>仕事で通話する

[作業による通話] 機能を使用すると、エンタープライズ ユーザーはクライアントから音声通話をSkype for Businessできます。 ユーザーが音声通話を発信すると、発信元の PBX Skype for Business PSTN 電話にルーティングされます。 発信者が電話に応答すると、通話は宛先番号に転送されます。 呼び出しの受信者が応答し、呼び出しはコントロール Skype for Businessを使用して確立されます。 発信者は、自分のプレゼンスを管理し、コントロールを呼び出Skype for Business。 サーバー管理者は、企業の仕事を通じて通話を有効にして構成します。 詳細については、「Plan [for Call Via Work in Skype for Business Server 2015」を参照](plan-your-deployment/enterprise-voice-solution/call-via-work.md)してください。 
  
## <a name="mobile-device-support-improvements"></a>モバイル デバイスのサポートの強化

モバイル デバイスサポートの機能強化には、Enterprise Edition ユーザーのモバイル エクスペリエンスを向上させる機能 (会話履歴やログ データへのアクセス、拡張されたモバイル会議エクスペリエンス、Office 全体のシングル サインオン サポートなど) が含まれます。 さらに、共通アプリ フレームワークを介して統合を簡素化するための Android のサポート、パフォーマンスの向上、および機能が改善されています。 
  
> [!NOTE]
> Lync 2013 UCWA サーバーは、モバイル クライアントをサポートSkype for Business Server 2015 にアップグレードする必要があります。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>モバイル デバイスでサーバー側の会話履歴が利用できる

会話履歴、不足している IM、通話ログ データへのモバイル アクセスを有効にするために、この情報のアーカイブは、すべてのモバイル クライアントのサーバーを介して処理されます。 IM の自動受け入れ機能は、モバイル ユーザーが IM にすぐに応答しない場合にサーバーのタイム アウト メッセージを防止することで、信頼性を向上します。 サーバー ベースの Exchange/Outlook フォルダー統合を利用するには、Exchange Server 2013 以降、および更新されたモバイル クライアントが必要です。 
  
### <a name="enhanced-meeting-experiences"></a>会議エクスペリエンスの強化

デスクトップで利用できる会議機能は、モバイル ユーザーも利用できます。 新しい機能には、次の機能が含まれます。
  
- 共有コンテンツの非同期PowerPointナビゲーション
- 発表者が共有コンテンツを制御PowerPointする
- 発表者が参加者を認める、または拒否できるロビー管理
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business Android の機能強化に関する説明

Skype for Business Android では、iOS および iOS 上で使用できる機能に似たSkype for Business機能がSkype for Business提供Windows。
  
- 会話を続行または再参加する
- 証明書とパッシブ認証を有効にする
- 他のユーザーを会話に招待する
- グループの会話を簡単に開始する
- ユーザーにならずに会議にSkype for Businessする
- Android タブレットでスマートフォンの UI を有効にする
- 参加者を追加または削除して会議を管理する
    
> [!NOTE]
> これらの機能には、Android OS バージョン 4.0 以上が必要です。 
  
## <a name="management-of-on-premises-servers"></a>オンプレミス サーバーの管理

Skype for Business Server 2015 には、インプレイス アップグレード、スマート セットアップ、パッチ適用とアップグレード プロセスの改善、フロントエンド プールのコールド スタート機能の向上、SQL Server AlwaysOn サポート、集中ログとトラブルシューティングなど、オンプレミス サーバーの管理性を向上させるいくつかの新機能が用意されています。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>オンプレミス サーバーの一時アップグレード

既存の Lync Server 2013 ハードウェアとサーバーへの投資を使用する新しい一時アップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードし、Skype for Business Server 2015 を展開する全体的なコストを削減できます。
  
インプレイス アップグレードには、ダウンタイムが必要ない Move User メソッドと、ダウンタイムが必要な Offline メソッドの 2 つのシナリオがあります。 ビジネスに最適なアップグレード手順の詳細については、「Plan to upgrade to upgrade to Skype for Business Server [2015」を参照](plan-your-deployment/upgrade.md)してください。 
  
> [!NOTE]
> Lync Server 2010 からアップグレードする場合は、インプレイス オプションを使用できません。 Lync Server 2010 からのアップグレードの詳細については、「Plan to upgrade to upgrade to Skype for Business Server [2015」を参照](plan-your-deployment/upgrade.md)してください。 
  
### <a name="smart-setup"></a>スマート セットアップ

更新プログラムを自動的に検出してダウンロードするスマート セットアップ機能は、セットアップ プログラムの一部です。 インストール プロセス中に、インストール プロセスで更新プログラムを確認する必要がある場合は、ユーザーに問い合されます。 詳細については[、「Install Skype for Business Server 2015」を参照してください](deploy/install/install.md)。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>フロント エンド サーバーの修正プログラムとアップグレード プロセスの改善

Skype for Business Server 2 つの新しいコマンドレットが導入されています。これは、以前のバージョンの Lync Server よりもずっと簡単にフロント エンド サーバーをアップグレードまたは修正するのに役立ちます。
  
フロント エンド サーバーにパッチを適用するか、その他のメンテナンスを実行する必要がある場合は **、「Invoke-CsComputerFailOver」** と入力し、そのサーバーの名前を指定します。 Skype for Business Server、そのサーバーのワークロードをプール内の他のサーバーに一時的に移動します。 その後、メンテナンスを実行し **、Invoke-CsComputerFailback** コマンドレットを使用して、そのサーバーをサービスに戻すことができます。 プール内の各サーバーにパッチを適用する必要がある場合は、単に各サーバーに対して、一度に 1 つ、この手順に従います。 これらの新しいコマンドレットを使用すると、以前のバージョンよりもはるかに速く、信頼性とワークフローが簡単なサーバーにパッチを適用できます。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>フロントエンド プールのコールド スタート機能の強化

Skype for Business Server、フロント エンド プール全体をコールドスタートするプロセスを簡素化し、改善する新しいコマンドレットが導入されています。 新しい **Start-CsPool** コマンドレットを使用すると、プール内のすべてのフロントエンド サーバーの前提条件をチェックし、各サーバーの起動を試みる。 問題が発生した場合は、それらを診断し、詳細と回避策を通知します。 場合によっては、個々のサーバーの一部が起動できない場合でも、プールを開始できます。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL ServerAlwaysOn のオンプレミス サーバーのサポート

Skype for Business Server 2015 では、AlwaysOn 可用性グループSQL Server AlwaysOn フェールオーバー クラスター インスタンスSQL Serverサポートが追加されています。 これらの機能に加えて、Skype for Business Server以前のバージョンの Lync Server と同様に、SQL Serverクラスタリングのサポートが引き続きサポートされています。
  
SQL ServerAlwaysOn 可用性グループは、SQL Server 2012 および SQL Server 2014 の高可用性および障害復旧ソリューションであり、データベース ミラーリングの代わりに使用できます。 可用性グループは、一緒にフェールオーバーするデータベースの個別のセット (可用性データベースと呼ばれる) のフェールオーバー環境をサポートします。 可用性グループは、読み取り/書き込みプライマリ データベースのセットと、対応するセカンダリ データベースの 1 ~ 4 セットをサポートします。 必要に応じて、セカンダリ データベースを読み取り専用アクセスおよび一部のバックアップ操作で使用できます。
  
SQL Serverフェールオーバー クラスター インスタンスは、Windows サーバー フェールオーバー クラスタリング (WSFC) 機能を活用して、サーバー インスタンス レベルの冗長性 (フェールオーバー クラスター インスタンス (FCI) でローカル高可用性を提供します。 FCI は、SQL Server Windows サーバー フェールオーバー クラスタリング (WSFC) ノード全体にインストールされ、場合によっては複数のサブネットにまたがってインストールされる 1 つのインスタンスです。
  
詳細については、「Plan for high availability and disaster recovery in Skype for Business Server [2015」を参照](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)してください。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>オンプレミス サーバーの一元的なログ記録とトラブルシューティングの改善

集中ログ サービスは、2015 年から 2015 年の優先ログSkype for Business Serverです。 このリリースでは新機能は追加されませんが、サービスと集中ログ サービス エージェント (ClsAgent.exe) の両方で信頼性とパフォーマンスが向上しました。管理者が発行したコマンドを受け取り、コントローラーと通信してコマンドを受け取るサービス実行可能ファイルです。
  
Skype for Business Server 2015 では、Windows PowerShellコマンドレットを使用して、ログ サービス エージェントの管理、トレースの開始、レポートの生成を行います。 (Lync Server 2013 では、ClsController.exeタスクを実行するために使用されます)。
  
集中ログ サービスは、2015 年Skype for Business Serverできます。 組み込みのシナリオ (定義済みのトレース) は、カスタム シナリオを作成する機能と同じままです。 AlwaysOn と呼ばれる特別なシナリオが常に実行され、管理者は、ほぼリアルタイムで一般的な問題を特定できます。
  
Snooper デバッグ ツールも更新され、モビリティ ログのデバッグが可能で、Lync 2013 または Skype for Business Server 2015 に接続するデバイスで動作します。 このツールは、デバッグ ツールから Web [ダウンロードとして使用できます](https://go.microsoft.com/fwlink/?LinkId=285257)。
  
## <a name="hybrid-deployment-and-management"></a>ハイブリッド展開と管理

Skype for Business Server 2015 では、次の機能を導入することで、ハイブリッド展開の管理および管理機能を有効にできます。
  
- お客様のオンプレミス資産の状態に基づくハイブリッド展開の推奨事項 (自動支援ツールの OnRamp Office 365決定)。
- 管理者がこれらのツールSkype for Business Serverハイブリッド展開を管理Skype for Business Serverコントロール パネルと管理者センターの機能拡張。
- 管理者が Microsoft 365 または Office 365 テナントにサインインし、ハイブリッド構成ウィザードを使用して Skype for Business Online とハイブリッドをセットアップできるコントロール パネルの機能強化。
- コントロール パネルでは、オンプレミス ユーザーをオンラインに移行したりSkype for Businessオンライン ユーザー Skype for Businessオンプレミスに戻したりできます。
- コントロール パネルの機能は、オンプレミス ユーザーから Skype for Business Online (ハイブリッド ユーザー) に移動されたオンプレミスのユーザー オブジェクトを識別してフィルター処理します。
- 管理センターの機能は、オンプレミスからオンラインに移行されたハイブリッド ユーザーから Skype for Business Online で最初に作成されたクラウド ユーザーを識別し、フィルター処理します。
- オンプレミスから管理できるプロパティに対してコントロール パネルを使用してハイブリッド ユーザーを管理する機能と、オンラインから管理できるプロパティの管理センターをSkype for Businessします。
- DirSync とのパスワード同期を使用して、オンプレミスの Active Directory パスワードをオンライン テナントと同期する機能。 構成されている場合、この機能を使用すると、フェデレーション認証AD FS を展開する必要が取り除かされますが、多要素認証には AD FS が必要です。 
- オンラインとオンプレミスのSkype for Business共存Exchange継続サポート。
    
> [!NOTE]
> Lync Online 2013 とオンプレミスの共存Exchangeサポート エクスペリエンスに変更はありません。 
  
## <a name="multi-factor-authentication"></a>多要素認証

多要素認証は、複数の検証方法を使用する必要がある認証方法であり、ユーザーのサインインとトランザクションに重要な第 2 層のセキュリティを追加します。 たとえば、ユーザー名とパスワード、および証明書が必要です。 Skype for Business Server 2015 は、Lync Server 2013 の累積的な更新プログラムで使用できる多要素認証機能に引き続き組み込まれています。 多要素認証の重要な変更点は次のとおりです。
  
- 2013 SP1 Office active Directory 認証ライブラリを 2013 SP1 で使用して、ExchangeおよびSharePoint
- クライアントでの多要素認証機能Skype for Business Web アプリサポート
    
複数Skype for Business認証を使用すると、地理的な場所に基づいてさまざまな認証オプションを提供できます。 たとえば、内部認証が統合 Windows 認証に依存し、組織外から認証する従業員が多要素認証を使用する環境を構成できます。 
  
多要素Skype for Businessの認証エクスペリエンスは、次の点に関係なくシームレスです。
  
- 地理的な場所 - ユーザーが組織の内部または外部からサインインするかどうか 
- クライアント/デバイスの種類 - 使用Skype for Businessクライアントが実行されているデバイス (PC、モバイル、iPadなど)
- アカウントの場所 - ユーザーがオンプレミスの Active Directory でホストされているのか、オンラインでホストAzure Active Directoryします。
