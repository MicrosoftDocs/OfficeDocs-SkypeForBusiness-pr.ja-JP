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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 開催者が電話会議ブリッジ会議で無料電話番号を使用する方法を制御する方法について説明します。
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096347"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>特定の Teams ユーザーの無料電話番号を無効にする

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
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell を使用する場合**  

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。