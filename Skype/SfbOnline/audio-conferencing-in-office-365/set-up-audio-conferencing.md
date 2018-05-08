---
title: Skype for Business および Microsoft Teams の電話会議のセットアップ
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '電話を使用して会議に参加する必要のあるビジネスで、ユーザーのダイヤルインまたはオーディオ会議を設定する方法について説明します。 '
ms.openlocfilehash: 303b22f43a756fcade575dd63ae9bba205e6cbda
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Skype for Business および Microsoft Teams の電話会議のセットアップ

自分の組織内のユーザーが、会議にダイヤル インするために電話機を使用する必要がある場合があります。 Skype ビジネスおよびマイクロソフトのチームには、これだけのオーディオ会議機能を搭載! 人は、ビジネスまたはマイクロソフトのチームのアプリケーションをモバイル デバイスまたは PC 上で、Skype を使用する代わりに、電話を使用するビジネスまたはマイクロソフトのチームの会議、Skype を呼び出すことができます。 
  
のみ、スケジュールや会議を計画している人の電話会議を設定する必要があります。 ダイヤルイン会議の参加者、ライセンスを取得、またはその他の設定に割り当てられている必要はありません。
  
オーディオ会議についてよく寄せられる質問は、[オーディオ会議のよく寄せられる質問](audio-conferencing-common-questions.md)を参照してください。
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>オーディオ会議は、国/地域で利用可能なかどうかを調べる手順 1。
<a name="__top"> </a>


[オーディオ会議や予定を呼び出すことで可用性を国や地域](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)に移動し、国または地域およびフリー ダイヤル電話システムでは、計画を呼び出すには、有料の電話に関する情報だけでなく、オーディオ会議、情報の可用性を取得するを選択数字、および通信のクレジットです。 
 
## <a name="step-2-get-and-assign-licenses"></a>手順 2: を取得し、ライセンスを割り当てる
 
1. オーディオ会議では、ダイヤルイン会議の設定はユーザーごとにライセンスが必要です。 オーディオ会議と、コストはどのくらいのために購入する必要がありますライセンスについては、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
        
2. オーディオ会議のライセンスを購入した後は、人、組織の会議やスケジュールを設定するのに割り当てるには、勤務時間内です。 [割り当てまたはビジネス向けの Office 365 のライセンスを削除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)する、ユーザーが組織内で会議をスケジュールまたは潜在顧客を購入したを参照してください。
    
3. また (しないコストは何も) 通信のクレジットのライセンスを割り当てることをお勧め同じ人に前の手順でライセンスを割り当てられました。 通信のクレジットを設定する方法については、[組織の通信のクレジットの設定](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)を参照してください。
    
> [!NOTE]
> 1 分あたりの支払電話会議を設定することもできます。 移動[ここで](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md)それらを使用する方法の詳細を確認してください。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>手順 3: 会議用ブリッジは、サービス番号を取得します。
<a name="__top"> </a>

オーディオ会議では、ユーザーの電話番号を使うことはできません。サービス番号を取得する必要があります。 用、会議用ブリッジは、有料または無料のサービスの番号のいずれかを取得できます。 Get 有料電話番号とサービスのフリー ダイヤル番号に 3 つの方法があります。 
  
- **ビジネス管理センターは、Skype を使用します。** 国や地域によっては、ビジネス管理センターは、Skype を使用して、会議用ブリッジのサービス番号を取得、[取得サービスの電話番号](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。
    
- **既存のサービスの番号を移植します。** ポートまたは現在のサービス プロバイダーまたは電話のキャリアからの既存の番号を Office 365 に転送。 [Office 365 に電話番号を転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)または詳細については[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)作業を行いやすくことがわかります。  
  
- **新しい番号の要求フォームを使用します。** 場合があります (国または地域) によってことはできませんビジネス管理センターでは、Skype を使用して、新しいサービスの番号を取得するか、特定の電話番号または市外局番が必要です。 その場合は、フォームをダウンロードして記入してからマイクロソフトに返送する必要があります。 詳細については[、組織の電話番号の管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を参照してください。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>手順 4: 会議用ブリッジにサービス番号を割り当てる
<a name="__top"> </a>

会議用ブリッジは、有料または無料の電話番号を取得すると、番号を割り当てる、ミーティングの招待で使用できるようにする必要があります。  

**Office 365 管理センター**には、オーディオ会議ブリッジに新しい電話番号を割り当てるには > **管理センター** > **ビジネス用の Skype** > **音声** > **電話番号**、携帯電話を選択します。数、および**割り当て**] をクリックします。

詳細については[、オーディオ会議ブリッジに新しい電話番号を割り当てる](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」を参照してください。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>手順 5: 会議用ブリッジの第 2 言語と既定を設定します。
<a name="__top"> </a>

次に、[オーディオ会議の自動応答の言語設定](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md)にダイヤルするときの電話番号に電話会議の呼び出し元を呼びかけられるように設定するのには、会議自動アテンダントを使用します。 

**Office 365 管理センター**を参照して > **管理センター** > **ビジネス用の Skype** > **電話会議** > **ブリッジの設定をマイクロソフト**では、会議ブリッジの電話番号を選択し、**言語の設定**] をクリックします。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>ブリッジの設定、会議を設定する手順 6。
<a name="__top"> </a>
    
会議用ブリッジの設定後、開始/終了の通知、暗証番号 (pin) の長さなどの既定の設定が使用するものことを確認します正しくない場合は、変更することができます。 

**Office 365 管理センター**に移動することができます > **管理センター** > **ビジネス用の Skype** > **電話会議** > **Microsoft ブリッジの設定**です。 **Microsoft ブリッジの設定**] ページが表示されます。 詳細については[、オーディオ会議ブリッジの設定を変更](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md)」を参照してください。

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a>手順 7: オーディオ会議プロバイダーとダイヤルインの電話番号を割り当てる

マイクロソフトが、プロバイダーでは、割り当てられているし、同時に、それらの通話およびフリー ダイヤル番号を設定ことを確認する必要があります。

プロバイダーとしてマイクロソフトを潜在顧客、または**Office 365 の管理センター**に移動して、会議のスケジュールを設定する、組織内のユーザーに割り当てる > **ビジネス用の Skype** > **電話会議** > **ユーザー**、しを選択一覧からユーザー**の編集**] をクリックします。 詳細については、必要な場合は、[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。

プロバイダーを設定して、ダイヤルを設定することも会議に追加するフリー ダイヤルの番号は、そのユーザーの招待します。 ドロップ ダウン リストから電話番号を選択します。 詳細については、[携帯電話への招待に含まれている番号の設定](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)を参照してください。 


## <a name="step-8-set-up-meeting-invitations-optional"></a>手順 8: を設定するミーティングの招待状 (省略可能)
<a name="__top"> </a>
 
ユーザーに設定されているダイヤルの番号は、会議の出席者に送信される会議出席依頼に自動的に追加されます。 ただし、する場合は、独自のヘルプおよび法律上のリンク、テキスト メッセージ、および小規模な会社のグラフィックを追加できます。 [ミーティングの招待状をカスタマイズする](../set-up-skype-for-business-online/customize-meeting-invitations.md)を参照してください。
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[電話会議の電話番号](phone-numbers-for-audio-conferencing.md)
  
[オンライン会議、電話会議のオプションを設定します。](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
