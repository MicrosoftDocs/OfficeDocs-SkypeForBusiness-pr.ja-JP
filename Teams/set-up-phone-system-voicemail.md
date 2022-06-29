---
title: クラウド ボイスメールのセットアップ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: ユーザーのクラウド ボイスメールを設定する方法について説明します。
ms.openlocfilehash: 259072194dc474d88a979ac3afb591e72eb51248
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494374"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、ユーザーのクラウド ボイスメールを設定する Microsoft 365 管理者向けです。

クラウド ボイスメールは、ユーザーの Exchange メールボックスにボイスメール メッセージを入金します。 クラウド ボイスメールは、サード パーティの電子メール システムをサポートしていません。 Exchange Onlineライセンス要件については、[サービスの説明Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)参照してください。 管理者ロールの詳細については、「管理者ロール [について](/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

## <a name="cloud-voicemail-provisioning"></a>クラウド ボイスメール プロビジョニング

Teams ユーザーの場合、クラウド ボイスメールは自動的に設定され、プロビジョニングされます。 *クラウド ボイスメールには、Microsoft Teams 電話 ライセンスは必要ありません。*

Teams ユーザーのプロビジョニングは、Skype for Business Online ユーザーの場合と同じではありません。 Skype for Business Online ユーザーの場合、クラウド ボイスメールは、ユーザーに電話システム ライセンスが割り当てられ、プロビジョニング システムによって有効にエンタープライズ VoIPされたときに自動的に設定され、プロビジョニングされました。

Skype for Business Serverオンプレミス ユーザーの場合、クラウド ボイスメールは自動的に設定およびプロビジョニングされます。 ただし、クラウド ボイスメールに呼び出しをルーティングするようにSkype for Business Server環境を構成する必要があります。 詳細については、「[オンプレミス ユーザーのサービスクラウド ボイスメール計画する](/skypeforbusiness/hybrid/plan-cloud-voicemail)」を参照してください。

## <a name="cloud-voicemail-storage"></a>クラウド ボイスメール ストレージ

クラウド ボイスメールによって生成されたボイスメール メッセージは、ユーザーの Exchange メールボックスに配信され、Exchange OnlineまたはExchange Serverに保存されます。 ボイスメール用の特定のストレージや追加のストレージはありません。 ボイスメールにアクセスするクライアント (Microsoft Outlook、Microsoft Teams、Skype for Businessなど) は、Exchange メールボックスと提供された API を介して行います。

ボイスメール メッセージには、音声メッセージとボイスメール文字起こし (有効な場合) を含む添付オーディオ ファイルが含まれています。

ユーザーの Exchange メールボックスには、記録されたカスタムのあいさつ文が格納されます。 これらのあいさつ文は、着信中に必要に応じてクラウド ボイスメールによって取得されます。

## <a name="cloud-voicemail-processing"></a>クラウド ボイスメール処理

クラウド ボイスメールの記録と文字起こしは、クラウド ボイスメールにルーティングされる呼び出しの元の Microsoft 365 から開始されます。 その後、メッセージがユーザーの Exchange メールボックスに配信されます。

たとえば、通話がヨーロッパのセッション ボーダー コントローラー (SBC) を介して使用できないダイレクト ルーティング ユーザーに着信した場合、ボイスメールの記録と文字起こしはヨーロッパで行われます。 その後、メッセージがユーザーの Exchange メールボックスに配信されます。 別の例では、北米の Teams ユーザーがヨーロッパで利用できない Teams ユーザーを呼び出しているとします。 この場合、呼び出しは北米から開始され、処理は北米で行われ、ボイスメールはヨーロッパのユーザーの Exchange メールボックスに配信されます。

Exchange メールボックスへのボイスメールの配信は、他の電子メールと同様に簡易メール トランスポート プロトコル (SMTP) を使用して行われます。

## <a name="manage-cloud-voicemail-for-users"></a>ユーザーのクラウド ボイスメールを管理する

ボイスメール ポリシーを指定し、ボイスメール設定を構成することで、ユーザーのクラウド ボイスメールを管理できます。  

- **ボイスメール ポリシー** を使用すると、ユーザーのグループの機能を管理できます。 通話応答ルール、ボイスメール文字起こし、文字起こし不適切な表現マスク、文字起こし翻訳、システム プロンプト言語などの機能に対して、既存または新しいボイスメール ポリシーを構成して割り当てることができます。 ボイスメール ポリシーの管理の詳細については、「ボイスメール ポリシーの [管理](manage-voicemail-policies.md)」を参照してください。

- **ボイスメール設定** を使用すると、個々のユーザーの設定を構成できます。 通話応答ルール、プロンプト言語、テキスト読み上げの既定値、休暇のあいさつなどの設定を構成できます。 個々のユーザーの設定を構成する方法については、「 [ボイスメール設定の管理](manage-voicemail-settings.md)」を参照してください。 エンド ユーザーは、[設定] **-> 通話 -> [ボイスメールの構成]** に移動して、Teams クライアントでこれらの設定を構成することもできます。

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>クラウド ボイスメールへの呼び出しのルーティングを制御する

クラウド ボイスメール用にプロビジョニングされたすべてのユーザーの既定の設定は、クラウド ボイスメールへの呼び出しのルーティングを許可し、ユーザーが通話をクラウド ボイスメールに転送できるようにすることです。

Teams 管理センターを使用するか PowerShell を使用して、クラウド ボイスメールへの呼び出しのルーティングを Teams ユーザーに許可するかどうかを制御できます。 

- Teams 管理センターを使用するには、 **音声** -> **通話ポリシー** ->新しいポリシーの追加または既存のポリシーの編集に移動します。> **ボイスメールを使用して着信通話をルーティングできます**。  

- PowerShell で、AllowVoicemail パラメーターでSet-CsTeamsCallingPolicyコマンドレットを使用します。 詳細については、「 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

  - AllowVoicemail を AlwaysDisabled に設定した場合、通話はボイスメールにルーティングされることはありません。ユーザーの通話転送または未回答の設定に関係なく。 ボイスメールは、Teams の通話転送または未応答の設定として使用できません。

  - AllowVoicemail を AlwaysEnabled に設定した場合、通話は、ユーザーの応答のない通話転送設定に関係なく、30 秒間呼び出した後、応答のないボイスメールに常に転送されます。

  - AllowVoicemail を UserOverride に設定した場合、通話は、ユーザーの通話転送や未回答の設定に基づいてボイスメールに転送されます。

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>オンプレミス ユーザーを操作するクラウド ボイスメールを設定する

クラウド ボイスメールを使用して、Exchange サーバーにメールボックスを持つユーザーや、Skype for Business Serverを使用しているユーザーにボイス メール機能を提供できます。

このセクションでは、Exchange Server メールボックス ユーザーのクラウド ボイスメールを設定する方法について説明します。 Skype for Business Server ユーザーのクラウド ボイスメールを構成する方法の詳細については、「[オンプレミス ユーザーのサービスクラウド ボイスメール計画](/skypeforbusiness/hybrid/plan-cloud-voicemail)する」を参照してください。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Exchange Server メールボックス ユーザーのクラウド ボイスメールを設定する

次の情報は、Exchange Serverに自分のメールボックスを持つ Teams ユーザーと連携するようにクラウド ボイスメールを構成する方法について説明します。

1. ボイスメール メッセージは、Exchange Online Protection経由でルーティングされる SMTP を介してユーザーの Exchange メールボックスに配信されます。 これらのメッセージの正常な配信を有効にするには、Exchange サーバーとExchange Online Protectionの間で Exchange コネクタが正しく構成されていることを確認します。 詳細については、「 [コネクタを使用してメール フローを構成する」を参照](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)してください。

2. Teams クライアントであいさつ文やビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 と Exchange Server メールボックスの間の接続を設定する必要があります。 この接続を有効にするには、「Exchange [とExchange Online組織の間で OAuth 認証を構成](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)する」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以降から Exchange ハイブリッド ウィザードを実行する必要があります。 Teams と Exchange Server間の統合と OAuth の構成に関するページで説明されている、[Teams とExchange Server間の統合と Oauth も構成](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)する必要があります。

## <a name="enable-protected-voicemail-in-your-organization"></a>組織内で保護されたボイスメールを有効にする

組織内のユーザーのボイスメール メッセージを他のユーザーが残すと、ボイスメールは電子メール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。

Microsoft Purview 情報保護を使用すると、内部発信者と外部発信者の両方によって残されたボイスメール メッセージを暗号化できます。 また、ユーザーがこれらのメッセージを転送できないようにすることもできます。 この機能は、Exchange Onlineメールボックスを持つユーザーに対してサポートされています。

ボイスメール メッセージを暗号化するには、秘密度ラベルを作成します。 自動ラベル付け機能を使用すると、着信ボイスメール メッセージにラベルが自動的に適用されるようにすることができます。

保護されたボイスメールを有効にすると、ユーザーは自分のボイスメール メールボックスを呼び出すか、Outlook、Outlook on the web、Outlook for Android または iOS でメッセージを開くことで、保護されたボイスメール メッセージをリッスンできます。 保護されたボイスメール メッセージは、Microsoft Teams またはSkype for Businessで開くできません。

ボイスメールの秘密度ラベルを作成するには、「 [秘密度ラベルを使用する](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions)」を参照してください。 [ **暗号化** ] セクションで、[ **ユーザーがラベルを適用するときにアクセス許可を割り当てる]** を選択します。 **[Outlook] を選択し、次のいずれかの制限を適用** してから、[**転送しない**] オプションを選択します。

ボイスメールに秘密度ラベルを適用する自動ラベル付けポリシーを作成するには、「 [自動ラベル付けポリシーを構成する方法](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)」を参照し、次の特定の設定を指定します。

- **[このラベルを適用する情報の選択] で**、[**カスタム ポリシー**] を選択します。

- **[ラベルを適用する場所の選択] で**、[**場所: すべてのユーザーの Exchange**] を選択します。

- [  **共通ルールまたは詳細ルールの設定**] で、[ **詳細ルール**] を選択します。

- Exchange ルール:
  - 条件：
    - **ヘッダー一致パターン**: Content-Class = Voice-CA
    - **送信者 IP アドレス:** 13.107.64.0/18、52.112.0.0/14、52.120.0.0/14、52.238.119.141/32、52.244.160.207/207/23

- **[自動適用するラベルの選択]** で、上の手順でボイスメール用に作成した秘密度ラベルを選択します。

- **電子メールのその他の設定** については、[**組織外から受信したメールに暗号化を適用** する] を選択し、Rights Management の所有者を指定します。

送信者 IP アドレスで指定された IP V4 範囲は、[OFFICE 365 URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)の ID 12 の一覧に基づいています。

メッセージの暗号化の詳細については、「 [メール メッセージを暗号化するメール フロー ルールを定義する」を](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)参照してください。

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>ユーザーがクラウド ボイスメール機能について学習できるように支援する

ユーザーがクラウド ボイスメール機能を使用および管理する方法について学習できるように、次の記事をお勧めします。

- [Teams でボイスメールを確認する](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Teams で通話設定を管理する](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
