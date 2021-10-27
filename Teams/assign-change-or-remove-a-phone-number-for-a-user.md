---
title: ユーザーの電話番号を割り当て、変更、または削除する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.openlocfilehash: 5e8041ce0a8cc95549a9dc75c0c8d74cd2438e1c
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579517"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>ユーザーの電話番号を割り当て、変更、または削除する

通話プランまたはオペレーター アカウントを設定するとConnectに電話番号が割り当てされます。 このMicrosoft Teamsユーザーが [通話] をクリックすると、割り当てる電話番号が一覧表示 **されます**。 

この記事は、通話プランとオペレーター サービスにConnect。 ダイレクト ルーティング シナリオでユーザーの電話番号を割り当て、変更、または削除する方法については、「ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする」 [を参照してください](./direct-routing-enable-users.md)。

通話プランまたはオペレーター ユーザーに番号を割り当てるConnect、ユーザーの番号を取得する必要があります。 詳細については、「通話プランのユーザーの[番号を取得](getting-phone-numbers-for-your-users.md)する」または「オペレーターユーザーの番号を設定する[」Connectしてください](operator-connect-configure.md#set-up-phone-numbers)。

  
> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する方法の 1 つは、[ユーザー] の管理Microsoft Teamsに>**です**。 ライセンスが割り当てられている場合は、ページに表示されます。  また、次のMicrosoft 365 管理センター。

> [!NOTE]
> このメモは、オンプレミスの Active Directory を使用してハイブリッドデプロイを行うお客様に適用されます。 通話プランまたはオペレーター Connect の電話番号をユーザーまたはリソース アカウントに割り当てる場合は、オンプレミスの Active Directory の電話番号が削除され、変更が Microsoft 365 に同期されている必要があります。
  
## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる

ユーザーに電話番号を割り当てるときに、電話番号とユーザーの使用場所が同じ国に設定されている必要があります。

管理センターで番号を割りTeamsするには:
    
1. 左側のナビゲーションで、[Voice **電話**  >  **をクリックします**。

2. [番号 **電話ページで**、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  

3. [編集] **ウィンドウの** [割 **り** 当て済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。

4. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。

   > [!NOTE]
   > オペレーターユーザーに番号を割り当てるConnect、関連する緊急対応の場所を割り当てまたは変更できない場合があります。 この機能は、オペレーターによって異なる場合があります。 詳細については、オペレーターにお問い合わせください。

5. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。 

6. **[保存]** をクリックします。

PowerShell を使用して数値を割り当てるには、次のように [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) コマンドレットを使用します。


''PowerShell Set-CsOnlineVoiceUser -Identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> ユーザーが有効になるには、Microsoft 365と Teamsの間の待機時間が長くなる可能性があります。最大 24 時間かかる場合があります。 電話番号が 24 時間後に正しく割り当てられていない場合は、「電話[サービス センター」を参照してください](https://pstnsd.powerappsportals.com/)。 

  
## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する

管理センターでユーザーの電話番号を変更するにはTeamsします。
    
1. 左側のナビゲーションで 、[ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 

2. 左側のナビゲーションで、[Voice **電話**  >  **をクリックします**。

3. [番号 **電話ページ** で、手順 1 で識別した番号を選択し、[編集] をクリック **します**。  

4. [編集]**ウィンドウの**[割り当て **] で****、[X] をクリックして** ユーザーを削除します。

5. **[保存]** をクリックします。

6. [番号 **電話ページで**、一覧で未割り当て番号を選択し、[編集] を **クリックします**。  

7. [編集] **ウィンドウの** [割 **り** 当て済み] で、表示名またはユーザー名でユーザーを検索し、[割り当て] を **クリックします**。

8. 関連付けられている緊急対応の場所を割り当てるか変更するには、[緊急 **対応の場所**] で場所を検索して選択します。

      > [!NOTE]
      > オペレーターユーザーの番号を変更するConnect、関連する緊急対応の場所を割り当てまたは変更できない場合があります。 この機能は、オペレーターによって異なる場合があります。 詳細については、オペレーターにお問い合わせください。

9. **[保存]** をクリックします。

PowerShell の例については [、Set-CsOnlineVoiceUser に関するページを参照してください](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する

管理センターで電話番号を削除するにはTeams使用します。

1. 左側のナビゲーションで 、[ユーザー] をクリックし、目的のユーザーを見つけてダブルクリックし、[アカウント]をクリックし、[全般情報] で、ユーザーに割り当てられている電話番号をメモします。 

2. 左側のナビゲーションで、[Voice **電話**  >  **をクリックします**。

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

