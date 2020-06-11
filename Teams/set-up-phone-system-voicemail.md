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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'ユーザーにクラウドボイスメールをセットアップする方法について説明します。 '
ms.openlocfilehash: 62729794ff1e23ce29b3e3aad86fa09b63a428e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691053"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、Microsoft 365 または Office 365 管理者を対象としています。詳しくは、「クラウドボイスメール機能をセットアップして、社内のすべてのユーザーを対象にしています[」で説明](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)しています。

> [!NOTE]
> クラウドボイスメールでは、Exchange メールボックスでのボイスメールメッセージのデポジットのみがサポートされ、サードパーティのメールシステムはサポートされません。 

> [!NOTE]
> 代理人が委任者の代わりに着信に応答する場合、クラウドボイスメールでは通知を利用できません。 不在着信の通知は、ユーザーが受信できます。

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>クラウドのみの環境: オンライン電話システムユーザーにクラウドボイスメールをセットアップする

オンライン電話システムを利用している場合は、**電話システム**のライセンスをユーザーに割り当てた後で、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。 

> [!NOTE]
> オンプレミスの電話番号を提供するオンラインの Skype for Business 電話システムユーザーの場合は、 [HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用して、ホストされているボイスメールを有効にする必要がある場合があります。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Exchange Server メールボックスユーザーにクラウドボイスメールをセットアップする

以下の情報は、電話システムに接続しているが、Exchange Server にメールボックスがあるユーザーと連携するようにクラウドボイスメールを構成する方法について説明します。 
  
1. ボイスメールメッセージは、Exchange Online Protection を介してルーティングされる SMTP 経由で、ユーザーの Exchange メールボックスに配信されます。 これらのメッセージが正常に配信されるようにするには、exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認します。[コネクタを使用して、メールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。 

2. Skype for Business クライアントでの応答メッセージや視覚ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Exchange Web Services 経由で Microsoft 365 または Office 365 から Exchange server メールボックスに接続する必要があります。 この接続を有効にするには、「 [exchange と Exchange Online の間の Oauth 認証を構成](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)する」で説明されている新しい exchange Oauth 認証プロトコルを構成するか、または EXCHANGE 2013 cu5 以降以上から Exchange ハイブリッドウィザードを実行する必要があります。 さらに、「skype for business [online と Exchange server の間の統合と oauth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明されているように、Skype For business Online と exchange server の間で統合と oauth を構成する必要があります。 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Skype for Business Server ユーザー用にクラウドボイスメールをセットアップする

クラウドボイスメール用に Skype for Business server ユーザーを構成するには、「[オンプレミスユーザー向けのクラウドボイスメールサービスの計画](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)」を参照してください。

## <a name="enabling-protected-voicemail-in-your-organization"></a>組織で保護されたボイスメールを有効にする

組織内のユーザーに対してボイスメールメッセージを残した場合、ボイスメールは、メールメッセージの添付ファイルとしてユーザーのメールボックスに配信されます。 メールフロールールを使ってメッセージの暗号化を適用すると、これらのボイスメールメッセージが他の受信者に転送されないようにすることができます。 保護されたボイスメールを有効にすると、ユーザーはボイスメールメールボックスを使用するか、outlook、Outlook on the web、または Android 用 Outlook または iOS 版 Outlook でメッセージを開くことによって、保護されたボイスメールメッセージを聞くことができます。 保護されたボイスメールメッセージを Skype for Business で開くことはできません。

メッセージの暗号化の詳細については、「[メールの暗号化](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)」を参照してください。

保護されたボイスメールを設定するには、次の操作を行います。

1. https://admin.microsoft.comグローバル管理者の権限を持つアカウントを使用して、に移動してサインインします。
2. [**すべて表示**] を選択し、[**管理センター**の Exchange] に移動し  >  **Exchange**ます。
3. Exchange 管理センターで、[**メールフロー**ルール] を選択し  >  **Rules**ます。
4. [追加] を選択し **+** **Add**、[ **Office 365 メッセージの暗号化と権限の保護をメッセージに適用する**] を選択します。
5. 新しいメールフロールールの名前を指定し、[**このルールを適用****する**条件] で [メッセージの種類] ボックスに「  >  **Include the message type**  >  **ボイスメール**」と入力します。 [ **OK]** を選びます。
6. [**実行する処理**] で、[ **Office 365 メッセージの暗号化と著作権の保護をメッセージに適用する**] を選択し、[ **1 つ選択**] を選択します。 [ **RMS テンプレート**] で、[**転送しない**] を選択します。 [ **OK]** 、[**保存**] の順に選択します。
    > [!NOTE]
    > **RMS テンプレート**の一覧が空の場合は、メッセージの暗号化を設定する必要があります。 メッセージの暗号化の設定の詳細については、次の記事を参照してください。
    > - [新しいメッセージの暗号化機能を設定する](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Azure Information Protection 用のテンプレートの構成と管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [メールの [転送しない] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> Skype for Business のお客様の場合、Microsoft Teams の通話ポリシーでボイスメールを無効にすると、Skype for Business ユーザーのボイスメールサービスを無効にすることがあります。

既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。

組織内のユーザーから受信したボイスメールメッセージは、Microsoft 365 または Office 365 組織がホストされている地域に transcribed されています。 テナントがホストされている地域は、ボイスメールメッセージを受信するユーザーが配置されている地域とは異なる場合があります。 テナントがホストされている地域を表示するには、[[組織プロファイル](https://go.microsoft.com/fwlink/p/?linkid=2067339)] ページに移動し、[**データの場所**] の横にある [詳細の**表示**] をクリックします。

> [!IMPORTANT]
> **New-csonlinevoicemailpolicy**コマンドレットを使って、書き起こしと議事録のプロファニティマスク用の新しいポリシーインスタンスを作成することはできません。また、 **new-csonlinevoicemailpolicy**コマンドレットを使用して既存のポリシーインスタンスを削除することもできません。

ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。 利用可能なボイスメールポリシーのすべてのインスタンスを表示するには、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用します。

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>組織のトランスクリプションをオフにする

組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>組織のトランスクリプション不適切表現マスキングをオンにする。

組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。 マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。 これを行う場合は、次を実行します。

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。 たとえば、すべてのユーザーに対してボイスメールの議事録が有効になっている場合は、 [new-csonlinevoicemailpolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して、特定のユーザーに対して議事録を無効にするポリシーを割り当てることができます。

単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>ユーザーのトランスクリプション不適切表現マスキングをオンにします。

特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。

単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Microsoft 365 および Office 365 のボイスメールサービスは、ボイスメールポリシーをキャッシュし、4時間ごとにキャッシュを更新します。 このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。

## <a name="help-your-users-learn-teams-voicemail-features"></a>チームのボイスメール機能についてユーザーが理解できるようにする

ボイスメールの設定と Teams のその他の通話機能の管理については、次の情報が記載されています。

- [Teams で通話設定を管理](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)します。 この記事では、すべてのエンドユーザーチームの通話機能を管理する方法について説明します。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Skype for Business ボイスメールの機能に関するユーザーの理解を支援する

ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。

- [Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。

- [Skype for Business 2016 トレーニング](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>関連項目
[Skype for Business Online をセットアップする](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server と Exchange Server の移行の計画](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
