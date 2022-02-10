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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '機能、可用性、およびビジネス向け Microsoft 電話 システムを計画および設定する方法について学習します。 '
ms.openlocfilehash: 3c641da9434745a9f349ad69171d7471090c1baf
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518919"
---
# <a name="heres-what-you-get-with-phone-system"></a>電話システムで利用できる機能

この記事では、以下の電話システム説明します。 電話システム をプライベート ブランチ Exchange (PBX) の交換として使用する方法と、公衆交換電話網 (PSTN) に接続するためのオプションの詳細については、「電話システム とは」を[参照](what-is-phone-system-in-office-365.md)してください。

クライアントは PC、Mac、およびモバイルで利用できます。この機能は、タブレットや携帯電話から PC やデスクトップ IP 電話にデバイス上で提供されます。 詳細については、「Get [clients for Microsoft Teams」を参照してください](get-clients.md)。

 > [!Note]
> さまざまなプラットフォーム上のTeamsシステムの詳細については、プラットフォーム別のTeams[を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

組織で電話システム機能を使用するには、組織がライセンスを持電話システムがあります。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

ほとんどの機能では、ユーザーライセンスを割り当て電話システムユーザーが "音声が有効" になっている必要があります。 ライセンスを割り当てるには [、Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) コマンドレットを使用し、 **EnterpriseVoiceEnabled** パラメーターを $true。 クラウド自動応答などの一部の機能では、ユーザーが音声を有効にする必要がなされません。 例外は次の表で呼び出されています。
  
## <a name="phone-system-features"></a>電話システムの機能

電話システム、次の機能を提供します。
  
|電話システム機能  |説明 |
|:-----|:-----|
|[クラウド自動応答](what-are-phone-system-auto-attendants.md)  |外部および内部の呼び出し元が組織内の会社のユーザーまたは部門を見つけて発信または転送できるメニュー システムを作成できます。  <br/> 自動応答ダイヤル *から名前で* 通話を受信し、番号によるディレクトリ検索でダイヤルするために、ユーザーが音声を有効にする必要はない点に注意してください。 自動 *応答メニュー* オプションから通話を受信するには、ユーザーが音声を有効にする必要があります。 |
|[クラウド呼び出しキュー](create-a-phone-system-call-queue.md) <br> |組織で通話キューを管理する方法を構成できます。たとえば、応答メッセージや保留音の設定、通話を処理する次の利用可能な通話エージェントの検索などです。  <br/> 通話キューから *通話を* 受信するには、ユーザーが音声を有効にする必要があります。|
|[保留中の音楽](music-on-hold.md) | パブリック交換電話網 (PSTN) からの外部通話が保留にされている場合に、サービスによって定義された既定の音楽またはテナント管理者によってアップロードされたカスタム音楽を再生します。 この機能は、通話キューに対して行われた呼び出しに加Teams対 1 の PSTN 間通話に対して機能します。 この機能は、他のプラットフォームと保留通知のパリティを提供します。 |
|応答/開始を呼び出す (名前と番号で)   |ユーザーがタッチで着信通話に応答し、完全な電話番号をダイヤルするか、クライアントの名前をクリックして発信通話を発信できます。   |
|[通話の転送オプションと同時呼び出し](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |ユーザーが転送ルールを設定して、通話をどこからでも移動したり、通話を同僚やボイスメールに転送したりすることができます。   |
|[グループ通話の集荷とグループへの転送](call-sharing-and-group-call-pickup.md)  | ユーザーが利用できない間に発生した通話に同僚が応答できるよう、ユーザーが同僚と着信通話を共有できます。 他の形式の通話共有 (着信の転送や同時呼び出しなど) よりも受信者の混乱を少なくします。ユーザーは、着信共有通話の通知方法を構成できます。 |
|[通話とコンサルティング転送を転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |ユーザーが通話を別のユーザーに転送できます。 または、オフィスを離れる必要があるが、会話を続ける場合は、PC または IP 電話から携帯電話に通話を転送できます。  <br/> 別のユーザー *から転送された* 通話を受信するために、ユーザーが音声を有効にする必要はなに注意してください。 |
|[通話中にボイスメールに転送する*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | ユーザーが通話中にボイスメールに転送できます。 |
|[コール パークおよび取得](call-park-and-retrieve.md)   | ユーザーがクラウド内のクラウド サービスでTeamsを保留にできます。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。  |
|検索から電話番号を呼び出す   | /call コマンドを使用し、名前または番号を指定することで、ユーザーが検索ボックスから通話を行います。  |
|[発信者番号](how-can-caller-id-be-used-in-your-organization.md)   |社内からの呼び出しには、会社のディレクトリから情報を取得する詳細な発信者番号が表示され、電話番号ではなく画像 ID と役職が表示されます。 外部の電話番号からの呼び出しの場合、電話サービス プロバイダーから提供された発信者番号が表示されます。 外部電話番号が企業ディレクトリのセカンダリ番号である場合は、会社のディレクトリからの情報が表示されます。   |
|デバイスの切り替え   |ユーザーは、pc スピーカーからヘッドセットに切り替えるなど、Teams に接続されている別の HID デバイスで通話または会議を再生できます。    |
|プレゼンス ベースの呼び出しルーティング  |プレゼンスを使用して受信通信を制御し、特に指定された通信を除くすべての受信通信をユーザーがブロックできます。   |
|[統合ダイヤル パッド](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | ユーザーが検索バーやダイヤル パッド内の任意の場所で名前または番号でダイヤルし、発信呼び出しのプロセスを高速化できます。  |
|フェデレーション呼び出し   |ユーザーがフェデレーション テナント内のユーザーと安全に接続、通信、共同作業できます。   |
|[ビデオ通話を行って受信する](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | ユーザーのアカウントでビデオ通話が有効になっている場合、ユーザーは連絡先と対面ビデオ通話を行います。 必要なのは、カメラ、コンピューターのスピーカー、マイクです。 コンピューターに組み込みのオーディオ デバイスが存在しない場合は、ヘッドセットを使用することもできます。 |
|[クラウド ボイスメール](set-up-phone-system-voicemail.md)  | ユーザーがボイスメールを受信すると、ボイスメール メッセージが添付されたメールExchangeメールボックスに配信されます。 ユーザーは、認定されたデスクトップフォン、およびすべてのアプリケーションまたはアプリケーションでTeamsをSkype for Businessできます。 ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。 <br> ユーザーは *ライセンスライセンスを* 必要と電話システム、また、ユーザーが自分の機能を使用するために音声を有効にするクラウド ボイスメール注意してください。    |
|[クラウド ボイスメールの設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーは、ボイスメール応答応答、通話応答ルール、および応答言語 (会社外のあいさつを含む) のクライアント設定を構成できます。 <br> ユーザーは *ライセンスライセンスを* 必要と電話システム、また、ユーザーが自分の機能を使用するために音声を有効にするクラウド ボイスメール注意してください。  |
|[セカンダリ呼び出し音](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | 複数のスピーカー デバイスを PC に接続しているユーザーは、既定のスピーカーに加えて、セカンダリ デバイスを呼び出す設定を選択できます。 たとえば、ヘッドセットを PC とデスク スピーカーに接続しているユーザーは、通話を見逃しがちなヘッドセットとデスク スピーカーの両方を呼び出し時に鳴らします。  |
|[独自のリング](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) アラート (Teamsのみ) |ユーザーが通話の種類を区別できるよう、通常の通話、転送された通話、委任された通話に個別の着信音を選択できます。   |
|[回線共有機能](shared-line-appearance.md)  | 別のユーザーが自分の代わりに通話を送受信できるよう、ユーザーが自分の電話回線を共有できます。|
|[取り込み](teams-calling-policy.md)中 (Teamsのみ)  | ユーザーが次の場合に着信呼び出しを処理する方法を構成できる呼び出し元ポリシー。 <ul><li>通話中 </li><li>会議で</li><li>は、通話を保留にしています。 </li></ul> 呼び出し元は、次のいずれかの応答を受け取ります。 <ul><li>通話先が電話を使っているときにビジー状態の信号を聞く</li> <li>は、ユーザーの未応答の設定に応じてルーティングされます。 1 つのオプションでは、発信者が既に通話中のユーザーのボイスメールを残すことができます。</li></ul> 呼び出し先は着信通知を受け取りますが、着信通話に応答できない。 この機能は既定で無効になっていますが、テナント管理者が有効にできます。|
|[通話のブロック](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーがブロックリストに (PSTN) 電話番号を追加して、その番号からの次の通話がユーザーの呼び出しをブロックできます。|
|[共通領域電話](set-up-common-area-phones.md)  | 一般的なエリアの電話は、通常、ロビーや会議室のような領域に配置され、複数のユーザーが利用できます。 一般的なエリア電話は、ユーザーではなくデバイスとして設定され、ネットワークに自動的にサインインできます。|
|[メディア バイパスのサポート](direct-routing-plan-media-bypass.md) (Teams ルーティングのみ)  | パフォーマンスを向上するために、メディアはセッション 境界コントローラー (SBC) とクライアントの間でメディアを送信する代わりに、電話システム。 |
|[割り当てられていない番号ルーティング](routing-calls-to-unassigned-numbers.md) | 割り当てられていない番号をユーザー、自動応答、通話キュー、またはカスタムアナウンスにルーティングできます。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>高レベルGCC DoD クラウドでの可用性
<a name="bkmk_setup"> </a>

次の機能は、GCC DoD クラウドでは使用できません。 

- [セカンダリ呼び出し音、ボイスメール、および拡張委任の通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [通話中にボイスメールに転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 検索バーから電話番号に電話する
- 保留中の音楽
- Azure ADの逆引き参照

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)
- [Microsoft Teams での Cloud Voice](cloud-voice-landing-page.md)
- [電話システムをセットアップする](setting-up-your-phone-system.md)
- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話システムの価格](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams会議を使用した仮想化デスクトップ インフラストラクチャの機能](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
