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
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539514"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てまたは変更する

電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の場所が必要です。 (住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。緊急対応の場所に番号を関連付ける場合は、場所を追加して、物理的な場所に正確な位置情報を提供することもできます。 場所には、ユーザーが配置されているフロア、建物、またはオフィスの番号を指定できます。 特定の緊急対応の場所には無制限の場所を含めることができます。また、ユーザーが別の office または建物に移動すると、その場所を変更できます。 たとえば、ユーザーがフロア34から床35に移動した場合です。
  
通話プランの取得方法と料金については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。
  
Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。

2. [**電話番号**] ページで、[**数値**] タブをクリックし、一覧でユーザー番号を選択し、[**編集**] をクリックします。

3. [**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。

    - 場所を割り当てるには、場所または場所を検索して、検索結果内の場所を選びます。

    - ユーザーに既に割り当てられている場所を変更するには、[ **X** ] をクリックして、既存の場所を削除してから、割り当てる場所を検索して選択します。

4. 電話番号情報を使用してユーザーにメールを送信するかどうかに応じて、**電話番号情報を含むメールユーザー**を無効にするか、有効にします。 既定では、これはオンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。
    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所を割り当てたり変更したりする](assign-change-emergency-location-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)
