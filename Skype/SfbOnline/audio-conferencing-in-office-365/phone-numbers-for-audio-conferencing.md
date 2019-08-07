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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: ダイヤルイン会議番号がある国と地域、およびそれらの番号の自動割り当て方法について説明します。
ms.openlocfilehash: 1e988db094b6d49f8fb8da548f6d71b3607975e2
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "35792311"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online の電話会議の電話番号

> [!NOTE]
> Microsoft Teams の電話番号に関する詳細については、「[Microsoft Teams の電話会議の電話番号](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams)」を参照してください。

Skype for Business の電話**会議**をセットアップすると、ダイヤルイン電話番号が自動的に組織に割り当てられます。 電話会議ブリッジに割り当てられている電話番号を確認するには、「 **Skype for business 管理センター** > **電話会議** > の**Microsoft bridge**」を参照してください。 「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers.md)」を参照してください。
  
> [!NOTE]
> 電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。 地域または国/地域で利用可能なダイヤルイン電話番号があるかどうかを確認するには、 **Skype for business 管理センター** > **の音声** > **電話番号**を使用し、[**追加**]、[**新しいサービス] の順にクリックします。数値**。 [**国/地域**]、[**都道府県/地域**]、[**市区町村**] のリストを使用して、検索をフィルタします。 また、有料サービスの電話番号をお探しの場合は、「**都道府県/地域**」リストから**無料通話**を選択してください。
  
## <a name="audio-conferencing-coverage-and-pricing"></a>電話会議のサービス対象範囲と価格情報

電話会議を使用できるすべての国や地域、都市の完全なリストについては、 「[電話会議および通話プランが利用可能な国と地域](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。 価格情報については、「[電話会議の価格](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)を確認する」を参照してください。
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>会議の出席依頼に表示されるダイヤルイン電話番号

Skype for Business Online ユーザーが Outlook または Outlook Web App で会議をスケジュールすると、ユーザーに対して設定されている既定の電話会議番号が会議の出席依頼に含まれます。 1人または複数のユーザーに別の既定の番号を選択する場合は、 **Skype for business 管理センター** > の**電話会議** > **ユーザー**にアクセスして変更することができます。 「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。
  
その他のダイヤルイン番号は、会議の出席依頼の [ **電話番号の検索**] リンクをクリックして表示できます。
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>電話会議ブリッジで設定されたダイヤルイン電話番号

会議ブリッジに割り当てることができる電話会議の電話番号には、**共有**と**専用**の2種類があります。 どちらの番号も、任意の発信者が、組織内で開催されている音声会議に参加するために使うことができます。
  
 **専用電話番号** とは、組織内のユーザーだけが使用できる電話番号のことです。誰かがこれらの番号のいずれかに電話をかけるときに使用する言語を変更できます。
  
 **共有電話番号** とは、他の Office 365 組織と共有できる電話番号です。誰かがこれらの番号のいずれかに通話するときに使用する言語は変更できません。
  
開催者に割り当てられている既定の電話会議番号は、会議出席依頼にのみ含まれていますが、発信者は会議に参加するために、会議ブリッジに割り当てられている電話番号を使うことができます。 会議に参加するために使用する電話番号の一覧はそれぞれの会議の招待状に含まれる [ **電話番号の検索**] リンクを使用して利用できます。
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自動的に割り当てられた電話会議の電話番号

共有電話会議の電話番号は、電話会議が有効になっている場合、組織に自動的に割り当てられます。 電話番号が割り当てられる場合、電話番号は会議ブリッジの既定の電話番号として割り当てられます。 ブリッジの既定の番号として割り当てられた電話番号は、組織の国/地域のものです。
  
> [!NOTE]
> 組織の国または地域の場所は、Microsoft 365 管理センターにサインインし、[**組織プロファイル**] の下に表示されていることがわかります。 
  
> [!CAUTION]
> この国/地域の組織の有料電話番号の利用には制限があるため、これらの国/地域の組織では、電話会議の有料電話番号が自動的に割り当てられることはありません。 これらの場所からの無料電話番号は、利用可能なインベントリに応じて利用可能になります。 
  
専用の電話会議の電話番号は、お客様が取得して組織に割り当てることができるサービス番号です。 サービス番号は、 **Skype For business 管理センター**を使用して見つけることができます。 詳細については、「[サービスの電話番号を取得](/microsoftteams/getting-service-phone-numbers)する」を参照してください。
  
電話番号が組織に自動的に割り当てられている国や地域のリストを確認するには、「[電話会議と通話プランを使用できる国および地域](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)」を参照してください。
  
## <a name="what-else-should-you-know"></a>その他の情報

- 電話会議でサポートされる言語の一覧を表示するには、「[電話会議でサポートされる言語](/MicrosoftTeams/audio-conferencing-supported-languages)」を参照してください。
    
- [Get-set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用して、組織の電話会議の専用電話番号を表示することができます。
    
- [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) コマンドレットを使って、ダイヤルインの専用電話番号に対して設定できる言語を表示できます。
    
- 電話会議の電話番号ごとに最大4つの言語を設定できます。1つはプライマリと3つのセカンダリです。 また、専用の電話会議用の電話番号で言語を設定することもできます。
    
- ユーザー用にダイヤルイン電話番号を設定するには、「[招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites.md)する」を参照してください。
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
