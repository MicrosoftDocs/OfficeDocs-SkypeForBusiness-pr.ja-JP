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
description: '概要: Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバーの一覧について学習します。'
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831757"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Skype for Business Server のトポロジの基本

**概要:** Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバーの一覧について確認します。

他に何かを準備する前に、Skype for Business Server の展開に適切なトポロジを計画している必要があります。 最初に決定する必要があるのは、Skype for Business Server のオンプレミス展開を行うのか、それともハイブリッド展開の Skype for Business Server Online 展開と組み合わせるかです。 どちらの場合も、ここではオンプレミス のトポロジについて詳しく説明しますが、ハイブリッドの詳細については独自のセクションに記載されています。

また、「Skype for Business Server の関連トポロジ」で [トポロジの例を確認することもできます](reference-topologies.md)。

## <a name="sites"></a>サイト

Skype for Business Server では、Skype for Business Server コンポーネントを含むネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 Skype for Business Server サイトは、Active Directory ドメイン サービス サイトおよびサイト間の別個の概念Microsoft Exchange Server注意してください。 Skype for Business Server サイトが Active Directory サイトに対応している必要はない。

Skype for Business Server は、高可用性と場所の要件に従って拡張できる 1 つ以上のサイトのオンプレミス展開をサポートします。

展開には少なくとも 1 つの中央サイト (データセンターとも呼ばれる、データセンターに配置されているすべてのサーバーのデータセンター) が存在し、展開内の各中央サイトには 1 つの Standard Edition サーバーまたは少なくとも 1 つの Enterprise Edition フロントエンド プールがあります。 次の各オプションの違いを確認できます。

- Standard Edition サーバーには、Express データベースにSQL Serverが含まれています。

- Enterprise Edition フロントエンド プールには次が含まれます。

  - 1 つ以上のフロントエンド サーバー (スケーラビリティの場合は少なくとも 3 つが理想的)、最大 12 サーバー。 複数のサーバーで負荷分散が必要になります。

  - 独立したバック エンド サーバー。

さまざまなサーバーの役割の詳細については、このセクションで少し後で説明します。

中央サイトに加えて、1 つ以上のブランチ サイトが中央サイトに関連付けられる場合もあります。 ほとんどの機能はセントラル サイトに依存しますが、何が構成されていますか。

- 公衆交換電話網 (PSTN) ゲートウェイと Skype for Business Server の一部の機能を組み合わせた存続可能ブランチ アプライアンス。

- 存続可能ブランチ サーバーは、Skype for Business Server レジストラーおよび仲介サーバー ソフトウェアがインストールされている Windows Server を実行しているサーバーです。

- スタンドアロン PSTN ゲートウェイ (存続可能ブランチ アプライアンスの一部ではない)。

- スタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバー プール (この役割を存続可能ブランチ アプライアンスと共に使用しない場合)。

## <a name="whats-in-a-skype-for-business-server-site"></a>Skype for Business Server サイトの内容

詳細を確認するために、セントラル サイトには次の設定も含めできます。

- 同じドメインまたは異なるドメイン内の複数のフロントエンド プール (フロント エンド プール内のすべてのフロントエンド サーバーとプールのバック エンド サーバーは同じドメイン内にある必要があるという計画に注意してください)。

- 複数の Standard Edition サーバー。

- Office Web Apps サーバー。PowerPoint プレゼンテーションの共有Officeレンダリングのために Skype for Business Server の web Apps と組み合Office使用されます。

- エッジ サーバーまたはエッジ プール (境界ネットワーク内)。 展開でフェデレーション パートナー、パブリック IM 接続、XMPP (Extensible Messaging and Presence Protocol) ゲートウェイ、リモート ユーザー アクセスをサポートする場合に必要です。 詳細については、「エッジ サーバーの計画」のドキュメントを参照してください。

- 常設チャット サーバー。 ユーザーが、時間のかかるマルチパーティのトピックベースの会話に参加できる場合に便利です。 詳細については、「Planning for Persistent Chat Server」トピックを参照してください。

- 監視。 展開内の エンタープライズ VoIP および音声ビデオ会議の音声ビデオ (A/V) Quality of Experience (QoE) および通話詳細記録 (CDR) のデータ収集をサポートするために使用されます。 詳細については、「監視の計画」トピックで説明します。

- ディレクターまたはディレクター プール。 必須ではないが、復元性を向上し、ユーザーのホーム プールへの Skype for Business ユーザー要求のリダイレクトを有効にする場合に役立ちます。 ディレクターを展開する場合は、プールごとに最大 10 人までサポートされます。 これが必要な場合は、「ディレクターの計画」トピックを参照してください。

- リバース プロキシ。 これは Skype for Business Server コンポーネントではなく、フェデレーション ユーザーの Web コンテンツの共有をサポートする場合は、モビリティ トラフィックをサポートする場合、リモート ユーザーがアドレス帳を使用する場合、会議に参加する場合など、環境内で必要になります。 準備ができたら、リバース プロキシ サーバーの設定に関するトピックで詳細を確認できます。

これらのサーバーのコロケーションに関する追加情報は、以下を参照してください。

中央サイトに展開されているフロント エンド プールと Standard Edition サーバーはすべて、展開されている場合は以下を共有します。

||||
|:-----|:-----|:-----|
|ディレクターまたはディレクター プール  <br/> |スタンドアロンの仲介サーバーまたは仲介サーバー プール  <br/> |Office Web Apps サーバー  <br/> |
|エッジ サーバーまたはエッジ プール  <br/> |常設チャット サーバーまたは常設チャット サーバー プール  <br/> |監視  <br/> |

この一覧内の Exchange ユニファイド メッセージング (UM) サーバーの場所 Exchange UM と統合する場合は、Skype for Business Server と一緒に使用できますが、Skype for Business Server サイトのコンポーネントではないので、ここでは説明しません。

複数のセントラル サイトを計画している場合は、セントラル サイトに展開されている次のサーバーと役割を共有できます。

|||
|:-----|:-----|
|スタンドアロンの仲介サーバーまたは仲介サーバー プール  <br/> |エッジ サーバーまたはエッジ プール  <br/> |
|常設チャット サーバーまたは常設チャット サーバー プール  <br/> |監視  <br/> |

最後のリストと同様に、ここに Exchange UM Server は含めず、これは Skype for Business Server 展開の一部ではないので、ここでは同じカテゴリに分類されます。

もちろん、展開には他にもいくつかのコンポーネントとオプションがあります。

|||||
|:-----|:-----|:-----|:-----|
|ファイアウォール  <br/> |PSTN ゲートウェイ (展開する場合エンタープライズ VoIP  <br/> |Exchange UM Server (Exchange UM と統合する場合)  <br/> |DNS 負荷分散  <br/> |
|ハードウェア ロード バランサー  <br/> |SQL Server データベース  <br/> |ファイル共有  <br/> ||

## <a name="server-roles"></a>サーバーの役割

Skype for Business Server を実行している各サーバーは、1 つ以上のサーバーの役割を実行します。 サーバーの役割は、そのサーバーによって提供される Skype for Business Server の機能の定義済みのセットです。 ネットワーク内で使用可能なすべてのサーバーの役割を展開する必要があるという必要はない。 必要な機能が含まれているサーバーの役割のみをインストールします。

多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 Skype for Business Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間でトラフィックを分散するためにロード バランサーを展開する必要があります。 Skype for Business Server は、ドメイン ネーム システム (DNS) 負荷分散とハードウェア ロード バランサーの両方をサポートしています。

### <a name="front-end-server-and-back-end-server"></a>フロントエンド サーバーおよびバック エンド サーバー

Skype for Business Server Enterprise Edition では、フロントエンド サーバーがコア サーバーの役割であり、多くの基本的な Skype for Business Server 機能を実行します。 フロントエンド サーバーとバック エンド サーバーは、Skype for Business Server Enterprise Edition の展開に必要な唯一のサーバーの役割です。

フロントエンド プールは、同じ構成のフロントエンド サーバーのセットで、共通のユーザー グループにサービスを提供するために一緒に動作します。 同じ役割を実行している複数のサーバーのプールは、スケーラビリティとフェールオーバー機能を提供します。

フロントエンド サーバーには次の機能があります。

- ユーザー認証と登録。

- プレゼンス情報と連絡先カードの交換。

- アドレス帳サービスと配布リストの展開。

- マルチパーティ IM 会議を含む IM 機能。

- Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。

- Skype for Business Server に含まれるアプリケーション (会議アテンダント、応答グループ アプリケーションなど) とサードパーティ アプリケーションの両方のアプリケーション ホスティング。

- オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。 この情報は、通話と音声ビデオ会議の両方でネットワークを通過するメディア (音声およびビデオ) の品質に関エンタープライズ VoIP指標を提供します。

- Web スケジューラーや Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。

- オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。 詳細については、「計画」のドキュメントの「[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)」を参照してください。

    Lync Server 2010 およびそれ以前のバージョンでは、監視とアーカイブは別々のサーバーの役割であり、フロントエンド サーバーに展開されません。

- オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。

フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。

さらに、展開内の 1 つのフロントエンド サーバーは、Skype for Business Server を実行しているすべてのサーバーに基本的な構成データを管理および展開する中央管理サーバーも実行します。 中央管理サーバーは、Lync Server 管理シェルとファイル転送機能も提供します。

バック エンド サーバーは、フロントエンド プールMicrosoft SQL Serverサービスを提供する、サーバーを実行しているデータベース サーバーです。 バック エンド サーバーは、プールのユーザー および会議データのバックアップ ストアとして機能し、応答グループ データベースなどの他のデータベースのプライマリ ストアです。 単一のバック エンド サーバーを使用できますが、フェールオーバーには [Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) のバック エンド サーバーの高可用性をお勧めします。 バック エンド サーバーは、Skype for Business Server ソフトウェアを実行しません。

> [!IMPORTANT]
> Skype for Business Server データベースを他のデータベースと共に使用はお勧めしません。 併置すると、可用性とパフォーマンスに影響することがあります。

> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が推奨されます。

バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。

### <a name="edge-server"></a>エッジ サーバー

エッジ サーバーを使用すると、ユーザーは組織のファイアウォールの外側のユーザーと通信し、共同作業を行える。 これらの外部ユーザーには、現在オフサイトで作業している組織自身のユーザー、フェデレーション パートナー組織のユーザー、および Skype for Business Server 展開でホストされている会議に参加するために招待された外部ユーザーを含めできます。

エッジ サーバーを展開すると、モバイル デバイスで Lync 機能をサポートするモビリティ サービスも有効になります。 ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。

エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。 これらの XMPP コンポーネントを構成して、Skype for Business Server ユーザーがインスタント メッセージングとプレゼンス用に XMPP ベースのパートナーから連絡先を追加できます。

> [!NOTE]
> XMPP ゲートウェイとプロキシは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細 [については、「XMPP フェデレーションの移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 」を参照してください。

### <a name="mediation-server"></a>仲介サーバー

仲介サーバーは、通話、通話エンタープライズ VoIPダイヤルイン会議を実装するために必要なコンポーネントです。 仲介サーバーは、内部の Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはセッション開始プロトコル (SIP) トランクとの間で信号を変換し、一部の構成ではメディアを変換します。 フロントエンド サーバーと同じサーバーに配置されている、またはスタンドアロンの仲介サーバー プールに分離されている仲介サーバーを実行できます。

詳細については [、Skype for Business Server の仲介サーバー コンポーネントを参照してください](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。

### <a name="video-interop-server"></a>ビデオ相互運用サーバー

ビデオ相互運用サーバーは、Skype for Business Server 2015 の新しい役割です。 これにより、Skype for Business Server の展開を特定のサード パーティ VTC (ビデオ会議システム) ソリューションと統合できます。 VIS は、サードパーティの電話会議システムと Skype for Business Server 展開の仲介者として機能します。 このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。

詳細については [、「Plan for Video Interop Server in Skype for Business Server」を参照してください](../../plan-your-deployment/video-interop-server.md)。

### <a name="director"></a>ディレクター

ディレクターは Skype for Business Server のユーザー要求を認証できますが、ユーザー アカウントをホームにしたり、プレゼンスサービスや会議サービスを提供したりすることはできません。 ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。 内部サーバーに要求を送信する前にディレクターで認証を実行できます。 サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。

### <a name="persistent-chat-server-roles"></a>常設チャット サーバーの役割

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。

Skype for Business Server Standard Edition を実行しているサーバーは、同じサーバー上に位置する常設チャットを実行することもできます。 常設チャット フロントエンド サーバーを Enterprise Edition フロントエンド サーバーと共に使用することはできません。

詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」を参照](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)してください。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性と障害復旧のサポート

Skype for Business Server は、プールによってサーバーの冗長性によって高可用性を提供します。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。

Skype for Business Server では、プールのペアリングを有効にすることで障害復旧対策も提供します。 このトポロジを展開する場合は、フロント エンド プールのペアを指定し、ペアの各プールは個別のデータ センターと個別の地理的領域に配置されます。 1 つのプールまたはサイトがダウンした場合は、サービスの中断を最小限に抑え、そのプールのユーザーを、ペアの他のプールを使用するリダイレクトできます。

Skype for Business Server では、バック エンド サーバーの高可用性に関する複数のオプションもサポートされています。 これらには次のコマンドレットがあります。

- データベース ミラーリング

- AlwaysOn 可用性グループ

- AlwaysOn フェールオーバー クラスター インスタンス (FCI)

- SQL フェールオーバー クラスタリング

プールのペアリングとバック エンド サーバーの高可用性の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。

## <a name="server-collocation-in-skype-for-business-server"></a>Skype for Business Server でのサーバーのコロケーション

既に共に存在する用語を使用しましたが、これは何を意味しますか? Skype for Business Server を使用すると、同じサーバー (一緒に配置されるサーバー)、または異なるサーバー上にいくつかのサーバーの役割と機能を見つけますが、開始するときに混乱を招く可能性があります。また、Standard Edition サーバーと Enterprise Edition サーバーのどちらを展開するか (それぞれに独自のルールが適用されます)。 計画を支援するために、サーバーの配置を Standard Edition サーバー展開と Enterprise Edition フロントエンド プールの展開に含めます (ほとんどの場合、この情報は同じであり、異なる場所では特に呼び出されます)。

### <a name="collocation-of-server-roles"></a>サーバーの役割の一覧

Standard Edition サーバーには次の役割が配置されています (追加の構成が必要ですが)。Enterprise Edition フロントエンド プールでは、この役割を別のサーバーに配置または展開できます。

- 仲介

これらのサーバーの役割は、それぞれ別のサーバーに展開する必要があります。

- ディレクター

- Edge

- ビデオ相互運用サーバー

- Office Web Apps

### <a name="databases"></a>Databases

これは、Standard Edition サーバー展開と Enterprise Edition サーバー プール展開の間に大きな違いがある領域です。そのため、以下に 2 つのセクションを示し、その後に両方の規則を追加します。

#### <a name="standard"></a>標準

Express SQL Server Standard Edition サーバー上に同一に位置し、移動できないので、これは非常に簡単です。 さらに、Standard Edition サーバーに常設チャット サーバーを展開する場合は、Standard Edition サーバー上に常設チャットと常設チャット コンプライアンス データベースを併合することもできますが、必要ではありません。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

これらは Standard Edition サーバー上に一緒に表示できませんが、次に示すデータベース サーバーは 1 台のデータベース サーバー上に移動できます。

- 監視データベース

- アーカイブ データベース

- Enterprise Edition フロントエンド プールの任意のバック エンド データベース

#### <a name="enterprise"></a>Enterprise

次のデータベースは、同じバック エンド サーバーにSQL Server。

- バック エンド データベース

- 監視データベース

- アーカイブ データベース

- 常設チャット データベース

- 常設チャット コンプライアンス データベース

#### <a name="both"></a>Both/フォーム/データシート

1 つの SQL インスタンス、または同じ SQL データベース内の複数の SQL インスタンスに Skype for Business Server データベースを共に展開する場合は、次の追加規則に従う必要SQL Serverがあります。

- 各 SQL インスタンスには、Enterprise Edition フロントエンド プール用の単一のバック エンド データベース、1 つの監視データベース、単一のアーカイブ データベース、単一の常設チャット データベース、および単一の常設チャット コンプライアンス データベースのみを含めできます。

- データベース サーバーは、複数の Enterprise Edition フロントエンド プール、アーカイブを実行している 1 台のサーバー、監視を実行する 1 台のサーバー、1 つの常設チャット データベース、および 1 つの常設チャット コンプライアンス データベースをサポートすることはできませんが、データベースが SQL Server の同じインスタンスを使用するか、SQL Server の個別のインスタンスを使用するかに関係なく、それぞれをサポートできます。

    > [!NOTE]
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。

### <a name="file-shares"></a>ファイル共有

ファイル共有は、別のサーバー上に作成するか、または次の一部またはすべてと同じサーバーに共有できます。

- データベース サーバー (Enterprise Edition フロントエンド プールのバック エンド サーバーを含む)

- 監視データベース

- アーカイブ データベース

- 常設チャット データベース

- 常設チャット コンプライアンス データベース

> [!CAUTION]
> これらのサーバーにファイル共有を共に作成することもできますが、お勧めしない点に注意してください。 ファイル共有を他のサーバーの役割と共に使用する場合は、ディスク領域とパフォーマンスの問題を定期的に監視してください。

### <a name="keep-in-mind"></a>注意点

- Skype for Business Server コンポーネントではないリバース プロキシ サーバーは、トポロジ内に含めなくても、共に使用できません。 フェデレーション ユーザーの Web コンテンツの共有をサポートする場合は、リバース プロキシが必要です。 必要に応じて、他のアプリケーションで使用されている組織に既に存在する既存のリバース プロキシ サーバーを構成して、Skype for Business Server のリバース プロキシ サポートを実装します。

- Exchange UM コンポーネントまたは SharePoint Server コンポーネントを Skype for Business Server の役割と共に使用できません。

## <a name="see-also"></a>関連項目

[Skype for Business Server のリファレンス トポロジ](reference-topologies.md)
