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
description: '概要: Skype for Business Server 2015 の新機能については、こちらのトピックを参照してください。 新しいクライアントエクスペリエンスの詳細については、「Lync が Skype for Business に変わりました。新機能」を参照してください。'
ms.openlocfilehash: 0a11c94f7c31b0140a256ab350f5dad6112bc71e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824081"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の新機能

**概要:** このトピックでは、Skype for Business Server 2015 の新機能について説明します。 新しいクライアントエクスペリエンスの詳細については、「 [Lync が Skype For business に変わりました。新機能」](https://go.microsoft.com/fwlink/p/?LinkId=529022)を参照してください。
  
Lync は Skype for Business に変わりました。これは、Skype の優れたセキュリティ、コンプライアンス、および管理機能を備えたコミュニケーションとコラボレーションプラットフォームです。 Skype for Business には、プレゼンス、IM、音声通話、ビデオ通話、オンライン会議などの機能が用意されています。 Skype for Business では、新しいクライアントエクスペリエンス、新しいサーバーのリリース、Office 365 のサービスの更新が提供されています。 組織内のユーザーが既に Skype に精通している場合は、同僚と簡単に検索して連絡を取ることができる Skype for Business の機能がさらに簡単になります。 組織内のユーザーが Lync から Skype for Business に表示されている場合は、そのユーザーが既に使用しているすべての機能が認識されますが、新しいインターフェイスで簡単なコントロールと新しい追加機能が提供されます。 Skype for Business Server 2015 には、新しいクライアントエクスペリエンスに加えて、オンプレミスサーバーとハイブリッドソリューションの管理性を向上させるための新機能がいくつか用意されています。
  
Skype for Business Server 2015 の新機能には、次のような改善が含まれています。
  
- ユーザー エクスペリエンス  
- 音声とビデオのサポート
- モバイル機能のサポート
- オンプレミス サーバーの管理
- ハイブリッド ソリューションの展開および管理
- 複数要素の認証のサポート
    
## <a name="user-experience"></a>ユーザー エクスペリエンス

Skype for Business クライアントは、コンシューマー版の Skype とよく似ていて、同じボタンとアイコンを使用しています。 メニューとタスク階層が少なくなっているため、必要なコントロールとコマンドをすばやく見つけることができます。 
  
Skype for Business には、上で説明した新しいユーザーエクスペリエンスと、以前にリリースされた Lync 2013 ユーザーエクスペリエンスが含まれています。 両方のエクスペリエンスを含めることで、企業は新しいクライアントロールアウトのプロセスとタイミングを制御して、ユーザーの変更を管理することができます。既定のユーザーエクスペリエンスは、使用しているサーバーのバージョンによって異なります。 管理者は、**Set-CsClientPolicy** コマンドレットと EnableSkypeUI パラメーターを使用して、優先するエクスペリエンスを選択できます。 クライアントエクスペリエンスの構成の詳細については[、「skype](deploy/deploy-clients/configure-the-client-experience.md) for Business と[デスクトップクライアントの機能の比較](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)」を参照してください。
  
> [!NOTE]
> Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョンでは使用できません。 Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。 
  
## <a name="voice-and-video-improvements"></a>音声とビデオの改善点

Skype for Business Server 2015 には、音声とビデオの機能が強化されています。これには、データの収集と分析が含まれます。また、サードパーティのビデオ会議システムとの相互運用性が向上しています。
  
### <a name="call-data-collection-and-analysis"></a>通話データの収集と分析

通話料金の評価機能により、Skype for Business Server 2015 管理者は通話データを収集できます。 この機能は、オンプレミス展開でのみ使用可能です。 ユーザーは通話の終了後、調査に回答するように求められます。 詳細については、「[Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md)」を参照してください。
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>サードパーティ製ビデオ会議システムとの相互運用性の向上

ビデオ相互運用機能サーバー (VIS) は、Skype for Business Server と Cisco のビデオ会議 (VTC) システムとの仲介として機能します。 ユーザーはミーティングに参加するときに、Cisco VTC システムを選択できるようになりました。 ビデオ相互運用サーバー (VIS) は、オンプレミス展開でスタンドアロン サーバーの役割として実装されます。 詳細については、「 [Skype For Business server 2015 でのビデオ相互運用機能プランの計画](plan-your-deployment/video-interop-server.md)」を参照してください。
  
### <a name="call-via-work"></a>勤務先から通話

職場での通話機能により、エンタープライズユーザーは Skype for Business クライアントから音声通話を発信できます。 ユーザーが音声通話を発信すると、Skype for Business から発信者の PBX または PSTN 携帯電話に転送されます。 発信者が電話に応答すると、通話は宛先番号に転送されます。 通話の受信者が回答すると、コントロールパネルとして Skype for Business を使用して通話が確立されます。 発信者は、Skype for Business のプレゼンスを管理して、コントロールを呼び出すことができます。 サーバー管理者は、エンタープライズ用に「勤務先から通話」を有効にして構成できます。 詳細については、「 [Skype For Business Server 2015 での通話の計画](plan-your-deployment/enterprise-voice-solution/call-via-work.md)」を参照してください。 
  
## <a name="mobile-device-support-improvements"></a>モバイル デバイスのサポートの改善点

モバイルデバイスサポートの改善には、会話履歴とログデータへのアクセス、モバイル会議エクスペリエンスの強化、Office 間のシングルサインオンサポートなど、Enterprise Edition ユーザー向けのモバイルエクスペリエンスを向上させるための機能が含まれています。 さらに、Android のサポート、パフォーマンスの改善、機能の改善により、共通のアプリフレームワークによる統合が簡単になりました。 
  
> [!NOTE]
> Lync 2013 UCWA サーバーは、モバイルクライアントをサポートするために、Skype for Business Server 2015 にアップグレードする必要があります。 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>モバイル デバイスで利用可能になったサーバー側の会話履歴

会話履歴、不在着信した IM、通話ログデータへのモバイルアクセスを有効にするために、この情報のアーカイブが、すべてのモバイルクライアントでサーバー経由で処理されるようになりました。 IM の自動承諾機能は、モバイル ユーザーが IM にすぐに応答しない場合に、サーバーのタイムアウト メッセージが表示されないようにすることで、信頼性が向上しています。 サーバーベースの Exchange/Outlook フォルダー統合、Exchange Server 2013 以降、および更新されたモバイルクライアントを利用するために必要です。 
  
### <a name="enhanced-meeting-experiences"></a>会議エクスペリエンスの向上

デスクトップで使用可能な会議機能を、モバイル ユーザーも利用できるようになりました。 新機能には次のようなものがあります。
  
- 共有 PowerPoint コンテンツの非同期操作
- 発表者が PowerPoint の共有コンテンツを操作するための機能
- プレゼンターが参加者を受け入れまたは拒否できるようにするロビー管理機能
    
### <a name="skype-for-business-on-android-improvements"></a>Android 版 Skype for Business の機能強化

Android 版 skype for Business では、iOS 版 Skype for Business と Windows 版 Skype for business で利用できる機能と同様の機能が提供されるようになりました。
  
- 会話を続行または再度参加する
- 証明書およびパッシブ認証を有効にする
- 会話に他のユーザーを招待する
- グループ会話を簡単に開始する
- Skype for Business ユーザーにならずに会議に参加する
- Android タブレットでスマートフォンの UI を有効にする
- 参加者を追加または削除して会議を管理する
    
> [!NOTE]
> これらの機能には、Android OS バージョン 4.0 以上が必要です。 
  
## <a name="management-of-on-premises-servers"></a>オンプレミス サーバーの管理

Skype for Business Server 2015 には、インプレースアップグレード、スマートセットアップ、改善された更新プログラムやアップグレードプロセスなど、オンプレミスのサーバーの管理性を向上させるための新機能がいくつか追加されています。強化されたフロントエンドプールのコールドスタート機能、SQL Server AlwaysOnサポートと一元的なログ記録とトラブルシューティング。
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>オンプレミス サーバーのインプレース アップグレード

既存の Lync Server 2013 ハードウェアとサーバーの投資を使用する新しいインプレースアップグレード機能を使用して、Lync Server 2013 システムを Skype for Business Server 2015 にアップグレードできるようになりました。その結果、Skype for Business Server 2015 の展開にかかる全体的なコストが削減されます。
  
インプレース アップグレードには、ユーザーの移動というダウンタイムを必要としない手法と、オフラインというダウンタイムを必要とする手法の 2 つのシナリオがあります。 どちらのアップグレード手順が自分のビジネスに適しているかの詳細については、「[Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md)」を参照してください。 
  
> [!NOTE]
> Lync Server 2010 からアップグレードする場合、インプレースオプションは使用できません。 Lync Server 2010 からのアップグレードの詳細については、「 [Skype For Business Server 2015 へのアップグレードを計画する](plan-your-deployment/upgrade.md)」を参照してください。 
  
### <a name="smart-setup"></a>スマート セットアップ

セットアップ プログラムに、更新プログラムを自動的に検出してダウンロードするスマート セットアップ機能が含まれるようになりました。 インストールプロセス中に、インストールプロセスで更新プログラムを確認するかどうかをユーザーに確認するメッセージが表示されます。 詳細については、「[Install Skype for Business Server 2015](deploy/install/install.md)」を参照してください。
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>フロントエンド サーバーのパッチおよびアップグレード プロセスの向上

Skype for Business Server では、以前のバージョンの Lync Server よりも、フロントエンドサーバーのアップグレードまたは更新に役立つ新しいコマンドレットが2つ導入されています。
  
フロントエンドサーバーに修正プログラムを適用する必要がある場合、またはその他のメンテナンスを実行する場合は、「**呼び出す-CsComputerFailOver** 」と入力してサーバー名を指定するだけです。 Skype for Business Server は、サーバーの作業負荷をプール内の他のサーバーに一時的に移動します。 その後、メンテナンスを実行してから、**Invoke-CsComputerFailback** コマンドレットを使用してサーバーをサービスに戻します。 プール内の各サーバーにパッチを適用する必要がある場合は、サーバーごとにそれぞれ 1 回ずつこの手順を実行するだけです。 これらの新しいコマンドレットにより、以前のバージョンよりも迅速に、より高い信頼性と簡単なワークフローで、サーバーにパッチを適用できます。
  
### <a name="improved-front-end-pool-cold-start-capability"></a>フロントエンド プールのコールド スタート機能の向上

Skype for Business Server には、フロントエンドプール全体のコールドスタートのプロセスを効率化して改善する新しいコマンドレットが導入されています。 新しい **Start-CsPool** コマンドレットを使用すると、プール内のすべてのフロントエンド サーバーの前提条件がチェックされ、その後で各サーバーの起動が試行されます。 何らかの問題が発生した場合は、それらを診断して、詳細および回避策をユーザーに知らせます。 起動できない個別のサーバーがあったとしても、場合によってはユーザーがプールを起動できるようにします。
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>オンプレミス サーバーの SQL Server の AlwaysOn のサポート

Skype for Business Server 2015 は、SQL Server AlwaysOn 可用性グループと SQL Server AlwaysOn フェールオーバークラスターインスタンスの両方のサポートを追加します。 これらの機能に加えて、Skype for Business Server は、以前のバージョンの Lync Server と同じように、データベースのミラーリングと SQL Server クラスタリングのサポートを継続します。
  
SQL Server AlwaysOn 可用性グループは、SQL Server 2012 および SQL Server 2014 の高可用性および障害回復ソリューションであり、データベースミラーリングの代わりに使用できます。 可用性グループは、一緒にフェールオーバーされる個別のデータベース セット (可用性データベースと呼ばれる) のフェールオーバー環境をサポートします。 可用性グループは、1 セットの読み取り/書き込みプライマリ データベースと、1 ～ 4 セットの対応するセカンダリ データベースをサポートします。 オプションで、セカンダリ データベースを読み取り専用アクセスおよび一部のバックアップ操作に使用できます。
  
SQL Server フェールオーバークラスターインスタンスでは、Windows Server フェールオーバークラスタリング (WSFC) 機能を利用し、サーバーインスタンスレベル (フェールオーバークラスターインスタンス) で冗長性を通じてローカルの高可用性を実現します。 FCI は、Windows Server フェールオーバークラスタリング (WSFC) ノードの間にインストールされる SQL Server の1つのインスタンスであり、場合によっては複数のサブネット間でインストールされます。
  
詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>オンプレミス サーバーの集中ログとトラブルシューティングの改善点

一元管理のログサービスは、Skype for Business Server 2015 の優先ログ環境です。 このリリースには新機能はありませんが、サービスと一元ログサービスエージェント (ClsAgent) の両方で信頼性とパフォーマンスが向上しています。コントローラーと通信して、管理者によって発行されます。
  
Skype for Business Server 2015 は、Windows PowerShell コマンドレットを使って、ログサービスエージェントの管理、トレースの開始、レポートの生成を行います。 (Lync Server 2013 では、これらのタスクを実行するために、ClsController が使用されています)。
  
中央集中ログサービスは、任意の Skype for Business Server 2015 で実行できます。 カスタム シナリオを作成できるのと同様に、組み込みシナリオ (定義済みのトレース) は従来のまま変わりません。 常に稼働しており、管理者がほぼリアルタイムで一般的な問題を特定できる、AlwaysOn と呼ばれる特別なシナリオがあります。
  
Snooper デバッグツールも更新され、モビリティログのデバッグが可能になり、Lync 2013 または Skype for Business Server 2015 に接続しているデバイスで動作するようになりました。 このツールは、[デバッグツール](https://go.microsoft.com/fwlink/?LinkId=285257)から Web からダウンロードできます。
  
## <a name="hybrid-deployment-and-management"></a>ハイブリッド展開および管理

Skype for Business Server 2015 を使用すると、次の機能が導入され、ハイブリッド展開の管理と管理機能が有効になります。
  
- お客様のオンプレミスアセットの状態に基づいたハイブリッド展開の推奨事項 (O365 自動アシスタンスツールの OnRamp)。
- Skype for Business Server コントロールパネルと Skype for Business Server 管理センターの拡張機能により、管理者はこれらのツールを使用してハイブリッド展開を管理できるようになります。
- コントロールパネルの拡張機能により、管理者は O365 テナントにサインインし、ハイブリッド構成ウィザードを使用して Skype for Business Online とハイブリッドにセットアップすることができます。
- オンプレミスユーザーを Skype for Business Online に移行するか、Skype for Business Online ユーザーをオンプレミスに戻すためのコントロールパネルのサポート。
- オンプレミスユーザーから Skype for Business Online (ハイブリッドユーザー) に移動されたオンプレミスのユーザーオブジェクトを特定してフィルター処理するためのコントロールパネル機能。
- オンプレミスからオンラインに移行したハイブリッドユーザーから Skype for Business Online で初めて作成されたクラウドユーザーを特定してフィルター処理するための管理センター機能。
- オンプレミスのプロパティについてはコントロールパネルを使ってハイブリッドユーザーを管理し、Skype for Business Online から管理できるプロパティについては管理センターを使用することができます。
- DirSync によるパスワード同期を使用して、オンプレミスの Active Directory パスワードをオンライン テナントと同期する機能。この機能が構成されている場合、フェデレーション認証用に AD FS を展開する必要はありませんが、複数要素の認証には、AD FS が引き続き必要です。 
- Skype for Business Online とオンプレミスの Exchange 間の共存を引き続きサポートします。
    
> [!NOTE]
> Lync Online 2013 および Exchange のオンプレミスの共存とサポートのエクスペリエンスは変更されません。 
  
## <a name="multi-factor-authentication"></a>複数要素の認証

複数要素の認証は、複数の確認方法の使用を義務付けて、ユーザーのサインインおよびトランザクションに対する重要な第 2 のセキュリティ レイヤーを追加する認証方法です。 たとえば、ユーザー名とパスワード、および証明書が必要とされます。 Skype for Business Server 2015 は、Lync Server 2013 累積更新プログラムで利用可能な多要素認証機能に基づいて構築されます。 複数要素の認証の大幅な変更は次のとおりです。
  
- Exchange および SharePoint との統合への Office 2013 SP1 Active Directory 認証ライブラリの使用
- Skype for Business Web App クライアントでの多要素認証機能のサポート
    
Skype for Business の多要素認証を使用すると、地理に基づいてさまざまな認証オプションを提供できるようになりました。 たとえば顧客は、内部認証のベースには統合 Windows 認証を使用するとともに、社外から認証を求める従業員には複数要素の認証を使用するように、環境を構成することができます。 
  
Skype for Business の多要素認証エクスペリエンスは、次のような点でシームレスに動作します。
  
- 地理的な場所-ユーザーが組織の内外からサインインしているかどうか 
- クライアント/デバイスの種類-使用されている Skype for Business クライアントとクライアントが実行されているデバイス (PC、モバイル、iPad など)
- アカウントの場所: ユーザーがオンプレミスの Active Directory でホストされているか、または Azure Active Directory Online (O365) でホストされているか
