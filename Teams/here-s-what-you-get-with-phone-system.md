---
title: 電話システムで利用できる機能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
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
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '機能、可用性、およびビジネス向け Microsoft Phone System の計画とセットアップ方法について説明します。 '
ms.openlocfilehash: 3c63362b1be16a2e6ad1b55ca6090fadb81b3ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120688"
---
# <a name="heres-what-you-get-with-phone-system"></a>電話システムで利用できる機能

この記事では、電話システムの機能について説明します。 PBX (Private Branch Exchange) の交換用として電話システムを使用する方法と公衆交換電話網 (PSTN) に接続するためのオプションの詳細については、「電話システムとは」を参照 [してください](what-is-phone-system-in-office-365.md)。

クライアントは、タブレットや携帯電話から PC やデスクトップ IP 電話にデバイス上の機能を提供する PC、Mac、モバイルで利用できます。 詳細については [、「Microsoft Teams のクライアントを取得する」を参照してください](get-clients.md)。

 > [!Note]
> さまざまなプラットフォームでの Teams の電話システムの詳細については、プラットフォーム別 [の Teams の機能を参照してください](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  
## <a name="phone-system-features"></a>電話システムの機能

電話システムには、次の機能があります。 特に指定しない限り、機能は Teams と Skype for Business Online の両方で使用できます。
  
|||
|:-----|:-----|
|**電話システム機能** <br/> |**説明** <br/> |
|[クラウド自動応答](what-are-phone-system-auto-attendants.md) <br/> |外部および内部の発信者が組織内の会社のユーザーまたは部門に通話を見つけて発信または転送できるメニュー システムを作成できます。  <br/> |
|[クラウド通話キュー](create-a-phone-system-call-queue.md) <br/> |組織の通話キューの管理方法を構成できます。たとえば、応答メッセージや音楽を保留に設定する、通話を処理するために利用可能な次の通話エージェントを検索する、などです。  <br/> |
|保留中の音楽 | 公衆交換電話網 (PSTN) からの外部通話が保留にされている場合、サービスによって定義された既定の音楽を再生します。 この機能は、通話キューに対して行われた通話に加えて、1 対 1 の PSTN 対 Teams 通話に対して機能します。 この機能は、他のプラットフォームと一緒に保留通知を提供します。 この機能は管理者が構成できますが、現在 [は PowerShell 経由でのみ行います](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 PSTN 通話のコンサルト転送では、保留音楽もサポートされていません。|
|通話の応答/開始 (名前と番号)  <br/> |ユーザーがタッチして着信通話に応答し、完全な電話番号をダイヤルするか、クライアントの名前をクリックして発信通話を発信できます。  <br/> |
|[通話の転送オプションと同時呼び出し](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |ユーザーが転送ルールを設定して、通話をどこからでも移動したり、通話を同僚やボイスメールに転送したりすることができます。  <br/> |
|[グループ通話の受け取りとグループへの転送](call-sharing-and-group-call-pickup.md) <br/> | ユーザーが同僚と着信通話を共有して、ユーザーが応答できない間に発生した通話に同僚が応答できます。 他の形式の通話共有 (着信の転送や同時呼び出しなど) よりも受信者への影響が少なく、ユーザーは着信共有通話の通知方法を構成できます。 |
|[通話とコンサルティングの転送を転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |ユーザーが通話を別のユーザーに転送できます。 または、オフィスを離れる必要があるが、会話を続ける場合は、PC または IP 電話から携帯電話に通話を転送できます。  <br/> |
|[通話中にボイスメールに転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | ユーザーが通話中にボイスメールに転送できます。 |
|[コール パークおよび取得](call-park-and-retrieve.md)  <br/> | ユーザーがクラウドの Teams サービスで通話を保留にできます。 通話の保留を実行すると、Teams サービスにより通話解除のための固有のコードが生成されます。 通話を保留したユーザーまたは他のユーザーは、そのコードとサポートされているアプリやデバイスを使用して、通話を再開できます。 <br/> |
|検索から電話番号に電話する  <br/> | ユーザーが /call コマンドを使用して名前または番号を指定して、検索ボックスから通話を行います。 <br/> |
|[発信者番号](how-can-caller-id-be-used-in-your-organization.md)  <br/> |社内からの通話には、会社のディレクトリから情報を取得する詳細な発信者番号が表示され、電話番号ではなく画像 ID と役職が表示されます。 外部の電話番号からの通話の場合、電話サービス プロバイダーから提供された発信者番号が表示されます。 外部の電話番号が企業ディレクトリの第 2 の番号である場合は、企業ディレクトリからの情報が表示されます。  <br/> |
|デバイスの切り替え  <br/> |ユーザーが Teams に接続されている別の HID デバイスで通話または会議を再生できます。たとえば、PC スピーカーからヘッドセットに切り替えます。   <br/> |
|プレゼンス ベースの通話ルーティング <br/> |プレゼンスを使用して受信通信を制御し、特に指定された通信を除くすべての受信通信をユーザーがブロックできます。  <br/> |
|[統合ダイヤル パッド](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | ユーザーは、検索バーやダイヤル パッド内の任意の場所で名前または番号でダイヤルし、発信通話の処理を高速化できます。 <br/> |
|フェデレーション通話  <br/> |ユーザーがフェデレーション テナント内のユーザーと安全に接続、通信、共同作業できます。  <br/> |
|[ビデオ通話を行う、またはビデオ通話を受信する](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | ユーザーのアカウントでビデオ通話が有効になっている場合、ユーザーは連絡先と対面でビデオ通話を行います。 必要なのは、カメラ、コンピューターのスピーカー、マイクです。 コンピューターに組み込みのオーディオ デバイスがインストールされている場合は、ヘッドセットを使用することもできます。<br/> |
|[クラウド ボイスメール](set-up-phone-system-voicemail.md) <br/> | ユーザーがボイスメールを受信すると、ボイスメール メッセージが添付されたメールとして Exchange メールボックスに配信されます。 ユーザーは、認定されたデスクトップ電話、およびすべての Teams または Skype for Business アプリケーションでメッセージを聞くできます。 ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。   <br/> |
|[クラウド ボイスメール のユーザー設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | ユーザーは、ボイスメール応答メッセージ、通話応答ルール、および応答メッセージの言語 (アウトオブオフィスの応答メッセージを含む) のクライアント設定を構成できます。   |
|[セカンダリ呼び出し音](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | 複数のスピーカー デバイスを PC に接続しているユーザーは、既定のスピーカーに加えて、第 2 デバイスを呼び出す設定を選択できます。 たとえば、PC に接続されているヘッドセットとデスク スピーカーを持つユーザーは、通話が入ってくるとヘッドセットとデスク スピーカーの両方が鳴り、通話を見逃すのをなくします。  |
|[独自の呼び出し](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) 音通知 (Teams のみ)<br/> |ユーザーは、通常の通話、転送された通話、委任された通話に個別の着信音を選択して、通話の種類を区別できます。  <br/> |
|[回線共有機能](shared-line-appearance.md) <br/> | 別のユーザーが自分の代わりに通話を送受信できるよう、ユーザーが自分の電話回線を共有できます。|
|[取り込み中](teams-calling-policy.md) (Teams のみ) <br/> | ユーザーが既に通話または会議に参加している場合、または通話を保留にしている場合に、着信通話を処理する方法を構成できる通話ポリシー。 呼び出し先が既に電話を使用している場合、発信者は取り込み中の信号を聞くでしょう。 呼び出し先は着信通知を受け取りますが、着信に応答できない。 この機能は既定では無効になっていますが、テナント管理者が有効にすることができます。 |
|[通話のブロック](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | ユーザーがブロックリストに (PSTN) 電話番号を追加して、その番号からの次の通話がユーザーの呼び出しをブロックします。|
|[共通領域の電話](set-up-common-area-phones.md) <br/> | 一般的な地域の電話は、ロビーや会議室のような場所に置かれるので、複数のユーザーが利用できます。 共通領域の電話は、ユーザーではなくデバイスとして設定され、ネットワークに自動的にサインインできます。|
|[メディア バイパス サポート](direct-routing-plan-media-bypass.md) (Teams ダイレクト ルーティングのみ) <br/> | パフォーマンスを向上するために、メディアは Microsoft Phone System 経由で送信する代わりに、セッション ボーダー コントローラー (SBC) とクライアントの間に保持されます。 |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High クラウドと DoD クラウドでの可用性
<a name="bkmk_setup"> </a>

GCC High および DoD Cloud では、次の機能はまだ利用できません。 
- [セカンダリ呼び出し、ボイスメール、拡張委任の通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [通話中にボイスメールに転送する](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 検索バーから電話番号に電話する
- 保留中の音楽
- Azure AD逆数値参照

## <a name="related-topics"></a>関連項目

- [電話システムとは](what-is-phone-system-in-office-365.md)
- [Microsoft Teams での Cloud Voice](cloud-voice-landing-page.md)
- [電話システムをセットアップする](setting-up-your-phone-system.md)
- [どの通話プランが適していますか?](calling-plan-landing-page.md)
- [電話システムのダイレクト ルーティング](direct-routing-landing-page.md)
- [通話品質を監視および管理する](monitor-call-quality-qos.md)
- [Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話システムの価格](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [通話と会議を含む仮想化デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
