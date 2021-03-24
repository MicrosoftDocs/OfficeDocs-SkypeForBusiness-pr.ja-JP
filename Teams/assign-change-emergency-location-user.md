---
title: ユーザーの緊急対応の場所を割り当てたり変更したりする
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てる方法または変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102983"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てたり変更したりする

通話プランを設定する場合は、電話番号またはユーザーごとに緊急対応の場所を割り当てる必要があります。 ヨーロッパの国では、緊急対応の場所は、Microsoft 365 または Office 365 から電話番号を取得した場合、または電話番号を Microsoft 365 または Office 365 に転送した場合に関連付けされます。 米国では、緊急対応の場所はユーザーに割り当てられた電話番号に関連付けされます。 緊急対応の住所は、割り当てられているユーザーが新しい場所に移動した場合に変更できます。 緊急対応の住所と場所の詳細については、「緊急対応の場所、場所、通話ルーティングとは [何か」を参照してください](./what-are-emergency-locations-addresses-and-call-routing.md)。
  
通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てまたは変更できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**音声電話番号]** を  >  **クリックします**。

2. [電話番号 **] ページで** 、[番号] タブを **クリック** し、一覧からユーザー番号を選び、[編集] をクリック **します**。

3. [編集] **ウィンドウの** [緊急対応の **場所] で、** 次のいずれかの操作を行います。

   - 緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。

   - ユーザーに既に割り当てられている緊急対応の場所を変更するには **、[X]** をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。

4. 電話番号情報を含むメールをユーザーに送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、オンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineVoiceUser」を参照してください](/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする](assign-change-emergency-place-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)