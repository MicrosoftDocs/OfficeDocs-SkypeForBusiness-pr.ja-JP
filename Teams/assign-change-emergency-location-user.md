---
title: ユーザーの緊急対応の場所を割り当てたり変更したりする
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
description: この記事では、組織内のユーザーに緊急対応の場所を割り当てる方法または変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efe6b81961a4f7ca4eeb39e3f10b0c117cba7d6e
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634906"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てたり変更したりする

[PSTN](pstn-connectivity.md)接続オプションに関係なく、Microsoft 通話プラン、オペレーター Connect、または直接ルーティングを選択する場合、緊急対応の場所を各電話番号またはユーザーに割り当てる &mdash; &mdash; 必要があります。

ただし、PSTN 接続オプションによっては、ユーザーの緊急対応の場所を管理および割り当てる方法が異なる場合があります。 詳細については、「緊急通話の [管理」を参照してください](what-are-emergency-locations-addresses-and-call-routing.md)。

この記事では、ユーザーの緊急対応の場所を割り当てる方法または変更する方法について説明します。 

この記事は、通話プランとオペレーター サービスにConnect。
  
管理者センターまたは PowerShell を使用して、ユーザーの緊急対応Microsoft Teamsを割り当てまたは変更できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[音声Microsoft Teams **番号]**  >  **電話クリックします**。

2. [番号 **電話] ページで**、[数値]タブをクリックし、一覧からユーザー番号を選び、[編集] を **クリックします**。

3. [編集] **ウィンドウの** [緊急対応の **場所] で**、次のいずれかの操作を行います。

   - 緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。

   - ユーザーに既に割り当てられている緊急対応の場所を変更するには **、[X]** をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。

4. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineVoiceUser」を参照してください](/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする](assign-change-emergency-place-user.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)
