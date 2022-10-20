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
ms.openlocfilehash: 5421ff4e73d93c12244b3419342110b419f1b500
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614190"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>組織の緊急対応の場所の位置情報を追加、変更、削除する

組織内の物理的な場所の数に応じて、建物、フロア、オフィスの *場所* を追加して、より具体的な緊急対応の場所を作成できます。

ただし、PSTN 接続オプションによっては、緊急対応の場所と場所の要件を管理する方法が異なる場合があります。 詳細については、「 [緊急通話の管理](what-are-emergency-locations-addresses-and-call-routing.md)」を参照してください。

この記事では、組織の緊急対応 *の場所* を追加、変更、または削除する方法について説明します。

この記事は、Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、およびダイレクト ルーティングに適用されます。

Microsoft Teams 管理センターまたは PowerShell を使用して、組織の緊急対応の場所を管理します。
  
## <a name="add-a-place-to-an-emergency-location"></a>緊急の場所に場所を追加する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. 一覧で、場所を追加する場所の名前をクリックします。
3. [場所] タブ **で** 、[ **追加**] をクリックします。
4. 場所の名前を入力し、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation) を参照してください。
    
## <a name="change-a-place-for-an-emergency-location"></a>緊急対応の場所を変更する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. 一覧で、場所を変更する場所の名前をクリックします。
3. [場所] タブ **で** 、変更する場所を選択し、[編集] をクリック **します**。
4. 場所の情報を更新し、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation) を参照してください。
    
## <a name="remove-a-place-from-an-emergency-location"></a>緊急の場所から場所を削除する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所の **緊急アドレス****]** >  をクリックします。
2. 一覧で、場所を削除する場所の名前をクリックします。
3. [場所] タブ **で** 、削除する場所を選択し、[削除] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Remove-CsOnlineLisLocation を](/powershell/module/skype/remove-csonlinelislocation)参照してください。
    
## <a name="related-topics"></a>関連項目

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)