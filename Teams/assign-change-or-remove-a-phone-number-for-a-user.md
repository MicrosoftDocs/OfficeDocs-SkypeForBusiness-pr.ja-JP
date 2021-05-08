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
description: 外部の企業やクライアントがコールインできるよう、Teamsの電話番号を割り当て、変更、または削除する方法について学習します。
ms.openlocfilehash: 4f40049b3856f24d3ae5ddd3999be7213817bcdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120819"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>ユーザーの電話番号を割り当て、変更、または削除する (通話プラン)

通話プランを設定すると、ユーザーに電話番号が割り当てされます。 このMicrosoft Teamsユーザーが [通話] をクリックすると、割り当てる電話番号が一覧表示 **されます**。 ダイレクト ルーティング シナリオでユーザーの電話番号を割り当て、変更、または削除する手順については、「ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする」 [を参照してください](./direct-routing-enable-users.md)。

![ユーザーの電話番号が [Teams] に表示されます。](media/teams-phone-number.png)

ユーザーが電話を送受信できるようユーザーを設定する場合は、まず Microsoft Teams 管理センターを使用して電話番号を割り当てる必要があります。 必要に応じて、電話番号を変更または削除できます。
  
Teams で通話プランを取得する方法と料金については[、「Teams」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する方法の 1 つは、管理センターの [ユーザー] Microsoft Teamsに>**です**。 ライセンスが割り当てられている場合は、ページに表示されます。  また、管理センター Microsoft 365使用できます。
  
## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**
    
1. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
2. [番号 **電話ページで**、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  
3. [編集] **ウィンドウの** [割 **り** 当て] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。
4. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。
5. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。 
6. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**
    
1. 左側のナビゲーションで [ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
3. [番号 **電話ページで**、手順 1 で識別した番号を選択し、[編集] をクリック **します**。  
4. [編集]**ウィンドウの**[割り当て **] で****、[X] をクリックして** ユーザーを削除します。
5. **[保存]** をクリックします。
6. [番号 **電話ページで**、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  
7. [編集] **ウィンドウの** [割 **り** 当て] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。
8. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。
9. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する
 
![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで [ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
3. [番号 **電話ページで**、手順 2 で識別した番号を選択し、[編集] を **クリックします**。  
4. [編集]**ウィンドウの**[割り当て **] で****、[X] をクリックして** ユーザーを削除します。
5. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)。

## <a name="related-topics"></a>関連トピック

[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[通話プランのMicrosoft 365](./calling-plans-for-office-365.md)