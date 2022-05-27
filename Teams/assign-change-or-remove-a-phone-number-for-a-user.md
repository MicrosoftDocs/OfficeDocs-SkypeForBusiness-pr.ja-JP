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
description: 外部の企業やクライアントが呼び出すことができるように、Teams ユーザーの勤務先の電話番号を割り当て、変更、または削除する方法について説明します。
ms.openlocfilehash: dc616425b4dce35a2a40179e0ee4a56d31bae12b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676489"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>ユーザーの電話番号を割り当て、変更、または削除する

通話プランまたはオペレーター接続を設定するときに、ユーザーに電話番号を割り当てます。 Microsoft Teamsでは、ユーザーが **[通話**] をクリックすると、割り当てる電話番号が一覧表示されます。

この記事は、通話プランとオペレーター接続に適用されます。 ダイレクト ルーティング シナリオでユーザーに電話番号を割り当てる、変更する、または削除する方法については、「ダイレクト ルーティング [、音声、ボイスメールのユーザーを有効にする](./direct-routing-enable-users.md)」を参照してください。

通話プランまたはオペレーター接続ユーザーに番号を割り当てる前に、ユーザーの番号を取得する必要があります。 詳細については、「[通話プランユーザーの番号を取得する](getting-phone-numbers-for-your-users.md)」または[「オペレーター接続 ユーザーの番号を設定する](operator-connect-configure.md#set-up-phone-numbers)」を参照してください。

> [!NOTE]
> ユーザーにライセンスが割り当てられているかどうかを確認する 1 つの方法は、Microsoft Teams管理センター> **Users** に移動することです。 ライセンスが割り当てられている場合は、ページに表示されます。  Microsoft 365 管理センターを使用することもできます。

> [!NOTE]
> このメモは、オンプレミスの Active Directoryを使用してハイブリッド展開を行っているお客様に適用されます。 通話プランまたはオペレーター接続電話番号をユーザーまたはリソース アカウントに割り当てる場合は、オンプレミスの Active Directoryのユーザーまたはリソース アカウント オブジェクトの msRTCSIP-Line 属性に格納されているすべての電話番号が削除され、変更がMicrosoft 365に同期されていることを確認する必要があります。

## <a name="assign-a-phone-number-to-a-user"></a>ユーザーに電話番号を割り当てる

ユーザーに電話番号を割り当てる場合は、電話番号とユーザーの使用場所が同じ国であることを確認します。

Teams管理センターを使用して番号を割り当てるには:

1. 左側のナビゲーションで、[**Voice** > **電話 numbers**] をクリックします。

2. **[電話番号**] ページで、一覧で割り当てられていない番号を選択し、[編集] をクリック **します**。

3. **[編集]** ウィンドウの [**割り当て元**] で、表示名またはユーザー名でユーザーを検索し、[**割り当て**] をクリックします。

4. 関連付けられている緊急対応の場所を割り当てるか変更するには、[ **緊急の場所]** で場所を検索して選択します。

   > [!NOTE]
   > オペレーター接続ユーザーに番号を割り当てる場合は、関連する緊急対応の場所を割り当てたり変更したりできない場合があります。 この機能は、オペレーターによって異なります。 詳細については、オペレーターにお問い合わせください。

5. 電話番号情報を含む電子メールをユーザーに送信するかどうかに応じて、電話番号情報を **含む電子メール ユーザーを** オフまたはオンにします。 既定では、これはオンです。
6. **[保存]** をクリックします。

PowerShell を使用して数値を割り当てるには、 [次のように Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) コマンドレットを使用します。

通話プラン番号の場合:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

オペレーター接続番号の場合:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

次に例を示します。

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> Microsoft 365とTeamsの間の待機時間のため、ユーザーが有効になるまでに最大で 24 時間かかる場合があります。 24 時間後に電話番号が正しく割り当てられていない場合は、[番号サービス センター電話](https://pstnsd.powerappsportals.com/)参照してください。

## <a name="change-a-phone-number-for-a-user"></a>ユーザーの電話番号を変更する

Teams管理センターを使用してユーザーの電話番号を変更するには:

1. 左側のナビゲーションで [ **ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[ **アカウント**] をクリックし、[ **全般情報**] で、ユーザーに割り当てられている電話番号をメモします。

2. 左側のナビゲーションで、[**音声** \> **電話番号**] をクリックします。

3. **[電話番号**] ページで、手順 1 で識別した番号を選択し、[編集] をクリック **します**。

4. **[編集]** ウィンドウの [**割り当て対象**] で、[**X**] をクリックしてユーザーを削除します。

5. **[保存]** をクリックします。

6. **[電話番号**] ページで、一覧で割り当てられていない番号を選択し、[編集] をクリック **します**。

7. **[編集]** ウィンドウの [**割り当て元**] で、表示名またはユーザー名でユーザーを検索し、[**割り当て**] をクリックします。

8. 関連付けられている緊急対応の場所を割り当てるか変更するには、[ **緊急の場所]** で場所を検索して選択します。

      > [!NOTE]
      > オペレーター接続ユーザーの番号を変更する場合は、関連する緊急対応の場所を割り当てたり変更したりできない場合があります。 この機能は、オペレーターによって異なります。 詳細については、オペレーターにお問い合わせください。

9. **[保存]** をクリックします。

PowerShell の例については、「 [Set-CsPhoneNumberAssignment」を](/powershell/module/teams/set-csphonenumberassignment)参照してください。

## <a name="remove-a-phone-number-from-a-user"></a>ユーザーの電話番号を削除する

Teams管理センターを使用して電話番号を削除するには:

1. 左側のナビゲーションで [ **ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[ **アカウント**] をクリックし、[ **全般情報**] で、ユーザーに割り当てられている電話番号をメモします。

2. 左側のナビゲーションで、[**音声** \> **電話番号**] をクリックします。

3. **[電話番号**] ページで、手順 2 で識別した番号を選択し、[編集] をクリック **します**。

4. **[編集]** ウィンドウの [**割り当て対象**] で、[**X**] をクリックしてユーザーを削除します。

5. **[保存]** をクリックします。

PowerShell の例については、「 [Remove-CsPhoneNumberAssignment」を](/powershell/module/teams/remove-csphonenumberassignment)参照してください。

## <a name="related-topics"></a>関連項目

[住所検証とは何ですか?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
