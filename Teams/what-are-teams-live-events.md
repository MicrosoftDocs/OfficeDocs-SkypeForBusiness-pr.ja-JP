---
title: ライブ イベントをチームは何ですか。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviwer: tonysmit
description: どのようにビデオ、およびマイクロソフトのチーム、Yammer、および Microsoft のストリームでの大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にするイベントについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4017e059f202a89451b9aad419fd007bb4758765
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "21711071"
---
# <a name="what-are-teams-live-events"></a>ライブ イベントをチームは何ですか。
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

どのようにビデオ、およびマイクロソフトのチーム、Yammer、および Microsoft のストリームでの大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にするイベントについて説明します。  

## <a name="overview"></a>概要
Microsoft 365 でのライブ イベントは、ビデオ、および大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にします。  Microsoft 365 のライブ イベントは、接続全体の契約のライフ サイクル全体を通じて参加者と、実行中に、前後のライブ イベントの促進、新たなレベルへのストリーミング ライブのビデオを表示します。 ライブ イベントを作成するには、対象ユーザー、チーム、またはコミュニティが存在する、Microsoft のストリーム、マイクロソフトのチームまたは Yammer を使用して任意の場所にします。  

マイクロソフトのチームでは、チャット ベースのコラボレーション、会議の呼び出しと、ライブ イベントと、会議の出席者を展開することができます。 マイクロソフトのチームのライブ イベントは、大規模なオンライン ユーザーにビデオ、および会議のコンテンツをブロードキャストするユーザーを有効にすると、チームの会議の拡張です。 これらは、一対多の通信の相互作用をリードしているイベントのホストと、ホストによって共有されているコンテンツを表示するのには、対象ユーザーへの参加が主な目的は場所のものです。 出席者が Yammer、チーム、および Microsoft のストリーム、ライブまたは記録されたイベントを見ることができ、モデレートの Q & A を使用して、発表者と対話できるか、Yammer の会話です。 

ライブ イベントは、次のバージョンの Skype 会議のブロードキャストと見なされ、最終的には、チームでは、Skype 会議をブロードキャストすることで提供される機能を置き換えます。 ライブ イベントのパブリック プレビュー リリースでは、マイクロソフトが新しい、または今後のイベントのサービスの中断は生じませんが、Skype 会議をブロードキャストをサポートするために継続します。 参加者の数などの画面を共有するには、新しい機能を活用してチームでのライブ イベントを試すし、エンコーダーの外部のハードウェアとソフトウェアのサポートすることをお勧めします。 

## <a name="key-components"></a>主要なコンポーネント
次の図は、Microsoft の 365 のライブ イベントに関連する高レベルのコンポーネントを示しています。 

![チームのライブ イベント](media/teams-live-events.png)

### <a name="scheduling"></a>スケジュール
チームは、開催者のアクセス許可を適切な参加者のイベントを作成する、イベントを指定するには、チーム メンバー、生産会議出席依頼方法を選択するための機能を提供します。 Yammer グループ内でのライブ イベントが作成されている場合、ライブ イベントの参加者はイベント チームとやり取りするため、Yammer の会話を使用することになります。 

### <a name="production"></a>生産
Microsoft 365 でのライブ イベントでは、多様な運用シナリオをサポートして、web カムを使用してクイック スタートのイベントまたは studio 品質の機器を使用して外部エンコーダー イベントが含まれます。 ビデオ入力、ライブ イベントの基盤でありまるちかめらの本格的なビデオ制作を 1 つの web カメラから異なることができます。 お客様は、プロジェクトの要件と予算に応じてこれらのオプションを選択できます。 
- **クイック スタート**: クイック スタートの方法により、チーム会議を使用して、ライブのイベントを生成します。 このオプションは、オーディオを使用して、ビデオ デバイスが PC に接続されているまたはリモートの発表者を招待する場合に最適とパネリストのイベントに参加しています。 このオプションでは、簡単に自分の web カムを使用し、ブロードキャストへの入力として、画面を共有することができます。 
- **エンコーダーの外部**: 外部エンコーダーが外部のハードウェアまたは Microsoft ストリームでのソフトウェア ・ ベースのエンコーダーから直接ライブのイベントを生成するユーザーを許可します。 このオプションが既にある場合 studio 品質の機器 (例: メディアのミキサー) RTMP サービス サポート ストリーミングに最適です。 このオプションは通常、メディア ミキサーから 1 つのストリームを視聴者にブロードキャスト – エグゼクティブ ・町のホールなど大規模なイベントで使用されます。 

### <a name="streaming-platform"></a>プラットフォームのストリーミング
これは、次の構成されています。

#### <a name="azure-media-services"></a>Azure のメディア サービス
[Azure のメディア サービス](https://docs.microsoft.com/en-us/azure/media-services/previous/)では、今日の最も人気のあるモバイル デバイスでの大規模な対象ユーザーに到達するのには、ブロードキャスト品質ビデオ ストリームのサービスを示します。 メディア サービスがユーザー補助の設定、配布、およびスケーラビリティを強化して、ローカルおよび世界中の対象ユーザーにコンテンツをストリーム配信を容易かつコスト ・ パフォーマンスにより、-コンテンツを保護しながら。

#### <a name="azure-content-delivery-network-cdn"></a>Azure コンテンツ配信ネットワーク (CDN)
ストリームがライブになった後、 [Azure コンテンツ配信ネットワーク (CDN)](https://docs.microsoft.com/en-us/azure/cdn/)を通じて配信されます。 Azure のメディア サービスでは、ストリーミング エンドポイントの CDN の統合を提供します。 これにより、ストリームのバッファリングのない世界中で表示するができます。 

### <a name="enterprise-content-delivery-network-ecdn"></a>エンタープライズ コンテンツ配信ネットワーク (eCDN) 
ECDN の目標は、ビデオ コンテンツをインターネットから取得し、ネットワークのパフォーマンスに影響を与えずに、企業全体でコンテンツを配布すること。 ライブ イベント用にネットワークを最適化するために、次の認定パートナーを使用できます。 
- ハイブ
- Kollective
- (準備中にクイック スタート) ランプ

### <a name="attendee-experience"></a>参加者の経験
参加者の経験は、ライブ イベントの最も重要な側面と、出席者が問題なくライブ イベントに参加できることが重要です。 参加者経験では、Azure のメディア プレーヤーを使用してし、デスクトップ、ブラウザー、およびモバイル (iOS、Android) の間で動作します。 Office 365 は、Yammer とチーム共同作業の 2 つのハブとライブの参加者としての経験に統合されているこれらのコラボレーション ツールです。 ベースの外部のエンコーダーのライブ イベントは、Microsoft ストリーム ポータルの出席者でもアクセスできます。

## <a name="prerequisites"></a>前提条件

### <a name="who-can-create-live-events"></a>ライブ イベントを作成することができます。
次の前提条件は、プレビューの時間内でライブ イベントをスケジュールするのにはユーザーの必要があります。  
- ユーザーは、Office 365 エンタープライズ E3 または E5 のライセンスを持っています。 
- マイクロソフト チーム、ビジネス オンライン、および Microsoft のストリームの Skype のユーザーになっています。
- チームでプライベートな会議のスケジュール設定をユーザーが有効になっている (TeamsMeetingPolicy AllowPrivateMeetingScheduling を True に設定します)。
- チームでのライブ イベントのスケジュールをユーザーが有効になっている (TeamsMeetingBroadcastPolicy AllowBroadcastScheduling を True に設定します)。
- ユーザーは、(外部のエンコーダーの生産) の Microsoft のストリームでのライブ イベントを作成するアクセス許可を持っています。

> [!NOTE]
> 製作者またはチームのライブ イベントで発表者として office 365 の来園者、連合、および匿名ユーザーの参加を要請することはできません。 
 
### <a name="who-can-watch-live-event"></a>ライブ イベントを監視します。
ライブ イベントに参加できるユーザーを表示するのには次の表を確認します。 

|**出席者の表示/非表示**           |**クイック スタート** |**外部エンコーダー**  |
|------------------------------|-------------|------------------|
|公開 (匿名ユーザー)      |  あり        |  なし              |
|ゲスト ユーザー *                   |  なし         |  なし              |
|連合会社 * のすべてのユーザー |  なし         |  なし              |
|会社のすべてのユーザー           |  あり        |  あり             |
|特定のグループ/ユーザー      |  あり        |  あり             |
* ゲストおよびフェデレーション ユーザーは、匿名のライブ イベントの参加者として参加できます。

運用方法によって、認証されたユーザーとして、ライブ イベントに参加するには、Office 365 のライセンスが必要です。

- **クイック スタートの生産**: ユーザーは、チームのユーザーである必要があります。
- **外部のエンコーダーの生産**: ユーザーは、ストリームのユーザーである必要があります。
 
## <a name="capabilities"></a>機能
次の表には、ライブ イベントと Skype 会議のブロードキャストとの違いで提供される中心的な機能が強調表示されます。 

|機能   |Skype 会議ブロードキャスト |チームのライブ イベント (クイック スタート) |チームのライブ イベント (外部エンコーダー) |
|---------|---------|---------|---------|
|対象ユーザーの最大サイズ |10,000 の出席者 |10,000 参加者 * |10,000 参加者 * |
|ライブ イベントの作成 |   Skype の会議のブロードキャストのポータル |チームがチームで Yammer | チームは、ストリームを使用して、チームが Yammer |
|Yammer 契約対象者 |& #x 2714 です。 |& #x 2714 です。(感) |& #x 2714 です。(感) |
|利用者の参加: モデレートの Q & A |& #x 2714 です。  |& #x 2714 です。 |& #x 2714 です。 |
|Windows 上のクライアントの生産者 |& #x 2714 です。(ビジネス用の Skype) |& #x 2714 です。(チーム) |& #x 2714 です。(ストリーム、ストリームを使用してチームを埋め込む) |
|プロデューサー クライアントを Mac に |X  | & #x 2714 です。(チーム) |& #x 2714 です。(ストリーム、ストリームを使用してチームを埋め込む) |
|プロデューサーの UI での参加者数 |X  |& #x 2714 です。(チーム) |& #x 2714 です。(ストリーム、ストリームを使用してチームを埋め込む) |
|複数の発表者は、します。 |& #x 2714 です。(ビジネス用の Skype) |& #x 2714 です。(チーム) |該当なし  |
会議中に発表者を招待します。 |& #x 2714 です。(ビジネス用の Skype) |X |該当なし |
|Web およびモバイルの発表者の参加 |& #x 2714 です。(ビジネス用の Skype)  |X |該当なし |
|発表者 – PSTN のアクセス |X |& #x 2714 です。(チーム) |該当なし |
|画面を表示します。 |X |& #x 2714 です。(チーム) |該当なし |
|(PPT の共有)、PowerPoint をプレゼンテーションします。 |& #x 2714 です。 |(画面を共有することで軽減) X |該当なし |
|クラウド ベースのミーティングのレコーディング |& #x 2714 です。 |& #x 2714 です。 |& #x 2714 です。 |
|自動記録をマイクロソフトのストリームに発行します。 |X |X |& #x 2714 です。 |
|リアルタイム キャプションと翻訳 |& #x 2714 です。 |& #x 2714 です。(準備中) |X |
|ライブ イベントの録画でキャプション |& #x 2714 です。 |& #x 2714 です。(準備中) |& #x 2714 です。 |
|出席者の DVR コントロール (一時停止、巻き戻し) |& #x 2714 です。 |& #x 2714 です。 |& #x 2714 です。 |
|パートナー eCDN のサポート |& #x 2714 です。(ハイブ、Kollective、ランプ) |& #x 2714 です。(準備中) |& #x 2714 です。(ハイブ、Kollective、ランプ) |
|生産者の後にブロードキャストの参加者のレポート |& #x 2714 です。 |& #x 2714 です。(準備中) |X |
|対象な言葉の分析: ライブ投票と投票 |& #x 2714 です。(マイクロソフトのパルス) |X |X |

* 制限は、プレビュー中に変更されること 

## <a name="planning--setup"></a>計画およびセットアップ
この資料では、組織内のチームのライブ イベントを持つユーザーをセットアップする方法について説明します。

1. ライブ イベントは、現在の領域を理解する[ライブ イベントをチームの地域の可用性](#configure-live-events)を確認してください。
2. いない場合、は、組織の[ビジネス オンラインの Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e)を設定します。
3. 参加者が企業ネットワーク内から参加する場合は、契約時と、ネットワーク帯域幅を最適化するために[eCDN、マイクロソフト推奨プロバイダーの設定](#set-up-ecdn-provider-for-teams-live-events)を検討します。 
4. [ライブ イベントを作成することができ](#who-can-create-live-events)、[ライブ イベントを監視する](#who-can-watch-live-event)ための適切なライセンスの割り当てがあることを確認します。 
5. [ライブ イベントのスケジュールを有効にする](#enable-live-event-scheduling-for-the-user)会社でのライブ イベントを作成することができるよう、ユーザーのために。 クイック スタートと外部エンコーダーのイベントの両方に必要です。 
6. 外部エンコーダーのイベントの[Microsoft ストリーム管理ポータルでのライブ イベントの作成のためのユーザーを有効に](#enable-microsoft-stream-for-users-in-the-organization)します。  

### <a name="regional-availability-for-teams-live-events"></a>チームのライブ イベントの地域の可用性
チームのライブ イベントは、複数の地域で使用できます。 次の情報は、イベント チームのメンバーと出席者の可用性を示します。 構成内容の変更、および Office 365 テナントによって、イベントの地域が自動的に選択します。

#### <a name="regions-available"></a>使用可能な領域
- 南北アメリカ
- ヨーロッパとアフリカ
- アジア太平洋地域

#### <a name="exclusions"></a>除外リスト
- [ローカル] に移動します。
  - 英国、インド、およびその他のマイクロソフト チームに [ローカル] は現在サポートされていません。
- ローカル - カナダを移動します。 
  - プレビューでは、お客様がイベントを作成できますが、北米地域内のデータが所属します。
- 中国
  - イベント チームのメンバーと参加者を Azure CDN アクセスできないため、中国でには、チームのライブ イベントを使用することができなきます。 回避策では、会社の VPN 接続は、お客様の企業ネットワークを使用して、CDN に接続されているクライアントの取得を使用します。

### <a name="set-up-your-network-for-live-events-in-microsoft-teams"></a>マイクロソフトのチームでのライブ イベント用にネットワークを設定します
クイック スタートのライブ イベントでは、[マイクロソフトのチームの組織のネットワークを準備](https://docs.microsoft.com/en-us/microsoftteams/prepare-network)するのには必要です。  

クイック スタートと外部エンコーダーの両方のライブ イベント、Url、IP アドレス、ポート、およびチームとストリームを正しく構成する必要があるプロトコルの詳細で最新の状態の一覧については、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を移動します。 マイクロソフトが継続的に Office 365 のサービスを向上させることし、新しい機能を追加するには、必要なポート、Url、つまり時間の経過と共に IP アドレスを変更することがあります。 この情報を更新または変更されたときに通知を受信する RSS 経由で購読することをお勧めします。

### <a name="set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>マイクロソフトのチームでのライブ イベントの eCDN のプロバイダーを設定します 
適応のビットレート (ABR) のストリーミングを使用して、ライブ イベントのビデオの再生は、ユニキャスト ストリーム、つまり、万人がインターネットから自分のビデオ ストリームを取得します。 ライブ イベントや、組織の大部分に送信されるビデオは、膨大なインターネットの帯域幅のあるユーザーによって消費されている可能性があります。  ライブ イベントの場合は、このインターネット トラフィックを削減する組織では、マイクロソフトのソリューションは、統合のライブ イベントでは、ソフトウェアを提供するビデオの配信パートナーには、ネットワーク (SDNs) またはエンタープライズ ・ コンテンツ配信ネットワーク (eCDNs) が定義されている信頼されています。 これらの SDN/eCDN ・ プラットフォームを犠牲にエンド ユーザー エクスペリエンスを表示することがなくネットワークの帯域幅を最適化するために組織を有効化します。 パートナーは、エンタープライズ ネットワーク上よりスケーラブルで効率的なビデオ配信を有効にするに役立ちます。

#### <a name="purchase--setup-your-solution-outside-of-microsoft-teams"></a>購入すると、マイクロソフトのチーム以外で、ソリューションのセットアップ
マイクロソフトのビデオ配信を信頼できるパートナーを活用することでビデオの配信を拡大・縮小で専門的なヘルプを取得します。  前に、購入して、外部とマイクロソフトのチームとは別に SDN と eCDN ソリューションをセットアップする必要があります、マイクロソフトのチームで使用するビデオ配信プロバイダーを有効にできます。

次の SDN と eCDN ソリューションは、事前統合されてし、Microsoft のストリームで使用する設定をすることができます。 次のプロバイダーからの情報を参照してください。

ハイブのストリーミングは、ライブおよびオンデマンドのエンタープライズ ビデオ配信のシンプルかつ強力なソリューションを提供します。 ハイブは、追加のハードウェアや帯域幅は必要ありませんし、何千ものネットワークに影響を与えず、同時のビデオ ビューアーを有効にするセキュリティで保護された方法を提供するソフトウェア ・ ベースのソリューションです。 お客様への影響のビデオが、SDN と eCDN ソリューションを購入する前に、ネットワーク上にあるを理解して、ハイブのストリーミングが用意されていますブラウザ ・ ベースの分析ソリューション マイクロソフト ユーザーの場合。 [詳細情報](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
Kollective のクラウド ベースのスマートのピアリング配布プラットフォームは、さまざまな形式でコンテンツを配信 (ライブのストリーミング ・ ビデオ、オンデマンド ビデオ、ソフトウェアの更新プログラム、セキュリティ修正プログラムなど) には、既存のネットワーク インフラストラクチャを活用してより速くより信頼性の高いで帯域幅が小さくします。 ハードウェアの追加と、世界最大の金融機関によって信頼されている、セキュリティで保護されたプラットフォームでは、セットアップと保守が容易です。 [詳細情報](http://www.kollective.com)
 
ランプ OmniCache は、次世代ネットワークの配分を提供し、グローバル Wan 経由でビデオ コンテンツのシームレスな配信を保証する、イベントの製作者を支援するネットワーク帯域幅を最適化し、成功したライブ イベントのブロードキャストし、オンデマンドのストリーミングをサポートしては。 ランプの OmniCache のライブ イベントのクイック スタートのサポートを準備中です。  [詳細情報](http://www.ramp.com) 
 
[!NOTE] 選択した eCDN ソリューションは、選択した[サード パーティ プロバイダーのサービスとプライバシーのポリシー条件]()、eCDN プロバイダーのソリューションの使用を制御しますがします。 マイクロソフト ボリューム ライセンス契約の条項またはオンライン サービスの条件は、eCDN プロバイダーのソリューションを使用することはできません。 [サード パーティ プロバイダーの条件]()に同意しない場合、有効にしないで eCDN ソリューションは、マイクロソフトのチーム、です。 

#### <a name="configure-ecdn-for-quick-start-live-events"></a>「クイック スタート」のライブ イベント eCDN を構成します。 
PowerShell を使用してマイクロソフトのチームでは、ライブ イベントの eCDN のプロバイダーを構成できます。 注: 1 つの eCDN ・ プロバイダーのみを構成できます、テナントの任意の時点で。 

**ハイブ eCDN プロバイダーを構成します。** 

[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 
1. ハイブ相手からライセンス ID と API テンプレートの URL を取得します。 
2. 次の PowerShell コマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```

**Kollective eCDN プロバイダーを構成します。** 

[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 
1. Kollective 連絡先から API トークンおよび API のテンプレートの URL を取得します。 
2. 次の PowerShell コマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```

**ランプ eCDN プロバイダーを構成します。**

#### <a name="configure-ecdn-for-external-encoder-live-events"></a>「外部エンコーダー」のライブ イベント eCDN を構成します。 
外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを構成する](https://docs.microsoft.com/stream/network-caching)にもする必要があります。 「クイック スタート」を通じてマイクロソフトのチームまたは Yammer のライブ イベントを作成する場合は、マイクロソフト チームと同様に統合するには、SDN と eCDN のプロバイダーを構成する必要があります。

### <a name="enable-live-event-scheduling-for-the-user"></a>ユーザーのライブ イベントのスケジュール設定を有効にします。
チームのユーザーの既定では、ライブ イベントのスケジュールが有効になっています。  

チーム PowerShell の TeamsMeetingBroadcastPolicy の AllowBroadcastScheduling コントロールの設定を使用して、ユーザーは、かに、チームでのライブ イベントを作成できるかどうか。 Office 365 の PowerShell での TeamsMeetingBroadcastPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーはグローバル ポリシーは既定で有効になっている記録を取得します。 

 グローバル ポリシーにフォールバックするのにユーザー、ユーザーの特定のポリシーの割り当てを削除するのには次のコマンドレットを使用します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
グローバル ポリシーで AllowBroadcastScheduling の値を変更するには、次のコマンドレットを使用します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="scenarios"></a>Scenarios
**ライブ イベントを作成できるようにするには自分の会社ですべてのユーザーを必要とします。**
1. 確認するグローバル CsTeamsMeetingBroadcastPolicy AllowBroadcastScheduling = True です。
2. すべてのユーザーあるグローバルの CsTeamsMeetingBroadcastPolicy または AllowBroadcastScheduling と CsTeamsMeetingBroadcastPolicy のポリシーのいずれかを確認して指定します。

**ライブのイベントを作成できるようにするユーザーの大半が選択的に無効にする特定のユーザーに許可されていないします。**
1. 確認するグローバル CsTeamsMeetingBroadcastPolicy AllowBroadcastScheduling = True です。
2. 大半のユーザーがあるグローバルの CsTeamsMeetingBroadcastPolicy または AllowBroadcastScheduling と CsTeamsMeetingBroadcastPolicy のポリシーのいずれかを確認 = True です。
3. AllowBroadcastScheduling と CsTeamsMeetingBroadcastPolicy のポリシーのいずれかの他のすべてのユーザーが許可されてことを確認 = False です。

**ライブ イベントを 100% 無効にするスケジュールを設定します。**
1. 確認するグローバル CsTeamsMeetingBroadcastPolicy AllowBroadcastScheduling = False です。
2. すべてのユーザーにグローバル CsTeamsMeetingBroadcastPolicy または CsTeamsMeetingBroadcastPolicy のポリシーの 1 つに AllowBroadcastScheduling を与えたことを確認 = False です。

**ライブのイベントを無効にするか、ユーザーの大多数が、ライブ イベントに特定のユーザーを選択して有効にします。** 
1. 確認するグローバル CsTeamsMeetingBroadcastPolicy AllowBroadcastScheduling = False です。
2. 大多数のユーザーが与えられてグローバル CsTeamsMeetingBroadcastPolicy または CsTeamsMeetingBroadcastPolicy のポリシーのいずれかの AllowBroadcastScheduling を持つことを確認 = False です。
3. AllowBroadcastScheduling と CsTeamsMeetingBroadcastPolicy のポリシーのいずれかの他のすべてのユーザーが許可されてことを確認 = True です。

### <a name="enable-creation-of-external-encoder-based-live-events-for-users"></a>エンコーダーに基づくユーザーのライブ イベントを外部の作成を有効にします。

#### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>組織内のユーザーに対して Microsoft ストリームを有効にします。
Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。 詳細については、[ストリームのライセンスの概要](https://docs.microsoft.com/en-us/stream/license-overview)を参照してください。 注 Microsoft ストリームは、ビジネスに関する重要事項またはビジネス プレミアム プランには含まれません。  

方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。 [この資料](https://docs.microsoft.com/en-us/stream/disable-user-organization)で定義されているユーザーの Microsoft のストリームがブロックされていないことを確認します。

#### <a name="ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>ユーザーは、Microsoft ストリームでライブ イベントの作成のアクセス許可を持っていることを確認します。
既定で、ストリームで指定されたコンテンツを作成して、ストリームが有効になっているし、ライセンスがユーザーに割り当てられている会社内のすべてのユーザーできます。 Microsoft ストリームの管理者は、ストリーム内の[コンテンツを作成するための従業員を制限する](https://docs.microsoft.com/en-us/stream/restrict-uploaders)ことができます。 この制限の一覧にあるユーザーはミーティングを記録することができません。

#### <a name="ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>ライブ イベントを開催者がストリームの管理で設定する会社のポリシーに同意したがあることを確認します。
Microsoft ストリームには、管理者[、会社のガイドラインのポリシーを設定する](https://docs.microsoft.com/en-us/stream/company-policy-and-consent)には、従業員がコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますし、ユーザーする必要がありますようにマイクロソフトのチームで (外部のエンコーダーの生産) でのライブ イベントを作成する前にします。 組織でのライブ イベントの機能をロールアウトする前にこれらのライブ イベントを作成するユーザーは、ポリシーに同意したがいることを確認します。 

## <a name="configure-live-events"></a>ライブ イベントを構成します。

### <a name="set-up-event-support-link-coming-soon"></a>(準備中) イベントのサポートのリンクを設定します。
これは、ライブ イベントの参加者に表示されるリンクです。 

PowerShell

Windows PowerShell のでは、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
### <a name="configure-attendee-visibility-options"></a>出席者の表示/非表示のオプションを構成します。
これにより、適切な参加者の可視性を持つイベントを作成するライブ イベントを開催します。

|**値**  |**動作**  |
|---------|---------|
|全員     |ライブ イベントを次の出席者の可視性を作成するオプションをユーザーが持っている: 会社、および特定のユーザーのすべてのメンバーを公開します。 |
|EveryoneInCompany     |ユーザーは、ライブ イベントを次の出席者の可視性を作成するオプションを持っている: 会社および特定のユーザーのすべてのメンバーです。 ユーザーは、匿名ユーザーが参加できるライブ イベントを作成できません。|
|InvitedUsers |ユーザーは、イベント開催者によって入力されたとおりに、特定の人に制限されているライブのイベントのみを作成できます。 ユーザーは、公開キーと認証の会社のすべてのメンバーでライブ イベントを作成できません。 |

PowerShell

ユーザーが匿名の参加者を監視することができますブロードキャストのイベントのスケジュールを設定するかどうかは、PowerShell の TeamsMeetingBroadcastPolicy の BroadcastAttendeeVisibility コントロールの設定を使用します。 ここで Office 365 の PowerShell での TeamsMeetingBroadcastPolicy を管理する方法の詳細については。  

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、EveryoneInCompany に設定する既定値を保持するグローバル ポリシーを取得します。 
 
Windows PowerShell のでは、グローバル ポリシーで匿名イベントを作成するようにするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>レコーディングのオプションを構成します。
> [!NOTE]
> このオプションは、クイック スタートの運用方法のみを使用するイベントに適用されます。

これにより、ライブ イベントは、常に記録、記録されることはないかどうか、またはイベントの開催者は、かのイベントが記録することができるかどうか制御する管理者です。  

|**値**  |**動作**  |
|---------|---------|
|常に有効になっています。 |このユーザーごとのライブ イベントは、常に記録されます。 ユーザーには、オーバーライドするためのオプションを持っていません。 ライブのイベントが記録される場合は、イベントのチーム メンバーは、イベントの後にレコーディングをダウンロードすることと出席者は、イベント終了後のイベントを監視できます。 |
|AlwaysDisabled |このユーザーが開催するライブ イベントが記録されることはありません。 ユーザーには、オーバーライドするためのオプションを持っていません。 ライブのイベントが記録される場合は、イベント チームのメンバーの記録は作成されず、出席者はイベントが上にあるを見ることはできません。 |
|UserOverride |ユーザーは、イベント チームのメンバーの記録ファイルを作成することができ、参加者は、イベント終了後のイベントを監視できますので、ライブ イベントが記録されるかどうかを決定できます。 |

PowerShell

コントロールのライブ イベントの開催者によって作成されたライブ イベントのオプションを記録する PowerShell の TeamsMeetingBroadcastPolicy で BroadcastRecordingMode の設定を使用します。

Windows PowerShell のでは、グローバル ポリシーでの記録モードを更新するのには次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>(準備中) チームのライブ イベントのリアルタイム議事録を作成し、変換を構成します。
> [!NOTE]
> このオプションは、クイック スタートの運用方法のみを使用するイベントに適用されます。

これにより、リアルタイムのキャプションとライブ イベントの出席者に対して変換を有効にするのにはライブ イベントを開催します。 

PowerShell

ライブ イベントの参加者が議事録と翻訳を参照してくださいできるかどうかにコントロールする PowerShell の TeamsMeetingBroadcastPolicy で AllowBroadcastTranscription の設定を使用します。 ここで Office 365 の PowerShell での TeamsMeetingBroadcastPolicy を管理する方法の詳細については。  

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーが議事録と翻訳が既定で無効になっているは、グローバル ポリシーを取得します。

Windows PowerShell では、[グローバル ポリシーでの議事録やイベントの出席者のために翻訳を有効にするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="self-service-administration-tools"></a>セルフ サービス管理ツール 
直接 Microsoft は、Office 365 のオンラインのすべてのデータ センターを制御し、システム全体のパフォーマンスは、ですが、Office 365 のユーザーの合計の経験を提供する要素の一部だけを制御できます。 組織自体は、データ センターでお客様のワイド エリア ネットワーク (WAN)、ネットワーク接続を担当し、お客様のローカル エリア ネットワーク (Lan)。 さらに、ユーザーのデバイスとその構成を担当しています。必要なライセンスなど、必要な機能は、ユーザーごとの管理を担当する、マイクロソフトが、ユーザーは、機能へのアクセスを必要がある限りのこれらの機能を管理することに。

お客様は、さまざまなチームのライブ イベントの関連タスクを管理するために次のツールを使用できます。
- [Microsoft Office 365 管理者センター](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [マイクロソフトのチームと Skype のオンライン ビジネスの管理センター](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Microsoft ストリーム管理センター
- [リモートの Windows PowerShell の](https://technet.microsoft.com/en-us/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
- に関して Windows PowerShell は、it のすべてのユーザーを管理するか、ユーザーの許可を許可します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)


### <a name="related-topics"></a>関連トピック: 

- [Yammer、マイクロソフトのチーム、および Microsoft のストリーム内の Microsoft 365 の間でのライブ イベント](https://docs.microsoft.com/stream/live-event-m365)
- [マイクロソフトのチームでのライブ イベント](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer のライブ イベント](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft ストリームでのライブ イベント](https://review.docs.microsoft.com/stream/live-event-overview)