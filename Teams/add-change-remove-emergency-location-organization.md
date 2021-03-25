---
title: 緊急対応の場所を追加、変更、削除する
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: b918cbcbebf8edb2cd54d08e0e4a3177867fa623
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121525"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>組織の緊急対応の場所を追加、変更、削除する

緊急対応の場所は電話番号に関連付けられている必要がありますが、この場合、国や地域によって異なる場合があります。 たとえば、米国では、電話番号をユーザーに割り当てるときに緊急対応の場所を関連付ける必要があります。 英国では、Microsoft 365 または Office 365 から電話番号を取得したり、現在のサービス プロバイダーから電話番号を転送したりするときに、緊急対応の場所を電話番号に関連付ける必要があります。

どの国や地域にいても、緊急対応の場所に場所や場所を追加して、緊急対応の場所を削除できます。 組織の物理的な場所の数に応じて、ビル、フロア、オフィスの場所を作成できます。 「緊急 [通話を管理する」を参照してください](what-are-emergency-locations-addresses-and-call-routing.md)。
  
通話プランを取得する方法と料金については、「Teams のアドオン ライセンス [」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。
  
## <a name="add-an-emergency-location"></a>緊急対応の場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. **[追加]** をクリックします。
3. 場所の名前と説明を入力します。
4. 国または地域を選択し、住所を入力します。

   > [!NOTE]
   > ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 または Office 365 で電話番号を正常にアクティブ化するには、緊急対応の場所に設定された住所 (番号の取得に使用される) が電話番号の市局番と一致している必要があります。

5. 住所が見つからない場合に、手動で住所を編集する場合は、[アドレスを手動で編集する] **をオンにしてください**。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineLisSkyicAddress を参照してください](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、変更する場所を選び、[編集] をクリック **します**。
3. 必要な変更を行います。
4. **[保存]** をクリックします。

> [!NOTE]
> 住所が検証されていない場合にのみ、場所の住所情報を変更できます。 住所が既に検証済みで、住所を変更する必要がある場合は、場所を削除し、正しい住所で新しい場所を作成します。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineLisSkyicAddress」を参照してください](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>緊急対応の場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、削除する場所を選び、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Remove-CsOnlineLisSkyicAddress を参照してください](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)