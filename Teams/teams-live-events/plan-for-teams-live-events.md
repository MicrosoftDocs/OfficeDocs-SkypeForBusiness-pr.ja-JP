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
ms.openlocfilehash: c0246a8517035ab5edd347fef30ae3f86af4afd9
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903082"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams でのライブ イベントの計画

組織で大規模な会議を開催するために Teams のライブイベントを計画している場合、そのイベントを立ち上げる前にいくつかの要素を考慮する必要があります。

## <a name="who-can-attend-create-and-schedule-live-events"></a>ライブ イベントに参加、およびライブ イベントを作成、スケジュールできるのは誰か。

誰でも、ライセンスなしでライブ イベントに参加できます。 [管理クイック スタート - 会議とライブ イベント](../quick-start-meetings-live-events.md)をお読みください。

ユーザーが Teams ライブ イベントをスケジュールするには、次の前提条件を満たす必要があります。

以下に、割り当てられる必要のあるライセンスを示します。  

- Office 365 Enterprise E1、E3、E5 のいずれかのライセンス、または Office 365 A3 または A5 ライセンス
- Microsoft Teams のライセンス
- Microsoft Stream のライセンス

> [!IMPORTANT]
> ライブ イベントを作成およびスケジュール設定するユーザーには、Exchange Online のメールボックスが必要です。

認証されたユーザーとしてライブ イベントに参加するのに、Office 365 のライセンスが必要であることを理解することは重要ですが、この要件は使用する作成方法によって異なります。

- **Teams で作成したイベントの場合**、ユーザーには Teams のライセンスが割り当てられている必要があります。
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

|**機能**   |**Skype 会議ブロードキャスト** |**Teams で生成されたイベント** |**外部アプリまたはデバイスで作成されたイベント** |
|---------|---------|---------|---------|
|最大視聴者数 |出席者 10,000 名 |出席者 10,000 名 <sup>1</sup> |出席者 10,000 名 <sup>1</sup> |
|ライブ イベントの最大期間 |4 時間 |4 時間 |4 時間 |
|ライブ イベントの発表者とプロデューサーの最大数 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Office 365 組織ごとの同時ライブ イベントの最大数 |15  | 15  | 15  |
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
|Partner eCDN のサポート |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |
|ブロードキャスト後のプロデューサー向け出席レポート |&#x2714; |&#x2714; |&#x274C; |
|視聴者の感情分析 – ライブ投票/投票 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 設定されている制限が変更される場合があります。 「[Teams の制限と仕様](../limits-specifications-teams.md)」を確認してください。<br/>
<sup>2</sup> ライブ イベントには最大 250 人の発表者とプロデューサーを指定することができますが、リストには最後に話した 10 人しか表示されません。

## <a name="regional-availability"></a>利用可能な地域

世界中の複数の地域で Teams ライブ イベントを使用できます。 次に、イベント チームのメンバーと出席者向けの利用状況を示します。

> [!IMPORTANT]
> イベントの地域は、開催者と Microsoft 365 または Office 365 に応じて自動的に選択されます。

**利用可能な地域**

- 南北アメリカ
- ヨーロッパ/アフリカ
- アジア太平洋
- カナダ、インド、オーストラリア、日本、英国のデータの場所

**除外対象と考慮事項**

- **データの場所**: 上記以外の Teams のデータの場所はサポートされていません。
- **中国:** 中国では Azure CDN にアクセスできないため、イベント チームのメンバーと出席者は Teams ライブ イベントを使用できません。 企業の VPN 接続を使用して、顧客の企業ネットワーク経由でクライアントを CDN に接続することにより、これを回避できます。

## <a name="next-steps"></a>次のステップ

「[Microsoft Teams でのライブ イベントのセットアップ](set-up-for-teams-live-events.md)」に進みます。

### <a name="related-topics"></a>関連項目

- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)
