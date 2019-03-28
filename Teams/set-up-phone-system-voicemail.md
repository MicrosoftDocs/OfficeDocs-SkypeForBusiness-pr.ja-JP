---
title: クラウドのボイスメールを設定します
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 8219934b8e95962f0e9ea81f4965ad9e5c55fb34
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934773"
---
# <a name="set-up-cloud-voicemail"></a>クラウドのボイスメールを設定します

この資料では、すべてのユーザーのビジネスでのクラウドのボイスメール機能を設定する必要のある[Office 365 の管理者用](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)の。

> [!NOTE]
> クラウド ボイスメールでは、Exchange のメールボックスにのみデポジットのボイスメール メッセージをサポートし、任意のサード ・ パーティ製の電子メール システムをサポートしていません。 クラウド ボイスメールがサード ・ パーティ製の電子メール システムにメールボックスを持つユーザーがない保証されたサービスの稼働時間や変更など、他のボイスメール機能とボイスメール メッセージに表示されますが、SMTP を使用してメッセージを再送、フォールバック メカニズムとして、あいさつ文とその他の設定です。

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>クラウドのみの環境: クラウドのボイスメールを設定します

オンライン ビジネスの計画を呼び出すユーザーの Skype は、クラウドのボイスメールが自動的に設定し、についてと電話番号の**電話システム**のライセンスを割り当てるには、ユーザーの準備します。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になる可能性があります。 [マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。 After you do that, they will be able to receive voicemail messages!
    
3. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

## <a name="phone-system-with-on-premises-environments"></a>オンプレミス環境での電話システム

次の情報は、設置計画を呼び出す環境で動作するクラウドのボイス メールを構成する方法です。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。 Exchange Online ライセンスの購入も必要になります。 [マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てまたはビジネス向けの Office 365 のライセンスを削除](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)、およびお客様のビジネス ユーザーに Exchange Online ライセンスです。
    
3. [ビジネス クラウド コネクタのエディションについてを構成する Skype](https://technet.microsoft.com/library/mt605228.aspx)の**電話システムの音声とボイスメール サービスのユーザーを有効にする**] セクションの指示に従います。

4. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。

5. オンプレミスのメールボックスを持つ電話システム ユーザーのために Azure ボイスメール メッセージの配信を構成する方法については、「[Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158)」もご覧ください。

6. 参照してください次のドキュメントに記載されている手順に従います:[ハイブリッド構成ウィザード](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)

## <a name="setting-voicemail-policies-in-your-organization"></a>組織内のボイスメール ポリシーの設定

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

## <a name="related-topics"></a>関連項目
[Skype for Business Online のセットアップ](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Office 365 での電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)


