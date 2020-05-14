---
title: Skype for Business Server 2015 の新機能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: このトピックでは、Skype for Business Server 2015 の新機能について説明します。 新しいクライアント環境の詳細については、「Lync が Skype for Business で提供されるようになりました--新機能」を参照してください。'
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221087"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の新機能

**概要:** このトピックでは、Skype for Business Server 2015 の新機能について説明します。 新しいクライアント環境の詳細については、「 [Lync が Skype For business で提供されるようになりました--新機能」を参照](https://go.microsoft.com/fwlink/p/?LinkId=529022)してください。
  
Lync は現在、Skype for Business になっています。このプラットフォームは、Skype による企業レベルのセキュリティ、コンプライアンス、および Lync の管理によって得られる機能を統合したコミュニケーションとコラボレーションのプラットフォームです。 Skype for Business には、プレゼンス、IM、音声およびビデオ通話、オンライン会議などの機能が用意されています。 Skype for Business では、Microsoft 365 または Office 365 の新しいクライアント環境、新しいサーバーリリース、サービスへの更新が提供されています。 組織内のユーザーが既に Skype に精通している場合、共同作業者との間で簡単に検索して接続できる Skype for Business の機能が強化されます。 組織内のユーザーが Lync から Skype for Business に出てきた場合は、既に使用しているすべての機能が認識されますが、シンプルなコントロールと新しい追加機能を備えた新しいインターフェイスが提供されます。 新しいクライアント環境に加えて、Skype for Business Server 2015 には、オンプレミスサーバーとハイブリッドソリューションの管理性を向上させるためのいくつかの新機能が用意されています。
  
Skype for Business Server 2015 の新機能には、次のような改善が加えられています。
  
- ユーザー エクスペリエンス  
- 音声およびビデオのサポート
- モバイル サポート
- オンプレミスサーバーの管理
- ハイブリッドソリューションの展開と管理
- 多要素認証のサポート
    
## <a name="user-experience"></a>ユーザー エクスペリエンス

Skype for Business クライアントは、Skype のコンシューマーバージョンによく似ており、同じボタンとアイコンを使用します。 メニューおよび flatter のタスク階層が少ないほど、ユーザーは必要なコントロールやコマンドをすばやく見つけることができます。 
  
Skype for Business には、上記で説明した新しいユーザー環境と、以前にリリースされた Lync 2013 のユーザー環境が含まれています。 両方のエクスペリエンスが含まれているため、企業は新しいクライアントロールアウトのプロセスとタイミングを制御することによって、ユーザーの変更を管理することができます。既定のユーザー環境は、使用しているサーバーのバージョンによって異なります。 管理者は、EnableSkypeUI パラメーターを指定して、 **Set-CsClientPolicy**コマンドレットを使用することによって、推奨される機能を選択します。 クライアント環境の構成の詳細については、「skype for business および[デスクトップクライアント機能の比較](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)を使用した[クライアント環境の設定](deploy/deploy-clients/configure-the-client-experience.md)」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアントの機能は、Skype for Business 2016 クライアントバージョンのオプションではありません。 Lync 2013 クライアントを使用するようにクライアント環境を構成しようとする前に、クライアントバージョンをチェックして、番号16で始まらないことを確認してください。例: x.x.x. 
  
## <a name="voice-and-video-improvements"></a>音声とビデオの機能強化

Skype for Business Server 2015 には、音声とビデオの機能が強化されており、通話データの収集と分析、サードパーティ製ビデオ会議システムとの相互運用性が向上しています。
  
### <a name="call-data-collection-and-analysis"></a>通話データの収集と分析

通話の評価機能により、Skype for Business Server 2015 管理者は通話データを収集できます。 この機能は、オンプレミスの展開でのみ使用できます。 ユーザーは、通話の完了後にアンケートを受けるように求められます。 詳細については、「 [Rate My Call In Skype For Business Server 2015](manage/health-and-monitoring/rate-my-call.md)」を参照してください。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>サードパーティ製ビデオ会議システムとの相互運用性の向上

ビデオ相互運用サーバー (VIS) は、Skype for Business Server と Cisco ビデオ会議 (VTC) システム間の仲介者として機能します。 会議に参加するときに、ユーザーが Cisco VTC システムを選択できるようになりました。 ビデオ相互運用サーバー (VIS) は、オンプレミス展開用のスタンドアロンサーバーの役割として実装されています。 詳細については、「 [Plan For Video Interop server In Skype For Business server 2015](plan-your-deployment/video-interop-server.md)」を参照してください。
  
### <a name="call-via-work"></a>勤務先から通話

[勤務先から通話する機能を使用すると、エンタープライズユーザーは Skype for Business クライアントから音声通話を行うことができます。 ユーザーが音声通話を発信すると、Skype for Business から発信者の PBX または PSTN 電話にルーティングされます。 発信者が電話に応答すると、通話は宛先番号に送られます。 通話受信者が応答し、コントロールパネルとして Skype for Business が提供されている通話が確立されます。 発信者は、自分のプレゼンスを管理し、Skype for Business からコントロールを呼び出すことができます。 サーバー管理者は、社内の勤務先から通話を有効化および構成します。 詳細については、「 [Plan For Call Via Work In Skype For Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md)」を参照してください。 
  
## <a name="mobile-device-support-improvements"></a>モバイルデバイスのサポートの向上

モバイルデバイスのサポートの機能強化には、Office での会話履歴やログデータへのアクセス、拡張されたモバイル会議エクスペリエンス、シングルサインオンのサポートなど、Enterprise Edition ユーザーのモバイルエクスペリエンスを向上させる機能が含まれています。 さらに、Android のサポート、パフォーマンスの向上、および機能が、共通のアプリフレームワークによる統合を簡素化するために向上しました。 
  
> [!NOTE]
> モバイルクライアントをサポートするには、Lync 2013 UCWA サーバーを Skype for Business Server 2015 にアップグレードする必要があります。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>モバイルデバイスでは、サーバー側の会話履歴を使用できるようになりました。

会話の履歴、不在着信した IM、および通話ログデータへのモバイルアクセスを有効にするため、この情報のアーカイブは、すべてのモバイルクライアントでサーバーを介して処理されるようになりました。 IM の自動承諾機能は、モバイルユーザーがすぐに IM に応答しない場合にサーバーのタイムアウトメッセージを防ぐことで、信頼性を向上させます。 サーバーベースの Exchange/Outlook フォルダー統合を利用するには、Exchange Server 2013 またはそれ以降のバージョン、および更新されたモバイルクライアントが必要です。 
  
### <a name="enhanced-meeting-experiences"></a>拡張会議のエクスペリエンス

これで、デスクトップで利用できる会議機能が、モバイルユーザーも利用できるようになりました。 新機能は次のとおりです。
  
- 共有 PowerPoint コンテンツの非同期ナビゲーション
- 発表者が PowerPoint の共有コンテンツを制御する機能
- 参加者を許可または拒否できるようにするプレゼンターのロビー管理
    
### <a name="skype-for-business-on-android-improvements"></a>Android の Skype for Business の機能強化

Android 上の skype for Business では、Windows で Skype for business と Skype for business で使用できるものと同様の機能が提供されるようになりました。
  
- 会話を続行または再参加する
- 証明書とパッシブ認証を有効にする
- 会話に他のユーザーを招待する
- グループの会話を簡単に開始する
- Skype for Business ユーザーなしで会議に参加する
- Android タブレットでスマートフォン UI を有効にする
- 参加者を追加または削除して会議を管理する
    
> [!NOTE]
> これらの機能には、Android OS バージョン4.0 以降が必要です。 
  
## <a name="management-of-on-premises-servers"></a>オンプレミスサーバーの管理

Skype for Business Server 2015 には、一括アップグレード、スマートセットアップ、強化されたパッチおよびアップグレードプロセス、フロントエンドプールのコールドスタート機能、SQL Server AlwaysOn サポート、集中ログおよびトラブルシューティングなど、オンプレミスサーバーの管理性を向上させるためのいくつかの新機能が用意されています。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>オンプレミスサーバーの一括アップグレード

既存の Lync Server 2013 ハードウェアとサーバーへの投資を使用する新しい一括アップグレード機能を使用して Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードできるようになりました。これにより、Skype for Business Server 2015 を展開するための全体的なコストが削減されます。
  
一括アップグレードには2つのシナリオがあります。これには、ダウンタイムを必要としない移動ユーザーメソッドと、ダウンタイムを必要とするオフライン方法があります。 お客様のビジネスに適したアップグレード手順の詳細については、「 [Plan to upgrade To Skype for Business Server 2015](plan-your-deployment/upgrade.md)」を参照してください。 
  
> [!NOTE]
> Lync Server 2010 からアップグレードしている場合は、インプレースオプションは使用できません。 Lync Server 2010 からのアップグレードの詳細については、「 [Plan to upgrade To Skype For Business Server 2015](plan-your-deployment/upgrade.md)」を参照してください。 
  
### <a name="smart-setup"></a>スマートセットアップ

更新プログラムを自動的に検出してダウンロードするスマートセットアップ機能は、セットアッププログラムの一部になっています。 インストールプロセス中に、インストールプロセスで更新プログラムをチェックする必要があるかどうかを確認するメッセージがユーザーに表示されます。 詳細については、「 [Install Skype For Business Server 2015](deploy/install/install.md)」を参照してください。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>フロントエンドサーバーのパッチおよびアップグレードプロセスの改善

Skype for Business Server には、以前のバージョンの Lync Server よりも、フロントエンドサーバーのアップグレードまたは修正を容易にするための2つの新しいコマンドレットが導入されています。
  
フロントエンドサーバーにパッチを適用したり、その他のメンテナンスを実行したりする必要がある場合は、「 **Invoke-CsComputerFailOver** 」と入力し、そのサーバーの名前を指定します。 Skype for Business Server は、サーバーのワークロードをプール内の他のサーバーに一時的に移動します。 その後、メンテナンスを実行した後、 **Invoke-CsComputerFailback バック**コマンドレットを使用して、そのサーバーをサービスに戻すことができます。 プール内の各サーバーにパッチを適用する必要がある場合は、サーバーごとに1つずつ、この手順を実行するだけです。 これらの新しいコマンドレットを使用すると、以前のバージョンよりもサーバーを更新しやすくなり、より信頼性が高く、ワークフローがより簡単になります。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>フロントエンドプールのコールドスタート機能の強化

Skype for Business Server には、フロントエンドプール全体のコールドスタートのプロセスを簡略化して改善する新しいコマンドレットが導入されています。 新しい**Start-CsPool**コマンドレットを使用すると、プール内のすべてのフロントエンドサーバーの前提条件が確認され、各サーバーの起動が試行されます。 問題が発生した場合は、それを診断して詳細と回避策を通知します。 場合によっては、一部のサーバーを開始できない場合でもプールを開始できることがあります。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>オンプレミスサーバーの SQL Server AlwaysOn サポート

Skype for Business Server 2015 には、SQL Server AlwaysOn 可用性グループと SQL Server AlwaysOn フェールオーバークラスターインスタンスの両方のサポートが追加されています。 これらの機能に加えて、Skype for Business Server は、以前のバージョンの Lync Server と同様に、データベースミラーリングと SQL Server のクラスター化のサポートを継続しています。
  
SQL Server の AlwaysOn 可用性グループは、SQL Server 2012 および SQL Server 2014 の高可用性および障害復旧ソリューションで、データベースミラーリングに代わる機能を提供します。 可用性グループは、互いにフェールオーバーするデータベースの個別セット (可用性データベースと呼ばれる) のフェールオーバー環境をサポートします。 可用性グループは、一連の読み取り/書き込みプライマリデータベースと、対応するセカンダリデータベースのセットを1つだけサポートします。 必要に応じて、セカンダリデータベースを読み取り専用アクセスで使用可能にしたり、一部のバックアップ操作に使用したりできます。
  
SQL Server フェールオーバークラスターインスタンスでは、Windows Server フェールオーバークラスタリング (WSFC) 機能を活用して、サーバーインスタンスレベル (フェールオーバークラスターインスタンス (FCI)) で冗長性によってローカルの高可用性を実現します。 FCI は、Windows Server フェールオーバークラスタリング (WSFC) ノード間、および場合によっては複数のサブネットにわたってインストールされる SQL Server の単一のインスタンスです。
  
詳細については、「 [Plan for high availability and disaster recovery In Skype For Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>オンプレミスサーバーの集中ログとトラブルシューティングの向上

集中ログサービスは、Skype for Business Server 2015 の推奨されるログ環境です。 このリリースには新しい機能はありませんが、サービスと集中ログサービスエージェント (ClsAgent .exe) の両方の信頼性とパフォーマンスが向上しています。これは、コントローラーと通信し、管理者によって発行されたコマンドを受信するサービスの実行可能ファイルです。
  
Skype for Business Server 2015 は、Windows PowerShell コマンドレットを使用して、ログサービスエージェントの管理、トレースの開始、およびレポートの生成を行います。 (Lync Server 2013 は、これらのタスクを実行するために ClsController を使用しています)。
  
集中ログサービスは、任意の Skype for Business Server 2015 で実行できます。 組み込みのシナリオ (事前定義されたトレース) は、カスタムのシナリオを作成できるのと同じです。 AlwaysOn という特殊なシナリオがあり、常に実行されており、管理者は、ほぼリアルタイムで一般的な問題を見つけることができます。
  
また、Snooper デバッグツールは、モビリティログをデバッグできるように更新され、Lync 2013 または Skype for Business Server 2015 に接続するデバイスで動作します。 このツールは、[デバッグツール](https://go.microsoft.com/fwlink/?LinkId=285257)から Web からダウンロードできます。
  
## <a name="hybrid-deployment-and-management"></a>ハイブリッド展開と管理

Skype for Business Server 2015 では、次の機能を導入することによって、ハイブリッド展開の管理および管理機能が有効になります。
  
- Office 365 の OnRamp ツールによって決定された、お客様のオンプレミス資産の状態に基づくハイブリッド展開の推奨事項。
- Skype for Business Server コントロールパネルと Skype for Business Server 管理センターの機能拡張により、管理者はこれらのツールを使用してハイブリッド展開を管理できるようになります。
- 管理者が Microsoft 365 または Office 365 テナントにサインインし、ハイブリッド構成ウィザードを使用して Skype for Business Online でハイブリッドをセットアップできるようにするコントロールパネルの拡張機能。
- コントロールパネルは、オンプレミスのユーザーを Skype for business Online に移動したり、Skype for Business Online ユーザーをオンプレミスに移行したりするためのサポートを行います。
- オンプレミスユーザーからの Skype for Business Online (つまりハイブリッドユーザー) に移動されたオンプレミスのユーザーオブジェクトを識別してフィルター処理するコントロールパネルの機能。
- オンプレミスからオンラインに移行したハイブリッドユーザーから、Skype for Business Online で最初に作成されたクラウドユーザーを識別してフィルター処理する管理センターの機能。
- コントロールパネルを使用して、オンプレミスで管理可能なプロパティと、Skype for Business Online から管理可能なプロパティの管理センターを使用して、ハイブリッドユーザーを管理できます。
- DirSync でのパスワード同期を使用して、オンプレミスの Active Directory パスワードとオンラインテナントを同期する機能。 この機能が構成されている場合、フェデレーション認証用に AD fs を展開する必要はありませんが、多要素認証を行うには依然として AD FS が必要です。 
- Skype for Business Online とオンプレミスの Exchange との共存のサポートが継続されます。
    
> [!NOTE]
> Lync Online 2013 と Exchange オンプレミスの共存とサポートのための変更はありません。 
  
## <a name="multi-factor-authentication"></a>多要素認証

多要素認証は、複数の検証方法の使用を必要とし、ユーザーのサインインとトランザクションにセキュリティの重要な第2層を追加する認証方式です。 たとえば、ユーザー名とパスワードを要求し、証明書を要求します。 Skype for Business Server 2015 は、Lync Server 2013 の累積的な更新プログラムで利用できる多要素認証機能に基づいて構築を継続します。 多要素認証の重要な変更点は次のとおりです。
  
- Office 2013 SP1 Active Directory 認証ライブラリを使用して Exchange と SharePoint との統合を行う
- Skype for Business Web App クライアントでの多要素認証機能のサポート
    
Skype for Business の多要素認証を使用すると、地域に基づいてさまざまな認証オプションを提供できるようになりました。 たとえば、ユーザーは、内部認証が統合 Windows 認証を使用するように環境を構成できますが、組織の外部から認証を受ける従業員は多要素認証を使用します。 
  
Skype for Business の多要素認証の機能は、次のような点でシームレスです。
  
- 地理的な場所-ユーザーが組織の内部または外部からサインインしているかどうか 
- クライアント/デバイスの種類-使用する Skype for Business クライアントとクライアントが実行しているデバイス (PC、モバイル、iPad など)
- アカウントの場所-ユーザーがオンプレミスの Active Directory または Azure Active Directory Online でホストされているかどうか。
