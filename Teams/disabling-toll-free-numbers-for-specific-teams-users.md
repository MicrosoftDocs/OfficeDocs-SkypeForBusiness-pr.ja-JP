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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が自分たちの会議で無料電話番号を使用することができるかを制御することができます。
ms.openlocfilehash: 6fd415575110f9c6ae1dcf7b4fc006213a23cedd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232628"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>特定の Teams ユーザーの無料電話番号を無効にする

Microsoft の電話会議ブリッジでの無料電話番号を所属する組織が持っている場合、特定の開催者の会議においてそれらの無料電話番号を使用することを許可したり禁止したりすることができます。  

既定では、組織内のすべてのユーザーが無料電話番号を使用できる状態になっています。それらの番号は、利用可能な場合、出席者が会議に参加するために使用することができます。 これが組織内の一部のユーザーにとって望ましくない動作である場合は、無料電話番号を有効化する制御によって特定のユーザーのみに無料電話番号の使用を制限することができます。 

該当する開催者に対して無料電話番号が無効になっている場合: 
 - その開催者の招待状に、無料電話番号は記載されなくなります。 
 - 無料電話番号は、開催者の招待状に参照先として含まれる「電話番号の検索」ページにリストされなくなります。 
 - 出席者は、指定された開催者の会議に、組織の無料電話番号にダイヤルして参加することはできなくなります。 
 - 開催者のすべての会議は自動的に再スケジュールされ、無料電話番号はそれらの会議から削除されます。  

    > [!IMPORTANT]
    > これにより、開催者のすべてのメールの招待状が、該当する会議の出席者に再送信されます。 

 - 出席者は、有料電話番号を使用して、引き続きその開催者の会議に参加することができます。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーの無料電話番号を無効にする 

**マイクロソフトのチーム管理センター**。

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. [**電話会議**] の隣で、[**編集**] をクリックします。

3. **このユーザーからの要求を達成するためのフリー ダイヤル番号**は**無効**に設定します。 

4. [**保存**] をクリックします。 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell を使用する**  

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
