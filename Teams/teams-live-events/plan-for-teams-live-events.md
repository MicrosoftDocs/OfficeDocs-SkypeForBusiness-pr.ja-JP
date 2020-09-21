---
title: Microsoft Teams でのライブ イベントの計画
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: この記事では、Microsoft Teams でのライブ イベントを立ち上げる前に考慮すべき要素について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 61f929452f26bd83b5d4deea93113f9edac29e26
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962818"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams でのライブ イベントの計画

組織で大規模な会議を開催するために Teams のライブイベントを計画している場合、そのイベントを立ち上げる前にいくつかの要素を考慮する必要があります。

 > [!Note]
> 別のプラットフォームでの Teams のライブ イベントについての詳細は、 [プラットフォームごとの Teams の機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)を参照してください。

## <a name="who-can-attend-create-and-schedule-live-events"></a>ライブ イベントに参加、およびライブ イベントを作成、スケジュールできるのは誰か。

誰でも、ライセンスなしでライブ イベントに参加できます。 [管理クイック スタート - 会議とライブ イベント](../quick-start-meetings-live-events.md)をお読みください。

ユーザーが Teams ライブ イベントをスケジュールするには、次の前提条件を満たす必要があります。

Teams ライブ イベントを作成または表示するために割り当てる必要があるライセンスは次のとおりです。  

- Microsoft 365 Enterprise E1、E3、E5 のいずれかのライセンス、または Office 365 Education A3 または A5 ライセンスがある。
- Microsoft Teams のライセンス。 - これは上記のライセンスに含まれています。 
- コンテンツを外部のアプリまたはデバイスと共有する場合は、Microsoft Stream のライセンスが必要です。「[Microsoft Stream のライセンス](https://docs.microsoft.com/stream/license-overview)」をご覧ください。 

  ユーザーに録音とそれのダウンロードのみを許可する場合は、Microsoft Stream のライセンスを割り当てる必要はありません。 つまり、録音は Microsoft Stream に保存されず、削除されるまでの 30 日間の制限付きで Azure Media Services (AMS) に保存されます。 現時点では、削除機能を含め、管理者が制御または管理できるものではありません。

> [!NOTE]
> 現時点では、Teams ライブ イベントの作成と開催に使用できる Microsoft 365 Small Business プランはありません。

認証されたユーザーとしてライブ イベントに参加するのに、Microsoft 365 または Office 365 のライセンスが必要であることを理解することは重要ですが、この要件は使用する作成方法によって異なります。

- **Teams で作成したイベントの場合**、ユーザーには Teams のライセンスが割り当てられている必要があります。
- **外部アプリまたはデバイスで作成したイベントの場合**、ユーザーには Stream のライセンスが割り当てられている必要があります。

> [!NOTE]
> Teams のライブ イベントは、米国政府機関クラウド コミュニティ (GCC) 組織で利用できるようになりました。

ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)」を参照してください。

ユーザーには以下が設定されている必要があります。

- Teams でのプライベート会議のスケジューリングが有効である (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling パラメーター = True*)。
- Teams 会議で有効なビデオ共有 (*TeamsMeetingPolicy -AllowIPVideo パラメーター = True*)。
- Teams 会議で有効な画面共有 (*TeamsMeetingPolicy -ScreenSharingMode パラメーター = EntireScreen*)。
- Teams でのライブ イベントのスケジューリングが有効である (*The TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling パラメーター = True*)。
- Stream でライブ イベントを作成する許可 (外部アプリまたはデバイス生成の場合)。
- Teams 会議をスケジュールできるように構成された共存モード (*アイランド、会議優先、または Teams のみ*)。

> [!IMPORTANT]
> 認証されていない匿名ユーザーは、Teams ライブ イベントのプロデューサーや発表者としては招待できません。

ゲストがライブイベントに表示されるようにするには、次の操作を行います:

1. [ユーザーをゲストとしてチームに追加します](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. ユーザーにゲストの招待を承諾してチームに参加してもらいます。
3. [ライブイベントをスケジュールし、ゲストをイベントグループに追加します](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

ベストプラクティスとして、ライブイベントのプロデューサーと発表者がイベントの前にチャットして情報を共有できるように、チャネルを作成することをお勧めします。 Microsoft 365 の資格情報を持たないゲストには、Teams の予定表は表示されません。 簡単にイベントに参加できるように、プロデューサーはイベントリンクをチャネルに投稿できます。 発表者は、Teams を開いてチャネルに移動し、リンクをクリックしてイベントに参加できます。 

## <a name="who-can-watch-live-events"></a>ライブ イベントは誰が視聴できるか。

|**出席者の表示/非表示**       |**チームの生成**  |**外部アプリまたはデバイス生成**  |
|------------------------------|-----------------|----------------------|
|パブリック (匿名ユーザー)      |  はい            |  いいえ                  |
|ゲスト ユーザー                   |  はい            |  いいえ                  |
|外部アクセス (フェデレーション) のある会社のすべてのユーザー |  Yes<sup>1</sup>|  いいえ                  |
|会社内の全員           |  はい            |  はい                 |
|特定のグループ/ユーザー      |  はい            |  はい                 |

<sup>1</sup> 外部アクセス (フェデレーション) 参加者は、[ユーザー] と [グループ] からのみ招待することができます <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams ライブ イベントと Skype 会議ブロードキャスト

次の表に、ライブ イベントで提供されるコア機能と特徴、および Skype 会議ブロードキャストとの相違点を示します。

> [!IMPORTANT]
> **Microsoft 365 ライブ イベントの上限の引き上げ**
> 
> お客様が急速に変化するコミュニケーションのニーズに対応できるように、Microsoft 365 ライブ イベントは、2020 年 7 月 1 日まで、Teams でホストされるライブ イベントの既定の上限を一時的に引き上げます。 2020 年 4 月下旬から次の上限が適用されるようになります。
> - 参加者の制限: イベントは最大 20,000 人の参加者をサポートできます
> - 同時イベント: テナント全体で 50 のイベントを同時にホストできます
> - イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました

|**機能**   |**Skype 会議ブロードキャスト** |**Teams で生成されたイベント** |**外部アプリまたはデバイスで作成されたイベント** |
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
|会議中の発表者の招待 |&#x2714; (Skype for Business) |&#x274C; |該当なし |
|Web やモバイルでの発表者の参加 |&#x2714; (Skype for Business)  |&#x274C; |N/A |
|外部アクセス (フェデレーション) およびゲストの発表者/参加者 |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |該当なし |
|発表者 – PSTN アクセス |&#x274C; |&#x2714; (Teams) |N/A |
|画面表示 |&#x274C; |&#x2714; (Teams) |N/A |
|Windows でのシステム音声の共有 (画面の共有時にのみ可能)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|PowerPoint 表示 (PPT 共有) |&#x2714; |&#x274C; (画面共有により軽減) |該当なし |
|クラウド ベースの会議記録 |&#x2714; |&#x2714; |&#x2714; |
|Stream への記録の自動公開 |&#x274C; |&#x274C; |&#x2714; |
|ライブ キャプションと字幕 |&#x2714; |&#x2714; |&#x274C; |
|ライブ イベント記録のキャプション |&#x2714; |&#x2714; |&#x2714; |
|出席者の DVR 制御 (一時停止、巻き戻し) |&#x2714; |&#x2714; |&#x2714; |
|Partner eCDN のサポート |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|ブロードキャスト後のプロデューサー向け出席レポート |&#x2714; |&#x2714; |&#x274C; |
|視聴者の感情分析 – ライブ投票/投票 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 設定されている制限が変更される場合があります。 「[Teams の制限と仕様](../limits-specifications-teams.md)」を確認してください。<br/>
<sup>2</sup> ライブ イベントには最大 250 人の発表者とプロデューサーを指定することができますが、リストには最後に話した 10 人しか表示されません。

## <a name="regional-availability"></a>利用可能な地域

世界中の複数の地域で Teams ライブ イベントを使用できます。 次に、イベント チームのメンバーと出席者向けの利用状況を示します。

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
- カナダ
- インド
- 日本
- 英国

**これらの国/地域およびクラウドはサポートされていません**
- ドイツ
- フランス
- ノルウェー
- 南アフリカ
- 韓国
- スイス
- アラブ首長国連邦
- Government Community Cloud (GCC)-H
- DOD

**除外対象と考慮事項**

- **データの場所**: 上記以外の Teams のデータの場所はサポートされていません。
- **中国:** 中国では Azure CDN にアクセスできないため、イベント チームのメンバーと出席者は Teams ライブ イベントを使用できません。 企業の VPN 接続を使用して、顧客の企業ネットワーク経由でクライアントを CDN に接続することにより、これを回避できます。

## <a name="next-steps"></a>次のステップ

「[Microsoft Teams でのライブ イベントのセットアップ](set-up-for-teams-live-events.md)」に進みます。

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
