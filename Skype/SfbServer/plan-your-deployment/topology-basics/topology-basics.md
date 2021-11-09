---
title: トポロジの基本Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: 使用するトポロジを選択Skype for Business Server。 サーバーのコロケーションについてSkype for Business Server。'
ms.openlocfilehash: 9f28857d6fa8ddbbd77713e113f73314e8f9d3c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856534"
---
# <a name="topology-basics-for-skype-for-business-server"></a>トポロジの基本Skype for Business Server

**概要:** ユーザーのトポロジを選択Skype for Business Server。 サーバーのコロケーションについてSkype for Business Server。

他に何かを準備する前に、ユーザーが適切なトポロジを計画している必要Skype for Business Server。 最初に決定する必要があるのは、Skype for Business Server のオンプレミス展開を行う場合、またはハイブリッド展開でこれを Skype for Business Server Online 展開と組み合わせる場合です。 いずれにしろ、ここではオンプレミス のトポロジについて詳しく説明しますが、ハイブリッドの詳細は独自のセクションに記載されています。

トポロジの例については、「リファレンス トポロジ for [Skype for Business Server」を参照Skype for Business Server。](reference-topologies.md)

## <a name="sites"></a>サイト

このSkype for Business Server、ネットワーク上のサイトを定義し、これらのコンポーネントをSkype for Business Serverします。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 このサイトSkype for Business Server Active Directory ドメイン サービス サイトおよびサイトとは別の概念Microsoft Exchange Server注意してください。 ユーザー Skype for Business Server Active Directory サイトに対応する必要はない。

Skype for Business Serverは、高可用性と場所の要件に応じて拡張できる 1 つ以上のサイトのオンプレミス展開をサポートします。

展開には、少なくとも 1 つの中央サイト (データセンターとも呼ばれるデータセンター)が存在し、展開内の各中央サイトには 1 つの Standard Edition サーバー、または少なくとも 1 つの Enterprise Edition フロントエンド プールがあります。 以下の各オプションの違いを確認できます。

- Standard Editionサーバーには、データベースに関連付SQL Server Expressがあります。

- Enterprise Editionフロントエンド プールには、次の機能が含まれます。

  - 1 つ以上のフロント エンド サーバー (スケーラビリティの場合は 3 つ以上が理想的です)。最大 12 個。 複数のサーバーで負荷分散が必要になります。

  - 別のバック エンド サーバー。

このセクションでは、さまざまなサーバーの役割について少し後で説明します。

中央サイトに加えて、1 つ以上のブランチ サイトが中央サイトに関連付けられる場合もあります。 これらは、ほぼすべての機能について中央サイトに依存しています。したがって、それらは正確に何で構成されていますか?

- 公衆交換電話網 (PSTN) ゲートウェイといくつかの機能を組み合わせた存続可能ブランチ アプライアンスSkype for Business Serverします。

- 存続可能ブランチ サーバー、レジストラーおよび仲介サーバー ソフトウェアがインストールWindowsサーバー Skype for Business Serverサーバーを実行しているサーバーです。

- スタンドアロン PSTN ゲートウェイ (存続可能ブランチ アプライアンスの一部ではありません)。

- スタンドアロン仲介サーバーまたはスタンドアロンの仲介サーバー プール (この役割を存続可能ブランチ アプライアンスに関連付けたくない場合)。

## <a name="whats-in-a-skype-for-business-server-site"></a>サイトのSkype for Business Server?

詳細を確認するには、中央サイトに次の情報を追加できます。

- 同じドメインまたは異なるドメイン内の複数のフロントエンド プール (フロント エンド プール内のすべてのフロント エンド サーバーと、プールのバック エンド サーバーが同じドメイン内にいる必要があるという計画に注意してください)。

- 複数の Standard Edition サーバー。

- OfficeWeb Apps Server( Web Apps Server) は、Officeプレゼンテーションの共有とレンダリングSkype for Business Server Web Apps とPowerPointされます。

- エッジ サーバーまたはエッジ プール (境界ネットワーク内)。 展開でフェデレーション パートナー、パブリック IM 接続、拡張メッセージングおよびプレゼンス プロトコル (XMPP) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。 詳細については、エッジ サーバー計画のドキュメントを参照してください。

- 常設チャット サーバー。 ユーザーが、時間のかかる複数のトピックベースの会話に参加できる場合に便利です。 詳細については、「常設チャット サーバーの計画」を参照してください。

- 監視。 展開内の エンタープライズ VoIP および A/V 会議の音声/ビデオ (A/V) Quality of Experience (QoE) および通話詳細記録 (CDR) のデータ収集をサポートするために使用されます。 詳細については、「監視の計画」トピックで説明します。

- ディレクターまたはディレクター プール。 必須ではなく、復元性を向上し、ユーザーのホーム プールへのユーザー要求Skype for Businessリダイレクトを有効にする場合に便利です。 ディレクターを展開する場合は、プールごとに最大 10 がサポートされます。 これが必要な場合は、必ず「ディレクターの計画」のトピックをご覧ください。

- リバース プロキシ。 これは Skype for Business Server コンポーネントではなく、フェデレーション ユーザー用の Web コンテンツの共有をサポートする場合、Mobility トラフィックをサポートする場合、リモート ユーザーがアドレス帳を使用する場合、会議に参加する場合など、これは環境で必要になります。 準備ができたら、詳細を確認できるリバース プロキシ サーバーの設定に関するトピックがあります。

これらのサーバーのコロケーションに関する追加情報は、以下に示します。

セントラル サイトに展開Standard Editionフロント エンド プールとサーバーは、展開したと仮定して、次の情報を共有します。

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|ディレクターまたはディレクター プール   |スタンドアロン仲介サーバーまたは仲介サーバー プール   |Office Web Apps サーバー   |
|エッジ サーバーまたはエッジ プール   |常設チャット サーバーまたは常設チャット サーバー プール   |監視   |

このリストExchangeユニファイド メッセージング (UM) サーバーの場所 Exchange UM と統合する場合は、Skype for Business Server と一緒に使用できますが、Skype for Business Server サイトのコンポーネントではないので、ここでは説明を行いません。

複数のセントラル サイトを使用する予定の場合、中央サイトに展開されている場合は、次のサーバーと役割を共有できます。

|&nbsp;|&nbsp;|
|:-----|:-----|
|スタンドアロン仲介サーバーまたは仲介サーバー プール   |エッジ サーバーまたはエッジ プール   |
|常設チャット サーバーまたは常設チャット サーバー プール   |監視   |

最後の一覧と同様に、Skype for Business Server 展開の一部ではないので、ここに Exchange UM サーバーは含めず、ここでも同じカテゴリに分類されます。

もちろん、展開には他にもいくつかのコンポーネントとオプションがあります。

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|ファイアウォール   |PSTN ゲートウェイ (PSTN ゲートウェイを展開するエンタープライズ VoIP   |ExchangeUM サーバー (UM と統合する場合Exchange)   |DNS 負荷分散   |
|ハードウェア ロード バランサー   |SQL Server データベース   |ファイル共有   ||

## <a name="server-roles"></a>サーバーの役割

サーバーを実行しているSkype for Business Server 1 つ以上のサーバーの役割を実行します。 サーバー の役割は、そのサーバーによってSkype for Business Server機能の定義済みのセットです。 ネットワークで使用可能なすべてのサーバーの役割を展開する必要はない。 必要な機能が含まれているサーバーの役割のみをインストールします。

多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 サーバー内のほとんどの種類のプールSkype for Business Server、プール内のさまざまなサーバー間でトラフィックを分散するためにロード バランサーを展開する必要があります。 Skype for Business Serverは、ドメイン ネーム システム (DNS) 負荷分散とハードウェア ロード バランサーの両方をサポートします。

### <a name="front-end-server-and-back-end-server"></a>フロントエンド サーバーおよびバック エンド サーバー

このSkype for Business Server Enterprise Editionフロント エンド サーバーは、コア サーバーの役割であり、多くの基本的な機能Skype for Business Serverします。 フロントエンド サーバーは、バック エンド サーバーと共に、すべての展開に必要なSkype for Business Server Enterprise Editionです。

フロントエンド プールは、まったく同じように構成されたフロントエンド サーバーのセットです。これらは連携して共通のユーザー グループにサービスを提供します。同じ役割を実行している複数のサーバーのプールでは、スケーラビリティとフェールオーバー機能を提供します。

フロントエンド サーバーには次の機能があります。

- ユーザー認証と登録。

- プレゼンス情報と連絡先カード交換。

- アドレス帳サービスと配布リストの拡張。

- マルチパーティ IM 会議を含む IM 機能。

- Web 会議、PSTN ダイヤルイン会議、音声ビデオ会議 (展開されている場合)。

- アプリケーション ホスティング (Skype for Business Server および応答グループ アプリケーションなど会議アテンダント、サード パーティ製アプリケーションの両方。

- オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。 この情報は、音声通話と音声ビデオ会議の両方でネットワークを通過するメディア (オーディオとビデオ) の品質に関するエンタープライズ VoIPを提供します。

- Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。

- オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。詳細については、「計画」のドキュメントの「[Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)」を参照してください。

    Lync Server 2010 以前のバージョンでは、監視とアーカイブは、フロント エンド サーバー上ではなく、個別のサーバーの役割でした。

- オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。

フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。

さらに、展開内の 1 つのフロント エンド サーバーがサーバーの全体管理サーバーを実行し、サーバーを実行しているすべてのサーバーに基本的な構成データを管理および展開Skype for Business Server。 また、サーバーの全体管理サーバーには、Lync Server 管理シェルとファイル転送機能も用意されています。

バック エンド サーバーは、フロントエンド Microsoft SQL Serverデータベース サービスを提供するデータベース サーバーです。 バック エンド サーバーは、プールのユーザーおよび会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアです。 単一のバック エンド サーバーを使用できますが、フェールオーバーの場合は、Skype for Business Serverでバック エンド サーバー[の](../high-availability-and-disaster-recovery/back-end-server.md)高可用性を使用できます。 バック エンド サーバーは、ソフトウェアをSkype for Business Serverしません。

> [!IMPORTANT]
> データベースを他のデータベースとSkype for Business Serverすることをお勧めしません。 併置すると、可用性とパフォーマンスに影響することがあります。

> [!NOTE]
> SQLミラーリングは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、2019 年Skype for Business Serverです。

バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。

### <a name="edge-server"></a>エッジ サーバー

エッジ サーバーを使用すると、ユーザーは組織のファイアウォール外のユーザーと通信して共同作業できます。 これらの外部ユーザーには、現在オフサイトで作業している組織の独自のユーザー、フェデレーション パートナー組織のユーザー、および Skype for Business Server 展開でホストされている会議に参加するために招待された外部ユーザーが含まれます。

エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。 ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。

エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。 これらの XMPP コンポーネントを構成して、Skype for Business Serverユーザーがインスタント メッセージングとプレゼンスのために XMPP ベースのパートナーから連絡先を追加できます。

> [!NOTE]
> XMPP ゲートウェイとプロキシは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。

### <a name="mediation-server"></a>仲介サーバー

仲介サーバーは、電話会議、通話エンタープライズ VoIPダイヤルイン会議を実装するために必要なコンポーネントです。 仲介サーバーは、内部 Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランクとの間のシグナリング、および一部の構成ではメディアを変換します。 フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。

詳細については、「仲介[サーバー コンポーネント」を参照Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)

### <a name="video-interop-server"></a>ビデオ相互運用サーバー

ビデオ相互運用サーバーは、2015 年のSkype for Business Serverです。 これにより、特定のサードパーティの VTC (ビデオ電話会議システム) ソリューションSkype for Business Server展開を統合できます。 VIS は、サードパーティの電話会議システムと展開の間の仲介Skype for Business Serverします。 このリリースでは、VIS は、Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。

詳細については[、「Plan for Video Interop Server in](../../plan-your-deployment/video-interop-server.md)Skype for Business Server」 を参照してください。

### <a name="director"></a>ディレクター

ディレクターはユーザー要求Skype for Business Server認証できますが、ユーザー アカウントをホームしたり、プレゼンスサービスや会議サービスを提供したりすることはできません。 ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。 内部サーバーに要求を送信する前にディレクターで認証を実行できます。 サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。

### <a name="persistent-chat-server-roles"></a>常設チャット サーバーの役割

> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。

常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。

また、Skype for Business Server Standard Editionサーバーは、同じサーバー上で常設チャットを同時に実行することもできます。 常設チャット フロント エンド サーバーとフロントエンド サーバーをEnterprise Editionすることはできません。

詳細については[、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)してください。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性と障害復旧のサポート

Skype for Business Serverを介してサーバーの冗長性によって高可用性を提供します。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。

Skype for Business Server、プールのペアリングを有効にすることで障害復旧対策も提供します。 このトポロジを展開する場合は、フロント エンド プールのペアを指定します。各プールは、1 つのペア内の個別のデータ センター内にあり、別の地理的領域に配置されます。 1 つのプールまたはサイトがダウンした場合は、そのプールのユーザーをリダイレクトして、サービスの中断を最小限に抑え、ペアの他のプールを使用できます。

Skype for Business Serverは、バック エンド サーバーの高可用性に関する複数のオプションもサポートしています。 これらには次のコマンドレットがあります。

- データベース ミラーリング

- AlwaysOn 可用性グループ

- AlwaysOn フェールオーバー クラスター インスタンス (FCI)

- SQLフェールオーバー クラスタリング

プールのペアリングとバック エンド サーバーの高可用性の詳細については、「Plan for high availability and disaster recovery in Skype for Business Server」[を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>サーバーのコロケーション (Skype for Business Server

既に collocate という用語を使用していますが、これはどういう意味ですか? Skype for Business Server を使用すると、同じサーバー上の一部のサーバーの役割と機能 (コロケーション、または異なるサーバー) を検索できますが、開始するときに、Standard Edition または Enterprise Edition サーバーの展開を行っているかどうか (それぞれ独自のルールが適用されます) と混乱する可能性があります。 計画を立て支援するために、Standard Edition サーバー展開と Enterprise Edition フロントエンド プール展開にサーバーのコロケーションを含めます (ほとんどの場合、この情報は同一であり、異なる場合は、具体的に呼び出されます)。

### <a name="collocation-of-server-roles"></a>サーバーの役割のコロケーション

Standard Edition サーバーには、次の役割 (追加の構成が必要ですが) が含まれますが、Enterprise Edition フロント エンド プールでは、この役割をコロケーションするか、別のサーバーに展開できます。

- 仲介

これらのサーバーの役割は、それぞれ別のサーバーに展開する必要があります。

- ディレクター

- Edge

- ビデオ相互運用サーバー

- Office Web Apps

### <a name="databases"></a>Databases

これは、Standard Edition サーバー展開と Enterprise Edition サーバー プール展開の間で実際に異なる領域なので、以下に 2 つのセクションを示し、その後に両方の追加ルールを追加します。

#### <a name="standard"></a>Standard

このSQL Server Expressサーバー上にStandard Edition移動できないので、これは非常に簡単です。 さらに、Standard Edition サーバーに常設チャット サーバーを展開する場合は、Standard Edition サーバー上の常設チャットと常設チャット コンプライアンス データベースを併合することもできますが、その必要は必要ではありません。

> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。

これらは、サーバー上にStandard Editionできませんが、独自の 1 つのデータベース サーバー上に移動できます。

- 監視データベース

- アーカイブ データベース

- フロントエンド プール用のEnterprise Editionデータベース

#### <a name="enterprise"></a>Enterprise

次のデータベースは、同じバック エンド サーバーにSQL Server。

- バック エンド データベース

- 監視データベース

- アーカイブ データベース

- 常設チャット データベース

- 常設チャット コンプライアンス データベース

#### <a name="both"></a>Both/フォーム/データシート

1 つの SQL インスタンス内の Skype for Business Server データベースを照合する場合、または同じ SQL データベース内の複数の SQL インスタンスで照合する場合は、次に示す追加SQL Serverがあります。

- 各 SQL インスタンスには、Enterprise Edition フロントエンド プール用の 1 つのバック エンド データベース、1 つの監視データベース、1 つのアーカイブ データベース、1 つの常設チャット データベース、および単一の常設チャット コンプライアンス データベースのみを含めできます。

- データベース サーバーは、複数の Enterprise Edition フロントエンド プール、アーカイブを実行している 1 つのサーバー、監視を実行する 1 つのサーバー、1 つの常設チャット データベース、および 1 つの常設チャット コンプライアンス データベースをサポートすることはできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server のインスタンスを個別に使用するかにかかわらず、それぞれ 1 つをサポートできます。

    > [!NOTE]
    > 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。

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

- リバース プロキシ サーバーを照合できません。これは、Skype for Business Serverコンポーネントではなく、トポロジ内に含めなくても良い場合があります。 フェデレーション ユーザー向け Web コンテンツの共有をサポートする場合は、リバース プロキシが必要です。 必要な場合は、他のアプリケーションで使用されている既存のリバース プロキシ サーバーを構成して、Skype for Business Server のリバース プロキシ サポートを実装します。

- UM コンポーネントまたはサーバー コンポーネントExchange、SharePoint役割をSkype for Business Serverできません。

## <a name="see-also"></a>関連項目

[データの参照トポロジSkype for Business Server](reference-topologies.md)