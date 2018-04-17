---
title: Phone numbers for Audio Conferencing
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned.
ms.openlocfilehash: 9b1fca6a576a9de77e74bcab8df740b5106cf5bc
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="phone-numbers-for-audio-conferencing"></a>Phone numbers for Audio Conferencing

When you are setting up **Audio Conferencing** for Skype for Business and Microsoft Teams, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。 If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. [**国/地域**]、[**都道府県/地域**]、[**市区町村**] のリストを使用して、検索をフィルタします。 Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Audio Conferencing coverage and pricing

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). For pricing information, see 
  
[電話会議の料金](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>会議の出席依頼に表示されるダイヤルイン電話番号

When a Skype for Business Online or Microsoft Teams user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. 「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。
  
その他のダイヤルイン番号は、会議の出席依頼の [ **電話番号の検索**] リンクをクリックして表示できます。
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Dial-in phone numbers set on an audio conferencing bridge

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。
  
 **共有電話番号** とは、他の Office 365 組織と共有できる電話番号です。誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. 会議に参加するために使用する電話番号の一覧はそれぞれの会議の招待状に含まれる [ **電話番号の検索**] リンクを使用して利用できます。
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Automatically assigned audio conferencing phone numbers

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. 電話番号が割り当てられる場合、電話番号は会議ブリッジの既定の電話番号として割り当てられます。 ブリッジの既定の番号として割り当てられた電話番号は、組織の国/地域のものです。
  
> [!NOTE]
> The country or region location of your organization can be found by signing in to the **Office 365 admin center** and looking under **Organization Profile**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. これらの場所からの無料電話番号は、利用可能なインベントリに応じて利用可能になります。 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
  
To see a list of those countries/regions that have phone numbers automatically assigned to organizations, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## <a name="what-else-should-you-know"></a>その他の情報

- To see the list of supported languages for audio conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- You can use the [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet to see the dedicated phone numbers for audio conferencing for you organization.
    
- [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使って、ダイヤルインの専用電話番号に対して設定できる言語を表示できます。
    
- You can set up to 4 languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- To set the dial-in phone number for a user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
