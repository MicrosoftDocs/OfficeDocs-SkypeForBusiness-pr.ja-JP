---
title: 通話プランの設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- LIL_Placement
- seo-marvel-mar2020
description: 地域で利用可能なプランの表示、ライセンスの割り当て&購入、電話番号の取得、緊急対応住所の&場所の追加など、通話プランを設定する方法について説明します。
ms.openlocfilehash: 4b459e82aa99194dc62c721d42b162961b61f372
ms.sourcegitcommit: cd9fbda4ea85a83cb22e241a94d0825ff8186cca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62228935"
---
# <a name="set-up-calling-plans"></a>通話プランの設定

他のTeamsユーザーへの通話は無料ですが、ユーザーが社外で電話を発信できるようにするには、国内通話プランまたは国際通話プランをMicrosoft 365で取得します。 ビジネス向けの通話プランを簡単に設定できます。  通話プランの詳細については、「 [どの通話プランが適しているか」を](calling-plan-landing-page.md)参照してください。

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>手順 1: お客様の国/地域で通話プランが使用できるかどうかを確認する
[電話会議と通話プランの国と地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)に移動し、国または地域を選択して通話プランに関する可用性情報のほか、電話会議、Teams 電話、有料電話番号、フリーダイヤル番号、通信クレジットに関する情報を取得します。

国または地域で通話プランを使用できない場合は、使用可能なすべての [オプションについて PSTN 接続オプション](pstn-connectivity.md) を参照してください。
  
## <a name="step-2-buy-and-assign-licenses"></a>手順 2: ライセンスを購入して割り当てる
1. Teams 電話機能がMicrosoft 365 プランに含まれていない場合は、アドオン ライセンス **電話システム** 購入する必要がある場合があります。 **ライセンスを電話システム** したら、[Microsoft 365の通話プランを](calling-plans-for-office-365.md)購入します。 ライセンスとプランの購入については、[Microsoft Teams アドオンライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) を参照してください。 
    
    > [!TIP]
    > **電話システム** ライセンスとMicrosoft 365での通話プランが一緒に行われるため、通話プランを購入するオプションを確認するには、最初に **電話システム** ライセンスが必要です。
  
2. まずライセンスを割り当て、組織内のユーザーに通話プランを割り当てます。 [アドオン ライセンスMicrosoft Teams割り当てるに関するページを](./teams-add-on-licensing/assign-teams-add-on-licenses.md)参照してください。
    
## <a name="step-3-get-phone-numbers"></a>手順 3: 電話番号を取得する
新しいユーザー番号を取得する方法には次の 3 通りあります。

- **Teams管理センターを使用します。** 一部の国/地域では、Teams管理センターを使用してユーザーの番号を取得できます。「[ユーザーの電話番号を取得する」を参照してください](getting-phone-numbers-for-your-users.md)。
    
- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社からMicrosoft 365に既存の番号を移植または転送できます。 詳細については、「電話番号[をTeamsに転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」または「[組織の電話番号を管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
  
- **新しい番号には申請書を使用します。** Teams管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市外局番が必要になる場合があります。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については、「[組織のために電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。 

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>手順 4: 組織の緊急連絡先の住所と場所を追加する
<a name="bkmk_add_addresses"> </a> 緊急対応の住所は電話番号に関連付ける必要があります。 この関連付けが発生した場合、国と地域によって異なる場合があります。 例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。 英国では、Microsoft 365から電話番号を取得するとき、または現在のサービス プロバイダーから電話番号を転送する場合は、緊急アドレスを電話番号に関連付ける必要があります。 

緊急通報と緊急対応住所の管理については、「緊急通報の [管理](what-are-emergency-locations-addresses-and-call-routing.md) と、 [組織の緊急対応の場所の追加、変更、または削除を管理する」を参照してください](add-change-remove-emergency-location-organization.md)。
    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>手順 5: ユーザーに緊急連絡先の住所と電話番号を割り当てる
<a name="bkmk_add_addresses"> </a> Microsoft 365で通話プランを設定する場合は、各ユーザーに電話番号と緊急時の住所を割り当てる必要があります。 電話番号に関連付けるには、先に緊急連絡先の住所を作成する必要があります。 詳細については、「 [緊急対応住所の割り当てまたは変更](assign-change-emergency-location-user.md)」を参照してください。


> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。 



## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>手順 6: 新しい電話番号をユーザーに通知する

Microsoft では、メールを送信するか、ビジネスで推奨される通信方法を使用して、新しい電話番号についてユーザーに伝えることをお勧めします。
 
**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。

![[通話] をクリックした後に使用できるオプションのスクリーン ショット。](media/teams-phone-number.png)

## <a name="run-a-self-diagnostics-tool"></a>自己診断ツールを実行する

Microsoft 365管理者ユーザーは、テナント内で実行できる診断にアクセスして、PSTN 通話を発信または受信するようにユーザーが適切に構成されていることを確認できます。 

> [!NOTE]
>この機能は、Microsoft 365政府機関、Microsoft 365 21Vianet、またはMicrosoft 365ドイツでは使用できません。

次のように、[テストの実行] を選択します。 これにより、Microsoft 365 管理 センターに診断が設定されます。
>> [!div class="nextstepaction"]
>> [テストの実行: PSTN をTeamsする](https://aka.ms/TeamsPSTNDiag)

診断では、さまざまな検証が実行されます。

## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>電話番号の割り当てを自動化したい場合
<a name="bkmk_add_addresses"> </a>

Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。 
  
- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber?view=skype-ps): Business Voice Directory から電話番号を取得します。
    
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment?view=teams-ps): 電話番号を設定します。
    
詳細については、[PowerShell の概要Teams](teams-powershell-overview.md)参照してください。
  

## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md) 

[組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Teams: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
