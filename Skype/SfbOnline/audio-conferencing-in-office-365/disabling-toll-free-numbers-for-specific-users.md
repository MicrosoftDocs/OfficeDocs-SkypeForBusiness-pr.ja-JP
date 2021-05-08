---
title: 特定のオンライン ユーザーの無料電話番号Skype for Business無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が会議に無料電話番号を使用する方法を制御できます。
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238512"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>特定のオンライン ユーザーの無料電話番号Skype for Business無効にする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> ユーザーのツールフリー番号を無効にする方法についてはTeams特定のユーザーに対する無料電話番号の無効化に関する[Teams参照してください](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。

組織の Microsoft 電話会議ブリッジに無料電話番号がある場合、特定の開催者の会議でその使用を許可または禁止することができます。  

既定では、組織内のすべてのユーザーは、無料電話番号を使用することができます。つまり、それらの番号が使用可能な場合は、会議に参加するために参加者が使用できます。 この設定が組織の特定のユーザーに対しては必要ない場合、特定のユーザーが会議でそれらの番号を使用するのを無料電話番号有効化コントロールを使って制限できます。 

特定の開催者の無料電話番号が無効になっている場合: 
 - 対象の開催者が招待する会議で無料電話番号は含まれなくなります。 
 - 無料電話番号は、対象の開催者が招待する会議で参照される [電話番号の検索] ページにリストされなくなります。 
 - 参加者は、組織の無料電話番号をダイヤルしてその開催者の会議に参加できなくなります。 
 - その開催者のすべての会議は自動的に再スケジュールされ、無料電話番号が削除されます。  

    > [!IMPORTANT]
    > この場合、それらの会議の参加者すべてに開催者の電子メールの全招待状が再送信されます。 

 - 参加者は、電話番号 (有料) を使用して対象開催者の会議に引き続き参加できます。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーの無料電話番号を無効にする 

**Microsoft Teams 管理センター** から次の操作を行います。

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の横の [**編集**] をクリックします。

3. **[このユーザーからの会議出席依頼にフリー ダイヤルの番号を含める]** を **[オフ]** に設定します。 

4. **[保存]** をクリックします。 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**PowerShell を使用する場合**  

このコントロールを有効または無効にするには、Set-CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用できます。 次に例を示します。 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
