---
title: Skype for Business Server のトポロジの基礎
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '概要: Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバー collocation について説明します。'
ms.openlocfilehash: 00154c754292fd960942f0f0da7f95bb6b5b1c19
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "35820993"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Skype for Business Server のトポロジの基礎

**概要:** Skype for Business Server のトポロジを選択します。 Skype for Business Server のサーバー collocation について説明します。

他のものを準備する前に、Skype for Business Server の展開に適したトポロジを計画していることをご確認ください。 事前に決定する必要があるのは、Skype for Business Server のオンプレミス展開を使用する場合、またはハイブリッド展開で Skype for Business Server Online の展開に統合する場合です。 どちらの場合も、ここではオンプレミスのトポロジについて詳しく説明しますが、ここでは、ハイブリッドの詳細について説明します。

また、 [Skype For Business Server 用のリファレンストポロジ](reference-topologies.md)でも、いくつかのトポロジの例を見ることができます。

## <a name="sites"></a>サイト

Skype for Business Server では、Skype for business Server コンポーネントが含まれているネットワーク上のサイトを定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 Skype for Business Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念です。 お使いの Skype for Business Server サイトは、お使いの Active Directory サイトに対応している必要はありません。

Skype for Business Server は、高可用性と場所の要件に従って拡大縮小できる1つ以上のサイトのオンプレミス展開をサポートします。

展開には、少なくとも1つのセントラルサイト (データセンターとも呼ばれます) があります。また、展開の各セントラルサイトには、1つの Standard Edition サーバー、または少なくとも1つの Enterprise Edition のフロントエンドプールがあります。 以下に各オプションの違いを示します。

- Standard Edition server には、併置された SQL Server Express データベースが含まれています。

- Enterprise Edition のフロントエンドプールには以下が含まれます。

  - 1つ以上のフロントエンドサーバー (理想的には、スケーラビリティの場合は最低3つ)、最大値は12です。 サーバーが 2 台以上の場合は、負荷分散が必要になります。

  - 別のバックエンドサーバー。

各サーバーの役割の詳細については、このセクションで後述します。

セントラルサイトに加えて、サイトに関連付けられた1つ以上の分岐サイトを作成することもできます。 ほぼすべての機能についてセントラルサイトに依存しているため、完全にはどのような機能を備えていますか。

- Survivable Branch Appliance: 公衆交換電話網 (PSTN) ゲートウェイと一部の Skype for Business Server 機能を組み合わせたものです。

- Survivable Branch Server は、Skype for Business Server レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server を実行しているサーバーです。

- スタンドアロン PSTN ゲートウェイ (Survivable Branch アプライアンスの一部ではありません)。

- スタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバープール (この役割を Survivable Branch アプライアンスで検索したくない場合)。

## <a name="whats-in-a-skype-for-business-server-site"></a>Skype for Business Server サイトには何がありますか?

さらに詳しい情報を得るには、セントラルサイトで次の操作を行うこともできます。

- 複数のフロントエンドプール、同じドメインまたは異なるドメイン内 (フロントエンドプールのすべてのフロントエンドサーバーと、プールのバックエンドサーバーが同じドメインに存在することを計画することを忘れないでください)。

- 複数の Standard Edition サーバー。

- Office Web Apps Server。 Skype for Business Server の Office Web Apps で PowerPoint プレゼンテーションの共有やレンダリングに使用されます。

- エッジサーバーまたはエッジプール (境界ネットワーク)。 展開で、フェデレーション パートナー、パブリック IM 接続、XMPP (eXtensible Messaging and Presence Protocol) ゲートウェイ、およびリモート ユーザー アクセスをサポートする場合に必要です。 詳細については、「microsoft Edge Server の計画ドキュメント」を参照してください。

- 常設チャットサーバー。 トピックに基づく長時間のマルチパーティ会話にユーザーが参加できるようにする場合に便利です。 常設チャットサーバーの計画についての詳細はこちらをご覧ください。

- 監視。 オーディオ/ビデオ (A/V) Quality of Experience (QoE) のデータ収集、および展開でのエンタープライズ Voip 会議および通話の詳細記録 (CDR) をサポートするために使用されます。 「計画」のドキュメントの「監視」トピックで詳しく説明します。

- ディレクターまたはディレクタープール。 これは必須ではありませんが、回復性を向上させ、ユーザーのホームプールへの Skype for Business ユーザー要求のリダイレクションを有効にする場合に便利です。 ディレクターを展開する場合は、1つのプールあたり最大10個のプールがサポートされます。 これが必要な場合は、ディレクターの計画に関するトピックを参照してください。

- リバースプロキシ。 これは Skype for Business Server コンポーネントではありませんが、フェデレーションされたユーザーのために web コンテンツを共有する場合、リモートユーザーがアドレス帳を使用したり、会議に参加したりする必要がある場合は、これを行うことをお勧めします。環境で使用する必要があります。 リバースプロキシサーバーのトピックを設定すると、準備が整った時点で詳細を確認できます。

これらのサーバーの併置に関する追加情報を次に示します。

セントラルサイトに展開されているすべてのフロントエンドプールおよび標準エディションのサーバーは、展開済みであれば、次のものを共有します。

||||
|:-----|:-----|:-----|
|ディレクターまたはディレクタープール  <br/> |スタンドアロンの仲介サーバーまたは仲介サーバープール  <br/> |Office Web Apps サーバー  <br/> |
|エッジサーバーまたはエッジプール  <br/> |常設チャットサーバーまたは常設チャットサーバープール  <br/> |監視  <br/> |

このリストでは、Exchange ユニファイドメッセージング (UM) サーバーはどこにありますか? 確かに、Exchange UM と統合する場合は、Skype for Business Server でも使用できますが、Skype for Business Server サイトのコンポーネントではないため、ここでは説明しません。

複数のセントラルサイトを作成することを計画している可能性があります。そのため、セントラルサイトに展開されている場合は、次のサーバーとロールを共有できます。

|||
|:-----|:-----|
|スタンドアロンの仲介サーバーまたは仲介サーバープール  <br/> |エッジサーバーまたはエッジプール  <br/> |
|常設チャットサーバーまたは常設チャットサーバープール  <br/> |監視  <br/> |

最後の一覧と同じように、ここには Exchange UM サーバーを含めません。これは、Skype for Business Server の展開の一部ではないため、ここでも同じカテゴリに分類されます。

もちろん、展開にはその他のコンポーネントやオプションを含めることもできます。

|||||
|:-----|:-----|:-----|:-----|
|ファイアウォール  <br/> |PSTN ゲートウェイ (エンタープライズ VoIP を展開する場合)  <br/> |Exchange UM サーバー (Exchange UM と統合する場合)  <br/> |DNS 負荷分散  <br/> |
|ハードウェア ロード バランサー  <br/> |SQL Server データベース  <br/> |ファイル共有  <br/> ||

## <a name="server-roles"></a>サーバーの役割

Skype for Business Server を実行している各サーバーは、1つ以上のサーバーの役割を実行します。 サーバーの役割は、そのサーバーによって提供される、定義済みの Skype for Business Server 機能のセットです。 ネットワークで使用できるサーバーの役割をすべて展開する必要はありません。 必要な機能が含まれているサーバーの役割のみをインストールします。

多くのサーバーの役割では、すべてが同じサーバーの役割を実行する複数のサーバーのプールを展開して、スケーラビリティと高可用性を実現できます。 プール内の各サーバーは同じサーバーの役割を実行する必要があります。 Skype for Business Server のほとんどの種類のプールでは、プール内のさまざまなサーバー間でトラフィックを分散させるために、ロードバランサーを展開する必要があります。 Skype for Business Server は、ドメインネームシステム (DNS) 負荷分散とハードウェアロードバランサーの両方をサポートしています。

### <a name="front-end-server-and-back-end-server"></a>フロントエンド サーバーおよびバックエンド サーバー

Skype for Business Server Enterprise Edition では、フロントエンドサーバーは主要サーバーの役割であり、多くの基本的な Skype for Business Server 機能を実行します。 フロントエンドサーバーはバックエンドサーバーと共に、Skype for Business Server Enterprise Edition の展開に必要な唯一のサーバーロールです。

フロントエンドプールは、共通して構成される一連のフロントエンドサーバーであり、共通のユーザーグループに対してサービスを提供するために一緒に動作します。 同じ役割を実行する複数のサーバーのプールでは、スケーラビリティとフェールオーバー機能が提供されます。

フロントエンドサーバーには、次のものが含まれます。

- ユーザーの認証および登録。

- プレゼンス情報および連絡先カードの交換。

- アドレス帳サービスおよび配布リスト展開。

- IM 機能 (マルチパーティ IM 会議など)。

- Web 会議、PSTN ダイヤルイン会議、および音声ビデオ会議 (展開されている場合)。

- Skype for Business Server に含まれているアプリケーション (会議アテンダントと応答グループアプリケーションなど) とサードパーティアプリケーションの両方のアプリケーションホスト。

- オプションで、使用状況の情報を詳細な通話の記録 (CDR) や通話エラー記録 (CER) の形式で収集するための監視。 この情報には、企業の音声通話と A/V 会議の両方について、ネットワーク上を通過するメディア (音声およびビデオ) の品質に関する基準が記載されています。

- Web Scheduler、Join Launcher など、Web ベースのタスクをサポートするための Web コンポーネント。

- オプションで、コンプライアンス上の理由で IM 通信および会議の内容をアーカイブするアーカイブ機能。詳細については、「計画」のドキュメントの「[Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)」を参照してください。

    Lync Server 2010 以前のバージョンでは、監視とアーカイブは個別のサーバーロールであり、フロントエンドサーバーには併置されていませんでした。

- オプションで、常設チャットが有効になっている場合は、チャット ルーム管理用の常設チャット Web サービス、およびファイルのアップロード/ダウンロード用の常設チャット Web サービス。

フロントエンド プールは、ユーザーおよび会議データ用のプライマリ ストアでもあります。各ユーザーに関する情報は、プール内の 3 つのフロントエンド サーバーにレプリケートされ、バックエンド サーバーにバックアップされます。

さらに、展開に含まれる1台のフロントエンドサーバーも中央管理サーバーを実行します。これは、Skype for Business Server を実行しているすべてのサーバーの基本構成データを管理し、展開します。 サーバーの全体管理サーバーでは、Lync Server 管理シェルとファイル転送機能も提供されます。

バックエンドサーバーは、フロントエンドプールのデータベースサービスを提供する Microsoft SQL Server を実行しているデータベースサーバーです。 バックエンドサーバーは、プールのユーザーと会議データのバックアップストアとして機能し、応答グループデータベースなど、他のデータベースのプライマリストアです。 バックエンドサーバーは1つしかありませんが、フェールオーバーには、 [Skype For Business Server のバックエンドサーバーの高可用性](../high-availability-and-disaster-recovery/back-end-server.md)が推奨されます。 バックエンドサーバーでは、Skype for Business Server ソフトウェアは実行されません。

> [!IMPORTANT]
> Skype for Business Server データベースを他のデータベースに配置することはお勧めしません。 併置すると、可用性とパフォーマンスに影響することがあります。

> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。

バックエンド サーバーのデータベースには、プレゼンス情報、ユーザーの連絡先リスト、会議データ (現在のすべての会議の状態に関する固定データなど)、および会議のスケジュール データなどの情報が格納されています。

### <a name="edge-server"></a>エッジ サーバー

エッジサーバーにより、ユーザーは組織のファイアウォール外のユーザーと通信して共同作業を行うことができます。 これらの外部ユーザーは、現在オフサイトで作業している組織の独自のユーザー、フェデレーションパートナー組織のユーザー、Skype for Business Server 展開でホストされている会議に参加するよう招待された外部ユーザーを含めることができます。

エッジサーバーを展開すると、モバイルデバイスで Lync 機能をサポートするモビリティサービスも有効になります。 ユーザーは、サポートされる Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。 モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。

エッジ サーバーには、完全に統合された XMPP (eXtensible Messaging and Presence Protocol) プロキシと、フロントエンド サーバーに含まれる XMPP ゲートウェイも含まれます。 これらの XMPP コンポーネントを構成することで、Skype for Business Server ユーザーは、インスタントメッセージ (im) とプレゼンスのために、XMPP ベースのパートナーから連絡先を追加できるようになります。

> [!NOTE]
> XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 詳細については、「 [XMPP フェデレーションを移行](../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。

### <a name="mediation-server"></a>仲介サーバー

仲介サーバーは、エンタープライズ Voip を実装するために必要なコンポーネントであり、勤務先からの通話、およびダイヤルイン会議に使用されます。 仲介サーバーは、内部の Skype for Business Server インフラストラクチャと公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、またはセッション開始プロトコル (SIP) トランク間のメディアを変換します。 仲介サーバーは、フロントエンドサーバーと同じサーバーまたはスタンドアロンの仲介サーバープールに分けて実行できます。

詳細については、「 [Skype For Business server の仲介サーバーコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)」を参照してください。

### <a name="video-interop-server"></a>ビデオ相互運用サーバー

ビデオ相互運用機能サーバーは、Skype for Business Server 2015 の新しい役割です。 Skype for Business Server の展開を特定のサードパーティの VTC (ビデオ会議システム) ソリューションに統合することができます。 VIS は、サードパーティの電話会議システムと Skype for Business Server の展開の間の媒介として機能します。 このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に焦点を合わせています。

詳細については、「 [Skype For Business server でのビデオ相互運用機能の計画](../../plan-your-deployment/video-interop-server.md)」を参照してください。

### <a name="director"></a>ディレクター

ディレクターは、Skype for Business Server ユーザー要求を認証することができますが、ユーザーアカウントをホームにしたり、プレゼンスや会議サービスを提供したりすることはありません。 ディレクターは、外部ユーザー アクセスが有効になっている展開でセキュリティを強化するのに非常に役立ちます。 内部サーバーに要求を送信する前にディレクターで認証を実行できます。 サービス拒否攻撃が発生した場合、攻撃はディレクターによって終了され、フロントエンド サーバーには到達しません。

### <a name="persistent-chat-server-roles"></a>常設チャットサーバーの役割

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。

常設チャットでは、ユーザーがトピックに基づく長時間のマルチパーティ会話に参加できます。常設チャット フロントエンド サーバーは、常設チャット サービスを実行します。常設チャット バックエンド サーバーでは、チャット履歴データと、カテゴリおよびチャット ルームに関する情報が格納されます。オプションの常設チャット コンプライアンス バックエンド サーバーでは、コンプライアンスの目的でチャットの内容とコンプライアンス イベントを格納できます。

Skype for Business Server Standard Edition を実行しているサーバーでも、同じサーバー上で同一の常設チャットを実行できます。 Enterprise Edition フロントエンドサーバーでは、常設チャットフロントエンドサーバーを検索することはできません。

詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。

## <a name="high-availability-and-disaster-recovery-support"></a>高可用性および障害復旧のサポート

Skype for Business Server は、プールを介したサーバーの冗長性によって高可用性を実現します。 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。

Skype for Business Server は、プールのペアリングを有効にすることで、障害回復の手段も提供します。 このトポロジを展開する場合、フロントエンドプールのペアを指定します。各プールは、別々のデータセンターにあり、各プールは別々の地理的領域に配置されています。 1つのプールまたはサイトがダウンした場合は、サービスの中断を最小限に抑えて、そのプールのユーザーを、ペア内の他のプールを使用するようにリダイレクトすることができます。

Skype for Business Server では、バックエンドサーバーの高可用性を実現するためのいくつかのオプションもサポートされています。 たとえば、以下のようなものです。

- データベース ミラーリング

- AlwaysOn 可用性グループ

- AlwaysOn フェールオーバークラスターインスタンス (FCI)

- SQL フェールオーバー クラスタリング

プールのペアリングとバックエンドサーバーの高可用性の詳細については、「 [Skype For Business Server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。

## <a name="server-collocation-in-skype-for-business-server"></a>Skype for Business Server のサーバー collocation

用語の概要は既に使用していますが、これは何を意味していますか? Skype for Business Server を使用すると、サーバーの役割と機能の一部を同じサーバー (collocation または別のサーバー) で検索できますが、作業を開始したときや、標準エディションと Enterprise Edition サーバーのどちらを実行しているかがわかりにくくなることがあります。展開 (それぞれに独自のルールが付属しています)。 お客様の計画を支援するため、Standard Edition server の展開と Enterprise Edition のフロントエンドプール展開にはサーバーの collocation が含まれています (ほとんどの場合、この情報は同一であり、特定の場所にあります。

### <a name="collocation-of-server-roles"></a>サーバーの役割の併置

Standard Edition サーバーには、次の役割が含まれています (ただし、その他の構成が必要です)。 Enterprise Edition のフロントエンドプールでは、この役割を併置したり、別のサーバーに展開したりすることができます。

- 仲介

次のサーバーの役割は、それぞれ別のサーバーに展開する必要があります。

- ディレクター

- Edge

- ビデオ相互運用サーバー

- Office Web Apps

### <a name="databases"></a>データベース

この領域では、Standard Edition server 展開と Enterprise Edition server プールの展開の相違点について説明します。次に、2つのセクションに加えて、両方について追加ルールをいくつか紹介します。

#### <a name="standard"></a>Standard

SQL Server Express は Standard Edition Server に併置されているため、移動できません。これは非常に簡単です。 さらに、標準エディションのサーバーに常設チャットサーバーを展開すると、常設チャットと常設チャットのコンプライアンスデータベースも Standard Edition サーバーで検索することができますが、必要はありません。

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。

これらは標準エディションのサーバー上では使用できませんが、1つのデータベースサーバーにアクセスできます。

- 監視データベース

- アーカイブ データベース

- Enterprise Edition フロントエンドプールの任意のバックエンドデータベース

#### <a name="enterprise"></a>Enterprise

次のデータベースは、同じバックエンド SQL Server に併置できます。

- バックエンド データベース

- 監視データベース

- アーカイブ データベース

- 常設チャットデータベース

- 常設チャットのコンプライアンスデータベース

#### <a name="both"></a>両方

ここでは、1つの SQL インスタンスで、または同じ SQL Server データベース内の複数の SQL インスタンスで、Skype for Business Server データベースを検索する場合に、いくつかの追加の規則に従う必要があります。

- 各 SQL インスタンスには、Enterprise Edition フロントエンドプール用のバックエンドデータベースを1つだけ含めることができます。1つの監視データベース、1つのアーカイブデータベース、1つの常設チャットデータベース、1つの永続的なチャットのコンプライアンスデータベースが含まれます。

- データベースサーバーでは、複数の Enterprise Edition フロントエンドプールをサポートしていません。アーカイブを実行しているサーバー1台、監視を実行している1台のサーバー、1つの常設チャットデータベース、1つの永続的なチャットのコンプライアンスデータベースがサポートされています。データベースで SQL Server の同じインスタンスと SQL Server の別のインスタンスのどちらを使うかに関係なく、

    > [!NOTE]
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。

### <a name="file-shares"></a>ファイル共有

ファイル共有は、別個のサーバーに配置することも、次の一部またはすべてと同じサーバーに併置することもできます。

- データベースサーバー (Enterprise Edition フロントエンドプールのバックエンドサーバーを含む)

- 監視データベース

- アーカイブ データベース

- 常設チャットデータベース

- 常設チャットのコンプライアンスデータベース

> [!CAUTION]
> これらのサーバー上にファイル共有を並置することはできますが、この方法は推奨されていないことに注意してください。 他のサーバーの役割とファイル共有を検索する場合は、ディスク容量とパフォーマンスの問題が定期的に監視されていることを確認してください。

### <a name="keep-in-mind"></a>注意が必要な点

- Skype for Business Server コンポーネントではなく、逆プロキシサーバーを作成することはできません。また、トポロジに含まれていない可能性もあります。 フェデレーションされたユーザーのための web コンテンツの共有をサポートしたい場合は、リバースプロキシが必要です。 必要な場合は、他のアプリケーションで既に使用されている既存のリバースプロキシサーバーを構成して、Skype for Business Server のリバースプロキシサポートを実装します。

- 任意の Skype for Business Server の役割を持つ Exchange UM コンポーネントまたは SharePoint Server コンポーネントを検索することはできません。

## <a name="see-also"></a>関連項目

[Skype for Business Server のリファレンストポロジ](reference-topologies.md)
