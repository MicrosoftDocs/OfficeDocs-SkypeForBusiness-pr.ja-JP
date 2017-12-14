---
title: "電話システム ボイスメールのセットアップ - 管理者ヘルプ"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# 電話システム ボイスメールのセットアップ - 管理者ヘルプ

この記事は、組織内の全員のために電話システムのボイスメール機能をセットアップする [Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)を対象にしています。
  
> [!NOTE]
> 電話システム ボイスメールでは、ボイスメール メッセージの預かりで Exchange メールボックスのみをサポートし、サードパーティーの電子メール システムはサポートしません。フォールバック メカニズムとして、電話システム ボイスメールでは SMTP を使用してメッセージを再送信できます。このため、サードパーティーの電子メール システムのメールボックスを使っているユーザーは、受信するボイスメール メッセージでサービスの稼働時間が保証されたり、挨拶文やその他の設定の変更などのその他のボイスメール機能が提供されたりすることはありません。 
  
## クラウドのみの環境: 電話システム ボイスメールのセットアップ

Skype for Business Online および通話プランのユーザーには電話システム ボイスメールが自動的にセットアップされ、ユーザーに **電話システム** ライセンスと電話番号を割り当てるとプロビジョニングされます。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。Exchange Online ライセンスの購入も必要になる可能性があります。「[Skype for Business と Microsoft Teams のアドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
    
2. [一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[Skype for Business と Microsoft Teams のライセンスを割り当てる](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、および Exchange Online ライセンスを組織のメンバーに割り当てます。これが完了すると、メンバーはボイスメール メッセージを受信できるようになります。
    
3. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。
    
## オンプレミス環境での電話システム

電話システム ボイスメールをオンプレミスの通話プラン環境で動作させる設定に関する情報は以下のとおりです。
  
1. 電話システム機能がプランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になることがあります。Exchange Online ライセンスの購入も必要になります。「[Skype for Business と Microsoft Teams のアドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
    
2. [一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)、[Skype for Business と Microsoft Teams のライセンスを割り当てる](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、および Exchange Online ライセンスを組織のユーザーに割り当てます。
    
3. 「Skype for Business Cloud Connector エディションの構成」ガイド[](https://technet.microsoft.com/en-us/library/mt605228.aspx)」セクションの手順に従います。
    
4. ボイスメール トランスクリプションに対するサポートは 2017 年 3 月時点で追加されており、すべての組織とユーザーに対して既定で有効になっています。Windows PowerShell を使用し、下記の手順を実行することによって、所属する組織のトランスクリプションを無効にすることができます。
    
5. オンプレミスのメールボックスを持つ電話システム ユーザーのために Azure ボイスメール メッセージの配信を構成する方法については、「[Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158)」もご覧ください。
    
## 組織内のボイスメール ポリシーの設定

既定では、ボイスメール トランスクリプションはすべての組織およびユーザーに対して有効になりますが、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) および[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) コマンドレットを使用することで制御できます。
  
> [!IMPORTANT]
> **New-CsOnlineVoiceMailPolicy** コマンドレットを使用してトランスクリプションの新しいポリシー インスタンスを作成することはできません。また、 **Remove-CsOnlineVoiceMailPolicy** コマンドレットを使用して既存のポリシー インスタンスを削除することはできません。
  
ボイスメール ポリシーを使用してユーザーのトランスクリプション設定を管理することができます。すべての利用できるボイスメール ポリシー インスタンスを確認するには、[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]() コマンドレットを使用します。
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### 組織のトランスクリプションをオフにする

組織のトランスクリプションに関する既定の設定はオンになっており、[Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) を使用して無効にすることができます。これを行う場合は、次を実行します。
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### ユーザーのトランスクリプションをオフにする

ユーザー ポリシーは組織の既定の設定より前に評価されます。たとえば、ボイスメール トランスクリプションがすべてのユーザーに対して有効になっている場合、[Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) コマンドレットを使用して、特定のユーザーに対するトランスクリプションを無効にするポリシーを割り当てることができます。
  
単一ユーザーに対するトランスクリプションを無効にするには、次を実行します。
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Office 365 のボイスメール サービスによってボイスメール ポリシーがキャッシュされ、4 時間ごとにキャッシュが更新されます。このため、ポリシーを変更した場合、変更が適用されるまでに最長で 4 時間かかる場合があります。 
  
## Skype for Business ボイスメールの機能に関するユーザーの理解を支援する

ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。
  
- [Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。
    
- [Skype for Business 2016 トレーニング](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## 関連トピック

[Skype for Business Online のセットアップ](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Office 365 での電話システムで利用できる機能](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  

