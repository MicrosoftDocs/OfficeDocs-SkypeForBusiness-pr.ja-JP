---
title: ユーザー用の緊急対応の場所の場所を割り当てる、変更する
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てる、または変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232468"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てまたは変更する

電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の場所が必要です。 (住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。緊急対応の場所に番号を関連付ける場合は、場所を追加して、物理的な場所に正確な位置情報を提供することもできます。 場所には、ユーザーが配置されているフロア、建物、またはオフィスの番号を指定できます。 特定の緊急対応の場所には無制限の場所を含めることができます。また、ユーザーが別の office または建物に移動すると、その場所を変更できます。 たとえば、ユーザーがフロア34から床35に移動した場合です。
  
通話プランの取得方法と料金については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
  
Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。

2. [**電話番号**] ページで、一覧からユーザー番号を選び、[**編集**] をクリックします。

3. [**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。

    - 場所を割り当てるには、場所または場所を検索して、検索結果内の場所を選びます。

    - ユーザーに既に割り当てられている場所を変更するには、[ **X** ] をクリックして、既存の場所を削除してから、割り当てる場所を検索して選択します。

4. **[保存]** をクリックします。

## <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。
    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所を割り当てたり変更したりする](assign-change-emergency-location-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
