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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 組織の緊急対応の場所を追加、変更、または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c0a195a221bff5b008f5754592450f4f2b1e42e6
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606636"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>組織の緊急対応の場所を追加、変更、削除する

[PSTN 接続オプション](pstn-connectivity.md)&mdash;に関係なく、Microsoft 通話プラン、オペレーター接続、オペレーター コネクト モバイル (パブリック プレビュー リリース)、またはダイレクト ルーティング&mdash;の緊急対応の場所を電話番号に関連付けることができます。

ただし、PSTN 接続オプションによっては、緊急対応の場所と場所の要件を管理する方法が異なる場合があります。 詳細については、「 [緊急通話の管理](what-are-emergency-locations-addresses-and-call-routing.md)」を参照してください。

この記事では、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。 

この記事は、Microsoft 通話プラン、オペレーター接続、オペレーター コネクト モバイル (パブリック プレビュー リリース)、およびダイレクト ルーティングに適用されます。

Microsoft Teams 管理センターまたは PowerShell を使用して、組織の緊急対応の場所を管理します。

緊急対応の場所を割り当てるには、ユーザー、電話番号、および緊急の場所がすべて同じ国にある必要があります。 詳細については、「ユーザーの [緊急対応の場所の割り当てまたは変更」を参照してください](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>緊急対応の場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. **[追加]** をクリックします。
3. 場所の名前と説明を入力します。
4. 国または地域を選択し、住所を入力します。

   > [!NOTE]
   > ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 で電話番号を正常にアクティブ化するには、電話番号の取得に使用される緊急対応の場所に設定された住所が電話番号の市外局番と一致する必要があることを理解することが重要です。

5. アドレスが見つからない場合に、アドレスを手動で編集する場合は、[アドレス **を手動で編集] を** オンにします。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress) を参照してください。
    
## <a name="change-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. 一覧で、変更する場所を選択し、[編集] をクリック **します**。
3. 必要な変更を加えます。
4. **[保存]** をクリックします。

> [!NOTE]
> 場所の住所情報は、住所が検証されていない場合にのみ変更できます。 アドレスが既に検証されており、住所を変更し、場所を削除してから、正しい住所で新しい場所を作成する必要がある場合。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress) を参照してください。
    
## <a name="remove-an-emergency-location"></a>緊急の場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. 一覧で、削除する場所を選択し、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress) を参照してください。

## <a name="related-topics"></a>関連項目

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)