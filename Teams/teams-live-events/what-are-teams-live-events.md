---
title: ライブ イベントをチームは何ですか。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
description: どのようにビデオ、およびマイクロソフトのチーム、Yammer、および Microsoft のストリームでの大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にするイベントについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfdee5d1cf43c358d2b6a36aad66c38d3e9d8ec9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870592"
---
# <a name="what-are-teams-live-events"></a>ライブ イベントをチームは何ですか。
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>概要
Microsoft 365 でのライブ イベントは、ビデオ、および大規模なオンライン ユーザーを対象にコンテンツをブロードキャストするユーザーを有効にします。 Microsoft 365 のライブ イベントは、接続全体の契約のライフ サイクル全体を通じて参加者と、実行中に、前後のライブ イベントの促進、新たなレベルへのストリーミング ライブのビデオを表示します。 Yammer または対象ユーザー、チーム、またはコミュニティが存在する、Microsoft のストリーム、マイクロソフトのチームを使用して任意の場所には、ライブ イベントを作成できます。  

チャット ベースのコラボレーション、通話、会議、マイクロソフトのチームが提供し、ライブ イベントのため開くことができます、会議の参加者。 マイクロソフトのチームのライブ イベントは、大規模なオンライン ユーザーにビデオ、および会議のコンテンツをブロードキャストするユーザーを有効にすると、チームの会議の拡張です。 これらは、一対多の通信の相互作用をリードしているイベントのホストと、ホストによって共有されているコンテンツを表示するのには、対象ユーザーへの参加が主な目的は場所のものです。 出席者は Yammer、チーム、および Microsoft のストリーム、ライブまたは記録されたイベントを見ることができ、モデレート Q を使用して、発表者と、または、Yammer の会話と対話できます。 

ライブ イベントは、次のバージョンの Skype 会議のブロードキャストと見なされ、最終的には、チームでは、Skype 会議をブロードキャストすることで提供される機能を置き換えます。 チームのライブ イベントのパブリック プレビュー リリースでは、実行中に新しい、または今後のイベントのサービスの中断は生じませんが、Skype 会議をブロードキャストをサポートするために継続します。 ただし、ライブのイベントのすべての画面を共有、参加者の数を含む、エキサイティングな新しい機能を活用してチームを試してみてくださいすることを推奨し、外部のハードウェアとソフトウェアのエンコーダーのサポートします。 

では、本題に入りましょう。 最初に、Microsoft 365 のライブ イベントとの接続方法に関連する高レベルのコンポーネントを示しています次の図を見てみましょう。 

![チームのライブ イベント](../media/teams-live-events.png)

## <a name="key-components"></a>主要なコンポーネント
マイクロソフトのチームでのライブ イベントで使用される 4 つの主要コンポーネントが、上記の図からわかるようにがあります。

### <a name="scheduling"></a>スケジュール
チームでは、アクセス許可を適切な参加者のイベントを作成する、チーム メンバーのイベントを指定、運用方法を選択し、会議出席依頼の開催者の機能を提供します。 Yammer グループ内でのライブ イベントが作成されている場合、ライブ イベントの参加者は Yammer の会話を使用して、イベントの参加者と対話するためにできるようになります。 

### <a name="production"></a>生産
Microsoft 365 でのライブ イベントでは、多様な運用シナリオをサポートして、web カムを使用してクイック スタートのイベントまたは studio 品質の機器を使用して外部エンコーダー イベントが含まれます。 ビデオ入力、ライブ イベントの基盤でありまるちかめらの本格的なビデオ制作を 1 つの web カメラから異なることができます。 そのプロジェクトの要件と予算に応じてこれらのオプションを選択できます。 イベントを生成する 2 つの方法があります。

- **クイック スタートの生産**: クイック スタートの生産方法により、チーム会議を使用して、ライブのイベントを生成します。 このオプションをお勧めし、オーディオおよびビデオ デバイスを使用する場合の最も簡単なオプションは、PC に接続されているか、イベントに参加するためのリモートの発表者を招待します。 このオプションでは、簡単に自分の web カムを使用し、イベントへの入力として、画面を共有することができます。 


- **外部エンコーダーの生産**: 外部エンコーダーは、外部ハードウェアまたは[マイクロソフトのストリーム](https://stream.microsoft.com)を持つソフトウェア ・ ベースのエンコーダーから直接ライブのイベントを生成するユーザーを許可します。 このオプションが既にある場合 studio 品質機器 (たとえば、メディアのミキサー)、リアルタイム メッセージング プロトコル (RTMP) サービスをサポートするストリーミングに最適です。 生産のこのタイプは通常、経営の町ホール: 対象ユーザーにメディア ミキサーから 1 つのストリームが放送されるなど大規模なイベントで使用されます。 

### <a name="streaming-platform"></a>プラットフォームのストリーミング
ライブ イベントをストリーミング プラットフォームは、次の 4 つの部分で構成されています。

- **Azure のメディア サービス**  [Azure のメディア サービス](https://docs.microsoft.com/azure/media-services/previous/)では、今日の最も人気のあるモバイル デバイスでの大規模な対象ユーザーに到達するのには、ブロードキャスト品質ビデオ ストリームのサービスを示します。 メディア サービスのユーザー補助の設定、配布、およびスケーラビリティを強化し、ローカルまたは世界中の対象ユーザーにコンテンツをストリーム配信を容易かつコスト ・ パフォーマンスは、-コンテンツを保護しながら。
- **Azure コンテンツ配信ネットワーク (CDN)** ストリームがライブになった後、 [Azure コンテンツ配信ネットワーク (CDN)](https://docs.microsoft.com/azure/cdn/)を通じて配信されます。 Azure のメディア サービスでは、端点のストリーミング用の統合された CDN を提供します。 これにより、ストリームのバッファリングのない世界中で表示します。
- **エンタープライズ コンテンツ配信ネットワーク (eCDN)** ECDN の目標は、ビデオ コンテンツをインターネットから取得し、ネットワークのパフォーマンスに影響を与えずに、企業全体でコンテンツを配布すること。 使用できます、次のいずれかの認定 eCDN パートナー組織内で保持されているライブのイベント用にネットワークを最適化します。
    - ハイブ
    - Kollective
    - ランプ
- **出席者が発生します。** 参加者の経験は、ライブ イベントの最も重要な側面と、問題なくライブ イベントで、参加者が参加できることを非常に重要です。 参加者経験では、Azure のメディア プレーヤーを使用してし、デスクトップ、ブラウザー、およびモバイル (iOS、Android) の間で動作します。 Office 365 は、Yammer とチーム共同作業の 2 つのハブとライブの参加者としての経験に統合されているこれらのコラボレーション ツールです。 ベースの外部のエンコーダーのライブ イベントは、[管理ツール](#administrative-tools)での出席者でもアクセスできます。

## <a name="planning-for-live-events"></a>ライブ イベントを計画します。
Organizaiton で大規模な会議を保持するためにチームのライブ イベントを計画する際は、すべてを設定する開始する前に考慮すべきいくつかの要因があります。 

### <a name="who-can-create-and-schedule-live-events"></a>作成し、ライブ イベントのスケジュールを設定したことができますでしょうか。 
次の前提条件は、チームのライブ イベントのスケジュールを設定する必要があります。

ここでは、ライセンスを割り当てる必要があります。  
- Office 365 エンタープライズ E3 または E5 のライセンスです。 
- マイクロソフトのチーム、ビジネス用の Skype とストリームの Microsoft のライセンスです。

Office 365 のライセンスが認証されたユーザーとしてのライブ イベントに参加するために必要なですが、これは使用される運用方法に依存する必要があります。

- **クイック スタートの生産** ユーザーには、マイクロソフトのチームのライセンスを割り当てる必要があります。
- **外部のエンコーダーの生産**ユーザーには、ストリームのマイクロソフトのライセンスを割り当てる必要があります。

ライセンスの詳細については、 [Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)を参照してください。

ユーザーが必要です。
- プライベートな会議のスケジュールを有効になっているチーム (*、TeamsMeetingPolicy AllowPrivateMeetingScheduling パラメーター = True*)。
- イベントのスケジュールが有効になっているチームでのライブ (*、TeamsMeetingBroadcastPolicy AllowBroadcastScheduling パラメーター = True*)。
- ([外部エンコーダーの生産](#production)) の Microsoft のストリームでのライブ イベントを作成するアクセスを許可します。

> [!IMPORTANT]
> 製作者またはチームのライブ イベントで発表者として office 365 の来園者、連合、および匿名ユーザーの参加を要請することはできません。 ただし、ゲストとフェデレーション ユーザーは、匿名のライブ イベントの参加者として参加できます。 
 
### <a name="who-can-watch-live-events"></a>ライブ イベントを監視したことができますでしょうか。

|**出席者の表示/非表示**           |**クイック スタート** |**外部エンコーダー**  |
|------------------------------|-------------|------------------|
|公開 (匿名ユーザー)      |  あり        |  なし              |
|ゲスト ユーザー                   |  なし         |  なし              |
|連合会社内のすべてのユーザー |  なし         |  なし              |
|会社のすべてのユーザー           |  あり        |  あり             |
|特定のグループ/ユーザー      |  あり        |  あり             |
 
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
|パートナー eCDN のサポート |& #x 2714 です。(ハイブ、Kollective、ランプ) |& #x 2714 です。(ハイブ、Kollective) |& #x 2714 です。(ハイブ、Kollective、ランプ) |
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
- ローカル カナダを移動します。

**除外リストと注意事項**
- **ローカル変数を移動する:** Unitied 王国 (英国)、インド、およびその他のマイクロソフト チームに [ローカル] は現在サポートされていません。
- **中国:** イベント チームのメンバーと参加者を Azure CDN アクセスできないため、中国でには、チームのライブ イベントを使用することができなきます。 回避策では、会社の VPN 接続は、お客様の企業ネットワークを使用して、CDN に接続されているクライアントの取得を使用します。

## <a name="setting-up-for-live-events"></a>ライブ イベントの設定
ライブ イベントを設定するときにいくつかの手順を行う必要があります。

### <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>手順 1: マイクロソフトのチームでのライブ イベントのネットワークのセットアップします。
クイック スタートのライブ イベントでは、[マイクロソフトのチームの組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)するのには必要です。  

### <a name="step-2-get-and-assign-licenses"></a>手順 2: ライセンスを取得して割り当てる
正しいライセンスの割り当てがあることを確認して[を作成し、ライブ イベントのスケジュールを設定することができますでしょうか。](#who-can-create-and-schedule-live-events)と[のライブ イベントを監視するですか?](#who-can-watch-live-events)。

### <a name="step-3-enable-live-event-scheduling-for-users"></a>手順 3: ユーザーのライブ イベントのスケジュール設定を有効にします。
チームのユーザーが行う必要があります追加の手順がある外部のエンコーダーのイベントをスケジュールするのにはユーザーのお問い合わせは、かどうかの既定では、ライブ イベントのスケジュールを有効になっています。

#### <a name="for-quick-start-events"></a>クイック スタートのイベント
チーム PowerShell では、 **TeamsMeetingBroadcastPolicy**の*AllowBroadcastScheduling*コントロールの設定を使用して、ユーザーは、かに、チームでのライブ イベントを作成できるかどうか。 TeamsMeetingBroadcastPolicy の管理に関する詳細については、[ここで](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

 ユーザーに割り当てられているカスタム ポリシーが割り当てられていない場合、*グローバル*ポリシーは、既定で有効になっている記録を持っているが、ユーザーに表示されます。

*AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
*グローバル*ポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

##### <a name="user-scenarios"></a>ユーザー シナリオ
**ライブ イベントを作成できるよう、社内のすべてのユーザーをします。**

実行し、確認の場合はユーザーには、 *「ローカル*ポリシーが割り当てられているが、その*AllowBroadcastScheduling* * *True*に設定します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
ユーザーには、*グローバル*ポリシー以外のポリシーが割り当てられている場合、次を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**ライブ イベントを組織全体で 100% 無効にするスケジュールを設定します。**

ブロードキャストのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
*グローバル*ポリシーは、実行するには、組織内のすべてのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**ライブ イベントを作成できるユーザーの数が多いが、一連のユーザーがそれらを作成することを防止します。**

一部のユーザーを有効にする) の**補助金 CsTeamsMeetingBroadcastPolicy**を使用して、*グローバル*ポリシーを割り当てるが最初次を実行して、 *AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
*グローバル*ポリシーの実行にユーザーまたはユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
作成し、(無効にする)、他のユーザーに**与える CsTeamsMeetingBroadcastPolicy**コマンドレットを使用してスケジュール設定を無効にするポリシーを設定します。 

新しいポリシーを作成すると無効になっていることを実行します。
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
スケジュールを無効にするを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**ライブのイベントを無効にするか、ユーザーの数が多いですが、それを作成するユーザーのセットを許可します。**

ブロードキャストのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
*グローバル*ポリシーの実行にこれらのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
作成、スケジュール設定を有効にするポリシーを割り当てると、実行します。
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
スケジューリングを有効にするを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

#### <a name="for-external-encoder-events"></a>外部エンコーダーのイベント
それらのユーザーのライブ イベントのスケジュール設定を有効にするのには、次を行う必要があります。

##### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>手順 1: のユーザー、組織 * * マイクロソフトのストリームを有効にします。
Microsoft ストリームは、対象の Office 365 サブスクリプションの一部として、またはスタンドアロン サービスとして利用できます。 詳細については、[ストリームのライセンスの概要](https://docs.microsoft.com/stream/license-overview)を参照してください。

> ![メモ]ビジネスに関する重要事項またはビジネス プレミアム プランでは、マイクロソフトのストリームが含まれていません。  

方法[Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)ユーザーが Microsoft のストリームにアクセスできるようにする方法の詳細について説明します。 [この資料](https://docs.microsoft.com/stream/disable-user-organization)で定義されているユーザーの Microsoft のストリームがブロックされていないことを確認します。

##### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>手順 2: は、ユーザーは、ライブ イベントの作成のアクセス許可を持つで Microsoft * ストリーム * ことを確認します。
既定では、管理者がエンコーダーを作成する外部のライブ イベントです。 Microsoft ストリームの管理者は、ストリームでの[ライブ イベントを作成するための他のユーザーを有効にする](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)ことができます。  

##### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>手順 3: がライブ イベントを開催者が会社のポリシーでストリームの管理 * * に設定するに同意したことを確認します。
Microsoft ストリームには、管理者[、会社のガイドラインのポリシーを設定する](https://docs.microsoft.com/stream/company-policy-and-consent)には、従業員がコンテンツを保存する前にこのポリシーをそのまま使用する必要がありますし、ユーザーする必要がありますようにマイクロソフトのチームで (外部のエンコーダーの生産) でのライブ イベントを作成する前にします。 組織でのライブ イベントの機能をロールアウトする前にこれらのライブ イベントを作成するユーザーは、ポリシーに同意したがいることを確認します。 

### <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>手順 4: マイクロソフトのチームでのライブ イベントの eCDN のプロバイダーのセットアップします。 
適応のビットレート (ABR) のストリーミングを使用して、ライブ イベントのビデオの再生は、ユニキャスト ストリーム、つまり、万人がインターネットから自分のビデオ ストリームを取得します。 ライブ イベントや、組織の大部分に送信されるビデオは、膨大なインターネットの帯域幅のあるユーザーによって消費されている可能性があります。 ライブ イベントの場合は、このインターネット トラフィックを削減する組織では、マイクロソフトのソリューションは、統合のライブ イベントでは、ソフトウェアを提供するビデオの配信パートナーには、ネットワーク (SDNs) またはエンタープライズ ・ コンテンツ配信ネットワーク (eCDNs) が定義されている信頼されています。 これらの SDN/eCDN ・ プラットフォームを犠牲にエンド ユーザー エクスペリエンスを表示することがなくネットワークの帯域幅を最適化するために組織を有効化します。 パートナーは、エンタープライズ ネットワーク上よりスケーラブルで効率的なビデオ配信を有効にするに役立ちます。

**購入とセットアップのソリューションをマイクロソフトのチーム以外で**マイクロソフトのビデオ配信を信頼できるパートナーを活用することでビデオの配信を拡大・縮小で専門的なヘルプを取得します。 前に、購入して、外部とマイクロソフトのチームとは別に SDN と eCDN ソリューションをセットアップする必要があります、マイクロソフトのチームで使用するビデオ配信プロバイダーを有効にできます。

次の SDN と eCDN ソリューションは、事前統合されてし、Microsoft のストリームで使用する設定をすることができます。

- **ハイブのストリーミング**ビデオ配信のライブとオンデマンドのエンタープライズのシンプルかつ強力なソリューションを提供します。 ハイブは、追加のハードウェアや帯域幅は必要ありませんし、何千ものネットワークに影響を与えず、同時のビデオ ビューアーを有効にするセキュリティで保護された方法を提供するソフトウェア ・ ベースのソリューションです。 お客様への影響のビデオが、SDN と eCDN ソリューションを購入する前に、ネットワーク上にあるを理解して、ハイブのストリーミングが用意されていますブラウザ ・ ベースの分析ソリューション マイクロソフト ユーザーの場合。 [詳細情報](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
 
- **Kollective**クラウド ・ ベースのスマート ピアリング配布プラットフォーム (ライブのストリーミング ・ ビデオ、オンデマンド ビデオ、ソフトウェアの更新プログラム、セキュリティ修正プログラムなど) には、さまざまな形式でコンテンツを配信する既存のネットワーク インフラストラクチャを活用するがより迅速に、確実にしより少ない帯域幅にします。 ハードウェアの追加と、世界最大の金融機関によって信頼されている、セキュリティで保護されたプラットフォームでは、セットアップと保守が容易です。 [詳細情報](http://www.kollective.com)
 
- イベントの製作者を支援するネットワーク帯域幅を最適化し、成功したライブ イベントのブロードキャストとオン ・ デマンドをサポートして、**ランプの OmniCache**は、次世代ネットワークの配分を提供し、グローバル Wan 経由でビデオ コンテンツのシームレスな配信を保証ストリーミングします。 ランプの OmniCache のライブ イベントのクイック スタートのサポートを準備中です。  [詳細情報](http://www.ramp.com) 
 
> [!NOTE] 
> 選択した eCDN ソリューションでは、選択した**サード パーティ プロバイダーのサービスとプライバシーのポリシー条件**、eCDN プロバイダーのソリューションの使用を制御するは。 マイクロソフト ボリューム ライセンス契約の条項またはオンライン サービスの条件は、eCDN プロバイダーのソリューションを使用することはできません。 **サード パーティ プロバイダーの条件**に同意しない場合は eCDN ソリューションは、マイクロソフトのチーム、有効にしないし。 

**設定可能な「クイック スタート」eCDN のライブ イベント**PowerShell を使用してマイクロソフトのチームでは、ライブ イベントの eCDN のプロバイダーを構成できます。 

> [!NOTE] 
> 組織の 1 つの eCDN プロバイダーを構成できます。 

***ハイブ***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 まず以下を実行して、ハイブのメンバーからライセンス ID と API のテンプレートの URL を入手します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective***[セット CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell コマンドレットを使用するには eCDN のプロバイダーを構成します。 最初から Kollective 相手では、API トークンおよび API のテンプレートの URL を取得し、次を実行します。
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**「外部エンコーダー」のライブ イベントを、eCDN を設定します** 

外部エンコーダーを使用して、ライブのイベントを作成する場合は、[マイクロソフトのストリームで、eCDN のプロバイダーを構成する](https://docs.microsoft.com/stream/network-caching)にもする必要があります。 

## <a name="configure-live-events"></a>ライブ イベントを構成します。

### <a name="set-up-event-support-link"></a>イベントのサポートのリンクを設定します。
これは、ライブ イベントの参加者に表示されるリンクです。 

Windows PowerShell で、次の手順を実行します。
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
 
Windows PowerShell では、[グローバル ポリシーで匿名イベントを作成するユーザーを許可するのには、次を実行します。
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

レコーディングのライブ イベントの開催者によって作成されたライブ イベントのオプションのコントロールに、PowerShell では、 **TeamsMeetingBroadcastPolicy**で*BroadcastRecordingMode*の設定を使用します。

Windows PowerShell のでは、グローバル ポリシーでの記録モードを更新するのには次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
### <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>(準備中) チームのライブ イベントのリアルタイム議事録を作成し、変換を構成します。
> [!NOTE]
> このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。

これにより、リアルタイムのキャプションとライブ イベントの出席者に対して変換を有効にするのにはライブ イベントを開催します。 

ライブ イベントの参加者が議事録と翻訳を参照してくださいできるかどうかにコントロールする PowerShell の**TeamsMeetingBroadcastPolicy**で*AllowBroadcastTranscription*の設定を使用します。 ここで、Office 365 の PowerShell では、 **TeamsMeetingBroadcastPolicy**を管理する方法の詳細については。  

カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、議事録作成と翻訳が既定で無効にするグローバル ポリシーを取得します。

Windows PowerShell では、[グローバル ポリシーでの議事録やイベントの出席者のために翻訳を有効にするのには、次のコマンドレットを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
### <a name="administrative-tools"></a>管理ツール 
直接 Microsoft は、Office 365 のオンラインのすべてのデータ センターを制御し、システム全体のパフォーマンスは、ですが、Office 365 のユーザーの合計の経験を提供する要素の一部だけを制御できます。 組織自体は、データ センターでお客様のワイド エリア ネットワーク (WAN)、ネットワーク接続を担当し、お客様のローカル エリア ネットワーク (Lan)。 さらに、ユーザーのデバイスとその構成を担当しています。必要なライセンスなど、必要な機能は、ユーザーごとの管理を担当する、マイクロソフトが、ユーザーは、機能へのアクセスを必要がある限りのこれらの機能を管理することに。

お客様は、さまざまなチームのライブ イベントの関連タスクを管理するために次のツールを使用できます。
- [Microsoft Office 365 管理者センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [マイクロソフトのチームと Skype のオンライン ビジネスの管理センター](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft ストリーム管理センター](https://stream.microsoft.com)
- [リモートの Windows PowerShell の](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

### <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報
に関して Windows PowerShell は、it のすべてのユーザーを管理するか、ユーザーの許可を許可します。 Windows PowerShell では、ビジネス オンラインを行う複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
 - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
 - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

### <a name="related-topics"></a>関連トピック: 
- [Yammer、マイクロソフトのチーム、および Microsoft のストリーム内の Microsoft 365 の間でのライブ イベント](https://docs.microsoft.com/stream/live-event-m365)
- [マイクロソフトのチームでのライブ イベント](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer のライブ イベント](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft ストリームでのライブ イベント](https://docs.microsoft.com/stream/live-event-overview)
