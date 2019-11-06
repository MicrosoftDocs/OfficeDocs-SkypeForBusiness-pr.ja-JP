---
title: 特定の Teams ユーザーの無料電話番号を無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が会議に無料の電話番号を使用する方法を制御できます。
ms.openlocfilehash: e2dddd04f376de69dbbc9579525966bac6351a0a
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37572104"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>特定の Teams ユーザーの無料電話番号を無効にする

組織の Microsoft 電話会議ブリッジに無料の電話番号がある場合は、特定の開催者の会議での使用を許可または禁止することができます。  

既定では、組織内のすべてのユーザーが無料電話番号を使用できるようになっています。つまり、それらの電話番号は、参加者が会議に参加するために使用できます。 組織内の一部のユーザーに対してこの操作を行う必要がない場合は、無料番号の有効化制御を利用して、特定のユーザーの会議でそれらの電話番号を使用しないように制限することができます。 

特定の開催者に対して無料電話番号が無効になっている場合: 
 - 無料電話番号は、会議の出席依頼に含まれなくなります。 
 - 無料電話番号は、会議の招待で参照されている [市内番号の検索] ページには表示されなくなります。 
 - 組織の無料電話番号をダイヤルした場合、参加者は、指定された開催者の会議に参加することはできません。 
 - 開催者のすべての会議が自動的に再スケジュールされ、無料の電話番号が削除されます。  

    > [!IMPORTANT]
    > この操作を行うと、開催者のすべてのメールの招待が、それらの会議の参加者全員に再送信されます。 

 - 参加者は、有料番号を使って開催者の会議に参加することができます。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーの無料電話番号を無効にする 

**Microsoft Teams 管理センター**から:

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [**電話会議**] の横の [**編集**] をクリックします。

3. **[このユーザーからの会議出席依頼には無料電話番号を含める (オフ)」** に設定します。 **** 

4. [**保存] をクリックします。** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell を使用する**  

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
