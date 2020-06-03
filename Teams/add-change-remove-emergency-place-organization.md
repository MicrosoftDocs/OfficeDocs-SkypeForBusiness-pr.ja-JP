---
title: 緊急対応の場所の場所を追加、変更、削除する
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
description: Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539434"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>組織の緊急対応の場所の位置情報を追加、変更、削除する

組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を追加して、より具体的な緊急対応の場所を作成することができます。 詳細については、「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」をご覧ください。
  
通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。
  
## <a name="add-a-place-to-an-emergency-location"></a>緊急対応の場所に場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. リストで、場所を追加する場所の名前をクリックします。
3. [**場所**] タブの [**追加**] をクリックします。
4. プレース名を入力し、[**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「[新しい-Csonlin」の場所](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)を参照してください。
    
## <a name="change-a-place-for-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. リストで、場所を変更する場所の名前をクリックします。
3. [**場所**] タブで変更する場所を選択し、[**編集**] をクリックします。
4. 場所情報を更新して、[**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。
    
## <a name="remove-a-place-from-an-emergency-location"></a>緊急対応の場所から場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。
2. リストで、場所を削除する場所の名前をクリックします。
3. [**場所**] タブで削除する場所を選択し、[**削除**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Csonlin¥ location の削除」を](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)参照してください。
    
## <a name="related-topics"></a>関連項目

- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
