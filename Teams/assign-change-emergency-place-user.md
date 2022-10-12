---
title: ユーザーの緊急対応の場所の割り当てまたは変更
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てるか変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bd471e42eb6e8c2404eef47636da2c9894268c
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551641"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てるか変更する

[PSTN 接続オプション](pstn-connectivity.md)に関係なく、Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、またはダイレクト ルーティング&mdash;を選択&mdash;するには、緊急の場所を各電話番号またはユーザーに割り当てる必要があります。

ただし、PSTN 接続オプションによっては、ユーザーの緊急対応の場所を管理および割り当てる方法が異なる場合があります。 詳細については、「 [緊急通話の管理](what-are-emergency-locations-addresses-and-call-routing.md)」を参照してください。

この記事では、Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応場所の *場所* を割り当てるか変更する方法について説明します。

この記事は、通話プラン、オペレーター接続、Teams Phone Mobile に適用されます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **音声** > **電話番号**] をクリックします。

2. [ **電話番号** ] ページで [ **数値** ] タブをクリックし、一覧でユーザー番号を選択して、[ **編集**] をクリックします。

3. **[編集]** ウィンドウの [**緊急の場所**] で、次のいずれかの操作を行います。

    - 場所を割り当てるには、場所または場所を検索し、検索結果で場所を選択します。

    - ユーザーに既に割り当てられている場所を変更するには、[ **X** ] をクリックして既存の場所と場所を削除し、割り当てる場所を検索して選択します。

4. 電話番号情報を使用してユーザーに電子メールを送信するかどうかに応じて、電話番号情報 **を持つユーザー Email** オフまたはオンにします。 既定では、これはオンです。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

[Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation) を参照してください。
    
## <a name="related-topics"></a>関連項目

- [緊急通報を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [ユーザーの緊急対応の場所を割り当てたり変更したりする](assign-change-emergency-location-user.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)