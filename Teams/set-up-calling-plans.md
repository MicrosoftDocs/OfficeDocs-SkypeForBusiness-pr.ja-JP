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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- LIL_Placement
- seo-marvel-mar2020
description: お客様の地域で利用可能なプランの表示、& ライセンスの割り当て、電話番号の取得、緊急対応の住所の追加など、通話プランのセットアップ方法について&します。
ms.openlocfilehash: a06ec3b71933e8e6ea640b6377581243140ef672
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117125"
---
# <a name="set-up-calling-plans"></a>通話プランの設定

他の Teams ユーザーへの通話は無料ですが、ユーザーが社外の電話に発信するには、Microsoft 365 または Office 365 で国内通話プランまたは国際通話プランを利用します。 ビジネス向け通話プランは簡単にセットアップできます。  通話プランの詳細については、「最適な通話プラン [」を参照してください](calling-plan-landing-page.md)。

## <a name="step-1-find-out-if-calling-plans-are-available-in-your-countryregion"></a>手順 1: お客様の国/地域で通話プランが使用できるかどうかを確認する
[電話会議および通話プランが利用可能な国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) で、お住まいの国と地域を選択し、電話会議、通話プラン、電話システム、有料または無料電話番号、通信クレジットについての情報を確認します。

お客様の国または地域で通話プランを利用できない場合は、ダイレクト ルーティングを使用して、オンプレミスのテレフォニー インフラストラクチャを電話システムに接続します。  詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。
  
## <a name="step-2-buy-and-assign-licenses"></a>手順 2: ライセンスを購入して割り当てる
1. 電話システム機能が Microsoft 365 または Office 365 プランに含まれていない場合は、電話システムアドオン ライセンスの購入が必要な場合があります。 電話システム ライセンス **を取得した** 後 [、Microsoft 365](calling-plans-for-office-365.md)または Office 365 の通話プランを購入します。 ライセンスとプランの購入については、[Microsoft Teams アドオンライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) を参照してください。 
    
    > [!TIP]
    >  Microsoft 365 または Office 365 の電話システム ライセンスと通話プランは一緒に行うので、通話プランを購入するオプションを確認するには、まず電話システム ライセンスを持っている **必要** があります。
  
2. まずライセンスを割り当て、組織内のユーザーに通話プランを割り当てます。 「Microsoft [Teams アドオン ライセンスを割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
## <a name="step-3-get-phone-numbers"></a>手順 3: 電話番号を取得する
新しいユーザー番号を取得する方法には次の 3 通りあります。

- **Teams 管理センターを使用します。** 一部の国/地域では、Teams 管理センターを使用してユーザーの電話番号を取得できます。「ユーザーの電話番号を取得する」 [を参照してください](getting-phone-numbers-for-your-users.md)。
    
- **既存の番号を移行する。** 現在のサービス プロバイダーまたは携帯電話会社から Microsoft 365 または Office 365 に既存の番号を移植または転送できます。 詳細については、「Teams に電話番号 [を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 」または「組織の電話番号を [管理する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
  
- **新しい番号には申請書を使用します。** (お客様の国/地域によって異なります) Teams 管理センターを使用して新しい電話番号を取得できない場合や、特定の電話番号または市番が必要になる場合があります。 その場合は、申請書をダウンロードして送信する必要があります。 詳細については、「[組織のために電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。 

## <a name="step-4-add-emergency-addresses-and-locations-for-your-organization"></a>手順 4: 組織の緊急連絡先の住所と場所を追加する
<a name="bkmk_add_addresses"></a>緊急対応の住所は電話番号に関連付けられている必要があります。 この関連付けは、国や地域によって異なる場合があります。 例えば米国では、電話番号をユーザーに割り当てるときに、緊急対応の住所を関連付ける必要があります。 英国では、Microsoft 365 または Office 365 から電話番号を取得する場合、または現在のサービス プロバイダーから電話番号を移行する場合、緊急対応の住所を電話番号に関連付ける必要があります。 

緊急通話と緊急対応の住所の管理については、「緊急[](what-are-emergency-locations-addresses-and-call-routing.md)通話の管理」および「組織の緊急対応の場所を追加、変更、または削除する」を[参照してください](add-change-remove-emergency-location-organization.md)。
    
## <a name="step-5-assign-an-emergency-address-and-a-phone-number-to-a-user"></a>手順 5: ユーザーに緊急連絡先の住所と電話番号を割り当てる
<a name="bkmk_add_addresses"> </a> Office 365 の通話プランを設定する場合は、各ユーザーに電話番号と緊急連絡先を割り当てる必要があります。 電話番号に関連付けるには、先に緊急連絡先の住所を作成する必要があります。  詳細については、「緊急対応の住所を [割り当てる、または変更する」を参照してください](assign-change-emergency-location-user.md)。


> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。



## <a name="step-6-tell-your-users-about-their-new-phone-numbers"></a>手順 6: 新しい電話番号をユーザーに通知する

Microsoft では、新しい電話番号についてユーザーに通知するために、メールを送信するか、またはお客様のビジネスに優先する通信方法を使用する方法をお勧めします。
 
**Microsoft Teams** では、ユーザーは左側のナビゲーションで [**通話**] をクリックすると、自分の電話番号を表示できます。電話番号はダイヤル パッドの上部に表示されます。

![[通話] をクリックした後に使用できるオプションのスクリーン ショット](media/teams-phone-number.png)


## <a name="do-you-want-to-automate-assigning-phone-numbers"></a>電話番号の割り当てを自動化したい場合
<a name="bkmk_add_addresses"> </a>

Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。 
  
- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber?view=skype-ps): Business Voice Directory から電話番号を取得します。
    
- [Set-CsOnlineVoiceUser](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps): 電話番号を設定します。
    
詳細については [、「Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。
  

## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md) 

[組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Teams: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
