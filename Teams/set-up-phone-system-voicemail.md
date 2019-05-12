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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ユーザーのクラウドのボイスメールを設定する方法について説明します。 '
ms.openlocfilehash: 827c52bf526ba84e4f571102354a096e2dc8e2f4
ms.sourcegitcommit: a46dad8dfc685534d81bb011f3c099c6f59ce2e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "33882870"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この資料では、すべてのユーザーのビジネスでのクラウドのボイスメール機能を設定する必要のある[Office 365 の管理者用](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の。

> [!NOTE]
> クラウド ボイスメールでは、Exchange のメールボックスにのみデポジットのボイスメール メッセージをサポートし、任意のサード ・ パーティ製の電子メール システムをサポートしていません。 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>クラウドのみの環境: クラウドのボイスメールを設定します

オンライン ビジネスの計画を呼び出すユーザーの Skype は、クラウドのボイスメールが自動的に設定し、についてと電話番号の**電話システム**のライセンスを割り当てるには、ユーザーの準備します。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になる可能性があります。 [マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。 これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。
    
3. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

## <a name="phone-system-with-on-premises-environments"></a>オンプレミス環境での電話システム

次の情報は、設置計画を呼び出す環境で動作するクラウドのボイス メールを構成する方法です。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になります。 [マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。
    
3. 設置 PSTN のユーザーに展開するソリューションの呼び出しに一致する手順に従います。 クラウド コネクタのエディションの[ビジネス クラウド コネクタのエディションについてを構成する Skype](https://technet.microsoft.com/library/mt605228.aspx)の**電話システムの音声とボイスメール サービスのユーザーを有効にする**セクション内の指示に従います。 Skype でビジネスのサーバーの呼び出しの PSTN、[設置型のエンタープライズ VoIP に対してユーザーを有効にする](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)に従ってください。 チーム直接ルーティングでは、[直接ルーティングを構成する](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)の**と電話番号の構成と有効にするエンタープライズ ボイス ボイスメール**のセクションに従ってください。

4. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

5. ボイスメール メッセージは、Exchange のオンライン保護を経由してルーティングする SMTP 経由でのユーザーの Exchange メールボックスに配信されます。 これらのメッセージが正常に配信を有効にするには、Exchange コネクタは、Exchange サーバーと Exchange のオンライン保護との間に正しく構成されていることを確認してください。 [メール フローを構成するコネクタを使用](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)します。

6. ビジネス クライアント用のあいさつ文や、Skype でボイスメールをビジュアルのカスタマイズなど、ボイスメールの機能を有効にするには、Office 365 から Exchange Web サービス経由で Exchange サーバーのメールボックスに接続する必要があります。 この接続を有効にするのには、 [Exchange および Exchange Online 組織間で認証を構成する OAuth](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)の認証プロトコルについて説明する新しい Exchange の Oauth を行う必要があります。 

> [!NOTE]
> Exchange 2013 CU5 から実行またはそれ以上の Exchange ハイブリッドのウィザードは、手順 5 と 6 の要件を自動的に処理します。 

## <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

> [!WARNING]
> お客様の Skype は、マイクロソフトのチームがポリシーを呼び出すことによってボイス メールを無効にする可能性がありますも無効にするビジネス ユーザー向けに、Skype のボイスメール サービス。

既定では、すべての組織とユーザーに対して、ボイスメール トランスクリプションは有効に、トランスクリプション不適切表現マスキングは無効になっています。ただし、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) と [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) コマンドレットを使用してそれらを制御することができます。

> [!IMPORTANT]
> 議事録と議事録の不適切な**新しい CsOnlineVoiceMailPolicy**コマンドレットを使用してマスクの新しいポリシー インスタンスを作成することはできません。 し、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。.

ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。 すべての利用可能なボイスメール ポリシーのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx)コマンドレットを使用することができます。

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>組織のトランスクリプションをオフにする

組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>組織のトランスクリプション不適切表現マスキングをオンにする。

組織では、トランスクリプション不適切表現マスキングは既定で無効になっています。 マスキングを有効にしなければならないビジネス上の要件がある場合は、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) を使用してトランスクリプション不適切表現マスキングを有効にすることができます。 これを行う場合は、次を実行します。

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。 などのすべてのユーザーは、ボイスメールの議事録が有効である場合は、[許可 CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx)コマンドレットを使用して特定のユーザーの議事録作成を無効にするポリシーを割り当てることができます。

単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>ユーザーのトランスクリプション不適切表現マスキングをオンにします。

特定のユーザーに対してトランスクリプション不適切表現マスキングを有効にするには、ポリシーを割り当てて、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) コマンドレットを使用して特定のユーザーに対するトランスクリプション不適切表現マスキングを有効にすることができます。

単一ユーザーに対するトランスクリプション不適切表現マスキングを有効にするには、次を実行します。

```
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

[Skype for Business Server と Exchange Server の移行の計画](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


