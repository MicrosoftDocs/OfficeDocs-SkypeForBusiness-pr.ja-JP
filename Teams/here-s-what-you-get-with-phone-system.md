---
title: 電話システムで利用できる機能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '機能、可用性、およびビジネス向けの電話システムMicrosoft計画および設定する方法について説明します。 '
ms.openlocfilehash: 118f2d52193583149e881bf564fb1df616bf108c
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392247"
---
# <a name="heres-what-you-get-with-phone-system"></a>電話システムで利用できる機能

この記事では、電話システムの機能について説明します。 プライベート ブランチ Exchange (PBX) の交換として電話システムを使用する方法と、公衆交換電話網 (PSTN) に接続するためのオプションの詳細については、「 [電話システムとは](what-is-phone-system-in-office-365.md)」を参照してください。

クライアントは PC、Mac、モバイルで利用でき、タブレットや携帯電話から PC やデスクトップ IP フォンにデバイス上の機能を提供します。 詳細については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」を参照してください。

 > [!Note]
> さまざまなプラットフォーム上の Teams 電話システムの詳細については、「プラットフォーム [別の Teams 機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)」を参照してください。

電話システム機能を使用するには、組織に電話システム ライセンスが必要です。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

ほとんどの機能では、電話システム ライセンスを割り当て、ユーザーが "音声が有効" であることを確認する必要があることに注意してください。 ライセンスを割り当てるには、 [Set-CsPhoneNumberAssignment コマンドレット](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) を使用し、 **EnterpriseVoiceEnabled** パラメーターを $true に設定します。 クラウド自動応答などのいくつかの機能では、ユーザーを音声で有効にする必要はありません。 例外は、次の表で呼び出されます。
  
## <a name="phone-system-features"></a>電話システムの機能

電話システムには、次の機能があります。
  
|電話システム機能  |説明 |
|:-----|:-----|
|[クラウド自動応答](what-are-phone-system-auto-attendants.md)  |外部および内部の発信者が組織内の会社のユーザーや部署に通話を見つけて転送できるようにするメニュー システムを作成できます。  <br/> ユーザーは、名前による自動応答ダイヤルから通話を受信し、番号ディレクトリ検索でダイヤルするために音声を有効にする必要 *はありません* 。 *自動応答* メニュー オプションから通話を受信するには、ユーザーが音声を有効にする必要があります。 |
|[クラウド呼び出しキュー](create-a-phone-system-call-queue.md) <br> |通話キューを組織に対して管理する方法を構成できます。たとえば、あいさつや保留音の設定、次に使用可能な通話エージェントを検索して通話を処理するなどです。  <br/> *通話キュー* から通話を受信するには、ユーザーが音声を有効にする必要があることに注意してください。|
|[保留中の音楽](music-on-hold.md) | 公衆交換電話網 (PSTN) からの外部通話が保留状態になったときに、サービスによって定義された既定の音楽またはテナント管理者によってアップロードされたカスタム音楽を再生します。 この機能は、通話キューへの呼び出しに加えて、1 対 1 の PSTN から Teams への呼び出しにも機能します。 この機能は、他のプラットフォームとの保留通知パリティを提供します。 |
|応答/開始の呼び出し (名前と番号による)   |ユーザーがタッチで着信呼び出しに応答し、完全な電話番号をダイヤルするか、クライアント内の名前をクリックして発信通話を発信できるようにします。   |
|[通話転送オプションと同時呼び出し](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |ユーザーが転送ルールを設定して、通話をどこからでも発信したり、通話を同僚やボイスメールに転送したりできます。   |
|[グループ通話のピックアップとグループへの転送](call-sharing-and-group-call-pickup.md)  | ユーザーが不在の間に発生した通話に同僚が応答できるように、ユーザーが着信通話を同僚と共有できるようにします。 ユーザーは着信共有通話の通知方法を構成できるため、他の形式の通話共有 (通話転送や同時呼び出しなど) よりも受信者に対する中断が少なくなります。 |
|[通話とコンサルティング転送を転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |ユーザーが別のユーザーに呼び出しを転送できるようにします。 または、オフィスを離れる必要があるが、会話を続けたい場合は、PC または IP 電話から携帯電話に通話を転送できます。  <br/> 別のユーザーから転送された呼び出しを受信するために、ユーザーが音声を有効にする必要 *はありません* 。 |
|[ボイスメール通話中に転送*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 通話中にユーザーがボイスメールに転送できるようにします。 |
|[コール パークおよび取得](call-park-and-retrieve.md)   | ユーザーがクラウドの Teams サービスで通話を保留にできるようにします。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。  |
|検索から電話番号を呼び出す   | /call コマンドを使用し、名前または数値を指定して、ユーザーが検索ボックスから呼び出しを行うことができます。  |
|[発信者番号](how-can-caller-id-be-used-in-your-organization.md)   |社内からの呼び出しには、会社のディレクトリから情報をプルする詳細な発信者 ID が表示され、電話番号ではなく画像 ID と役職が表示されます。 外部電話番号からの通話の場合は、電話サービス プロバイダーによって指定された発信者 ID が表示されます。 外部電話番号が企業ディレクトリ内のセカンダリ番号である場合は、企業ディレクトリからの情報が表示されます。   |
|デバイスの切り替え   |ユーザーが Teams に接続されている別の HID デバイスで通話または会議を再生できるようにします。たとえば、PC スピーカーからヘッドセットへの切り替えなどです。    |
|プレゼンス ベースの通話ルーティング  |プレゼンスを使用して受信通信を制御し、ユーザーが特に示されているものを除くすべての受信通信をブロックできるようにします。   |
|[統合されたダイヤル パッド](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | ユーザーが検索バーとダイヤル パッド内の任意の場所で名前または番号でダイヤルし、発信呼び出しを行うプロセスを高速化できます。  |
|フェデレーション呼び出し   |ユーザーがフェデレーション テナント内のユーザーと安全に接続、通信、共同作業できるようにします。   |
|[ビデオ通話を行って受信する](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | ユーザーのアカウントがビデオ通話に対して有効になっている場合、ユーザーは連絡先と対面でビデオ通話を行うことができます。 必要なのは、カメラ、コンピューターのスピーカー、マイクだけです。 コンピューターにオーディオ デバイスが組み込まれていない場合は、ヘッドセットを使用することもできます。 |
|[クラウド ボイスメール](set-up-phone-system-voicemail.md)  | ユーザーがボイスメールを受信すると、ボイスメール メッセージが添付ファイルとしてメールとして Exchange メールボックスに配信されます。 ユーザーは、認定されたデスクトップ電話、およびすべての Teams またはSkype for Business アプリケーションでメッセージを聞くことができます。 ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。 <br> ユーザーは電話システム ライセンスを必要 *とせず*、クラウド ボイスメール機能を使用するために音声を有効にする必要 *もありません*。    |
|[ユーザー設定のクラウド ボイスメール](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーは、ボイスメール の案内応答、応答ルールの呼び出し、および不在時のあいさつ文を含むあいさつ文の言語のクライアント設定を構成できます。 <br> ユーザーは電話システム ライセンスを必要 *とせず*、クラウド ボイスメール機能を使用するために音声を有効にする必要 *もありません*。  |
|[セカンダリ リンガー](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | PC に接続されている複数のスピーカー デバイスを持つユーザーは、既定のスピーカーに加えて、セカンダリ デバイスを呼び出すように設定できます。 たとえば、PC とデスク スピーカーに接続されたヘッドセットを持つユーザーは、通話が着信したときにヘッドセットとデスク スピーカーの両方を呼び出して、通話を見逃さないようにすることができます。  |
|[固有のリング アラート](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams のみ) |ユーザーが通話の種類を区別できるように、通常の通話、転送された呼び出し、委任された呼び出し用に個別の着信音を選択できます。   |
|[回線共有機能](shared-line-appearance.md)  | ユーザーが電話回線を共有して、別のユーザーが自分の代わりに通話を発信および受信できるようにします。|
|[ビジー状態](teams-calling-policy.md) (Teams のみ)  | ユーザーが次の場合の着信呼び出しの処理方法を構成できる呼び出し元ポリシー。 <ul><li>呼び出し中 </li><li>会議で</li><li>は保留にされた呼び出しを持っています。 </li></ul> 呼び出し元は、次のいずれかの応答を受け取ります。 <ul><li>通話先が電話に出たときにビジー信号を聞く</li> <li>は、ユーザーの未回答の設定に従ってルーティングされます。 1 つのオプションを使用すると、発信者は既に通話中のユーザーにボイスメールを残すことができます。</li></ul> 呼び出し先は不在着信通知を受け取りますが、着信呼び出しに応答できません。 この機能は既定では無効になっていますが、テナント管理者が有効にすることができます。|
|[呼び出しブロック](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーがブロックリストに (PSTN) 電話番号を追加して、その番号からの次の通話がユーザーの呼び出しをブロックできるようにします。|
|[共通エリア電話](set-up-common-area-phones.md)  | 一般的なエリア電話は、通常、ロビーや会議室などのエリアに配置され、複数のユーザーが利用できます。 共通エリア電話は、ユーザーではなくデバイスとして設定され、自動的にネットワークにサインインできます。|
|[メディア バイパスのサポート](direct-routing-plan-media-bypass.md) (Teams ダイレクト ルーティングの場合のみ)  | パフォーマンスを向上させるために、メディアは電話システムを介して送信するのではなく、セッション ボーダー コントローラー (SBC) とクライアントの間で保持されます。 |
|[割り当てられていない番号ルーティング](routing-calls-to-unassigned-numbers.md) | ユーザー、自動応答、通話キュー、またはカスタムアナウンスへの未割り当て番号のルーティングを許可します。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High クラウドと DoD クラウドでの可用性
<a name="bkmk_setup"> </a>

GCC High クラウドと DoD クラウドでは、次の機能はまだ使用できません。 

- [セカンダリ リンガー、ボイスメール、および拡張委任の通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [ボイスメール通話中に転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 検索バーから電話番号を呼び出す
- 保留中の音楽
- Azure AD の逆引き番号参照

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)
- [Microsoft Teams での Cloud Voice](cloud-voice-landing-page.md)
- [電話システムをセットアップする](setting-up-your-phone-system.md)
- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話システムの価格](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [通話と会議を含む仮想化デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
