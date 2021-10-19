---
title: ユーザーの緊急対応の場所を割り当て、変更する
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
description: この記事では、組織内のユーザーに緊急対応の場所を割り当てる方法または場所を変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1edc7bd6f5a1ea1b7a09f6747c1ee61f7dd74758
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465977"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>ユーザーの緊急対応の場所を割り当てる、または変更する

ユーザーに電話番号を割り当てると、アクティブな各電話番号に緊急対応の場所が関連付けられている必要があります。 **Microsoft 365 で電話番号を取得した場合、Microsoft 365 に電話番号を転送する場合、またはプロバイダーから電話番号を取得するときに、住所を関連付ける。**

緊急対応の場所に番号を関連付ける場合は、物理的な場所内のより正確な場所を提供する場所を追加できます。 場所には、ユーザーが配置されているフロア、ビルの主な場所、またはオフィス番号を指定できます。 特定の緊急対応の場所の場所の数に制限はありません。また、ユーザーが別のオフィスやビルに移動した場合に場所を変更できます。 たとえば、ユーザーがフロア 34 からフロア 35 に移動する場合です。
  
管理者センターまたは PowerShell を使用して、ユーザーの緊急対応の場所Microsoft Teamsを割り当てまたは変更できます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションで、[音声Microsoft Teams **番号]**  >  **を電話します**。

2. [番号 **電話ページで**、[数値] タブをクリックし、一覧からユーザー番号を選択し、[編集] を **クリックします**。

3. [編集] **ウィンドウの** [緊急対応の **場所] で**、次のいずれかの操作を行います。

    - 場所を割り当てるには、場所または場所を検索し、検索結果内の場所を選択します。

    - ユーザーに既に割り当てられている場所を変更するには **、[X]** をクリックして既存の場所と場所を削除し、割り当てる場所を検索して選択します。

4. ユーザーに電話番号情報を含むメールを送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。 既定では、この設定はオンになっています。

5. [**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell の使用

[「Set-CsOnlineLisLocation」を参照してください](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="related-topics"></a>関連項目

- [緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md)
- [組織の緊急対応の場所を追加、変更、削除する](add-change-remove-emergency-location-organization.md)
- [組織の緊急対応の場所の位置情報を追加、変更、削除する](add-change-remove-emergency-place-organization.md)
- [ユーザーの緊急対応の場所を割り当てたり変更したりする](assign-change-emergency-location-user.md)
- [組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)