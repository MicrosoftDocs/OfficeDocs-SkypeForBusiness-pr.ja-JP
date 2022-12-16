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
description: 外部の企業やクライアントが電話をかけることができるように、Teams ユーザーの勤務先電話番号を割り当て、変更、または削除する方法について説明します。
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414685"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>ユーザーの電話番号を割り当て、変更、または削除する

通話プラン、オペレーター接続、または Teams Phone Mobile を設定すると、ユーザーに電話番号を割り当てます。 Microsoft Teams では、ユーザーが **[通話**] をクリックしたときに割り当てた電話番号が一覧表示されます。

この記事は、通話プラン、オペレーター接続、および Teams Phone Mobile に適用されます。 ダイレクト ルーティング シナリオでユーザーから電話番号を割り当てる、変更する、または削除する方法については、「 [ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする](./direct-routing-enable-users.md)」を参照してください。

通話プラン、オペレーター接続、または Teams Phone Mobile ユーザーの番号を割り当てる前に、ユーザーの番号を取得する必要があります。 詳細については、「 [通話プラン ユーザーの番号を取得する](getting-phone-numbers-for-your-users.md)」、「 [オペレーター接続ユーザーの番号を設定](operator-connect-configure.md#set-up-phone-numbers)する」、または [「Teams Phone Mobile ユーザーの番号を設定する」を参照してください](operator-connect-mobile-configure.md)。

> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する 1 つの方法は、Microsoft Teams 管理センター> Users に移動 **することです**。 ライセンスが割り当てられている場合は、ページに表示されます。  Microsoft 365 管理センターを使用することもできます。

> [!NOTE]
> このメモは、オンプレミスの Active Directoryを使用してハイブリッド展開を行っているお客様に適用されます。 通話プランまたはオペレーター接続の電話番号をユーザーまたはリソース アカウントに割り当てる場合は、オンプレミスの Active Directoryのユーザーまたはリソース アカウント オブジェクトの msRTCSIP-Line 属性に格納されている電話番号が削除され、変更が Microsoft 365 に同期されていることを確認する必要があります。

## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる

ユーザーに電話番号を割り当てる場合は、電話番号とユーザーの使用場所が同じ国であることを確認します。

Teams 管理センターを使用して数値を割り当てるには:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


PowerShell を使用して数値を割り当てるには、次のように [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) コマンドレットを使用します。

通話プラン番号の場合:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Operator Connect 番号の場合:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Teams の携帯電話番号の場合:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

次に例を示します。

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```

> [!NOTE]
> Microsoft 365 と Teams の間の待機時間のため、ユーザーが有効になるまでに最大 24 時間かかることがあります。 24 時間後に電話番号が正しく割り当てられない場合は、「 [電話番号サービス センター](https://pstnsd.powerappsportals.com/)」を参照してください。

> [!NOTE]
> 電話番号を割り当てると、EnterpriseVoiceEnabled フラグが自動的に True に設定されます。

## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する

Teams 管理センターを使用してユーザーの電話番号を変更するには:

1. 左側のナビゲーションで、[ **ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[ **アカウント**] をクリックし、[ **全般情報**] の下で、ユーザーに割り当てられている電話番号をメモします。

2. 左側のナビゲーションで、[ **音声** \> **電話番号**] をクリックします。

3. [ **電話番号** ] ページで、手順 1 で特定した番号を選択し、[ **編集**] をクリックします。

4. [ **編集** ] ウィンドウの [ **割り当て** 先] で、[ **X** ] をクリックしてユーザーを削除します。

5. **[保存]** をクリックします。

6. [ **電話番号** ] ページで、一覧で割り当てられていない番号を選択し、[ **編集**] をクリックします。

7. [ **編集** ] ウィンドウの [ **割り当て先**] で、表示名またはユーザー名でユーザーを検索し、[ **割り当て**] をクリックします。

8. 関連付けられている緊急の場所を割り当てるか変更するには、[ **緊急対応の場所**] で場所を検索して選択します。

      > [!NOTE]
      > オペレーター接続または Teams Phone Mobile ユーザーの番号を変更する場合は、関連付けられている緊急対応の場所を割り当てたり変更したりできない場合があります。 この機能は、オペレーターによって異なります。 詳細については、オペレーターにお問い合わせください。

9. **[保存]** をクリックします。

PowerShell の例については、「 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)」を参照してください。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する

Teams 管理センターを使用して電話番号を削除するには:

1. 左側のナビゲーションで、[ **ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[ **アカウント**] をクリックし、[ **全般情報**] の下で、ユーザーに割り当てられている電話番号をメモします。

2. 左側のナビゲーションで、[ **音声** \> **電話番号**] をクリックします。

3. [ **電話番号** ] ページで、手順 2 で特定した番号を選択し、[ **編集**] をクリックします。

4. [ **編集** ] ウィンドウの [ **割り当て** 先] で、[ **X** ] をクリックしてユーザーを削除します。

5. **[保存]** をクリックします。

PowerShell の例については、「 [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)」を参照してください。

## <a name="related-topics"></a>関連項目

[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
