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
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams でのライブ イベントを立ち上げる前に考慮する必要のある要素について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f0c141751a9b67a47640ba5210c3cb7aeeadbb2
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558567"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Microsoft Teams でのライブ イベントの計画

組織で大規模な会議を開催するためにチームのライブイベントを計画している場合、すべての設定を始める前に考慮する必要がある要素がいくつかあります。 

## <a name="who-can-create-and-schedule-live-events"></a>ライブ イベントの作成とスケジュールを誰が行えるか。 
ユーザーが Teams ライブ イベントをスケジュールするには、次の前提条件を満たす必要があります。

以下に、割り当てられる必要のあるライセンスを示します。  
- Office 365 Enterprise E1、E3、または E5 ライセンス、または Office 365 A3 または A5 ライセンス
- Microsoft Teams ライセンス
- Microsoft Stream ライセンス

> [!IMPORTANT]
> ライブイベントを作成してスケジュールするユーザーには、Exchange Online メールボックスが必要です。

認証済みのユーザーとしてライブイベントに参加するには、Office 365 ライセンスが必要であることを知っておく必要がありますが、この要件は、使用されている運用方法によって異なります。

- **Teams で作成されたイベントの場合** ユーザーには Teams ライセンスが割り当てられている必要があります。
- **外部アプリまたはデバイスで生成されたイベントの場合**ユーザーには、ストリームライセンスが割り当てられている必要があります。

> [!NOTE]
> Teams ライブイベントは、米国政府機関向けクラウドコミュニティ (GCC) 組織で利用できるようになりました。

ライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

ユーザーには以下が設定されている必要があります。
- Teams でのプライベート会議のスケジューリングが有効である (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling パラメーター = True*)。
- Teams 会議で有効なビデオ共有 (*TeamsMeetingPolicy -AllowIPVideo パラメーター = True*)。
- Teams 会議で有効な画面共有 (*TeamsMeetingPolicy -ScreenSharingMode パラメーター = EntireScreen*)。
- Teams でのライブ イベントのスケジューリングが有効である (*The TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling パラメーター = True*)。
- ストリームでライブイベントを作成する権限 (外部アプリまたはデバイスの生産の場合)。

> [!IMPORTANT]
> 認証されていない匿名ユーザーは、Teams live イベントのプロデューサーまたは発表者として招待することはできません。 
 
## <a name="who-can-watch-live-events"></a>ライブ イベントは誰が視聴できるか。

|**出席者の表示/非表示**       |**Teams の生産**  |**外部アプリまたはデバイスの製造工程**  |
|------------------------------|-----------------|----------------------|
|パブリック (匿名ユーザー)      |  はい            |  いいえ                  |
|ゲスト ユーザー                   |  いいえ<sup>1</sup> |  いいえ                  |
|フェデレーション企業内の全員 |  <sup>2</sup> |  いいえ                  |
|会社内の全員           |  Yes            |  はい                 |
|特定のグループ/ユーザー      |  はい            |  はい                 |

live イベントが**組織全体**のオプションを使って設定されている場合、 <sup>1</sup>はライブイベントを監視できます。<br>
<sup>2</sup>ライブイベントは、匿名ユーザーとしてのみ見ることができます。

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams ライブ イベントと Skype 会議ブロードキャスト

次の表に、ライブ イベントで提供されるコア機能と特徴、および Skype 会議ブロードキャストとの相違点を示します。 

|**機能**   |**Skype 会議ブロードキャスト** |**Teams で作成されたイベント** |**外部アプリまたはデバイスで作成されたイベント** |
|---------|---------|---------|---------|
|最大視聴者数 |出席者 10,000 名 |1万出席者<sup>1</sup> |1万出席者<sup>1</sup> |
|ライブ イベントの最大期間 |4 時間 |4 時間 |4 時間 |
|Office 365 テナントあたりの同時ライブイベントの最大数 |マート  | マート  | マート  |
|ライブ イベントの作成 |   Skype 会議ブロードキャスト ポータル |Teams、Teams 経由の Yammer | Teams、Teams 経由の Yammer、Stream |
|視聴者のエンゲージメント – Yammer |&#x2714; |&#x2714; (統合エクスペリエンス) |&#x2714; (統合エクスペリエンス) |
|視聴者のエンゲージメント – モデレート Q & A |&#x2714;  |&#x2714; |&#x2714; |
|Windows でのプロデューサー クライアント |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|Mac でプロデューサー クライアント |X  | &#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|プロデューサー UI での出席者数 |X  |&#x2714; (Teams) |&#x2714; (Stream、埋め込み Stream 経由の Teams) |
|複数の発表者の許可 |&#x2714; (Skype for Business) |&#x2714; (Teams) |該当なし  |
|会議中の発表者の招待 |&#x2714; (Skype for Business) |X |N/A |
|Web やモバイルでの発表者の参加 |&#x2714; (Skype for Business)  |X |該当なし |
|フェデレーションおよびゲストの発表者/出席者 |&#x2714; (Skype for Business)  | (近日公開) |該当なし |
|発表者 – PSTN アクセス |X |&#x2714; (Teams) |該当なし |
|画面表示 |X |&#x2714; (Teams) |該当なし |
|PowerPoint (PPT 共有) を表示する |&#x2714; |X (画面共有により軽減) |N/A |
|クラウド ベースの会議記録 |&#x2714; |&#x2714; |&#x2714; |
|ストリームにレコーディングを自動発行する |X |X |&#x2714; |
|ライブキャプションと字幕 |&#x2714; |&#x2714; |X |
|ライブ イベント記録のキャプション |&#x2714; |&#x2714; |&#x2714; |
|出席者の DVR 制御 (一時停止、巻き戻し) |&#x2714; |&#x2714; |&#x2714; |
|Partner eCDN のサポート |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |
|ブロードキャスト後のプロデューサー向け出席レポート |&#x2714; |&#x2714; |X |
|視聴者の感情分析 – ライブ投票/投票 |&#x2714; (Microsoft Pulse) |X |X |

<sup>1</sup>設定された制限が変更される場合があります。

## <a name="regional-availability"></a>利用可能な地域
世界中の複数の地域で Teams ライブ イベントを使用できます。 次に、イベント チームのメンバーと出席者向けの利用状況を示します。 

> [!IMPORTANT]
> イベントの地域は、開催者と Office 365 組織に応じて自動的に選択されます。

**利用可能な地域**
- 南北アメリカ
- ヨーロッパ/アフリカ
- アジア太平洋
- 国内カナダ、インド、オーストラリア、日本、イギリスに移動

**除外対象と考慮事項**
- **ローカルに移動:** Teams の [ローカル] は、現在はサポートされていません。
- **中国:** 中国では Azure CDN にアクセスできないため、イベント チームのメンバーと出席者は Teams ライブ イベントを使用できません。 企業の VPN 接続を使用して、顧客の企業ネットワーク経由でクライアントを CDN に接続することにより、これを回避できます。

## <a name="next-steps"></a>次のステップ
「[Microsoft Teams でのライブ イベントのセットアップ](set-up-for-teams-live-events.md)」に進みます。

### <a name="related-topics"></a>関連項目
- [Teams のライブ イベントについて](what-are-teams-live-events.md)
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
- [Teams でライブ イベント設定を構成する](configure-teams-live-events.md)

