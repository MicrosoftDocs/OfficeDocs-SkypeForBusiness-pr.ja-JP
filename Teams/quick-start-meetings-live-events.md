---
title: 会議、ウェビナー、ライブ イベント
ms.reviewer: ''
description: 管理者が Microsoft Teams で会議、ウェビナー、ライブ イベントを展開および構成するためのガイド。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 982730f7c839eeab2a55bc8997eade8aec31bebc
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614270"
---
# <a name="meetings-webinars-and-live-events"></a>会議、ウェビナー、ライブ イベント

Microsoft Teams では、会議、ウェビナー、ライブ イベントなど、複数の方法で会議を行うことができます。

この記事は管理者と IT 担当者を対象としたもので、会議、ウェビナー、ライブ イベントの違いについて説明します。 その後、この機能をユーザーに迅速にロールアウトするために必要な情報へのリンクが提供されます。

[Meetings](#meetings), [webinars](#webinars), and [live events](#live-events) are all types of meetings, but webinars and live events provide additional control for the organizer over the conversation and participants. Webinars provide two-way interaction while live events provide a managed Q&A experience. 

会議の種類の違いによって、参加者の制限と参加者の機能も異なります。 

次の表は、3 種類の会議、推奨される参加者の数、および参加者が会議で対話する方法をまとめたものです。 各会議の種類に関する詳細情報を含むセクションは、表の後に記載されています。 この記事には、[大規模な会議のベスト プラクティス](#best-practices-for-large-meetings)に関するセクションも含まれています。

| 会議の種類 | Number of Participants | 操作 | サポートされている登録 |
|----------|--------|--------|-----|
| 会議  | 最大 20,000 人* | - 最大 1,000 人の参加者は、完全にインタラクティブな同等の会議機能を有します。 <br> - 参加者数が 1,000 を超え、最大 20,000 人の場合には、[閲覧限定](view-only-meeting-experience.md) 機能を有します。  | いいえ |
| ウェビナー | - 最大 1,000 人<br>- [閲覧限定](view-only-meeting-experience.md) 機能の制限が間もなく増加します。 |- 最大 1,000 人の参加者は、完全にインタラクティブな機能を有します。<br> - 対象ユーザーの相互作用が構成可能です。<br> - 発表者を指定できます。 | はい |
| ライブ イベント | 最大 20,000 人** |- 大規模な視聴者に配信。 <br>- 対象ユーザーの相互作用へのモデレート Q&A。 <br> - 外部発表者を含むプロデューサーと発表者を指定できます。<br>- より高度な運用機能をサポートしています。 | いいえ |

*通常の 10,000 が、2022 年 12 月 31 日まで 20,000 に増やされます。

**通常の 10,000 が、2022 年 12 月 31 日まで 20,000 に増やされます。 Yammer や Microsoft Stream のライブ イベントを使用して、さらに多くの人数をスケジュールすることさえできます。 詳細については、「[Microsoft 365 全体でライブ イベントをする](/stream/live-event-m365)」を参照してください。 ただし、20,000 人を超える参加者のイベントには、[Live Events Assistance Program](/stream/live-events-assistance) が必要であることにご留意ください。

Note that NDI is fully supported in meetings, webinars, and live events, allowing you to produce the broadcast by using tools such as OBS and Wirecast. For more information, see [Use NDI® technology in Microsoft Teams](use-ndi-in-meetings.md).

> [!NOTE]
> Microsoft Teams を使用してオンライン イベントを配信するためのロール別のガイダンスについては、 [Virtual Event Playbook](https://aka.ms/VirtualEventPlaybook) を参照してください。 Microsoft Tech Communityで [Virtual Event Forum](https://aka.ms/VirtualEventForum) に参加することもできます。

> [!NOTE]
> 様々なプラットフォームで Teams の会議とイベントをすばやく構成する方法についての詳細は、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="meetings"></a>会議

Teams の **会議** には、最大 1,000 人のユーザー向けの音声、ビデオ、画面共有、および 1,000 人を超える参加者の [閲覧専用機能](view-only-meeting-experience.md)が含まれます。 参加者は、Teams 会議に参加するために組織のメンバーである (または Teams アカウントを持っている) 必要はありません。 予定表の招待状から会議参加のリンクを使用して直接参加することもできるし、利用可能な場合は音声通話で参加することもできます。  

管理者は、会議の設定を構成し、会議ポリシーを指定して組織で有効にする会議機能を制御します。  

定期的にスケジュールされた会議に加えて、ユーザーはチャネル会議を作成できます。 チャネル会議を使用すると、チーム内のすべてのユーザーが会議があることを確認し、会議に参加し、会議チャットを使用できます。 チャネル会議は、チーム内のすべてのユーザーを会議に迅速に招待する方法です。 エンド ユーザーが会議をスケジュールする方法の詳細については、「[会議をスケジュールする](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)」を参照してください。

閲覧限定の会議エクスペリエンスの詳細については、「[Teams の閲覧限定会議エクスペリエンス](view-only-meeting-experience.md)」を参照してください。

### <a name="articles-for-administrators"></a>管理者向けの記事

次の表は、確認するべき主な記事を示しています。

| 記事 | 説明 |
|----------|--------|
| [会議の設定](meeting-settings-in-teams.md) |  匿名ユーザー、会議出席依頼、メディア トラフィックに関する会議設定を構成する方法について説明しています。  |
| [会議ポリシー](meeting-policies-overview.md)  | 会議の参加者が使用できる機能を決定するポリシーを作成および管理する方法について説明してします。 | 
| [Teams のクラウド会議記録の管理](cloud-recording.md) | 会議の記録を管理する方法について説明しています。 |
| [組織のデバイス管理](device-management.md)| 電話や Teams Rooms など、組織のデバイスを管理する方法について説明しています。 |
| [リアルタイム テレメトリを使用して低品質の会議をトラブルシューティングする](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | リアルタイム分析 (RTA) を使用し、個々のユーザーの Microsoft Teams 会議の品質の低下をトラブルシューティングする方法について説明します。|

### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 |
|----------|--------|
| [会議の管理](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Teams 会議を初めて使用するユーザー向けの簡潔なトレーニング ビデオ。 |
| [会議のスケジュール設定](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | さまざまな種類の会議をスケジュールする方法を説明する記事です。 |
| [Teams で効果的な会議を実行する](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | 会議をより魅力的で生産性の高い、意味のあるものにするための講師主導の無料クラスです。 |
| [Teams 会議の参加者設定の変更](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | 会議オプションの管理に関する記事。 |

## <a name="webinars"></a>ウェビナー

**ウェビナー** は、発表者と参加者が明確な役割を持つ構造化された会議です。 ウェビナーと Teams 会議の主な違いは、ウェビナーは登録をサポートし、出席者のエンゲージメント データを提供することです。 組織内でウェビナーを有効にするには、「[Teams でウェビナーを設定する](set-up-webinars.md)」を参照してください。

### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 | 
|----------|--------|
| [Teams ウェビナーを開始する](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Teams ウェビナーを初めて使用するユーザー向けの簡潔なトレーニング ビデオ。 |
| [ビジュアル クイック スタート ガイド](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | ウェビナーのスケジュール設定を開始する方法を説明するダウンロード可能なビジュアル ガイドです。 |


## <a name="live-events"></a>ライブ イベント

**ライブ イベント** は、組織が、最大 20,000 人までの大規模なオンライン参加者にストリーミングするイベントをスケジュールして生成できる構造化された会議です。 ライブ イベントでは、対象ユーザーの相互作用はマネージド Q&A エクスペリエンスです。

### <a name="articles-for-administrators"></a>管理者向けの記事

次の表は、確認するべき主な記事を示しています。

| 記事 | 説明 |
|----------|--------|
| [Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)  | ライブ イベントの簡単な概要。 |
| [Teams のライブ イベントの計画](teams-live-events/plan-for-teams-live-events.md) | ライブ イベントを構成するに先立って知っておくべきこと。 |
| [Teams のライブ イベントをセットアップする](teams-live-events/set-up-for-teams-live-events.md) | ネットワーク計画などの前提条件について説明します。 |
| [ライブ イベントを構成する](teams-live-events/configure-teams-live-events.md) | ライブ イベントを構成するための手順。|

### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 |
|:----------|:--------|
| [ライブ イベントを開始する](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | ライブ イベントの概要と開始方法。 |
| [Teams ライブ イベントのビデオ トレーニング](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | ライブ イベントを計画およびスケジュールする方法を説明するビデオです。  |

大規模な仮想イベントを生成するには、 [Virtual Event Guide](https://adoption.microsoft.com/virtual-event-guidance/)を確認してください。このガイドには、イベント開催者、技術プロデューサー、IT プロフェッショナル、コンテンツ作成者向けのガイダンスがあります。

## <a name="apps-for-meetings"></a>会議用アプリ

Microsoft enables you to enhance meeting experiences by integrating and using meeting apps. For example, whiteboard integration in Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

Teams で提供されるアプリを使用し、認定されたサード パーティ製のアプリとテンプレートを使用して、独自のカスタム アプリを作成することで、Teams の展開に会議アプリを追加できます。

次の表に、詳細な記事を示します:

| 記事 | 説明 |
|----------|--------|
| [Teams アプリの概要](deploy-apps-microsoft-teams-landing-page.md) | アプリの概要と、組織のアプリを展開する方法。 |
| [Teams 会議用アプリ](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | 会議アプリの拡張性、API リファレンス、および会議用にアプリを有効にして構成する方法の概要。 |
| [Teams でホワイトボードを管理する](manage-whiteboard.md) | ホワイトボードの機能と、組織で有効または無効にする方法について説明します。 |

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>会議、ウェビナー、ライブ イベントのライセンス要件

誰でも無料で Teams 会議、ウェビナー、パブリック ライブ イベントに参加できます。ライセンスは必要ありません。

会議、ウェビナー、またはライブ イベントを開催、スケジュール、ホストするユーザーには、「[Microsoft Teams サービス解説書](/office365/servicedescriptions/teams-service-description)」に記載されている Microsoft 365 ライセンスのうちのいずれかが必要です。 既に Teams を使用している場合は、会議、ウェビナー、ライブ イベントの開催とホストに必要なライセンスを持っていると思われます。

ユーザーが電話で会議にダイヤルインできるようにするには、電話会議を設定する必要があります。 電話会議の詳細については、「[Teams での電話会議](deploy-audio-conferencing-teams-landing-page.md)」を参照してください。

## <a name="best-practices-for-large-meetings"></a>大規模な会議のベスト プラクティス

このセクションでは、管理者向けのガイダンスと、管理者が発表者や開催者と共有できるヒントについて説明します。

イベントを成功させるためには、以下に示すプラクティスに従ってください。

- 大規模な会議、ウェビナー、ライブ イベントで最適なエクスペリエンスを実現するために、Microsoft では Teams デスクトップ クライアントまたは Teams モバイル クライアントの使用をお勧めします。

- オンプレミスおよびリモート ユーザーの両方において、すべての Microsoft [ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)が遵守されていることを確認します。
- [リアルタイム データ テレメトリ](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146)を使用して、イベントを監視し、考えられる問題とそのソースを特定します。
  - しきい値を超えたメトリックによって発生するエクスペリエンスの低下に直面しているユーザーのテレメトリを[分析する](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md)ために、会議モニターを指定します。
  - 会議モニターを発表者として設定して、非承認のビデオ ストリームを無効にし、偶発的なライブ マイクをミュートし、必要に応じて出席者を削除します。

### <a name="guidelines-for-your-end-users"></a>エンド ユーザー向けのガイドライン

開催者と発表者は、以下の推奨事項を実装する必要があります。

- 10 人以上の参加者を含む会議の場合は、 [Q&A](/MicrosoftTeams/manage-qna-for-teams) を使用して、質問に対する回答を正式に質問および受け取る機会を参加者に提供し、構造化されたディスカッションを行います。

- スムーズな会議を作成するために、イベント開催者は事前定義済の発表者を設定できます。 会議が開始すると、発表者は他の出席者を発表者の役割に昇格できます。

- 会議オプションを使用して共同開催者を定義する (パブリック プレビュー)

- ビデオとマイクの設定を事前に構成して、出席者のエクスペリエンスをコントロールします。
  - 混乱を避けるために、出席者のマイクを無効にします。 会議中に他のユーザーが対話する必要がある場合は、手を挙げるときにミュートを解除できるようにします。
  - 視覚的な注意散漫を避けるために、出席者のビデオを無効にします。 会議の適切な時間に、すべての出席者または特定の個人に対してビデオを許可できます。

- 会議中にアンケートと Q&A を使用します。

- ロビー コントロールを使用して、会議の参加またはロビーの保留をコントロールします。

- [Microsoft 365 ネットワーク接続テスト](https://connectivity.office.com/)を実行して、イベントの数日前から当日にかけて、ネットワークの適合性を確認します。

- 自宅からプレゼンテーションする場合は、他のデバイスが高帯域幅を消費していないかどうかを確認します (ストリーミング サービス、オンライン ゲーム、大容量のダウンロード)。

- より信頼性の高いオーディオ、ビデオ、画面共有のために、有線接続されたエンドポイントから発表してください。

- ユーザーがデスクトップまたはモバイル デバイスで最新の Teams アプリを使用していることを確認します。

- ノート PC を使用する場合は、高いネットワーク接続と十分な電力があることを確認します。

- デバイス、照明、またはネットワークの問題を特定するために、イベントの前にドライ ランをスケジュールします。 これにより、開催者/発表者は、使用する機能に慣れていることも確認することができます。
  - 問題が発生した場合は、修復作業が成功したことを確認するために、追加の予行演習をスケジュールします。
  
- スポットライト、PowerPoint Live、会議の記録、キャプション、トランスクリプションなどの機能を利用して、エンゲージメントと有効性を促進します。

- 発表者と参加者は、最適なエクスペリエンスを提供するために、Teams デスクトップ アプリケーションを使用する必要があります。

- 参加者は、大規模な会議中に気を散らさないように、チャット通知をオフにする必要があります。

- 大規模な会議の開催に関するその他のヒントについては、「[大規模なTeams 会議のベスト プラクティス](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams でのミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)

[Teams でウェビナーを設定する](set-up-webinars.md)

[Teams でのライブ イベント](teams-live-events/what-are-teams-live-events.md)

[Teams の閲覧限定の会議エクスペリエンス](view-only-meeting-experience.md)

[Teams の制限と仕様](limits-specifications-teams.md)

