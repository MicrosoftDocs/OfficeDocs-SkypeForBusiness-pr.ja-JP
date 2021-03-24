---
title: Skype for Business Server のトポロジの基本
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバーのコロケーションについて学習します。'
ms.openlocfilehash: 39a75de6162f51d5d838ace557a546db3500ac01
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103993"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Skype for Business Server のトポロジの基本

**概要:** Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバーのコロケーションについて学習します。

他に何かを準備する前に、Skype for Business Server の展開に適切なトポロジを計画している必要があります。 最初に決定する必要があるのは、Skype for Business Server のオンプレミス展開を行う場合か、ハイブリッド展開で Skype for Business Server Online 展開と組み合わせる場合です。 いずれにしろ、ここではオンプレミス のトポロジについて詳しく説明しますが、ハイブリッドの詳細は独自のセクションに記載されています。

トポロジの例については [、「Skype for Business Server のリファレンス トポロジ」でも確認できます](reference-topologies.md)。

## <a name="sites"></a>サイト

Skype for Business Server では、Skype for Business Server コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 Skype for Business Server サイトは、Active Directory ドメイン サービス サイトおよびサイトと別の概念Microsoft Exchange Server注意してください。 Skype for Business Server サイトは、Active Directory サイトに対応する必要はない。

Skype for Business Server は、高可用性と場所の要件に応じて拡張できる 1 つ以上のサイトのオンプレミス展開をサポートします。

展開には、少なくとも 1 つの中央サイト (データセンターとも呼ばれるデータセンター)が存在し、展開内の各中央サイトには Standard Edition サーバーが 1 つ、または少なくとも 1 つの Enterprise Edition フロント エンド プールがあります。 以下の各オプションの違いを確認できます。

- Standard Edition サーバーには、Express データベースにSQL Serverが含まれています。

- Enterprise Edition フロントエンド プールには、次の内容が含まれます。

  - 1 つ以上のフロント エンド サーバー (スケーラビリティの場合は 3 つ以上が理想的です)。最大 12 個。 複数のサーバーで負荷分散が必要になります。

  - 別のバック エンド サーバー。

このセクションでは、さまざまなサーバーの役割について少し後で説明します。

中央サイトに加えて、1 つ以上のブランチ サイトが中央サイトに関連付けられる場合もあります。 これらは、ほぼすべての機能について中央サイトに依存しています。したがって、それらは正確に何で構成されていますか?

- 一部の Skype for Business Server 機能と公衆交換電話網 (PSTN) ゲートウェイを組み合わせた存続可能ブランチ アプライアンス。

- 存続可能ブランチ サーバー、Skype for Business Server レジストラーと仲介サーバー ソフトウェアがインストールされている Windows Server を実行しているサーバーです。

- スタンドアロン PSTN ゲートウェイ (存続可能ブランチ アプライアンスの一部ではありません)。

- スタンドアロン仲介サーバーまたはスタンドアロンの仲介サーバー プール (この役割を存続可能ブランチ アプライアンスに関連付けたくない場合)。

## <a name="whats-in-a-skype-for-business-server-site"></a>Skype for Business Server サイトの内容

詳細を確認するには、中央サイトに次の情報を追加できます。

- 同じドメインまたは異なるドメイン内の複数のフロントエンド プール (フロント エンド プール内のすべてのフロント エンド サーバーと、プールのバック エンド サーバーが同じドメイン内にいる必要があるという計画に注意してください)。

- 複数の Standard Edition サーバー。

- Office Web Apps サーバーは、PowerPoint プレゼンテーションの共有とレンダリングOffice Skype for Business Server の Web アプリと一緒に使用されます。

- エッジ サーバーまたはエッジ プール (境界ネットワーク内)。 展開でフェデレーション パートナー、パブリック IM 接続、拡張メッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。 詳細については、エッジ サーバー計画のドキュメントを参照してください。

- 常設チャット サーバー。 ユーザーが、時間のかかる複数のトピックベースの会話に参加できる場合に便利です。 詳細については、「常設チャット サーバーの計画」を参照してください。

- 監視。 展開内の エンタープライズ VoIP 会議および音声ビデオ会議の音声/ビデオ (A/V) Quality of Experience (QoE) および通話詳細記録 (CDR) のデータ収集をサポートするために使用されます。 詳細については、「監視の計画」トピックで説明します。

- ディレクターまたはディレクター プール。 必要ありませんが、復元性を向上し、ユーザーのホーム プールへの Skype for Business ユーザー要求のリダイレクトを有効にする場合に便利です。 ディレクターを展開する場合は、プールごとに最大 10 がサポートされます。 これが必要な場合は、必ず「ディレクターの計画」のトピックをご覧ください。

- リバース プロキシ。 これは Skype for Business Server コンポーネントではなく、フェデレーション ユーザー用の Web コンテンツの共有をサポートする場合、Mobility トラフィックをサポートする場合、リモート ユーザーがアドレス帳を使用する場合、会議に参加する場合など、これは環境で必要になります。 準備ができたら、詳細を確認できるリバース プロキシ サーバーの設定に関するトピックがあります。

これらのサーバーのコロケーションに関する追加情報は、以下に示します。

中央サイトに展開されているフロントエンド プールと Standard Edition サーバーはすべて、展開したと仮定して、次の情報を共有します。

||||
|:-----|:-----|:-----|
|ディレクターまたはディレクター プール  <br/> |スタンドアロン仲介サーバーまたは仲介サーバー プール  <br/> |Office Web Apps サーバー  <br/> |
|エッジ サーバーまたはエッジ プール  <br/> |常設チャット サーバーまたは常設チャット サーバー プール  <br/> |監視  <br/> |

この一覧の Exchange ユニファイド メッセージング (UM) サーバーの場所 Exchange UM と統合する場合は、Skype for Business Server で使用できますが、Skype for Business Server サイトのコンポーネントではないので、ここでは説明しません。

複数のセントラル サイトを使用する予定の場合、中央サイトに展開されている場合は、次のサーバーと役割を共有できます。

|||
|:-----|:-----|
|スタンドアロン仲介サーバーまたは仲介サーバー プール  <br/> |エッジ サーバーまたはエッジ プール  <br/> |
|常設チャット サーバーまたは常設チャット サーバー プール  <br/> |監視  <br/> |

最後のリストと同様に、Exchange UM Server は Skype for Business Server 展開の一部ではないのでここには含めず、ここでも同じカテゴリに分類されます。

もちろん、展開には他にもいくつかのコンポーネントとオプションがあります。

|||||
|:-----|:-----|:-----|:-----|
|ファイアウォール  <br/> |PSTN ゲートウェイ (PSTN ゲートウェイを展開するエンタープライズ VoIP  <br/> |Exchange UM Server (Exchange UM と統合する場合)  <br/> |DNS 負荷分散  <br/> |
|ハードウェア ロード バランサー  <br/> |SQL Server データベース  <br/> |ファイル共有  <br/> ||

## <a name="server-roles"></a>サーバーの役割

Skype for Business Server を実行している各サーバーは、1 つ以上のサーバーの役割を実行します。 サーバーの役割は、そのサーバーによって提供される Skype for Business Server の機能の定義済みのセットです。 ネットワークで使用可能なすべてのサーバーの役割を展開する必要はない。 必要な機能が含まれているサーバーの役割のみをインストールします。

多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 Skype for Business Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間でトラフィックを分散するためにロード バランサーを展開する必要があります。 Skype for Business Server は、ドメイン ネーム システム (DNS) 負荷分散とハードウェア ロード バランサーの両方をサポートします。

### <a name="front-end-server-and-back-end-server"></a>フロントエンド サーバーおよびバック エンド サーバー

Skype for Business Server Enterprise Edition では、フロント エンド サーバーがコア サーバーの役割であり、多くの基本的な Skype for Business Server 機能を実行します。 フロントエンド サーバーは、バック エンド サーバーと共に、Skype for Business Server Enterprise Edition 展開に必要な唯一のサーバーの役割です。

フロントエンド プールは、同じ構成のフロント エンド サーバーのセットで、共通のユーザー グループにサービスを提供するために一緒に動作します。 同じ役割を実行している複数のサーバーのプールは、スケーラビリティとフェールオーバー機能を提供します。

フロントエンド サーバーには次の機能があります。

- ユーザー認証と登録。

- プレゼンス情報と連絡先カード交換。

- アドレス帳サービスと配布リストの拡張。

- マルチパーティ IM 会議を含む IM 機能。

- Web 会議、PSTN ダイヤルイン会議、音声ビデオ会議 (展開されている場合)。

- Skype for Business Server に含まれる両方のアプリケーション (会議アテンダント アプリケーションと応答グループ アプリケーションなど) のアプリケーションホスティング、およびサードパーティ製アプリケーション。

- オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。 この情報は、音声通話と音声ビデオ会議の両方でネットワークを通過するメディア (オーディオとビデオ) の品質に関するエンタープライズ VoIPを提供します。

- Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。

- オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。 詳細については、「計画」のドキュメントの「[Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)」を参照してください。

    Lync Server 2010 以前のバージョンでは、監視とアーカイブは、フロント エンド サーバー上ではなく、個別のサーバーの役割でした。

- オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。

フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。

さらに、展開内の 1 つのフロント エンド サーバーでは、サーバーの全体管理サーバーも実行され、Skype for Business Server を実行しているすべてのサーバーに基本的な構成データを管理および展開します。 また、サーバーの全体管理サーバーには、Lync Server 管理シェルとファイル転送機能も用意されています。

バック エンド サーバーは、フロントエンド Microsoft SQL Serverデータベース サービスを提供するデータベース サーバーです。 バック エンド サーバーは、プールのユーザーおよび会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアです。 単一のバック エンド サーバーを使用できますが、フェールオーバーには [Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) のバック エンド サーバーの高可用性をお勧めします。 バック エンド サーバーは、Skype for Business Server ソフトウェアを実行しません。

> [!IMPORTANT]
> Skype for Business Server データベースを他のデータベースと照合はお勧めしません。 併置すると、可用性とパフォーマンスに影響することがあります。

> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、Skype for Business Server 2019 で優先されます。

バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。

### <a name="edge-server"></a>エッジ サーバー

エッジ サーバーを使用すると、ユーザーは組織のファイアウォール外のユーザーと通信して共同作業できます。 これらの外部ユーザーには、現在オフサイトで作業している組織の独自のユーザー、フェデレーション パートナー組織のユーザー、Skype for Business Server 展開でホストされている会議に参加するために招待された外部ユーザーが含まれます。

エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。 ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。

エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。 これらの XMPP コンポーネントを構成して、Skype for Business Server ユーザーがインスタント メッセージングとプレゼンスのために XMPP ベースのパートナーから連絡先を追加できます。

> [!NOTE]
> XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。

### <a name="mediation-server"></a>仲介サーバー

仲介サーバーは、電話会議、通話エンタープライズ VoIPダイヤルイン会議を実装するために必要なコンポーネントです。 仲介サーバーは、内部の Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランクとの間で、シグナリングを変換し、一部の構成ではメディアを変換します。 フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。

詳細については [、「Skype for Business Server の仲介サーバー コンポーネント」を参照してください](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>ビデオ相互運用サーバー

ビデオ相互運用サーバーは、Skype for Business Server 2015 の新しい役割です。 これにより、Skype for Business Server 展開を特定のサードパーティ VTC (ビデオ 電話会議システム) ソリューションと統合できます。 VIS は、サードパーティの電話会議システムと Skype for Business Server 展開の間の仲介者として機能します。 このリリースでは、VIS は、Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。

詳細については [、「Plan for Video Interop Server in Skype for Business Server」を参照してください](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>ディレクター

ディレクターは Skype for Business Server ユーザー要求を認証できますが、ユーザー アカウントを使用したり、プレゼンスサービスや会議サービスを提供したりすることはできません。 ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。 内部サーバーに要求を送信する前にディレクターで認証を実行できます。 サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。

### <a name="persistent-chat-server-roles"></a>常設チャット サーバーの役割

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。

Skype for Business Server Standard Edition を実行しているサーバーは、同じサーバー上で常設チャットを実行することもできます。 常設チャット フロント エンド サーバーを Enterprise Edition フロント エンド サーバーと照合することはできません。

詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照してください](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性と障害復旧のサポート

Skype for Business Server は、プールを介してサーバーの冗長性によって高可用性を提供します。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。

Skype for Business Server は、プールのペアリングを有効にすることで障害復旧対策も提供します。 このトポロジを展開する場合は、フロント エンド プールのペアを指定します。各プールは、1 つのペア内の個別のデータ センター内にあり、別の地理的領域に配置されます。 1 つのプールまたはサイトがダウンした場合は、そのプールのユーザーをリダイレクトして、サービスの中断を最小限に抑え、ペアの他のプールを使用できます。

Skype for Business Server では、バック エンド サーバーの高可用性に関する複数のオプションもサポートされています。 これらには次のコマンドレットがあります。

- データベース ミラーリング

- AlwaysOn 可用性グループ

- AlwaysOn フェールオーバー クラスター インスタンス (FCI)

- SQLフェールオーバー クラスタリング

プールのペアリングとバック エンド サーバーの高可用性の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する [」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>Skype for Business Server でのサーバーのコロケーション

既に collocate という用語を使用していますが、これはどういう意味ですか? Skype for Business Server を使用すると、同じサーバー上の一部のサーバーの役割と機能 (コロケーション、または異なるサーバー) を検索できますが、開始する際、および Standard Edition または Enterprise Edition サーバーの展開を行っているかどうか (それぞれに独自のルールが含まれています) 場合、混乱する可能性があります。 計画を立て支援するために、Standard Edition サーバー展開と Enterprise Edition フロントエンド プール展開にサーバーコロケーションを含めます (ほとんどの場合、この情報は同一であり、異なる場合は特に呼び出されます)。

### <a name="collocation-of-server-roles"></a>サーバーの役割のコロケーション

Standard Edition サーバーには次の役割があります (追加の構成が必要ですが、追加の構成が必要です)、Enterprise Edition フロント エンド プールでは、この役割をコロケーションするか、別のサーバーに展開できます。

- 仲介

これらのサーバーの役割は、それぞれ別のサーバーに展開する必要があります。

- ディレクター

- Edge

- ビデオ相互運用サーバー

- Office Web Apps

### <a name="databases"></a>Databases

これは、Standard Edition サーバーの展開と Enterprise Edition サーバー プールの展開の間に大きな違いがある領域なので、以下に 2 つのセクションを示し、その後に両方の追加ルールを追加します。

#### <a name="standard"></a>標準

Express SQL Serverは Standard Edition サーバー上にコロケーションされ、移動できないので、これは非常に簡単です。 さらに、Standard Edition サーバーに常設チャット サーバーを展開する場合は、Standard Edition サーバー上の常設チャットと常設チャット コンプライアンス データベースを併合することもできますが、必要な必要は一つではありません。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

これらは Standard Edition サーバー上に同一に設定できませんが、独自の 1 つのデータベース サーバー上に移動できます。

- 監視データベース

- アーカイブ データベース

- Enterprise Edition フロントエンド プールの任意のバック エンド データベース

#### <a name="enterprise"></a>大企業

次のデータベースは、同じバック エンド サーバーにSQL Server。

- バック エンド データベース

- 監視データベース

- アーカイブ データベース

- 常設チャット データベース

- 常設チャット コンプライアンス データベース

#### <a name="both"></a>Both/フォーム/データシート

1 つの SQL インスタンスで Skype for Business Server データベースを照合する場合、または同じ SQL Server データベース内の複数の SQL インスタンスで照合する場合に従う追加のSQL Serverがあります。

- 各 SQL インスタンスには、Enterprise Edition フロントエンド プール用の 1 つのバック エンド データベース、1 つの監視データベース、1 つのアーカイブ データベース、1 つの常設チャット データベース、および単一の常設チャット コンプライアンス データベースのみを含めできます。

- データベース サーバーは、複数の Enterprise Edition フロントエンド プール、アーカイブを実行する 1 つのサーバー、監視を実行する 1 つのサーバー、1 つの常設チャット データベース、および 1 つの常設チャット コンプライアンス データベースをサポートすることはできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server のインスタンスを個別に使用するかに関係なく、それぞれ 1 つをサポートできます。

    > [!NOTE]
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレードの [開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

### <a name="file-shares"></a>ファイル共有

ファイル共有は、別のサーバー上に含め、または次のサーバーの一部またはすべてと同じサーバー上に共有できます。

- データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)

- 監視データベース

- アーカイブ データベース

- 常設チャット データベース

- 常設チャット コンプライアンス データベース

> [!CAUTION]
> これらのサーバーでファイル共有を共有することもできますが、お勧めしない点に注意してください。 ファイル共有を他のサーバーの役割と照合する場合は、ディスク領域とパフォーマンスの問題を定期的に監視してください。

### <a name="keep-in-mind"></a>注意点

- Skype for Business Server コンポーネントではなく、トポロジに含めなくても、リバース プロキシ サーバーを照合できません。 フェデレーション ユーザー向け Web コンテンツの共有をサポートする場合は、リバース プロキシが必要です。 必要な場合は、他のアプリケーションで使用されている既存のリバース プロキシ サーバーを組織に構成して、Skype for Business Server のリバース プロキシ サポートを実装します。

- Exchange UM コンポーネントまたは SharePoint Server コンポーネントを Skype for Business Server の役割と照合できません。

## <a name="see-also"></a>関連項目

[Skype for Business Server のリファレンス トポロジ](reference-topologies.md)