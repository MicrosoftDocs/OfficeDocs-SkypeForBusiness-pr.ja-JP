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
- NOCSH
ms.custom:
- Phone System
description: 'ユーザーにクラウドボイスメールをセットアップする方法について説明します。 '
ms.openlocfilehash: 1e33928c8ebd241d37f572d80eb895a0164e0d41
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693822"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、社内のすべてのユーザーにクラウドボイスメール機能を設定する必要がある[Office 365 管理者](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を対象としています。

> [!NOTE]
> クラウドボイスメールでは、Exchange メールボックスでのボイスメールメッセージのデポジットのみがサポートされ、サードパーティのメールシステムはサポートされません。 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>クラウドのみの環境: クラウドボイスメールをセットアップする

Skype for Business Online と通話プランのユーザーには、**電話システム**のライセンスと電話番号を割り当てた後で、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になる可能性があります。 「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
    
2. 一般[法人向け Office 365 のライセンスの割り当てまたは削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。 これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。
    
3. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

## <a name="phone-system-with-on-premises-environments"></a>オンプレミス環境での電話システム

次の情報は、オンプレミスの通話プラン環境で動作するようにクラウドボイスメールを構成する方法について説明します。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になります。 「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
    
2. 一般[法人向け Office 365 のライセンスの割り当てまたは削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)、および組織内のユーザーへの Exchange Online ライセンスの割り当てまたは削除を行います。
    
3. ユーザーに展開されているオンプレミス PSTN 通話ソリューションと一致する指示に従ってください。 Cloud Connector Edition の場合は、「 [Skype For Business Cloud Connector エディションの構成](https://technet.microsoft.com/library/mt605228.aspx)」の「**電話システムの音声およびボイスメールサービスのユーザーを有効にする**」セクションの手順に従います。 Skype for Business Server での PSTN 通話については、「[エンタープライズボイスオンプレミスのユーザーを有効にする](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)」を参照してください。 Teams のダイレクトルーティングの場合は、「**電話番号を設定し、エンタープライズボイスメールとボイスメールを有効に**する」のセクションに従って、[ [Direct ルーティングの構成](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)] を選びます。

4. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

5. ボイスメールメッセージは、Exchange Online Protection を介してルーティングされる SMTP 経由で、ユーザーの Exchange メールボックスに配信されます。 これらのメッセージが正常に配信されるようにするには、exchange サーバーと Exchange Online Protection の間で Exchange コネクタが正しく構成されていることを確認します。[コネクタを使用して、メールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。 

6. Skype for Business クライアントで、グリーティングのカスタマイズや、視覚ボイスメールなどのボイスメール機能を有効にするには、Exchange Web Services を使用した Office 365 から Exchange server メールボックスへの接続が必要です。 この接続を有効にするには、「 [exchange と Exchange Online 組織の間での Oauth 認証の構成](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)」で説明されている新しい exchange Oauth 認証プロトコルを構成するか、Exchange ハイブリッドウィザードを EXCHANGE 2013 cu5 以降以上で実行する必要があります。 さらに、「skype for business [online と Exchange server の間の統合と oauth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明されているように、Skype For business Online と exchange server の間で統合と oauth を構成する必要があります。 

## <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> Skype for Business のお客様の場合、Microsoft Teams の通話ポリシーでボイスメールを無効にすると、Skype for Business ユーザーのボイスメールサービスを無効にすることがあります。

既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。

組織内のユーザーから受信したボイスメールメッセージは、Office 365 テナントがホストされている地域に transcribed されています。 テナントがホストされている地域は、ボイスメールメッセージを受信するユーザーが配置されている地域とは異なる場合があります。 テナントがホストされている地域を表示するには、[[組織プロファイル](https://go.microsoft.com/fwlink/p/?linkid=2067339)] ページに移動し、[**データの場所**] の横にある [詳細の**表示**] をクリックします。

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
> Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Skype for Business ボイスメールの機能に関するユーザーの理解を支援する

ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。

- [Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。

- [Skype for Business 2016 トレーニング](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server と Exchange Server の移行の計画](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


