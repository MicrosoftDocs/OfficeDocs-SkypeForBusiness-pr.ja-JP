---
title: Skype for Business Onlineの電話会議の番号の一覧を見る
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Skype for Business Onlineでダイヤルイン会議の番号を検索する方法。 '
ms.openlocfilehash: 557aef5e85cdd176e2d95e1cd946ed23e00764a0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372889"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Skype for Business Onlineの電話会議の番号の一覧を見る

> [!NOTE]
> Microsoft Teams会議の番号については、  [「Microsoft Teams会議の番号の一覧を見る」](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) を参照してください。

When you set up Audio Conferencing for Skype for Business users, you can view the phone numbers that are available to them for audio conferencing. This list will have all of the audio conferencing phone numbers that are available to your organization.
  
 **Looking for prices?** See [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.** If you are looking to see if there are dial-in phone numbers available in your area or country/region, go to **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
If there is only one phone number available in your organization, it will be used as the default number for all of your users. When multiple phone numbers are available, you can select the default phone number for each user. This default number will be included in Skype for Business meeting invitations.
  
1 人のユーザーのダイヤルイン番号を変更するには、 [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md) を参照してください。
  
> [!NOTE]
> Domestic dial-in numbers are dedicated to your organization and are the only ones that can be set as a default phone number. However, international dial-in numbers may be shared across multiple organizations. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **マイクロソフトのブリッジ**をし。
    
   - オーディオ会議で使用可能な電話番号を表示することができます。
    
   - 場所を表示することもでき、オーディオ会議で使用されるプライマリとセカンダリの言語の自動アテンダントです。
    
> [!NOTE]
> You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number by choosing a new number from the list of available numbers in your organization. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

- 時間を短縮または、これを自動化するには、 [Get CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用することができます。
    
- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
