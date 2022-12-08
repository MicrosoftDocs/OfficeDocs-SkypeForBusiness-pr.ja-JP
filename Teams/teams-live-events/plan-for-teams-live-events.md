---
title: Microsoft Teams でのライブ イベントの計画
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: この記事では、Microsoft Teams でのライブ イベントを立ち上げる前に考慮すべき事項について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f458aded53926fed8772de70af2a105cdf9e5fda
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307652"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams でのライブ イベントの計画

組織で大規模な会議を開催するために Teams のライブ イベントを計画している場合、そのイベントを立ち上げる前に考慮すべき事項がいくつかあります。

> [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>ライブ イベントに参加、およびライブ イベントを作成、スケジュールできるのは誰か。

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

ユーザーが Teams ライブ イベントをスケジュールするには、次の前提条件を満たす必要があります。

Teams ライブ イベントを整理、作成または発表するために割り当てる必要があるライセンスは次のとおりです。  

- **整理:** Microsoft 365 または Office 365 Enterprise E1、E3、E5 のいずれかのライセンス、**[または]** Office 365 Education A3 または A5 ライセンス。 
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Microsoft Teams ライセンス - このライセンスは最初と 2 番目の項目に記載されているライセンスに含まれています。
- Microsoft Stream のライセンス - コンテンツを外部のアプリまたはデバイスと共有する場合はこのライセンスが必要です。「[Microsoft Stream のライセンス](/stream/license-overview)」をご覧ください。 新しい Teams エンコーダー サービスを使用してイベントを生成する場合は、Stream ライセンスは必要ありません。 

  Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> 現時点では、Teams ライブ イベントの作成と開催に使用できる Microsoft 365 Small Business プランはありません。

認証されたユーザーとしてライブ イベントに参加するのに、Microsoft 365 または Office 365 のライセンスが必要であることを理解することは重要ですが、この要件は使用する作成方法によって異なります。

- **Teams または Teams Powered Encoder を使用して生成されたイベントの場合**  ユーザーに Teams ライセンスを割り当てる必要があります。
- **外部アプリまたはデバイスで作成したイベントの場合**、ユーザーには Stream のライセンスが割り当てられている必要があります。

> [!NOTE]
> Teams のライブ イベントは、米国政府機関クラウド コミュニティ (GCC) 組織で利用できるようになりました。

ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

ユーザーには以下が設定されている必要があります。

- Teams でのプライベート会議のスケジューリングが有効である (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling パラメーター = True*)。
- Teams 会議で有効なビデオ共有 (*TeamsMeetingPolicy -AllowIPVideo パラメーター = True*)。
- Teams 会議で有効な画面共有 (*TeamsMeetingPolicy -ScreenSharingMode パラメーター = EntireScreen*)。
- Teams でのライブ イベントのスケジューリングが有効である (*The TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling パラメーター = True*)。
- Stream でライブ イベントを作成する許可 (外部アプリまたはデバイス生成の場合)。
- Teams 会議をスケジュールできるように構成された共存モード (*アイランド、会議優先、または Teams のみ*)。

> [!IMPORTANT]
> 認証されていない匿名ユーザーは、Teams ライブ イベントのプロデューサーや発表者としては招待できません。

### <a name="guest-to-present"></a>[発表を行うゲスト](#guest-to-present)

ゲストがライブ イベントで発表するようにするには、次のタスクを行います:

1. [ユーザーをゲストとしてチームに追加します](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. ユーザーにゲストの招待を承諾してチームに参加してもらいます。
3. [ライブイベントをスケジュールし、ゲストをイベントグループに追加します](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>ライブ イベントは誰が視聴できるか

| 出席者の表示 | Teams 生産性 | 外部アプリまたはデバイス生成 | Teams Powered Encoder
|------------------------------|-----------------|----------------------|----------------|
|パブリック (匿名ユーザー)      |  はい            |  いいえ                  | はい
|ゲスト ユーザー                   |  Yes<sup>1</sup>            |  いいえ                  |  はい            |
|外部アクセス (フェデレーション) のある会社のすべてのユーザー |  Yes<sup>1</sup>|  いいえ                  | Yes            |
|会社内の全員           |  はい            |  Yes                 | Yes                |
|特定のグループ/ユーザー      |  はい            |  Yes                 | Yes                |

<sup>1</sup> [ユーザー] と [グループ] からのみ招待することができます <br>

## <a name="teams-live-events"></a>Teams のライブ イベント

次の表は、ライブ イベントで提供される主要な機能と機能を示しています

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
>
> **お客様のニーズを引き続きサポートするために、2023 年 6 月 30 日までのライブ イベントの一時的な制限の引き上げを延長します。**
>
>- イベントでは、最大2万の出席者をサポートします
>- テナント全体で 50 のイベントを同時にホストできます
>- ブロードキャストあたり16時間のイベント期間
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). 

| 機能 | Skype 会議メディア | Teams で生成されたイベント | 外部アプリまたはデバイスで作成されたイベント |
|---------|---------|---------|---------|
|最大視聴者数 |出席者 10,000 名 |出席者 10,000 名 <sup>1</sup> |出席者 10,000 名 <sup>1</sup> |
|ライブ イベントの最大期間 |4 時間 |4 時間 |4 時間 |
|ライブ イベントの発表者とプロデューサーの最大数 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Microsoft 365 または Office 365 組織ごとの同時ライブ イベントの最大数 |15  | 15  | 15  |
|ライブ イベントの作成 |   Skype 会議ブロードキャスト ポータル |Teams、Teams 経由の Yammer | Teams、Teams 経由の Yammer、Stream |
|視聴者のエンゲージメント – Yammer |&#x2714; |&#x2714; (統合エクスペリエンス) |&#x2714; (統合エクスペリエンス) |
|視聴者のエンゲージメント – モデレート Q & A |&#x2714;  |&#x2714; |&#x2714; |
|Windows でのプロデューサー クライアント |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|Mac でプロデューサー クライアント |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|プロデューサー UI での出席者数 |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|複数の発表者の許可 |&#x2714; (Skype for Business) |&#x2714; (Teams) |N/A  |
|会議中の発表者の招待 |&#x2714; (Skype for Business) |&#x274C; |N/A |
|Web やモバイルでの発表者の参加 |&#x2714; (Skype for Business)  |&#x274C; |N/A |
|外部アクセス (フェデレーション) およびゲストの発表者/参加者 |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |N/A |
|発表者 – PSTN アクセス |&#x274C; |&#x2714; (Teams) |N/A |
|画面表示 |&#x274C; |&#x2714; (Teams) |N/A |
|Windows でのシステム音声の共有 (画面の共有時にのみ可能)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|PowerPoint 表示 (PPT 共有) |&#x2714; |&#x274C; (画面共有により軽減) |該当なし |
|クラウド ベースの会議記録 |&#x2714; |&#x2714; |&#x2714; |
|Stream への記録の自動公開 |&#x274C; |&#x274C; |&#x2714; |
|ライブ キャプションと字幕 |&#x2714; |&#x2714; |&#x274C; |
|ライブ イベント記録のキャプション |&#x2714; |&#x2714; |&#x2714; |
|出席者の DVR 制御 (一時停止、巻き戻し) |&#x2714; |&#x2714; |&#x2714; |
|eCDN のMicrosoft |&#x274C; |&#x2714; |&#x2714; |
|Partner eCDN のサポート |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|ブロードキャスト後のプロデューサー向け出席レポート |&#x2714; |&#x2714; |&#x274C; |
|視聴者の感情分析 – ライブ投票/投票 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> ライブ イベントには最大 １00 人の発表者とプロデューサーを指定することができますが、リストには最後に話した 10 人しか表示されません。

## <a name="regional-availability"></a>利用可能な地域

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> イベントの地域は、開催者と Microsoft 365 テナントの場所に応じて自動的に選択されます。

**これらの地域のデータ センターで利用可能**

- 北アメリカ
- 中央アメリカ
- 南アメリカ
- アジア太平洋
- ヨーロッパ/アフリカ

**これらの国/地域のデータの場所 (サポートされている)**

- オーストラリア
- ブラジル
- カナダ
- フランス
- ドイツ
- インド
- 日本
- ノルウェー
- シンガポール
- 南アフリカ
- 韓国
- スイス
- アラブ首長国連邦
- 英国

**除外対象と考慮事項**

- **データの場所**: 上記以外の Teams のデータの場所は、現在サポートされていません。

## <a name="next-steps"></a>次の手順

「[Microsoft Teams でのライブ イベントのセットアップ](set-up-for-teams-live-events.md)」に進みます。

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
