---
title: "電話システムでボイス メールを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Skype for Business のユーザーの電話システム (クラウド PBX) ボイス メールを設定する方法について説明します。 "
ms.openlocfilehash: 2db9325b48bf84c1fc44adbfa1097a3eddd55f9b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-phone-system-voicemail"></a>電話システムでボイス メールを設定します。

この記事では、 [Office 365 管理者](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)向け会社のすべてのユーザーに対して、電話システムでボイス メール機能を設定したいです。
  
> [!NOTE]
> 電話システムのボイス メールでは、Exchange メールボックスでのみデポジット ボイス メール メッセージをサポートし、任意のサード パーティのメール システムをサポートしていません。電話システムでボイス メール、代替メカニズムとしてなし保証されたサービスの稼働時間の変更など、その他のボイスメール機能とボイス メール メッセージを受信するサード パーティのメール システムにメールボックスを持つユーザーは、SMTP を使用してメッセージを再送信できます。あいさつのその他の設定します。 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>クラウドのみが混在する環境: 電話システムでボイス メールを設定します。

Skype for Business Online とプランの呼び出しのユーザーには、電話システムでボイス メールが自動的にセットアップと電話番号の**電話システムで**のライセンスの割り当て後に、ユーザーのプロビジョニングします。
  
1. 電話システムでこの機能は、現在のプランに含まれていない場合、は、**電話システムで**アドオン ライセンスを購入する必要があります。Exchange Online のライセンスを購入する必要もあります。[Skype for Business や Microsoft チーム アドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てたり一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)とビジネスでのユーザーに Exchange Online ライセンスします。後、ボイス メール メッセージを受信できるようにれます。
    
3. ボイス メールのトラン スクリプトのサポートは、2017年 3 月におけるが追加されているし、すべての組織とユーザーに対する既定で有効にします。Windows PowerShell を使用して、次の手順に従うと、組織のトラン スクリプトを無効にできます。
    
## <a name="phone-system-with-on-premises-environments"></a>オンプレミス環境との電話システム

社内環境の計画の呼び出しを操作する電話システムでボイス メールの構成については、次の情報です。
  
1. 電話システムでこの機能は、現在のプランに含まれていない場合、は、**電話システムで**アドオン ライセンスを購入する必要があります。Exchange Online のライセンスを購入する必要があります。[Skype for Business や Microsoft チーム アドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
2. [割り当てたり一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)とビジネスでのユーザーに Exchange Online ライセンスします。
    
3. **ユーザーの電話システムでの音声とボイス メールのサービスを有効にする** [Skype for Business クラウド コネクタ Edition ガイドを構成する](https://technet.microsoft.com/en-us/library/mt605228.aspx)セクションの指示に従います。
    
4. ボイス メールのトラン スクリプトのサポートは、2017年 3 月におけるが追加されているし、すべての組織とユーザーに対する既定で有効にします。Windows PowerShell を使用して、次の手順に従うと、組織のトラン スクリプトを無効にできます。 
    
5. 電話システムでユーザーをオンプレミスのメールボックスに対して Azure ボイス メール メッセージの配信を構成する方法については、 [Exchange Server のサポート Azure PBX ボイス メール](https://support.microsoft.com/en-us/kb/3195158)を表示することもできます。
    
## <a name="setting-voicemail-policies-in-your-organization"></a>組織のボイスメール ポリシーの設定

既定ではすべての組織とユーザーのボイス メールのトラン スクリプトが有効になっています。ただし、[セット CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)と[許可を付与する CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx)コマンドレットを使用して制御できます。
  
> [!IMPORTANT]
> **新規 CsOnlineVoiceMailPolicy**コマンドレットを使用して議事録を新しいポリシー インスタンスを作成することはできず、**削除 CsOnlineVoiceMailPolicy**コマンドレットを使用して、既存のポリシーのインスタンスを削除することはできません。
  
ボイス メールのポリシーを使用して、ユーザーのトラン スクリプトの設定を管理できます。ボイス メールが利用可能なポリシーのすべてのインスタンスを表示するには、 [Get CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)コマンドレットを使用することができます。
  
 **\\> Get CsOnlineVoicemailPolicy**
  
![Get CsOnlineVoiceMailPolicy 結果] ウィンドウ。](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>組織のトラン スクリプトを無効にします。

既定のトラン スクリプト上にあるため、組織の[設定 CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx)で無効にすることです。これを行うには、次のコマンドを実行します。
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a>ユーザーのトラン スクリプトを無効にします。

ユーザー ポリシーは、組織の既定の設定をする前に評価されます。たとえば、すべてのユーザーのボイス メールのトラン スクリプトが有効な場合は、[許可を付与する CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx)コマンドレットを使用して特定のユーザーのトラン スクリプトを無効にするポリシーを割り当てることができます。
  
1 人のユーザーのトラン スクリプトを無効にするには、次のコマンドを実行します。
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Office 365 でボイス メール サービスでは、ボイス メールのポリシーをキャッシュし、4 時間ごとにキャッシュを更新します。したがって、ポリシーの変更を行うを適用する最大 4 時間がかかる場合ことができます。 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Skype をビジネス ボイスメール機能について説明しやすくします。

トレーニング情報やビジネス ボイスメール Skype に成功するユーザーのために記事があります。対象とする、次の記事。
  
- [Skype for Business ボイス メールとオプションにチェック](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Skype for Business でボイス メールを聞く、ボイス メールのあいさつ文を変更する、ボイス メールの設定を変更、および速度が異なるボイス メールを聞く方法を説明します。
    
- [Skype for Business 2016 のトレーニング](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[ここではされた電話システムで Office 365 での表示](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
