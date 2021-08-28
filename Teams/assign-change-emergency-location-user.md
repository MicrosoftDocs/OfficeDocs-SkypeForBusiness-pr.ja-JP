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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: この記事では、組織内のユーザーに緊急対応の場所を割り当てる方法または変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36be65ef14cfe0fc97ce49dfa9227fe50daa18f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588379"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てたり変更したりする

通話プランを設定する場合は、各電話番号またはユーザーに緊急対応の場所を割り当てる必要があります。 ヨーロッパの国では、緊急対応の場所は、Microsoft 365 または Office 365 から電話番号を取得した場合、または電話番号を Microsoft 365 または Office 365 に転送するときに関連付けされます。 米国では、緊急対応の場所は、ユーザーに割り当てられた電話番号に関連付けされます。 緊急対応の住所は、割り当てられているユーザーが新しい場所に移動した場合に変更できます。 緊急対応の住所と場所の詳細については、「緊急対応の場所、場所、通話ルーティングとは」 [を参照してください](./what-are-emergency-locations-addresses-and-call-routing.md)。
  
通話プランを取得する方法と料金については、アドオン ライセンスのTeams[を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
管理者センターまたは PowerShell を使用して、ユーザーの緊急対応Microsoft Teamsを割り当てまたは変更できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[音声Microsoft Teams **番号]**  >  **を電話します**。

2. [数値 **電話ページで**、[数値] タブをクリックし、一覧からユーザー番号を選択し、[編集] をクリック **します**。

3. [編集] **ウィンドウの** [緊急対応の **場所] で**、次のいずれかの操作を行います。

   - 緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。

   - ユーザーに既に割り当てられている緊急対応の場所を変更するには **、[X]** をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。

4. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineVoiceUser」を参照してください](/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>関連トピック

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする](assign-change-emergency-place-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)