---
title: クラウド ボイスメールのセットアップ
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'ユーザーのアカウントをクラウド ボイスメールする方法について学習します。 '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117065"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、Microsoft 365 または Office 365 管理者向けです。詳細については、「クラウド ボイスメール 機能を設定する管理者ロールについて」を参照してください。 [](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> クラウド ボイスメールは、ボイスメール メッセージの受信をExchange、サード パーティのメール システムをサポートしません。 

> [!NOTE]
> 代理人が委任者の代理で通話に応答すると、その代理人の通知クラウド ボイスメール。 ユーザーは、着信を見逃した場合に通知を受け取る可能性があります。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>クラウド専用環境: オンライン ユーザー向クラウド ボイスメールを電話システムする

Online 電話システムの場合、クラウド ボイスメールにユーザーのライセンスを割り当てると、電話システム **が自動的** に設定され、プロビジョニングされます。 

> [!NOTE]
> オンプレミスでSkype for Business 電話システム指定された電話番号を持つオンライン ユーザーの場合[、Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)を使用してホスト型ボイス メールを有効にする必要$True。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>メールボックス ユーザークラウド ボイスメールのExchange Server設定

次の情報は、オンラインのユーザークラウド ボイスメールがメールボックスを持っているユーザーと一緒に作業電話システムを構成する方法についてExchange Server。 
  
1. ボイスメール メッセージは、ユーザーのメールボックスに配信されExchange経由でルーティングされた SMTP 経由でExchange Online Protection。 これらのメッセージの正常な配信を有効にするには、Exchange コネクタがサーバーとサーバー間で正しく構成Exchange確認Exchange Online Protection。[コネクタを使用してメール アドレスを構成Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Skype for Business クライアントであいさつ応答メッセージやビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web サービスを介した Exchange サーバー メールボックスへの接続が必要です。 この接続を有効にするには、「Exchange 組織と Exchange Online 組織間の[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。 さらに、Skype for Business Online と Exchange Server の間で統合と Oauth を構成する必要があります。詳細については[、「Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)と Exchange Server の間の統合と OAuth の構成」を参照してください。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>ユーザーのクラウド ボイスメール設定Skype for Business Serverする

サーバー ユーザー Skype for Businessを構成クラウド ボイスメール、オンプレミス ユーザーの クラウド ボイスメール[サービスの計画に関するページを参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>組織で保護されたボイスメールを有効にする

組織内のユーザーのボイスメール メッセージを他のユーザーが離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。 メール フロー ルールを使用してメッセージの暗号化を適用すると、これらのボイスメール メッセージが他の受信者に転送されるのを防ぐことが可能です。 保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスを呼び出したり、Web 上の Outlook、Outlook、または Android または iOS の Outlook でメッセージを開いて、保護されたボイスメール メッセージをリッスンできます。 保護されたボイスメール メッセージは、Skype for BusinessまたはMicrosoft Teams。

メッセージの暗号化の詳細については、「電子メールの暗号化」 [を参照してください](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

保護されたボイスメールを設定するには、次の操作を行います。

1. グローバル管理者 https://admin.microsoft.com アクセス許可を持つアカウントを使用して に移動し、サインインします。
2. [すべて **表示] を** 選択し、[管理センター]**に移動**  >  **Exchange。**
3. [管理センター Exchangeで、[メール フロールール **] を**  >  **選択します**。
4. [追加 **+** **]** を選択し、[**メッセージにOffice 365 Message Encryption保護を適用する] を選択します**。
5. 新しいメール フロー ルールの名前を指定し、[このルールを適用する場合] で、[メッセージのプロパティにメッセージの種類を含める] [ボイス メール]  >    >  **を選択します**。 **[OK] を選択します**。
6. [**次の操作を行う**] で **、[Office 365 Message Encryption保護** と権限保護をメッセージに適用する] を選択し、[1 つ選択]**を選択します**。 [RMS **テンプレート] で**、[転送しない **] を選択します**。 **[OK] を選択** し、[保存]**を選択します**。
    > [!NOTE]
    > RMS テンプレート **の一覧が** 空の場合は、Message Encryption を設定する必要があります。 Message Encryption の設定の詳細については、次の記事を参照してください。
    > - [新しい Message Encryption 機能を設定する](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Azure Information Protection のテンプレートの構成と管理](/information-protection/deploy-use/configure-policy-templates)
    > - [メールの [転送しない] オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> 顧客Skype for Business、通話ポリシーを通じてボイスメールを無効Microsoft Teams、ユーザーのボイスメール サービスを無効Skype for Businessがあります。

既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) と [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) コマンドレットを使用してそれらを制御することができます。

組織内のユーザーが受信したボイスメール メッセージは、組織がホストされているMicrosoft 365またはOffice 365に書き起こされます。 テナントがホストされているリージョンは、ボイスメール メッセージを受信するユーザーが保存されているリージョンと同じではない可能性があります。 テナントがホストされているリージョンを表示するには、[組織プロファイル][](https://go.microsoft.com/fwlink/p/?linkid=2067339)ページに移動し、[データの場所] の横にある [詳細の **表示]****をクリックします**。

> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** コマンドレットを使用して、トランスクリプションおよびトランスクリプション不適切な文字起こしマスク用の新しいポリシー インスタンスを作成したり **、Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除したりできない。

ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。 使用可能なすべてのボイスメール ポリシー インスタンスを表示するには [、Get-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) できます。

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
### <a name="turning-off-transcription-for-your-organization"></a>組織のトランスクリプションをオフにする

組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用して無効にすることができます。これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>組織のトランスクリプション不適切表現マスキングをオンにする。

組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。 マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。 これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。 たとえば、すべてのユーザーに対してボイスメールトランスクリプションが有効になっている場合 [、Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して、特定のユーザーのトランスクリプションを無効にするポリシーを割り当てできます。

単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>ユーザーのトランスクリプション不適切表現マスキングをオンにします。

特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。

単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 および Office 365ボイスメール サービスは、ボイスメール ポリシーをキャッシュし、4 時間ごとにキャッシュを更新します。 このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。

## <a name="help-your-users-learn-teams-voicemail-features"></a>ユーザーがボイスメール機能Teams学習する

ボイスメール設定の管理に関するユーザー向け情報と、その他の通話機能については、以下の情報Teams。

- [で通話設定を管理Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) この記事では、すべてのエンド ユーザーと通話機能を管理Teams説明します。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Skype for Business ボイスメールの機能に関するユーザーの理解を支援する

ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。

- [Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。

- [Skype for Business 2016 トレーニング](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server と Exchange Server の移行の計画](/SkypeForBusiness/hybrid/plan-um-migration)