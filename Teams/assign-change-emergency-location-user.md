---
title: ユーザーの緊急対応の場所を割り当てたり変更したりする
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てまたは変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f11bfd9762667823b4ec6b2883c9661f9f5754d0
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539504"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てたり変更したりする

通話プランを設定するときは、各電話番号またはユーザーに緊急対応の場所を割り当てる必要があります。 ヨーロッパの国では、Office 365 から、または電話番号を Office 365 に移行したときに、緊急対応の場所が電話番号と関連付けられます。 米国では、ユーザーに割り当てられた緊急対応の場所が電話番号と関連付けられています。 割り当てられたユーザーが新しい場所に移動した場合は、緊急対応の住所を変更することができます。 緊急対応の住所と場所の詳細については、「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」を参照してください。
  
通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。

2. [**電話番号**] ページで、[**数値**] タブをクリックし、一覧でユーザー番号を選択し、[**編集**] をクリックします。

3. [**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。

   - 緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。

   - 既にユーザーに割り当てられている緊急対応の場所を変更するには、[ **X** ] をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。

4. 電話番号情報を使用してユーザーにメールを送信するかどうかに応じて、**電話番号情報を含むメールユーザー**を無効にするか、有効にします。 既定では、これはオンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)」を参照してください。 

    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする](assign-change-emergency-place-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
