---
title: ユーザーの電話番号を割り当て、変更、または削除する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 外部の企業やクライアントがコールインできるよう、Teams ユーザーの作業用電話番号を割り当て、変更、または削除する方法について学習します。
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589621"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>ユーザーの電話番号を割り当て、変更、または削除する (通話プラン)

通話プランを設定する場合は、ユーザーに電話番号を割り当てる必要があります。 Microsoft Teams では、ユーザーが [通話] をクリックすると、割り当てる電話番号が一覧表示 **されます**。 ダイレクト ルーティングのシナリオでユーザーの電話番号を割り当て、変更、または削除する手順については、「ユーザーが直接ルーティング、音声、ボイスメールを使用できる」を参照 [してください](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)。

![Teams に表示されるユーザーの電話番号。](media/teams-phone-number.png)

ユーザーが通話を送受信できるようユーザーを設定する場合は、まず Microsoft Teams 管理センターを使用して電話番号を割り当てる必要があります。 必要に応じて、電話番号を変更または削除できます。
  
Teams で通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
  
> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する 1 つの方法は、Microsoft Teams 管理センターの [ユーザー] > **します**。 ライセンスが割り当てられている場合は、ページに表示されます。  Microsoft 365 管理センターを使用する方法もあります。
  
## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**
    
1. 左側のナビゲーションで、[音声電話番号 **]**  >  **をクリックします**。
2. [電話番号 **] ページで** 、一覧から割り当てられていない番号を選び、[編集] をクリック **します**。  
3. [編集] **ウィンドウの** [割 **り当て** 済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] をクリック **します**。
4. 関連する緊急対応の場所を割り当てる、または変更するには、[緊急対応の場所] で場所を検索して選択します。
5. 電話番号情報を含むメールをユーザーに送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、オンになっています。 
6. **[保存]** をクリックします。

PowerShell の例については [、「Set-CsOnlineVoiceUser」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**
    
1. 左側のナビゲーションで [ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[音声電話番号 **]**  >  **をクリックします**。
3. [電話番号 **] ページで** 、手順 1 で識別した番号を選び、[編集] をクリック **します**。  
4. [編集]**ウィンドウの**[割り当 **て済み] で****、[X]** をクリックしてユーザーを削除します。
5. **[保存]** をクリックします。
6. [電話番号 **] ページで** 、一覧から割り当てられていない番号を選び、[編集] をクリック **します**。  
7. [編集] **ウィンドウの** [割 **り当て** 済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] をクリック **します**。
8. 関連する緊急対応の場所を割り当てる、または変更するには、[緊急対応の場所] で場所を検索して選択します。
9. **[保存]** をクリックします。

PowerShell の例については [、「Set-CsOnlineVoiceUser」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで [ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[音声電話番号 **]**  >  **をクリックします**。
3. [電話番号 **] ページで** 、手順 2 で識別した番号を選び、[編集] をクリック **します**。  
4. [編集]**ウィンドウの**[割り当 **て済み] で****、[X]** をクリックしてユーザーを削除します。
5. **[保存]** をクリックします。

PowerShell の例については [、「Set-CsOnlineVoiceUser」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

## <a name="related-topics"></a>関連項目

[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Microsoft 365 の通話プラン](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
