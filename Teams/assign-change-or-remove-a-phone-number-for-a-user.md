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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 外部の企業やクライアントがコールインできるよう、Teamsの電話番号を割り当て、変更、または削除する方法について学習します。
ms.openlocfilehash: 44254c8d8c8886e72b699c3890017a2b817cd135
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727506"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>ユーザーの電話番号を割り当て、変更、または削除する (通話プラン)

通話プランを設定すると、ユーザーに電話番号が割り当てされます。 このMicrosoft Teamsユーザーが [通話] をクリックすると、割り当てる電話番号が一覧表示 **されます**。 ダイレクト ルーティング シナリオでユーザーの電話番号を割り当て、変更、または削除する手順については、「ユーザーに直接ルーティング、音声、ボイスメールを有効にする」を [参照してください](./direct-routing-enable-users.md)。

![ユーザーの電話番号が [Teams] に表示されます。](media/teams-phone-number.png)

ユーザーが通話を送受信できるようユーザーを設定する場合は、まず、Microsoft Teams 管理センターを使用して電話番号を割り当てる必要があります。 必要に応じて、電話番号を変更または削除できます。
  
Teams で通話プランを取得する方法と料金については[、「Teams」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する方法の 1 つは、[ユーザー] の管理Microsoft Teamsに>**です**。 ライセンスが割り当てられている場合は、ページに表示されます。  また、次のMicrosoft 365 管理センター。
  
## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる
 
![ロゴのアイコンMicrosoft Teams表示されます。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**
    
1. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
2. [番号 **電話] ページ** で、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  
3. [編集] **ウィンドウの** [割 **り** 当て済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。
4. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。
5. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。 
6. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser)。

> [!NOTE]
> Microsoft 365 または Office 365 と Teams の間の待機時間のため、ユーザーが有効になるのに最大 24 時間かかる場合があります。 電話番号が 24 時間後に正しく割り当てられていない場合は、ビジネス製品のサポートに問い [合わせ - 管理者向けヘルプ を参照してください](/microsoft-365/admin/contact-support-for-business-products)。 お手伝いします。

  
## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する
 
![ロゴのアイコンMicrosoft Teams表示されます。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**
    
1. 左側のナビゲーションで 、[ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
3. [番号 **電話ページ** で、手順 1 で識別した番号を選択し、[編集] をクリック **します**。  
4. [編集]**ウィンドウの**[割り当て **] で****、[X] をクリックして** ユーザーを削除します。
5. **[保存]** をクリックします。
6. [番号 **電話] ページ** で、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  
7. [編集] **ウィンドウの** [割 **り** 当て済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。
8. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。
9. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する
 
![ロゴのアイコンMicrosoft Teams表示されます。](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで 、[ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 
2. 左側のナビゲーションで、[Voice電話  >  **をクリックします**。
3. [番号 **電話ページで**、手順 2 で識別した番号を選択し、[編集] を **クリックします**。  
4. [編集]**ウィンドウの**[割り当て **] で****、[X] をクリックして** ユーザーを削除します。
5. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="related-topics"></a>関連項目

[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

[通話プランのMicrosoft 365](./calling-plans-for-office-365.md)
