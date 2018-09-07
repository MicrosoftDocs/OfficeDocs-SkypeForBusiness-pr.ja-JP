---
title: マイクロソフトのチームでの設定を変更するときにユーザーに送信される電子メール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'どのような情報については自動的にユーザーに電子メールで送信されたマイクロソフトのチームで、ダイヤルイン会議の設定を変更するときについて説明します。 '
ms.openlocfilehash: a352ecb335469e1e988c625f638c6136675dc5fc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23871047"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>マイクロソフトのチームでの設定を変更するときにユーザーに送信される電子メール

[オーディオ会議を](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)有効になっているユーザーにメールが自動送信オーディオ会議プロバイダーに Microsoft を使用します。
  
既定では、電話会議が有効になっているユーザーに送信される電子メールの 4 つの種類があります。 ただし、ユーザーに送信するメールの数を制限する場合は、オフにすることができます。 Office 365 のオーディオ会議は、ユーザーの電子メールを送信時に電子メールを送信します。
  
- **またはマイクロソフトに電話会議プロバイダーを変更するときに、オーディオ会議のライセンスが割り当てられます。**
    
     この電子メールには、会議、音声会議、ユーザーの指示およびリンク ビジネス オンライン会議の更新ツールの既存の会議を更新するために使用されるため、Skype を使用するのには、暗証番号 (pin) の既定の会議電話番号、会議 ID が含まれています、ユーザーです。 [ビジネスおよびマイクロソフトのチームのライセンスの割り当ての Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[オーディオ会議プロバイダーとしての Microsoft の割り当て](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。
    
    > [!NOTE]
    > 会議 Id を動的に組織を有効になっている、会議 Id を表す一意のすべてのユーザーの会議をスケジュールするがあります。 [組織で電話会議の動的な Id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)を設定できます。 
  
    このメールの例を以下に示します。
    
     ![Skype ビジネスのライセンスを確認します。](media/audio-conferencing-user-enabled.png)
  
    詳細については、 [Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)を見ることによってライセンスが表示されます。
    
- **会議 ID または既定の会議の電話番号、ユーザーの変更。**
    
    この電子メールには、会議 ID、既定の会議の電話番号、指示およびリンク ビジネス オンライン会議の更新ツールを使用して、ユーザーの既存の会議を更新するため、Skype を使用するのにが含まれています。 ですが、この電子メールにはユーザーの電話会議暗証番号 (pin) にはが含まれていません。 [](reset-a-conference-id-for-a-user-in-teams.md)Reset a conference organizer's PIN
  
    このメールの例を以下に示します。
    
     ![ダイヤルイン会議の情報が変更されました。](media/audio-conferencing-info-change.png)
  
- **オーディオ会議のユーザーの PIN がリセットされます。**
    
    この電子メールには、電話会議の開催者の暗証番号 (pin) では、既存の会議 ID、およびユーザーの既定の会議電話番号が含まれています。 [オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。
    
  
    このメールの例を以下に示します。
    
     ![ダイヤルイン会議の暗証番号 (pin) が変更されました。](media/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスを削除またはオーディオ会議プロバイダーが変更されたときマイクロソフトから他のプロバイダー、または [なし] にします。**
    
    これは、**オーディオ会議**のライセンスが削除されると、ユーザー、またはサード ・ パーティ製のオーディオ会議プロバイダーをマイクロソフトからユーザーの電話会議プロバイダーを変更する場合、プロバイダーを **[なし]** に設定する場合に発生します。 この電子メールには、説明および既定の会議電話番号] または [会議 ID などの特定の情報、オーディオ会議を削除するのには会議の更新ツールのオンライン ビジネスの Skype を使用するユーザーの情報が含まれています。
    
    「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
    
    このメールの例を以下に示します。
    
     ![ダイヤルイン会議が無効になります。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信される電子メール メッセージに変更を加える

ユーザーの電子メール アドレスなど*の*連絡先情報に記載されている表示名を自動的に送信される電子メールには、変更を行うことができます。 既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。 詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>しない場合は電子メールを送信しますか。

ユーザーに e メールを送信を無効にするとは、ユーザーにライセンスが割り当てられているを取得するときにも電子メールが送信されません。 会議 ID は、ここでは既定の会議の電話番号、および、さらに、オーディオ会議の暗証番号 (pin) をユーザーに送信されません。 このような場合は、別の電子メールを送信することによって、またはそれらを呼び出すことによってユーザーに通知する必要があります。
  
既定では、電子メールは、ユーザーに送信されますが、音声会議用の電子メールを受信しないようにする場合は、マイクロソフトのチームまたは Windows PowerShell を使用することができます。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**
  
詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。 

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。
  
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[ユーザーに電話会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
