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
ms.openlocfilehash: 1d38963771388b1aec9bb2274e23dcfd22e9fe4b
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120885"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

Microsoft を電話会議プロバイダーとして使用して[電話会議を利用できる](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)ようになっているユーザーに、メールが自動的に送信されます。

既定では、電話会議を利用できるユーザーに対して送信されるメールには、4 つの種類があります。 ただし、ユーザーに送信されるメールの数を制限する場合は、この設定をオフにすることができます。 Office 365 の電話会議は、次の場合にユーザーにメールを送信します。

- **電話会議のライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更している場合。**

     このメールには会議 ID、既定の電話会議の電話番号、ユーザーの電話会議 PIN、およびユーザーのために既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool の操作手順とリンクが記載されています。 [マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)または[オーディオ会議プロバイダーとしての Microsoft の割り当て](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。

    > [!NOTE]
    > 所属する組織で、動的な会議 ID が有効になっている場合、すべてのユーザーの会議に固有の会議 ID が設定されます。 [組織での電話会議の動的 ID ](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)をセットアップすることができます。 

    このメールの例を次に示します。

     ![Skype for Business のライセンス認証](media/audio-conferencing-user-enabled.png)

    [アドオン ライセンスをマイクロソフトのチーム](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を見ることによってライセンスの詳細を表示します。

- **ユーザーの会議 ID または既定の電話会議の電話番号が変更された場合。**

    このメールには会議 ID、既定の電話会議の電話番号、およびユーザーのために既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool の操作手順とリンクが記載されています。 ただし、このメールにはユーザーの電話会議 PIN は含まれていません。 「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。

    このメールの例を次に示します。

     ![ダイヤルイン会議情報が変更されました。](media/audio-conferencing-info-change.png)

- **ユーザーの電話会議の PIN がリセットされる場合。**

    このメールには、ユーザーに向けた組織の電話会議 PIN、既存の会議 ID、および既定の電話会議の電話番号が記載されます。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。
    
     このメールの例を次に示します。
    
     ![ダイヤルイン会議 PIN が変更されました。](media/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスが削除されたか、電話会議プロバイダーが Microsoft から他のプロバイダーに変更または、なしに設定された場合**

    これは、**電話会議**ライセンスがユーザーから削除された場合、ユーザーの電話会議プロバイダーを Microsoft からサードパーティの電話会議プロバイダーに変更する場合、またはプロバイダーを [**なし**] に設定する場合に発生します。 このメールには、ユーザーが Skype for Business Online Meeting Update Tool を使用して、既定の電話会議番号や会議 ID などの電話会議固有の情報を削除するための操作指示および情報が記載されています。

    「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。

    このメールの例を次に示します。

     ![ダイヤルイン会議がオフになっています。](media/audio-conferencing-turned-off.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>ユーザーに送信されるメールのメッセージを変更する

自動的にユーザーに送信されるメールの、*差出人*の連絡先情報に含まれるメール アドレスや表示名を、変更することができます。 既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。 詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>ユーザーにメールが送信されないようにする場合

ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられたときでもメールは送信されません。 この場合、会議 ID、既定の電話会議の電話番号、およびより重要であるユーザーの電話会議の PIN はユーザーに送信されません。 このような場合は、ユーザーに別個のメールを送信するか、電話をすることによって伝える必要があります。

既定では、メールはユーザーに送信されますが、Microsoft Teams または Windows PowerShell を使用して、電話会議についてのメールをユーザーが受け取らないようにすることができます。 

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

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
