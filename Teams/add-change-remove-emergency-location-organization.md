---
title: 緊急対応の場所を追加、変更、削除する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 'Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bed76fdfff2a6af2dabb3eef5c01dcfb39f422a
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539464"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>組織の緊急対応の場所を追加、変更、削除する

緊急対応の場所は電話番号と関連付けられている必要がありますが、このような状況は国と地域によって異なる場合があります。 たとえば、米国では、電話番号をユーザーに割り当てるときに緊急対応の場所を関連付ける必要があります。 英国では、Office 365 から電話番号を取得する場合や、現在のサービスプロバイダーから電話番号を移行する場合に、緊急対応の場所を電話番号に関連付ける必要があります。

お住まいの国または地域にかかわらず、緊急対応の場所を追加して、緊急対応の場所を削除することができます。 組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を作成することができます。 「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」をご覧ください。
  
通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。
  
## <a name="add-an-emergency-location"></a>緊急対応の場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. **[追加]** をクリックします。
3. 場所の名前と説明を入力します。
4. 国または地域を選択して、住所を入力します。

   > [!NOTE]
   > ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインの場合、Office 365 で電話番号を正しく有効にするには、番号の取得に使用する緊急対応の場所で設定された住所が電話番号の市外局番と一致する必要があることを理解しておくことが重要です。
5. 住所が見つからず、アドレスを手動で編集する場合は、[**アドレスを手動で編集**する] をオンにします。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「[新規-CsOnlineLisCivicAddress」を](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)参照してください。
    
## <a name="change-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. 一覧で、変更する場所を選択し、[**編集**] をクリックします。
3. 必要な変更を加えます。
4. **[保存]** をクリックします。

> [!NOTE]
> 住所が検証されていない場合にのみ、場所の住所情報を変更できます。 住所が既に検証されていて、住所を変更する必要がある場合は、場所を削除して、正しい住所を含む新しい場所を作成します。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)」を参照してください。
    
## <a name="remove-an-emergency-location"></a>緊急対応の場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. 一覧で、削除する場所を選択し、[**削除**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)」を参照してください。

## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
