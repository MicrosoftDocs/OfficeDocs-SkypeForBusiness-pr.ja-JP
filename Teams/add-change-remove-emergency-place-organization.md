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
description: Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806277"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>組織の緊急対応の場所の位置情報を追加、変更、削除する

組織の物理的な場所の数に応じて、建物、フロア、オフィスの場所を追加して、より具体的な緊急対応の場所を作成できます。 詳細 [については、「緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md) 」を参照してください。
  
通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。
  
## <a name="add-a-place-to-an-emergency-location"></a>緊急対応の場所に場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、場所を追加する場所の名前をクリックします。
3. [場所] **タブの [** 追加] を **クリックします**。
4. 場所名を入力し、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineLisLocation を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、場所を変更する場所の名前をクリックします。
3. [場所 **] タブ** で、変更する場所を選び、[編集] をクリック **します**。
4. 場所の情報を更新し、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineLisLocation」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>緊急対応の場所から場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。
2. 一覧で、場所を削除する場所の名前をクリックします。
3. [場所 **] タブ** で、削除する場所を選び、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Remove-CsOnlineLisLocation を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>関連項目

- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
