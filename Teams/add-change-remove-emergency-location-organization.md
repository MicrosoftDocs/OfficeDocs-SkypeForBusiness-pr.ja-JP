---
title: 緊急対応の場所を追加、変更、削除する
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: '管理センターで組織の緊急対応の場所を追加、変更、または削除Microsoft Teamsします。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 601d8ce50d5fcf06574f08abb2c78c73a40fefda
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536538"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>組織の緊急対応の場所を追加、変更、削除する

[PSTN](pstn-connectivity.md)接続オプションに関係なく、Microsoft 通話プラン、オペレーター Connect、または直接ルーティング -緊急対応の場所を電話番号に関連付けできます。 ただし、PSTN 接続オプションによっては、場所の要件が異なる場合があります。

**通話プランの場合、** 緊急対応の場所は電話番号に関連付けられている必要がありますが、このような場合は国や地域によって異なる場合があります。 たとえば、米国では、電話番号をユーザーに割り当てるときに緊急対応の場所を関連付ける必要があります。 英国では、Microsoft 365 から電話番号を取得したり、現在のサービス プロバイダーから電話番号を転送したりするときに、緊急対応の場所を電話番号に関連付ける必要があります。

どの国や地域に関係なく、緊急対応の場所に場所や場所を追加し、緊急対応の場所を削除できます。 組織の物理的な場所の数に応じて、ビル、フロア、オフィスの場所を作成できます。 「緊急 [通話の管理」を参照してください](what-are-emergency-locations-addresses-and-call-routing.md)。

組織の緊急対応の場所は、Microsoft Teamsまたは PowerShell を使用して管理します。

緊急対応の場所を割り当てるには、ユーザー、電話番号、緊急対応の場所すべてが同じ国にある必要があります。  詳細については、「ユーザーの緊急対応 [の場所を割り当てるまたは変更する」を参照してください](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>緊急対応の場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[場所Microsoft Teams緊急対応の住所 **]**  >  **をクリックします**。
2. **[追加]** をクリックします。
3. 場所の名前と説明を入力します。
4. 国または地域を選択し、住所を入力します。

   > [!NOTE]
   > ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 で電話番号を正常にアクティブ化するには、電話番号の取得に使用される緊急対応の場所に設定された住所が電話番号の市番と一致する必要があります。

5. 住所が見つからない場合に、アドレスを手動で編集する場合は、[アドレスを手動で編集 **する] をオンにしてください**。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineLisSkyicAddress を参照してください](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[場所Microsoft Teams緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、変更する場所を選択し、[編集] をクリック **します**。
3. 必要な変更を行います。
4. **[保存]** をクリックします。

> [!NOTE]
> 住所の住所情報は、住所が検証されていない場合にのみ変更できます。 住所が既に検証済みで、住所を変更する必要がある場合は、場所を削除し、正しい住所で新しい場所を作成します。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineLisSkycAddress」を参照してください](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>緊急対応の場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[場所Microsoft Teams緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、削除する場所を選択し、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Remove-CsOnlineLisSkyicAddress に関するページを参照してください](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)