---
title: Skype for Business Online の電話会議の電話番号
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: ダイヤルイン会議番号がある国と地域、およびそれらの番号の自動割り当て方法について説明します。
ms.openlocfilehash: 4ba3cea0b009ae91c2df1954cdee283397bf2037
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229149"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online の電話会議の電話番号

> [!NOTE]
> Microsoft Teams の電話番号に関する詳細については、「[Microsoft Teams の電話会議の電話番号](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams)」を参照してください。

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>電話会議のサービス対象範囲と価格情報

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>会議の出席依頼に表示されるダイヤルイン電話番号

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
その他のダイヤルイン番号は、会議の出席依頼の [ **電話番号の検索**] リンクをクリックして表示できます。
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>ダイヤルインの電話番号、電話会議ブリッジの設定

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。
  
 **共有電話番号** とは、他の Office 365 組織と共有できる電話番号です。誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>電話会議の電話番号を自動的に割り当てられます

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> **組織プロファイル**の下にある**Office 365 管理センター**にサインインし、組織の国または地域の場所をご覧ください。 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Toll-free numbers from these locations are available depending on available inventory. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).
  
電話番号が組織に自動的に割り当てられている国や地域のリストを確認するには、「[電話会議と通話プランを使用できる国および地域](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。
  
## <a name="what-else-should-you-know"></a>その他の情報

- オーディオ会議のサポートされている言語の一覧を表示するには、[サポートされている言語の音声会議](/MicrosoftTeams/audio-conferencing-supported-languages)を参照してください。
    
- [Get CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用すると、専用の電話番号は、組織の音声会議を参照してください。
    
- [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使って、ダイヤルインの専用電話番号に対して設定できる言語を表示できます。
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- ユーザーのダイヤルインの電話番号を設定するには、[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
