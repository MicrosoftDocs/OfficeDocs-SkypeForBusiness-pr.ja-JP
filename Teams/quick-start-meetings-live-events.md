---
title: クイック スタート - 会議、ウェビナー、ライブ イベント
ms.reviewer: ''
description: 管理者が Microsoft Teams で会議、ウェビナー、ライブ イベントを展開および構成するためのクイック スタート ガイド。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854443e529736207520cbfdbe845c0b4992f9cd6
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53647018"
---
# <a name="quick-start---meetings-webinars-and-live-events"></a>クイック スタート - 会議、ウェビナー、ライブ イベント 

Microsoft Teams では、会議、ウェビナー、ライブ イベントなど、複数の方法で会議を行うことができます。 

この記事は管理者と IT 担当者を対象としたもので、会議、ウェビナー、ライブ イベントの違いについて簡単に説明します。 その後、この機能をユーザーに迅速にロールアウトするために必要な情報へのリンクが提供されます。

> [!Note]
> 様々なプラットフォームで Teams の会議とイベントをすばやく構成する方法についての詳細は、「[プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

## <a name="meetings-webinars-and-live-events"></a>会議、ウェビナー、ライブ イベント

[会議](#meetings)、[ウェビナー](#webinars)、および[ライブ イベント](#live-events)は、すべて会議の種類ですが、ウェビナーとライブ イベントでは、会話と参加者にして対する開催者の追加の制御を提供します。 ウェビナーでは双方向の対話が提供される一方で、ライブ イベントではマネージド Q&A エクスペリエンスが提供されます。 

会議の種類の違いによって、参加者の制限と参加者の機能も異なります。 

次の表は、3 種類の会議、推奨される参加者の数、および参加者が会議で対話する方法を簡単にまとめたものです。各タイプの会議の詳細については、表の後に記載しています。<br><br>

| 会議の種類 | Number of Participants | 操作 | サポートされている登録 |
|----------|--------|--------|-----|
| 会議  | 最大 20,000 人* <br> | - 最大 1,000 人の参加者は、完全にインタラクティブな同等の会議機能を有します。 <br> - 参加者数が 1,000 を超え、最大 20,000 人の場合には、[閲覧限定](view-only-meeting-experience.md)機能を有します。  | いいえ |
| ウェビナー | - 最大 1,000 人<br>- [閲覧限定](view-only-meeting-experience.md)機能の制限が間もなく増加します。 |- 最大 1,000 人の参加者は、完全にインタラクティブな機能を有します。 <br> - 対象ユーザーの相互作用を構成可能。 <br> - 発表者を指定できます。 | はい |
| ライブ イベント | 最大 20,000 人** |- 大規模な視聴者に配信。 <br>- 対象ユーザーの相互作用に対するモデレートされた Q&A。 <br> - 外部発表者を含むプロデューサーと発表者を指定できます。<br>- より高度な運用機能をサポートしています。 | いいえ |
||||

*通常 10,000 人が、2021 年 12 月 31 日まで 20,000 人に増やされます。<br>

**通常 10,000 人が、2021 年 12 月 31 日まで 20,000 人に増やされます。 Yammer や Microsoft Stream のライブ イベントを使用して、さらに多くの人数をスケジュールすることさえできます。 詳細については、「[Microsoft 365 全体でライブ イベントをする](/stream/live-event-m365)」を参照してください。 ただし、20,000 人を超える参加者のイベントには、[Live Events Assistance Program](/stream/live-events-assistance) が必要であることにご留意ください。 

**大規模な会議、ウェビナー、ライブ イベントに関する考慮事項** - 大規模な会議を主催する場合は、以下の点を考慮してください。

- 大規模な会議、ウェビナー、ライブ イベントで最適なエクスペリエンスを実現するために、Microsoft では Teams デスクトップ クライアントまたは Teams モバイル クライアントの使用をお勧めします。 

- 大規模な会議、ウェビナー、ライブ イベントの発表者は、Teams デスクトップ クライアントを使用する必要があります。 

- 大規模な会議の開催に関するその他のヒントについては、「[大規模なTeams 会議のベスト プラクティス](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)」を参照してください。

閲覧限定の会議エクスペリエンスの詳細については、「[Teams の閲覧限定会議エクスペリエンス](view-only-meeting-experience.md)」を参照してください。

NDI は会議、ウェビナー、ライブ イベントで完全にサポートされているため、OBS や Wirecast などのツールを使用してブロードキャストを作成できます。 詳細については、「[Microsoft Teams で NDI® テクノロジを使用する](use-ndi-in-meetings.md)」を参照してください。


### <a name="meetings"></a>会議

Teams の **会議** には、最大 1,000 人のユーザー向けの音声、ビデオ、画面共有、および 1,000 人を超える参加者の [閲覧専用機能](view-only-meeting-experience.md)が含まれます。 参加者は、Teams 会議に参加するために組織のメンバーである (または Teams アカウントを持っている) 必要はありません。 予定表の招待状から会議参加のリンクを使用して直接参加することもできるし、利用可能な場合は音声通話で参加することもできます。  

管理者は、会議の設定を構成し、会議ポリシーを指定して組織で有効にする会議機能を制御します。  

定期的にスケジュールされた会議に加えて、ユーザーはチャネル会議を作成できます。 チャネル会議を使用すると、チーム内のすべてのユーザーが会議があることを確認し、会議に参加し、会議チャットを使用できます。 チャネル会議は、チーム内のすべてのユーザーを会議に迅速に招待する方法です。 エンド ユーザーが会議をスケジュールする方法の詳細については、「[会議をスケジュールする](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)」を参照してください。

#### <a name="articles-for-administrators"></a>管理者向けの記事

次の表は、確認するべき主な記事を示しています。

| 記事 | 説明 | 
|----------|--------|
| [会議の設定](meeting-settings-in-teams.md) |  匿名ユーザー、会議出席依頼、メディア トラフィックに関する会議設定を構成する方法について説明しています。  |
| [会議ポリシー](meeting-policies-in-teams.md)  | 会議の参加者が使用できる機能を決定するポリシーを作成および管理する方法について説明してします。 | 
| [Teams のクラウド会議記録の管理](cloud-recording.md) | 会議の記録を管理する方法について説明しています。 |
| [組織のデバイス管理](device-management.md)| 電話や Teams Rooms など、組織のデバイスを管理する方法について説明しています。 |
||

#### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 | 
|----------|--------|
| [会議の管理](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Teams 会議を初めて使用するユーザー向けの簡潔なトレーニング ビデオ。 |
| [会議のスケジュール設定](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | さまざまな種類の会議をスケジュールする方法を説明する記事です。 |
| [Teams で効果的な会議を実行する](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | 会議をより魅力的で生産性の高い、意味のあるものにするための講師主導の無料クラスです。 |
| [Teams 会議の参加者設定の変更](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | 会議オプションの管理に関する記事。
||


### <a name="webinars"></a>ウェビナー

**ウェビナー** は、発表者と参加者が明確な役割を持つ構造化された会議です。 ウェビナーと Teams 会議の主な違いは、ウェビナーは登録をサポートし、出席者のエンゲージメント データを提供することです。 組織内でウェビナーを有効にするには、「[Teams でウェビナーを設定する](set-up-webinars.md)」を参照してください。 


#### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 | 
|----------|--------|
| [Teams ウェビナーを開始する](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Teams ウェビナーを初めて使用するユーザー向けの簡潔なトレーニング ビデオ。 |
| [ビジュアル クイック スタート ガイド](https://teamworktools.azurewebsites.net/assets/TeamsWebinarsGetStartedGuide.pdf) | ウェビナーのスケジュール設定を開始する方法を説明するダウンロード可能なビジュアル ガイドです。  |
||


### <a name="live-events"></a>ライブ イベント

**ライブ イベント** は、組織が、最大 20,000 人までの大規模なオンライン参加者&mdash;にストリーミングするイベントをスケジュールして生成できる構造化された会議です。 ライブ イベントでは、対象ユーザーの相互作用はマネージド Q&A エクスペリエンスです。

#### <a name="articles-for-administrators"></a>管理者向けの記事

次の表は、確認するべき主な記事を示しています。

| 記事 | 説明 | 
|----------|--------|
| [Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)  | ライブ イベントの簡単な概要。 |
| [Teams のライブ イベントの計画](teams-live-events/plan-for-teams-live-events.md) | ライブ イベントを構成するに先立って知っておくべきこと。 |
| [Teams のライブ イベントをセットアップする](teams-live-events/set-up-for-teams-live-events.md) | ネットワーク計画などの前提条件について説明します。 |
| [ライブ イベントを構成する](teams-live-events/configure-teams-live-events.md) | ライブ イベントを構成するための手順。
||

#### <a name="key-training-for-end-users"></a>エンド ユーザー向けのトレーニング

次の表は、組織内のエンド ユーザーが利用できるトレーニングの一覧です:

| トレーニング | 説明 | 
|----------|--------|
| [ライブ イベントを開始する](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | ライブ イベントの概要と開始方法。 |
| [Teams ライブ イベントのビデオ トレーニング](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | ライブ イベントを計画およびスケジュールする方法を説明するビデオです。  |
||

大規模な仮想イベントを生成するには、 [Virtual Event Guide](https://adoption.microsoft.com/virtual-event-guidance/)を確認してください。このガイドには、イベント開催者、技術プロデューサー、IT プロフェッショナル、コンテンツ作成者向けのガイダンスがあります。 

## <a name="apps-for-meetings"></a>会議用アプリ

Microsoft では、会議アプリを統合して使用することで、会議エクスペリエンスを向上させます。たとえば、Teams 会議のホワイトボード統合は、Teams 会議の参加者が共有デジタル キャンバスで一緒に描画、スケッチ、および書き込みを行える Whiteboard Web アプリを利用しています。

Teams で提供されるアプリを使用し、認定されたサード パーティ製のアプリとテンプレートを使用して、独自のカスタム アプリを作成することで、Teams の展開に会議アプリを追加できます。 

次の表に、詳細な記事を示します:

| 記事 | 説明 | 
|----------|--------|
| [アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md) | アプリの概要と、組織のアプリを展開する方法。 |
| [Teams 会議用アプリ](/platform/apps-in-teams-meetings/teams-apps-in-meetings.md) | 会議アプリの拡張性、API リファレンス、および会議用にアプリを有効にして構成する方法の概要。 |
| [Teams 会議用アプリの詳細](/platform/apps-in-teams-meetings/teams-apps-in-meetings.md) | Teams 会議で使用できるアプリへのリンクが含まれています。 |
| [Teams でホワイトボードを管理する](manage-whiteboard.md) | ホワイトボードの機能と、組織で有効または無効にする方法について説明します。 |
||

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>会議、ウェビナー、ライブ イベントのライセンス要件

誰でも無料で Teams 会議、ウェビナー、ライブ イベントに参加できます&mdash;ライセンスは必要ありません。 

会議、ウェビナー、またはライブ イベントを開催、スケジュール、ホストするユーザーには、「[Microsoft Teams サービス解説書](/office365/servicedescriptions/teams-service-description)」に記載されている Microsoft 365 ライセンスのうちのいずれかが必要です。 既に Teams を使用している場合は、会議、ウェビナー、ライブ イベントの開催とホストに必要なライセンスを持っていると思われます。

ユーザーが電話で会議にダイヤルインできるようにするには、電話会議を設定する必要があります。 電話会議の詳細については、「[Teams での電話会議](deploy-audio-conferencing-teams-landing-page.md)」を参照してください。


## <a name="related-topics"></a>関連項目

[Teams でのミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)

[Teams でウェビナーを設定する](set-up-webinars.md)

[Teams でのライブ イベント](teams-live-events/what-are-teams-live-events.md)

[Teams の閲覧限定の会議エクスペリエンス](view-only-meeting-experience.md)

[Teams の制限と仕様](limits-specifications-teams.md)

[Microsoft テクニカル コミュニティ: Microsoft 365 のライブ イベント](https://resources.techcommunity.microsoft.com/live-events/)
