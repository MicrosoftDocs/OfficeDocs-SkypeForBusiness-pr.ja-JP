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
ms.openlocfilehash: b545f0b151c9d23d22f165c475aa972cc9f89ec4
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "22196100"
---
# <a name="what-are-teams-live-events"></a>ライブ イベントをチームは何ですか。
> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview"></a>概要
Microsoft 365 でのライブ イベントは、ビデオ、および大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にします。 Microsoft 365 のライブ イベントは、接続全体の契約のライフ サイクル全体を通じて参加者と、実行中に、前後のライブ イベントの促進、新たなレベルへのストリーミング ライブのビデオを表示します。 Yammer または対象ユーザー、チーム、またはコミュニティが存在する、Microsoft のストリーム、マイクロソフトのチームを使用して任意の場所には、ライブ イベントを作成できます。  

チャット ベースのコラボレーション、通話、会議、マイクロソフトのチームが実現し、ライブ イベントと、会議の出席者を展開することができます。 マイクロソフトのチームのライブ イベントは、大規模なオンライン ユーザーにビデオ、および会議のコンテンツをブロードキャストするユーザーを有効にすると、チームの会議の拡張です。 これらは、一対多の通信の相互作用をリードしているイベントのホストと、ホストによって共有されているコンテンツを表示するのには、対象ユーザーへの参加が主な目的は場所のものです。 出席者が Yammer、チーム、および Microsoft のストリーム、ライブまたは記録されたイベントを見ることができ、モデレートの Q & A を使用して、発表者と対話できるか、Yammer の会話です。 

ライブ イベントは、次のバージョンの Skype 会議のブロードキャストと見なされ、最終的には、チームでは、Skype 会議をブロードキャストすることで提供される機能を置き換えます。 ライブ イベントのパブリック プレビュー リリースでは、マイクロソフトが新しい、または今後のイベントのサービスの中断は生じませんが、Skype 会議をブロードキャストをサポートするために継続します。 参加者の数などの画面を共有するには、新しい機能を活用してチームでのライブ イベントを試すし、エンコーダーの外部のハードウェアとソフトウェアのサポートすることをお勧めします。 

次の図は、Microsoft の 365 のライブ イベントに関連する高レベルのコンポーネントを示しています。 

![チームのライブ イベント](media/teams-live-events.png)

## <a name="key-components"></a>主要なコンポーネント
ライブ イベントで使用されるいくつかの主要コンポーネントがあります。

### <a name="scheduling"></a>スケジュール
チームでは、アクセス許可を適切な参加者のイベントを作成する、チーム メンバーのイベントを指定、運用方法を選択し、会議出席依頼の開催者の機能を提供します。 Yammer グループ内でのライブ イベントが作成されている場合、ライブ イベントの参加者はイベント チームとやり取りするため、Yammer の会話を使用することになります。 

### <a name="production"></a>生産
Microsoft 365 でのライブ イベントでは、多様な運用シナリオをサポートして、web カムを使用してクイック スタートのイベントまたは studio 品質の機器を使用して外部エンコーダー イベントが含まれます。 ビデオ入力、ライブ イベントの基盤でありまるちかめらの本格的なビデオ制作を 1 つの web カメラから異なることができます。 お客様は、プロジェクトの要件と予算に応じてこれらのオプションを選択できます。 イベントを生成する 2 つの方法があります。

- **クイック スタート**: クイック スタートの方法により、チーム会議を使用して、ライブのイベントを生成します。 このオプションは、オーディオを使用して、ビデオ デバイスが PC に接続されているまたはリモートの発表者を招待する場合に最適とパネリストのイベントに参加しています。 このオプションでは、簡単に自分の web カムを使用し、ブロードキャストへの入力として、画面を共有することができます。 

- **エンコーダーの外部**: 外部エンコーダーが外部のハードウェアまたは Microsoft ストリームでのソフトウェア ・ ベースのエンコーダーから直接ライブのイベントを生成するユーザーを許可します。 このオプションが既にある場合 studio 品質の機器 (例: メディアのミキサー) RTMP サービス サポート ストリーミングに最適です。 このオプションは通常、メディア ミキサーから 1 つのストリームを視聴者にブロードキャスト – エグゼクティブ ・町のホールなど大規模なイベントで使用されます。 

### <a name="streaming-platform"></a>プラットフォームのストリーミング
ライブ イベントをストリーミング プラットフォームは、次の部分で構成されています。

- **Azure のメディア サービス**  [Azure のメディア サービス](https://docs.microsoft.com/en-us/azure/media-services/previous/)では、今日の最も人気のあるモバイル デバイスでの大規模な対象ユーザーに到達するのには、ブロードキャスト品質ビデオ ストリームのサービスを示します。 メディア サービスがユーザー補助の設定、配布、およびスケーラビリティを強化して、ローカルおよび世界中の対象ユーザーにコンテンツをストリーム配信を容易かつコスト ・ パフォーマンスにより、-コンテンツを保護しながら。
- **Azure コンテンツ配信ネットワーク (CDN)** ストリームがライブになった後、 [Azure コンテンツ配信ネットワーク (CDN)](https://docs.microsoft.com/en-us/azure/cdn/)を通じて配信されます。 Azure のメディア サービスでは、ストリーミング エンドポイントの CDN の統合を提供します。 これにより、ストリームのバッファリングのない世界中で表示するができます。
- **エンタープライズ コンテンツ配信ネットワーク (eCDN)** ECDN の目標は、ビデオ コンテンツをインターネットから取得し、ネットワークのパフォーマンスに影響を与えずに、企業全体でコンテンツを配布すること。 ライブ イベント用にネットワークを最適化するために、次の認定パートナーを使用できます。
    - ハイブ
    - Kollective
    - ランプ
- **出席者が発生します。** 参加者の経験は、ライブ イベントの最も重要な側面と、出席者が問題なくライブ イベントに参加できることが重要です。 参加者経験では、Azure のメディア プレーヤーを使用してし、デスクトップ、ブラウザー、およびモバイル (iOS、Android) の間で動作します。 Office 365 は、Yammer とチーム共同作業の 2 つのハブとライブの参加者としての経験に統合されているこれらのコラボレーション ツールです。 ベースの外部のエンコーダーのライブ イベントは、 **Microsoft ストリーム ポータル**の出席者でもアクセスできます。

## <a name="planning-for-live-events"></a>ライブ イベントを計画します。
チームのライブ イベントを使用して、大規模な会議を保持するために計画する際は、すべてを設定する前に考慮すべきいくつかの要因があります。 

### <a name="who-can-create-and-schedule-live-events"></a>作成し、ライブ イベントのスケジュールを設定したことができますでしょうか。
次の前提条件は、プレビューの時間内でライブ イベントをスケジュールするのにはユーザーの必要があります。  
- ユーザーには、Office 365 エンタープライズ E3 または E5 のライセンスが割り当てられています。 
- マイクロソフト チーム、ビジネス オンライン、および Microsoft のストリームの Skype のユーザーになっています。
- チームでプライベートな会議のスケジュール設定をユーザーが有効になっている (TeamsMeetingPolicy AllowPrivateMeetingScheduling を True に設定します)。
- チームでのライブ イベントのスケジュールをユーザーが有効になっている (TeamsMeetingBroadcastPolicy AllowBroadcastScheduling を True に設定します)。
- ユーザーは、(外部のエンコーダーの生産) の Microsoft のストリームでのライブ イベントを作成するアクセス許可を持っています。

> [!NOTE]
> 製作者またはチームのライブ イベントで発表者として office 365 の来園者、連合、および匿名ユーザーの参加を要請することはできません。 
 
### <a name="who-can-watch-live-events"></a>ライブ イベントを監視したことができますでしょうか。
|**出席者の表示/非表示**           |**クイック スタート** |**外部エンコーダー**  |
|------------------------------|-------------|------------------|
|公開 (匿名ユーザー)      |  あり        |  なし              |
|ゲスト ユーザー *                   |  なし         |  なし              |
|連合会社 * のすべてのユーザー |  なし         |  なし              |
|会社のすべてのユーザー           |  あり        |  あり             |
|特定のグループ/ユーザー      |  あり        |  あり             |

*ゲストとフェデレーション ユーザーは、匿名のライブ イベントの参加者として参加できます。*

Office 365 のライセンスが認証されたユーザーとしてのライブ イベントに参加するために必要なですが、これは使用される運用方法に依存する必要があります。

- **クイック スタートの生産** ユーザーには、マイクロソフトのチームのライセンスを割り当てる必要があります。
- **外部のエンコーダーの生産**ユーザーには、ストリームのマイクロソフトのライセンスを割り当てる必要があります。
 
### <a name="teams-live-events-and-skype-meeting-broadcast"></a>Skype 会議をブロードキャストし、チームのライブ イベント
次の表には、中核的な機能とのライブ イベントと Skype 会議のブロードキャストとの違いで提供される機能が強調表示されます。 

|**機能**   |**Skype 会議ブロードキャスト** |**チームのライブ イベント (クイック スタート)** |**チームのライブ イベント (外部エンコーダー)** |
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
|生産者の後にブロードキャストの参加者のレポート |& #x 2714 です。 |& #x 2714 です。(機能のリリース) |X |
|対象な言葉の分析: ライブ投票と投票 |& #x 2714 です。(マイクロソフトのパルス) |X |X |

> [!IMPORTANT]
> 設定されている制限を変更する場合があります。

### <a name="regional-availability"></a>地域の可用性
世界中に複数の地域のチームのライブ イベントを使用できます。 次の情報は、イベント チームのメンバーと出席者の可用性を示します。 

> [!IMPORTANT]
> 構成内容の変更、および Office 365 の組織によって、イベントの地域が自動的に選択します。

**これらの地域で利用可能です**
- 南北アメリカ
- ヨーロッパとアフリカ
- アジア太平洋地域

**除外リストと注意事項**
- **ローカル変数を移動する:** Unitied 王国 (英国)、インド、およびその他のマイクロソフト チームに [ローカル] は現在サポートされていません。
- **ローカル - カナダの移動:** このプレビュー中に提供するイベントを作成できますが、北米地域内のデータが所属します。
- **中国:** イベント チームのメンバーと参加者を Azure CDN アクセスできないため、中国でには、チームのライブ イベントを使用することができなきます。 回避策では、会社の VPN 接続は、お客様の企業ネットワークを使用して、CDN に接続されているクライアントの取得を使用します。

## <a name="setting-up-for-live-events"></a>ライブ イベントの設定
ライブ イベントを設定するときにいくつかの手順を行う必要があります。

#### <a name="step-1-set-up-skype-for-business-online"></a>手順 1: ビジネス オンラインの Skype を設定します。
いない場合、は、組織の[ビジネス オンラインの Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online?redirectSourcePath=%252fen-us%252farticle%252fset-up-skype-for-business-online-40296968-e779-4259-980b-c2de1c044c6e)を設定します。

#### <a name="step-2-setting-up-a-ecdn-provider"></a>ECDN プロバイダーを設定する手順 2。
参加者が企業ネットワーク内から参加する場合は、契約時と、ネットワーク帯域幅を最適化するために[eCDN、マイクロソフト推奨プロバイダーの設定](#set-up-ecdn-provider-for-teams-live-events)を検討します。 

#### <a name="step-3-getting-licenses"></a>手順 3: ライセンスを取得します。
[ライブ イベントを作成することができ](#who-can-create-live-events)、[ライブ イベントを監視する](#who-can-watch-live-event)ための適切なライセンスの割り当てがあることを確認します。 

#### <a name="step-4-enable-live-event-scheduling"></a>手順 4: ライブ イベントのスケジュールを有効にします。
[ライブ イベントのスケジュールを有効にする](#enable-live-event-scheduling-for-the-user)会社でのライブ イベントを作成することができるよう、ユーザーのために。 クイック スタートと外部エンコーダーのイベントの両方に必要です。

#### <a name="step-5-enable-users-for-microsoft-stream"></a>手順 5: Microsoft ストリームのユーザーを有効にします。
外部エンコーダーのイベントの[Microsoft ストリーム管理ポータルでのライブ イベントの作成のためのユーザーを有効に](#enable-microsoft-stream-for-users-in-the-organization)します。  

#### <a name="step-6-set-up-your-network-for-live-events-in-microsoft-teams"></a>手順 6: マイクロソフトのチームでのライブ イベントのネットワークのセットアップします。
クイック スタートのライブ イベントでは、[マイクロソフトのチームの組織のネットワークを準備](https://docs.microsoft.com/en-us/microsoftteams/prepare-network)するのには必要です。  

#### <a name="step-7-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>マイクロソフトのチームでのライブ イベントの eCDN のプロバイダー設定は、手順 7: 
適応のビットレート (ABR) のストリーミングを使用して、ライブ イベントのビデオの再生は、ユニキャスト ストリーム、つまり、万人がインターネットから自分のビデオ ストリームを取得します。 ライブ イベントや、組織の大部分に送信されるビデオは、膨大なインターネットの帯域幅のあるユーザーによって消費されている可能性があります。 ライブ イベントの場合は、このインターネット トラフィックを削減する組織では、マイクロソフトのソリューションは、統合のライブ イベントでは、ソフトウェアを提供するビデオの配信パートナーには、ネットワーク (SDNs) またはエンタープライズ ・ コンテンツ配信ネットワーク (eCDNs) が定義されている信頼されています。 これらの SDN/eCDN ・ プラットフォームを犠牲にエンド ユーザー エクスペリエンスを表示することがなくネットワークの帯域幅を最適化するために組織を有効化します。 パートナーは、エンタープライズ ネットワーク上よりスケーラブルで効率的なビデオ配信を有効にするに役立ちます。

**購入とセットアップのソリューションをマイクロソフトのチーム以外で**マイクロソフトのビデオ配信を信頼できるパートナーを活用することでビデオの配信を拡大・縮小で専門的なヘルプを取得します。 前に、購入して、外部とマイクロソフトのチームとは別に SDN と eCDN ソリューションをセットアップする必要があります、マイクロソフトのチームで使用するビデオ配信プロバイダーを有効にできます。

次の SDN と eCDN ソリューションは、事前統合されてし、Microsoft のストリームで使用する設定をすることができます。

- **ハイブのストリーミング**ビデオ配信のライブとオンデマンドのエンタープライズのシンプルかつ強力なソリューションを提供します。 ハイブは、追加のハードウェアや帯域幅は必要ありませんし、何千ものネットワークに影響を与えず、同時のビデオ ビューアーを有効にするセキュリティで保護された方法を提供するソフトウェア ・ ベースのソリューションです。 お客様への影響のビデオが、SDN と eCDN ソリューションを購入する前に、ネットワーク上にあるを理解して、ハイブのストリーミングが用意されていますブラウザ ・ ベースの分析ソリューション マイクロソフト ユーザーの場合。 [詳細情報](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective**クラウド ・ ベースのスマート ピアリング配布プラットフォーム (ライブのストリーミング ・ ビデオ、オンデマンド ビデオ、ソフトウェアの更新プログラム、セキュリティ修正プログラムなど) には、さまざまな形式でコンテンツを配信する既存のネットワーク インフラストラクチャを活用するがより迅速に、確実にしより少ない帯域幅にします。 ハードウェアの追加と、世界最大の金融機関によって信頼されている、セキュリティで保護されたプラットフォームでは、セットアップと保守が容易です。 [詳細情報](http://www.kollective.com)
 
- イベントの製作者を支援するネットワーク帯域幅を最適化し、成功したライブ イベントのブロードキャストとオン ・ デマンドをサポートして、**ランプの OmniCache**は、次世代ネットワークの配分を提供し、グローバル Wan 経由でビデオ コンテンツのシームレスな配信を保証ストリーミングします。 ランプの OmniCache のライブ イベントのクイック スタートのサポートを準備中です。  [詳細情報](http://www.ramp.com) 
 
> [!NOTE] 
> 選択した eCDN ソリューションは、選択した[サード パーティ プロバイダーのサービスとプライバシーのポリシー条件]()、eCDN プロバイダーのソリューションの使用を制御しますがします。 マイクロソフト ボリューム ライセンス契約の条項またはオンライン サービスの条件は、eCDN プロバイダーのソリューションを使用することはできません。 [サード パーティ プロバイダーの条件]()に同意しない場合、有効にしないで eCDN ソリューションは、マイクロソフトのチーム、です。 

**設定可能な「クイック スタート」eCDN のライブ イベント**PowerShell を使用してマイクロソフトのチームでは、ライブ イベントの eCDN のプロバイダーを構成できます。 

> [!NOTE] 
> 組織の 1 つの eCDN プロバイダーを構成できます。 

**ハイブ eCDN プロバイダーを設定します**[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 まず以下を実行して、ハイブのメンバーからライセンス ID と API のテンプレートの URL を入手します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective eCDN プロバイダーを設定します**[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 最初から Kollective 相手では、API トークンおよび API のテンプレートの URL を取得し、次を実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**「外部エンコーダー」のライブ イベントを、eCDN を設定します**外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを構成する](https://docs.microsoft.com/stream/network-caching)にもする必要があります。 「クイック スタート」を通じてマイクロソフトのチームまたは Yammer のライブ イベントを作成する場合は、マイクロソフト チームと同様に統合するには、SDN と eCDN のプロバイダーを構成する必要があります。

#### <a name="step-8-enable-live-event-scheduling-for-the-user"></a>手順 8: は、ユーザーのライブ イベントのスケジュール設定を有効にします。
チームのユーザーの既定では、ライブ イベントのスケジュールが有効になっています。  

チーム PowerShell の TeamsMeetingBroadcastPolicy の AllowBroadcastScheduling コントロールの設定を使用して、ユーザーは、かに、チームでのライブ イベントを作成できるかどうか。 Office 365 の PowerShell での TeamsMeetingBroadcastPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 カスタム ポリシーは、ユーザーに割り当てている、しない限り、記録が既定で有効になっているは、グローバル ポリシーがユーザーに表示されます。 

 グローバル ポリシーにフォールバックするのにユーザー、ユーザーの特定のポリシーの割り当てを削除するのには次のコマンドレットを使用します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
グローバル ポリシーで AllowBroadcastScheduling の値を変更するには、次のコマンドレットを使用します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastScheduling $false
```
#### <a name="user-scenarios"></a>ユーザー シナリオ
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

#### <a name="enable-external-encoder-based-live-events-for-users"></a>ユーザー、外部エンコーダー ベースのライブ イベントを展開を有効にします。

**組織内のユーザーの Microsoft のストリームを有効にします。** Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。 詳細については、[ストリームのライセンスの概要](https://docs.microsoft.com/stream/license-overview)を参照してください。 注 Microsoft ストリームは、ビジネスに関する重要事項またはビジネス プレミアム プランには含まれません。  

方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。 [この資料](https://docs.microsoft.com/stream/disable-user-organization)で定義されているユーザーの Microsoft のストリームがブロックされていないことを確認します。

**確認ユーザー Microsoft ストリームでのライブ イベントの作成の権限があります。** 既定で、ストリームで指定されたコンテンツを作成して、ストリームが有効になっているし、ライセンスがユーザーに割り当てられている会社内のすべてのユーザーできます。 Microsoft ストリームの管理者は、ストリーム内の[コンテンツを作成するための従業員を制限する](https://docs.microsoft.com/stream/restrict-uploaders)ことができます。 この制限の一覧にあるユーザーはミーティングを記録することができません。

**確認してライブ イベントの開催者がストリームの管理で設定する会社のポリシーに同意した**Microsoft ストリームには、管理者[、会社のガイドラインのポリシーを設定する](https://docs.microsoft.com/stream/company-policy-and-consent)には、従業員がコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますし、ユーザーする必要がありますようにマイクロソフトのチームで (外部のエンコーダーの生産) でのライブ イベントを作成する前にします。 組織でのライブ イベントの機能をロールアウトする前にこれらのライブ イベントを作成するユーザーは、ポリシーに同意したがいることを確認します。 

## <a name="configure-live-events"></a>ライブ イベントを構成します。

### <a name="set-up-event-support-link"></a>イベントのサポートのリンクを設定します。
これは、ライブ イベントの参加者に表示されるリンクです。 

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

ユーザーが匿名の参加者を監視することができますブロードキャストのイベントのスケジュールを設定するかどうかは、PowerShell の TeamsMeetingBroadcastPolicy の BroadcastAttendeeVisibility コントロールの設定を使用します。 

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、EveryoneInCompany に設定する既定値を保持するグローバル ポリシーを取得します。 
 
Windows PowerShell のでは、グローバル ポリシーで匿名イベントを作成するようにするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
### <a name="configure-recording-options"></a>レコーディングのオプションを構成します。
> [!NOTE]
> このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。

これにより、ライブ イベントは、常に記録、記録されることはないかどうか、またはイベントの開催者は、かのイベントが記録することができるかどうか制御する管理者です。  

|**値**  |**動作**  |
|---------|---------|
|常に有効になっています。 |このユーザーごとのライブ イベントは、常に記録されます。 ユーザー オプションをオーバーライドする必要はありません。 ライブのイベントが記録される場合は、イベントのチーム メンバーは、イベントの後にレコーディングをダウンロードすることと出席者は、イベント終了後のイベントを監視できます。 |
|AlwaysDisabled |このユーザーが開催するライブ イベントが記録されることはありません。 ユーザー オプションをオーバーライドする必要はありません。 ライブのイベントが記録される場合は、イベント チームのメンバーの記録は作成されず、出席者はイベントが上にあるを見ることはできません。 |
|UserOverride |ユーザーは、イベント チームのメンバーの記録ファイルを作成することができ、参加者がイベント終了後のイベントを監視するためにライブ イベントを記録するかどうかを決定できます。 |

コントロールのライブ イベントの開催者によって作成されたライブ イベントのオプションを記録する PowerShell の TeamsMeetingBroadcastPolicy で BroadcastRecordingMode の設定を使用します。

Windows PowerShell のでは、グローバル ポリシーでの記録モードを更新するのには次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>(準備中) チームのライブ イベントのリアルタイム議事録を作成し、変換を構成します。
> [!NOTE]
> このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。

これにより、リアルタイムのキャプションとライブ イベントの出席者に対して変換を有効にするのにはライブ イベントを開催します。 

ライブ イベントの参加者が議事録と翻訳を参照してくださいできるかどうかにコントロールする PowerShell の TeamsMeetingBroadcastPolicy で AllowBroadcastTranscription の設定を使用します。 ここで Office 365 の PowerShell での TeamsMeetingBroadcastPolicy を管理する方法の詳細については。  

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、議事録作成と翻訳が既定で無効にするグローバル ポリシーを取得します。

Windows PowerShell では、[グローバル ポリシーでの議事録やイベントの出席者のために翻訳を有効にするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="self-service-administration-tools"></a>セルフ サービス管理ツール 
直接 Microsoft は、Office 365 のオンラインのすべてのデータ センターを制御し、システム全体のパフォーマンスは、ですが、Office 365 のユーザーの合計の経験を提供する要素の一部だけを制御できます。 組織自体は、データ センターでお客様のワイド エリア ネットワーク (WAN)、ネットワーク接続を担当し、お客様のローカル エリア ネットワーク (Lan)。 さらに、ユーザーのデバイスとその構成を担当しています。必要なライセンスなど、必要な機能は、ユーザーごとの管理を担当する、マイクロソフトが、ユーザーは、機能へのアクセスを必要がある限りのこれらの機能を管理することに。

お客様は、さまざまなチームのライブ イベントの関連タスクを管理するために次のツールを使用できます。
- [Microsoft Office 365 管理者センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [マイクロソフトのチームと Skype のオンライン ビジネスの管理センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- Microsoft ストリーム管理センター
- [リモートの Windows PowerShell の](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
に関して Windows PowerShell は、it のすべてのユーザーを管理するか、ユーザーの許可を許可します。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
 - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>関連トピック: 
- [Yammer、マイクロソフトのチーム、および Microsoft のストリーム内の Microsoft 365 の間でのライブ イベント](https://docs.microsoft.com/stream/live-event-m365)
- [マイクロソフトのチームでのライブ イベント](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer のライブ イベント](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft ストリームでのライブ イベント](https://docs.microsoft.com/stream/live-event-overview)