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
description: '機能、可用性、およびビジネス向けのシステムMicrosoft 電話計画および設定する方法について説明します。 '
ms.openlocfilehash: 3c641da9434745a9f349ad69171d7471090c1baf
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518919"
---
# <a name="heres-what-you-get-with-phone-system"></a>電話システムで利用できる機能

この記事では、電話システム機能について説明します。 電話システムをプライベート ブランチ Exchange (PBX) の交換として使用する方法と、公衆交換電話網 (PSTN) に接続するためのオプションの詳細については、「[電話システムとは」](what-is-phone-system-in-office-365.md)を参照してください。

クライアントは PC、Mac、モバイルで使用できます。この機能は、タブレットや携帯電話から PC、デスクトップ IP フォンまで、デバイス上の機能を提供します。 詳細については、「[Microsoft Teamsのクライアントを取得する」を](get-clients.md)参照してください。

 > [!Note]
> さまざまなプラットフォーム上のTeams電話システムの詳細については、プラットフォーム[別のTeams機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)に関するページを参照してください。

電話システム機能を使用するには、組織に電話システムライセンスが必要です。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

ほとんどの機能では、電話システム ライセンスを割り当て、ユーザーが "音声が有効" になっていることを確認する必要があることに注意してください。 ライセンスを割り当てるには、 [Set-CsPhoneNumberAssignment コマンドレット](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) を使用し、 **EnterpriseVoiceEnabled** パラメーターを$trueに設定します。 クラウド自動応答などのいくつかの機能では、ユーザーが音声を有効にする必要はありません。 例外は、次の表で呼び出されます。
  
## <a name="phone-system-features"></a>電話システムの機能

電話システムには、次の機能が用意されています。
  
|電話システム機能  |説明 |
|:-----|:-----|
|[クラウド自動応答](what-are-phone-system-auto-attendants.md)  |外部および内部の呼び出し元が組織内の会社のユーザーまたは部署に通話を検索して発信または転送できるようにするメニュー システムを作成できます。  <br/> 自動応答ダイヤルからの通話を名前で受け取り、番号ディレクトリ検索でダイヤルするには、ユーザーが音声を有効にする必要 *はありません* 。 *自動応答* メニュー オプションから通話を受信するには、ユーザーが音声を有効にする必要があります。 |
|[クラウド呼び出しキュー](create-a-phone-system-call-queue.md) <br> |通話キューを組織に対して管理する方法を構成できます。たとえば、あいさつメッセージや保留音の設定、通話を処理するために使用可能な次の通話エージェントの検索などです。  <br/> *通話キュー* から通話を受信するには、ユーザーが音声を有効にする必要があることに注意してください。|
|[保留中の音楽](music-on-hold.md) | 公衆交換電話網 (PSTN) からの外部通話が保留になったときに、テナント管理者によってアップロードされたサービスまたはカスタム 音楽によって定義された既定の音楽を再生します。 この機能は、通話キューに対して行われた通話に加えて、1 対 1 の PSTN からTeamsへの呼び出しに対して機能します。 この機能は、他のプラットフォームとの保留通知パリティを提供します。 |
|通話応答/開始 (名前と番号)   |ユーザーがタッチで着信通話に応答し、完全な電話番号をダイヤルするか、クライアントの名前をクリックして発信通話を発信できるようにします。   |
|[通話転送オプションと同時リング](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |ユーザーが転送ルールを設定して、通話がどこからでも通話にアクセスできるようにしたり、通話を同僚やボイスメールに転送したりできます。   |
|[グループ通話のピックアップとグループへの転送](call-sharing-and-group-call-pickup.md)  | ユーザーが利用できない間に発生した通話に同僚が応答できるように、ユーザーが同僚と着信呼び出しを共有できるようにします。 ユーザーは着信共有通話の通知方法を構成できるため、他の形式の通話共有 (通話転送や同時呼び出しなど) よりも受信者に対する中断が少なくなります。 |
|[通話とコンサルティング転送を転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |ユーザーが別のユーザーに通話を転送できるようにします。 または、退社する必要があるが会話を続ける必要がある場合は、PC または IP 電話から携帯電話に通話を転送できます。  <br/> 別のユーザーから転送された通話を受信するには、ユーザーが音声を有効にする必要 *はありません* 。 |
|[ボイスメールの通話中に転送*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | ユーザーが通話中にボイスメールに転送できるようにします。 |
|[コール パークおよび取得](call-park-and-retrieve.md)   | ユーザーがクラウドのTeams サービスで通話を保留にできます。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。  |
|検索から電話番号を呼び出す   | ユーザーが /call コマンドを使用し、名前または番号を指定することで、検索ボックスから呼び出しを行うことができます。  |
|[発信者番号](how-can-caller-id-be-used-in-your-organization.md)   |社内からの通話には、会社のディレクトリから情報を取得する詳細な発信者番号が表示され、電話番号ではなく画像 ID と役職が表示されます。 外部電話番号からの呼び出しの場合は、電話サービス プロバイダーによって提供される発信者番号が表示されます。 外部電話番号が会社のディレクトリ内のセカンダリ番号の場合は、会社のディレクトリからの情報が表示されます。   |
|デバイスの切り替え   |ユーザーは、pc スピーカーからヘッドセットに切り替えるなど、Teamsに接続されている別の HID デバイスで通話や会議を再生できます。    |
|プレゼンス ベースの呼び出しルーティング  |プレゼンスを使用して受信通信を制御し、ユーザーが特に指定されたものを除くすべての受信通信をブロックできるようにします。   |
|[統合ダイヤル パッド](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | ユーザーは、検索バーとダイヤル パッド内の任意の場所に名前または番号でダイヤルでき、発信呼び出しのプロセスを高速化できます。  |
|フェデレーション呼び出し   |ユーザーがフェデレーション テナント内のユーザーと安全に接続、通信、共同作業できるようにします。   |
|[ビデオ通話の発信と受信](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | ユーザーのアカウントがビデオ通話に対して有効になっている場合、ユーザーは連絡先と対面してビデオ通話を行うことができます。 必要なのはカメラ、コンピューターのスピーカー、マイクだけです。 コンピューターにオーディオ デバイスが組み込まれていない場合は、ヘッドセットを使用することもできます。 |
|[クラウド ボイスメール](set-up-phone-system-voicemail.md)  | ユーザーがボイスメールを受信すると、ボイスメール メッセージが添付ファイルとしてメールとしてExchangeメールボックスに配信されます。 ユーザーは、認定されたデスクトップフォン、およびすべてのTeamsまたはSkype for Businessアプリケーションでメッセージを聞くことができます。 ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。 <br> ユーザーは電話システムライセンスを必要 *とせず*、クラウド ボイスメール機能を使用するために音声を有効にする必要 *もありません*。    |
|[クラウド ボイスメールユーザー設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーは、不在時のあいさつ文を含む、ボイスメールのあいさつ文、通話応答ルール、あいさつ文の言語に対するクライアント設定を構成できます。 <br> ユーザーは電話システムライセンスを必要 *とせず*、クラウド ボイスメール機能を使用するために音声を有効にする必要 *もありません*。  |
|[セカンダリ 呼び出し音](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | PC に接続されている複数のスピーカー デバイスを持つユーザーは、既定のスピーカーに加えて、セカンダリ デバイスを呼び出すように設定できます。 たとえば、PC とデスク スピーカーに接続されているヘッドセットを持つユーザーは、通話が着信したときに、ヘッドセットとデスクの両方のスピーカーを呼び出して、通話を見逃さないようにすることができます。  |
|[固有のリング アラート](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teamsのみ) |通常の呼び出し、転送された呼び出し、および委任された呼び出しに対して個別の着信音を選択して、通話の種類を区別できるようにします。   |
|[回線共有機能](shared-line-appearance.md)  | 別のユーザーが自分の代わりに通話を発信および受信できるように、ユーザーが自分の電話回線を共有できるようにします。|
|[ビジー時のビジー](teams-calling-policy.md) (Teamsのみ)  | ユーザーが次の場合に着信呼び出しを処理する方法を構成できる呼び出しポリシー。 <ul><li>通話中 </li><li>会議で</li><li>は保留中の呼び出しを持っています。 </li></ul> 呼び出し元は、次のいずれかの応答を受け取ります。 <ul><li>呼び出し先が電話にあるときにビジー信号を聞く</li> <li>は、ユーザーの未回答の設定に従ってルーティングされます。 1 つのオプションを使用すると、発信者は既に通話中のユーザーにボイスメールを残すことができます。</li></ul> 呼び出し先は不在着信通知を受け取りますが、着信呼び出しに応答できません。 この機能は既定では無効になっていますが、テナント管理者が有効にできます。|
|[呼び出しのブロック](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | ユーザーがブロックリストに (PSTN) 電話番号を追加して、その番号からの次の呼び出しがユーザーの呼び出しをブロックできるようにします。|
|[共通領域の電話](set-up-common-area-phones.md)  | 通常、共通エリアの電話はロビーや会議室などの領域に配置され、複数のユーザーが利用できます。 共通エリア電話は、ユーザーではなくデバイスとして設定され、ネットワークに自動的にサインインできます。|
|[メディア バイパスのサポート](direct-routing-plan-media-bypass.md) (Teams ダイレクト ルーティングのみ)  | パフォーマンスを向上させるために、メディアは、電話システム経由で送信するのではなく、セッション ボーダー コントローラー (SBC) とクライアントの間に保持されます。 |
|[割り当てられていない番号ルーティング](routing-calls-to-unassigned-numbers.md) | ユーザー、自動応答、通話キュー、またはカスタムのお知らせへの未割り当て番号のルーティングを許可します。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High クラウドと DoD クラウドでの可用性
<a name="bkmk_setup"> </a>

次の機能は、GCC High および DoD クラウドではまだ使用できません。 

- [セカンダリ 呼び出し元、ボイスメール、および拡張委任の呼び出し設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [ボイスメールの途中通話に転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 検索バーから電話番号を呼び出す
- 保留中の音楽
- 逆引き番号の参照をAzure ADする

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)
- [Microsoft Teams での Cloud Voice](cloud-voice-landing-page.md)
- [電話システムをセットアップする](setting-up-your-phone-system.md)
- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話システムの価格](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [通話と会議を使用した仮想化デスクトップ インフラストラクチャのTeams](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
