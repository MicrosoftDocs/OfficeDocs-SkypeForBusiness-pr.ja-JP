---
title: Microsoft Teams Calling プランを設定する
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
- m365initiative-voice
- highpri
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
description: 地域で利用可能なプランの表示、ライセンスの割り当て&購入、電話番号の取得、緊急対応&場所の追加など、通話プランを設定する方法について説明します。
ms.openlocfilehash: ac46c40fb5a63a40ed2ecbdc5f43fa71137f780c
ms.sourcegitcommit: 0a13f96663c7466b08d654bedcb6206f302189a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2022
ms.locfileid: "69139151"
---
# <a name="set-up-microsoft-teams-calling-plans"></a>Microsoft Teams Calling プランを設定する

他の Teams ユーザーへの通話は無料ですが、ユーザーが業務外で電話をかけることができるようにするには、ニーズに基づいて、国内通話プラン、国際通話プラン、または Microsoft 365 の従量課金制通話プランを入手します。 ビジネスにMicrosoft Teams Calling プランを簡単に設定できます。  通話プランの詳細については、「 [どの通話プランが適しているか](calling-plan-landing-page.md)」を参照してください。

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>手順 1: お客様の国/地域で通話プランが使用できるかどうかを確認する

[[電話会議と通話プランの国と地域の可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)] に移動し、国または地域を選択して通話プランに関する可用性情報と、電話会議、Teams 電話、有料電話番号、フリーダイヤル番号、コミュニケーション クレジットに関する情報を取得します。

通話プランが国または地域で利用できない場合は、使用可能なすべての [オプションの PSTN 接続オプション](pstn-connectivity.md) に関するページを参照してください。
  
## <a name="step-2-buy-and-assign-licenses"></a>手順 2: ライセンスを購入して割り当てる

1. Teams Phone 機能が Microsoft 365 プランに含まれていない場合は、 **電話システム** アドオン ライセンスの購入が必要になる場合があります。 **電話システム** ライセンスを取得したら、[Microsoft 365 の通話プランを](calling-plans-for-office-365.md)購入します。 ライセンスとプランの購入については、[Microsoft Teams アドオンライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) を参照してください。

    > [!TIP]
    > Microsoft 365 の **電話システム** ライセンスと通話プランは連携しているため、通話プランを購入するオプションを確認するには、まず **電話システム** ライセンスが必要です。
  
2. 最初にライセンスを割り当て、次に通話プランライセンスを組織内のユーザーに割り当てます。 [「Microsoft Teams アドオン ライセンスを割り当てる」を](./teams-add-on-licensing/assign-teams-add-on-licenses.md)参照してください。
    1. 従量課金制通話プランを購入する場合は、コミュニケーション クレジットの購入が必要になる場合があります。 コミュニケーション クレジットを購入する必要があるかどうかを判断するには、「 [従量課金制通話プランに資金を提供する方法」を](calling-plans-for-office-365.md#how-to-fund-a-pay-as-you-go-calling-plan)参照してください。

## <a name="step-3-get-phone-numbers"></a>手順 3: 電話番号を取得する

新しいユーザー番号を取得する方法には次の 3 通りあります。

- **Teams 管理センターを使用します。** 一部の国/地域では、Teams 管理センターを使用してユーザーの番号を取得できます。「 [ユーザーの電話番号を取得する](getting-phone-numbers-for-your-users.md)」を参照してください。

- **既存の番号を移行する。** 現在のサービス プロバイダーまたは電話会社から Microsoft 365 に既存の番号を移植または転送できます。 詳細については、「 [Teams に電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 」または [「組織の電話番号を管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。
  
- **新しい番号には申請書を使用します。** (国/地域によっては) Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号や市域コードが必要になる場合があります。 その場合は、フォームをダウンロードして返送する必要があります。 詳細については、「[組織のために電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>手順 4: 組織の緊急連絡先の住所と場所を追加する
<a name="bkmk_add_addresses"> </a>

緊急対応の住所を電話番号に関連付ける必要があります。 この関連付けが行われると、国と地域によって異なる場合があります。 例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。 英国では、Microsoft 365 から電話番号を取得するとき、または現在のサービス プロバイダーから電話番号を転送するときに、緊急対応アドレスを電話番号に関連付ける必要があります。

緊急通報と緊急対応アドレスの管理については、「 [緊急通報の管理](what-are-emergency-locations-addresses-and-call-routing.md) 」および [「組織の緊急対応の場所を追加、変更、または削除する](add-change-remove-emergency-location-organization.md)」を参照してください。

## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>手順 5: ユーザーに緊急連絡先の住所と電話番号を割り当てる
<a name="bkmk_add_addresses"> </a>

Microsoft 365 で通話プランを設定する場合は、各ユーザーに電話番号と緊急対応アドレスを割り当てる必要があります。 電話番号に関連付けるには、先に緊急連絡先の住所を作成する必要があります。 詳細については、「 [緊急対応アドレスの割り当てまたは変更](assign-change-emergency-location-user.md)」を参照してください。

> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。

## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>手順 6: 新しい電話番号をユーザーに通知する

Microsoft では、メールを送信するか、ビジネスで推奨されるコミュニケーション方法を使用して、新しい電話番号についてユーザーに伝えることをお勧めします。

In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![[通話] をクリックした後に使用できるオプションのスクリーン ショット。](media/teams-phone-number.png)

## <a name="run-a-self-diagnostics-tool"></a>自己診断ツールを実行する

Microsoft 365 管理者ユーザーは、ユーザーが PSTN 呼び出しを行うか受信するように適切に構成されていることを確認するために、テナント内で実行できる診断にアクセスできます。

> [!NOTE]
>この機能は、Microsoft 365 Government、21Vianet が運営する Microsoft 365、または Microsoft 365 Germany では使用できません。

次のように、[テストの実行] を選択します。 これにより、Microsoft 365 管理 センターに診断が設定されます。
>> [!div class="nextstepaction"]
>> [テストの実行: Teams PSTN](https://aka.ms/TeamsPSTNDiag)

診断では、さまざまな検証が実行されます。

## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>電話番号の割り当てを自動化したい場合
<a name="bkmk_add_addresses"> </a>

Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。
  
- [Get-CsPhoneNumberAssignment](/powershell/module/teams/Get-CsPhoneNumberAssignment): テナントから電話番号を取得します。

- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment): 電話番号を設定します。

詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。
  
## <a name="related-articles"></a>関連記事

[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)

[組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Teams: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
