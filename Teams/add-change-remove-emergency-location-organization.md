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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 組織の緊急対応の場所を追加、変更、または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 99ab0821b8ccdb14664dc0a2aa37c959499ff8ac
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774742"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>組織の緊急対応の場所を追加、変更、削除する

[PSTN 接続オプション](pstn-connectivity.md)に関係なく、Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、またはダイレクト ルーティング&mdash;の緊急の場所を選択&mdash;すると、電話番号に関連付けることができます。

ただし、PSTN 接続オプションによっては、緊急対応の場所と場所の要件を管理する方法が異なる場合があります。 詳細については、「 [緊急通報の管理](what-are-emergency-locations-addresses-and-call-routing.md)」を参照してください。

この記事では、組織の緊急対応場所を追加、変更、または削除する方法について説明します。 

この記事は、Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、ダイレクト ルーティングに適用されます。

Microsoft Teams 管理センターまたは PowerShell を使用して、組織の緊急対応の場所を管理します。

緊急対応の場所を割り当てるには、ユーザー、電話番号、緊急対応の場所がすべて同じ国にある必要があります。 詳細については、「ユーザーの [緊急対応場所の割り当てまたは変更](assign-change-emergency-location-user.md)」を参照してください。
  
## <a name="add-an-emergency-location"></a>緊急対応の場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **場所** > **の緊急対応アドレス**] をクリックします。
2. **[追加]** をクリックします。
3. 場所の名前と説明を入力します。
4. 国または地域を選択し、住所を入力します。

   > [!NOTE]
   > ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、電話番号を取得するために使用される緊急の場所に設定された住所である Microsoft 365 で電話番号を正常にアクティブ化するには、電話番号の市域コードと一致する必要があることを理解しておくことが重要です。

5. アドレスが見つからない場合、アドレスを手動で編集する場合は、[アドレスを **手動で編集]** をオンにします。
6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[「New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)」を参照してください。
    
## <a name="change-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **場所** > **の緊急対応アドレス**] をクリックします。
2. 一覧で、変更する場所を選択し、[ **編集**] をクリックします。
3. 必要な変更を行います。
4. **[保存]** をクリックします。

> [!NOTE]
> 住所が検証されていない場合にのみ、場所の住所情報を変更できます。 アドレスが既に検証されていて、アドレスを変更する必要がある場合は、場所を削除してから、正しいアドレスを使用して新しい場所を作成します。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)」を参照してください。
    
## <a name="remove-an-emergency-location"></a>緊急対応の場所を削除する

> [!NOTE]
> 場所は、ユーザーまたは電話番号が割り当てられていない場合にのみ削除できます。 番号またはユーザーが場所に割り当てられている場合は、最初に削除する必要があります。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **場所** > **の緊急対応アドレス**] をクリックします。
2. 一覧で、削除する場所を選択し、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[「Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)」を参照してください。

## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)
