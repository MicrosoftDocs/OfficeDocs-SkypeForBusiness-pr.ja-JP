---
title: Skype for Business Server 2015 の新機能
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
description: '概要: このトピックでは、Skype for Business Server 2015 の新機能について説明します。 新しいクライアント エクスペリエンスの詳細については、「Lync は Skype for Business になった」を参照してください。新機能を参照してください。'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827587"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の新機能

**概要:** このトピックでは、Skype for Business Server 2015 の新機能について説明します。 新しいクライアント エクスペリエンスの詳細については [、「Lync is now Skype for Business」を参照してください。新機能を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=529022)。
  
Lync は現在、Skype for Business であり、エンタープライズ レベルのセキュリティ、コンプライアンス、および Lync の制御により、Skype から着こたえたエクスペリエンスを実現する通信およびコラボレーション プラットフォームです。 Skype for Business は、プレゼンス、IM、音声およびビデオ通話、オンライン会議などの機能を提供します。 Skype for Business は、Microsoft 365 または Office 365 の新しいクライアント エクスペリエンス、新しいサーバー リリース、およびサービスの更新を提供します。 組織内のユーザーが既に Skype に慣れ親しんだ場合、同僚を簡単に見つけて接続できる Skype for Business のパワーとシンプルさを高く評価できます。 組織内のユーザーが Lync から Skype for Business にアクセスする場合、ユーザーは既に使用しているすべての機能を認識しますが、シンプルなコントロールと新しい追加機能を備え、新しい新しいインターフェイスで認識できます。 Skype for Business Server 2015 は、新しいクライアント エクスペリエンスに加えて、オンプレミス サーバーとハイブリッド ソリューションの管理性を向上させるいくつかの新機能を提供します。
  
Skype for Business Server 2015 の新機能には、次の点が改善されています。
  
- ユーザー エクスペリエンス  
- 音声とビデオのサポート
- モバイル サポート
- オンプレミス サーバーの管理
- ハイブリッド ソリューションの展開と管理
- 多要素認証のサポート
    
## <a name="user-experience"></a>ユーザー エクスペリエンス

Skype for Business クライアントは、コンシューマー 向けバージョンの Skype と非常に似ていますが、同じボタンとアイコンを使用します。 メニューを少なくし、タスク階層をフラット化すると、ユーザーは必要なコントロールやコマンドをすばやく見つけやすくすることができます。 
  
Skype for Business には、上記の新しいユーザー エクスペリエンスと、以前にリリースされた Lync 2013 ユーザー エクスペリエンスが含まれています。 両方のエクスペリエンスを含めることにより、企業は新しいクライアントロールアウトのプロセスとタイミングを制御することで、ユーザーの変更を管理できます。既定のユーザー エクスペリエンスは、使用しているサーバーのバージョンによって異なります。 管理者は、EnableSkypeUI パラメーターで **Set-CsClientPolicy** コマンドレットを使用して、優先するエクスペリエンスを選択します。 クライアント エクスペリエンスの構成の詳細については [、「Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) とデスクトップ クライアント機能の比較を使用して Skype for Business を使用してクライアント エクスペリエンスを構成する」 [を参照してください](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)。
  
> [!NOTE]
> Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。 Lync 2013 クライアントを使用するためのクライアント環境の構成を試みる前に、クライアントのバージョンを確認して、番号 16 で始まるのではないか確認してください。例: 16.x.x.x。 
  
## <a name="voice-and-video-improvements"></a>音声とビデオの機能強化

Skype for Business Server 2015 には、通話データの収集と分析、サード パーティ製ビデオ会議システムとの相互運用性の向上など、音声およびビデオ機能の改善が含まれています。
  
### <a name="call-data-collection-and-analysis"></a>通話データの収集と分析

通話の評価機能を使用すると、Skype for Business Server 2015 管理者が通話データを収集できます。 この機能は、オンプレミス展開でのみ使用できます。 ユーザーは、通話の完了後にアンケートに回答するように求めるメッセージが表示されます。 詳細については [、「Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md)での通話の評価」を参照してください。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>サード パーティ製ビデオ会議システムとの相互運用性の向上

ビデオ相互運用サーバー (VIS) は、Skype for Business Server と Cisco ビデオ会議 (VTC) システム間の仲介者として機能します。 会議に参加すると、ユーザーは Cisco VTC システムを選択できます。 ビデオ相互運用サーバー (VIS) は、オンプレミス展開のスタンドアロン サーバーの役割として実装されます。 詳細については [、「Plan for Video Interop Server in Skype for Business Server 2015」を参照](plan-your-deployment/video-interop-server.md)してください。
  
### <a name="call-via-work"></a>[Call via Work] (仕事から通話)

[仕事から通話] 機能を使用すると、エンタープライズ ユーザーは Skype for Business クライアントから音声通話を行える。 ユーザーが音声通話を発信すると、Skype for Business から発信者の PBX または PSTN 電話にルーティングされます。 発信者が電話に応答すると、通話は宛先番号に転送されます。 通話受信者が応答し、コントロール パネルとして機能する Skype for Business で通話が確立されます。 発信者は、Skype for Business からプレゼンスコントロールと通話コントロールを管理できます。 サーバー管理者は、企業の [仕事から通話] を有効にして構成します。 詳細については [、「Plan for Call Via Work in Skype for Business Server 2015」を参照](plan-your-deployment/enterprise-voice-solution/call-via-work.md)してください。 
  
## <a name="mobile-device-support-improvements"></a>モバイル デバイスのサポートの強化

モバイル デバイスのサポートの改善点には、会話履歴とログ データへのアクセス、モバイル会議エクスペリエンスの強化、Office 全体でのシングル サインオンのサポートなど、Enterprise Edition ユーザーのモバイル エクスペリエンスを向上させる機能が含まれます。 さらに、Android のサポート、パフォーマンスの向上、共通アプリ フレームワークによる統合を簡素化する機能が改善されています。 
  
> [!NOTE]
> モバイル クライアントをサポートするには、Lync 2013 UCWA サーバーを Skype for Business Server 2015 にアップグレードする必要があります。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>モバイル デバイスでサーバー側の会話履歴を利用できる

会話履歴、未入力 IM、通話ログ データへのモバイル アクセスを有効にするために、この情報のアーカイブは、すべてのモバイル クライアントのサーバーを介して処理されます。 IM の自動承諾機能は、モバイル ユーザーが IM にすぐに応答しない場合にサーバーのタイム アウト メッセージを防止することで、信頼性を向上します。 サーバー ベースの Exchange/Outlook フォルダー統合を利用するには、Exchange Server 2013 以降、および更新されたモバイル クライアントが必要です。 
  
### <a name="enhanced-meeting-experiences"></a>強化された会議エクスペリエンス

デスクトップで利用できる会議機能は、モバイル ユーザーも利用できます。 新しい機能には、次の機能が含まれます。
  
- 共有 PowerPoint コンテンツの非同期ナビゲーション
- 共有 PowerPoint コンテンツを制御する発表者の機能
- 発表者が参加者を許可または拒否できる、発表者のロビー管理
    
### <a name="skype-for-business-on-android-improvements"></a>Android での Skype for Business の機能強化

Android 上の Skype for Business では、iOS の Skype for Business と Windows 上の Skype for Business で利用できる機能に似た機能が提供されます。
  
- 会話を続行または再参加する
- 証明書とパッシブ認証を有効にする
- 他のユーザーを会話に招待する
- グループ会話を簡単に開始する
- Skype for Business ユーザーでなくても会議に参加する
- Android タブレットでスマートフォン UI を有効にする
- 参加者を追加または削除して会議を管理する
    
> [!NOTE]
> これらの機能には、Android OS バージョン 4.0 以上が必要です。 
  
## <a name="management-of-on-premises-servers"></a>オンプレミス サーバーの管理

Skype for Business Server 2015 には、一時アップグレード、スマート セットアップ、修正プログラムとアップグレード プロセスの改善、フロントエンド プールのコールド スタート機能の向上、SQL Server AlwaysOn のサポート、集中ログとトラブルシューティングなど、オンプレミス サーバーの管理性を向上させるいくつかの新機能が用意されています。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>オンプレミス サーバーの一時アップグレード

新しい一時アップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードできます。この機能では、既存の Lync Server 2013 のハードウェアとサーバーへの投資が使用され、Skype for Business Server 2015 を展開する全体的なコストが削減されます。
  
一時アップグレードには、ダウンタイムを必要とする移動ユーザー方式と、ダウンタイムを必要とするオフライン方式の 2 つのシナリオがあります。 ビジネスに最適なアップグレード手順の詳細については [、「Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)」を参照してください。 
  
> [!NOTE]
> Lync Server 2010 からアップグレードする場合、一時オプションは使用できません。 Lync Server 2010 からのアップグレードの詳細については [、「Plan to upgrade to Skype for Business Server 2015」](plan-your-deployment/upgrade.md)を参照してください。 
  
### <a name="smart-setup"></a>スマート セットアップ

更新プログラムを自動的に検出してダウンロードするスマート セットアップ機能は、セットアップ プログラムに含まれています。 インストール プロセス中に、インストール プロセスで更新プログラムを確認する必要があるという確認がユーザーに表示されます。 詳細については [、「Skype for Business Server 2015](deploy/install/install.md)のインストール」を参照してください。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>フロントエンド サーバーの修正プログラム適用およびアップグレード プロセスの改善

Skype for Business Server では、2 つの新しいコマンドレットが導入されています。このコマンドレットを使用すると、以前のバージョンの Lync Server よりもフロントエンド サーバーのアップグレードや修正プログラムの適用がはるかに簡単になります。
  
フロントエンド サーバーにパッチを適用する必要がある場合、または他のメンテナンスを実行する必要がある場合は **、「Invoke-CsComputerFailOver」** と入力し、そのサーバーの名前を指定します。 Skype for Business Server は、そのサーバーのワークロードをプール内の他のサーバーに一時的に移動します。 その後、メンテナンスを実行し **、Invoke-CsComputerFailback** コマンドレットを使用して、そのサーバーをサービスに戻すことができます。 プール内の各サーバーにパッチを適用する必要がある場合は、各サーバーに対して一度に 1 つの手順を実行します。 これらの新しいコマンドレットを使用すると、以前のバージョンよりもはるかに迅速にサーバーにパッチを適用し、信頼性とワークフローを簡単にできます。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>フロントエンド プールのコールド スタート機能の強化

Skype for Business Server には、フロント エンド プール全体をコールド スタートするプロセスを簡素化および改善する新しいコマンドレットが導入されています。 新しい **Start-CsPool** コマンドレットを使用すると、プール内のすべてのフロントエンド サーバーの前提条件が確認された後、各サーバーの起動が試行されます。 問題が発生した場合は、問題を診断し、詳細と回避策を通知します。 場合によっては、個別のサーバーの一部を開始できない場合でも、プールを開始できます。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server AlwaysOn のサポートを構成する

Skype for Business Server 2015 では、AlwaysOn 可用性グループSQL Server AlwaysOn フェールオーバー クラスター インスタンスSQL Server両方のサポートが追加されています。 これらの機能に加えて、Skype for Business Server は、過去のバージョンの Lync Server と同様に、データベース ミラーリングと SQL Server クラスタリングのサポートを継続します。
  
SQL Server AlwaysOn 可用性グループは、データベース ミラーリングの代替手段を提供する SQL Server 2012 および SQL Server 2014 の高可用性および障害復旧ソリューションです。 可用性グループは、一緒にフェールオーバーする個別のデータベースセット (可用性データベースと呼ばれる) のフェールオーバー環境をサポートします。 可用性グループは、一連の読み取り/書き込みプライマリ データベースと、対応するセカンダリ データベースの 1 ~ 4 セットをサポートします。 必要に応じて、セカンダリ データベースを読み取り専用アクセスおよび一部のバックアップ操作で使用できます。
  
SQL Server フェールオーバー クラスター インスタンスは、Windows Server フェールオーバー クラスタリング (WSFC) 機能を利用して、サーバー インスタンス レベル (フェールオーバー クラスター インスタンス (FCI)) の冗長性を通じてローカルの高可用性を提供します。 FCI は、Windows Server フェールオーバー クラスタリング (WSFC) ノードSQL Server、場合によっては複数のサブネットにまたがってインストールされる 1 つのインスタンスです。
  
詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 2015」を参照](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)してください。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>オンプレミス サーバーの集中ログとトラブルシューティングの改善

集中ログ サービスは、Skype for Business Server 2015 の優先ログ環境です。 このリリースには新機能はありません。ただし、サービスと集中ログ サービス エージェント (ClsAgent.exe) の両方で、信頼性とパフォーマンスが向上しています。これは、管理者と通信し、管理者によって発行されたコマンドを受け取るサービス実行可能ファイルです。
  
Skype for Business Server 2015 では、Windows PowerShellコマンドレットを使用して、ログ サービス エージェントの管理、トレースの開始、レポートの生成を行います。 (Lync Server 2013 は、これらのタスクClsController.exeを使用しました。
  
集中ログ サービスは、任意の Skype for Business Server 2015 で実行できます。 組み込みのシナリオ (定義済みのトレース) は、カスタム シナリオを作成する機能と同じです。 AlwaysOn という特別なシナリオが常に実行され、管理者がほぼリアルタイムで一般的な問題を特定できます。
  
Snooper デバッグ ツールも更新され、モビリティ ログのデバッグが可能にされ、Lync 2013 または Skype for Business Server 2015 に接続しているデバイスで動作します。 このツールは、デバッグ ツールから Web ダウンロード [として利用できます](https://go.microsoft.com/fwlink/?LinkId=285257)。
  
## <a name="hybrid-deployment-and-management"></a>ハイブリッド展開と管理

Skype for Business Server 2015 では、次の機能を導入することで、ハイブリッド展開の管理機能を利用できます。
  
- Office 365 自動アシスタンス ツールの OnRamp によって決定される、お客様のオンプレミス資産の状態に基づくハイブリッド展開の推奨事項。
- 管理者がこれらのツールを使用してハイブリッド展開を管理できるよう、Skype for Business Server コントロール パネルと Skype for Business Server 管理センターの機能強化。
- 管理者が Microsoft 365 または Office 365 テナントにサインインし、ハイブリッド構成ウィザードを使用して Skype for Business Online とのハイブリッドをセットアップできるコントロール パネルの拡張機能。
- オンプレミス ユーザーを Skype for Business Online に移動したり、Skype for Business Online ユーザーをオンプレミスに戻したりするために、コントロール パネルのサポート。
- オンプレミス ユーザーから Skype for Business Online (ハイブリッド ユーザー) に移動されたオンプレミスのユーザー オブジェクトを識別してフィルター処理するためのコントロール パネル機能。
- オンプレミスからオンラインに移行したハイブリッド ユーザーから、Skype for Business Online で最初に作成されたクラウド ユーザーを識別してフィルター処理するための管理センター機能。
- オンプレミスから管理可能なプロパティのコントロール パネルを使用してハイブリッド ユーザーを管理する機能、および Skype for Business Online から管理可能なプロパティの管理センターを使用する機能。
- DirSync とのパスワード同期を使用して、オンプレミスの Active Directory パスワードをオンライン テナントと同期する機能。 構成されている場合、この機能を使用するとフェデレーション認証用に AD FS を展開する必要は削除されますが、多要素認証では引き続き AD FS が必要です。 
- Skype for Business Online と Exchange オンプレミスの共存の継続的なサポート。
    
> [!NOTE]
> Lync Online 2013 と Exchange のオンプレミスの共存およびサポートエクスペリエンスからの変更はありません。 
  
## <a name="multi-factor-authentication"></a>多要素認証

多要素認証は、複数の検証方法を使用する必要がある認証方法であり、ユーザーのサインインとトランザクションに重要な第 2 層のセキュリティを追加します。 たとえば、ユーザー名とパスワード、および証明書が必要です。 Skype for Business Server 2015 は、Lync Server 2013 の累積的な更新プログラムで利用可能な多要素認証機能に基い続けて構築されています。 多要素認証の重要な変更点は次のとおりです。
  
- Exchange および SharePoint との統合Office 2013 SP1 Active Directory 認証ライブラリの使用
- Skype for Business Web App クライアントでの多要素認証機能のサポート
    
Skype for Business の多要素認証を使用すると、地域に基づいて異なる認証オプションを提供できます。 たとえば、内部認証が統合 Windows 認証に依存し、組織外から認証を行う従業員が多要素認証を使用する環境を構成できます。 
  
Skype for Business の多要素認証エクスペリエンスは、次の点に関係なくシームレスです。
  
- 地理的な場所 - ユーザーが組織の内部または外部からサインインするかどうか 
- クライアント/デバイスの種類 - どの Skype for Business クライアントが使用され、クライアントが実行されているデバイス (PC、モバイル、iPad など)
- アカウントの場所 - ユーザーがオンプレミスの Active Directory または Azure Active Directory Online でホストされているかどうか。
