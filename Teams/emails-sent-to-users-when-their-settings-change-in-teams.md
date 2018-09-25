---
title: Microsoft Teams で設定を変更したときにユーザーに送信されるメール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams でダイヤルイン会議の設定を変更したときにユーザーに自動的に送信される情報について説明します。 '
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016166"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

Microsoft を電話会議プロバイダーとして使用して[電話会議を利用できる](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ようになっているユーザーに、メールが自動的に送信されます。
  
既定では、電話会議が有効になっているユーザーに送信される電子メールの 4 つの種類があります。 ただし、ユーザーに送信するメールの数を制限する場合は、オフにすることができます。 Office 365 のオーディオ会議は、ユーザーの電子メールを送信時に電子メールを送信します。
  
- **電話会議のライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更している場合。**
    
     この電子メールには、会議、音声会議、ユーザーの指示およびリンク ビジネス オンライン会議の更新ツールの既存の会議を更新するために使用されるため、Skype を使用するのには、暗証番号 (pin) の既定の会議電話番号、会議 ID が含まれています、ユーザーです。 [ビジネスおよびマイクロソフトのチームのライセンスの割り当ての Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[オーディオ会議プロバイダーとしての Microsoft の割り当て](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。
    
    > [!NOTE]
    > 会議 Id を動的に組織を有効になっている、会議 Id を表す一意のすべてのユーザーの会議をスケジュールするがあります。 [組織で電話会議の動的な Id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)を設定できます。 
  
    このメールの例を次に示します。
    
     ![Skype for Business のライセンス認証](media/audio-conferencing-user-enabled.png)
  
    ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)」をご覧ください。
    
- **ユーザーの会議 ID または既定の電話会議の電話番号が変更された場合。**
    
    この電子メールには、会議 ID、既定の会議の電話番号、指示およびリンク ビジネス オンライン会議の更新ツールを使用して、ユーザーの既存の会議を更新するため、Skype を使用するのにが含まれています。 ですが、この電子メールにはユーザーの電話会議暗証番号 (pin) にはが含まれていません。 [](reset-a-conference-id-for-a-user-in-teams.md)Reset a conference organizer's PIN
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議情報が変更されました。](media/audio-conferencing-info-change.png)
  
- **ユーザーの電話会議の PIN がリセットされる場合。**
    
    この電子メールには、電話会議の開催者の暗証番号 (pin) では、既存の会議 ID、およびユーザーの既定の会議電話番号が含まれています。 [オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。
    
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議 PIN が変更されました。](media/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスが削除されたか、電話会議プロバイダーが Microsoft から他のプロバイダーに変更または、なしに設定された場合**
    
    これは、**オーディオ会議**のライセンスが削除されると、ユーザー、またはサード ・ パーティ製のオーディオ会議プロバイダーをマイクロソフトからユーザーの電話会議プロバイダーを変更する場合、プロバイダーを **[なし]** に設定する場合に発生します。 この電子メールには、説明および既定の会議電話番号] または [会議 ID などの特定の情報、オーディオ会議を削除するのには会議の更新ツールのオンライン ビジネスの Skype を使用するユーザーの情報が含まれています。
    
    「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
    
    このメールの例を次に示します。
    
     ![ダイヤルイン会議がオフになっています。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>ユーザーに送信されるメールのメッセージを変更する

ユーザーの電子メール アドレスなど*の*連絡先情報に記載されている表示名を自動的に送信される電子メールには、変更を行うことができます。 既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。 詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>ユーザーにメールが送信されないようにする場合

ユーザーに e メールを送信を無効にするとは、ユーザーにライセンスが割り当てられているを取得するときにも電子メールが送信されません。 会議 ID は、ここでは既定の会議の電話番号、および、さらに、オーディオ会議の暗証番号 (pin) をユーザーに送信されません。 このような場合は、別の電子メールを送信することによって、またはそれらを呼び出すことによってユーザーに通知する必要があります。
  
既定では、メールはユーザーに送信されますが、Microsoft Teams または Windows PowerShell を使用して、電話会議についてのメールをユーザーが受け取らないようにすることができます。 

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams と Skype for Business 管理センターを使用する: **

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. [**保存**] をクリックします。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Windows PowerShell を使用する**
  
詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。 

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
  
## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
