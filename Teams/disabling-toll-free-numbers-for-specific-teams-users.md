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
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が自分たちの会議で無料電話番号を使用することができるかを制御することができます。
ms.openlocfilehash: 158a4b31b0aaf65414af0d2119b3b6931a1f74ac
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014694"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>特定の Teams ユーザーの無料電話番号を無効にする

Microsoft の電話会議ブリッジでの無料電話番号を所属する組織が持っている場合、特定の開催者の会議においてそれらの無料電話番号を使用することを許可したり禁止したりすることができます。  

既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。 これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。 

該当する開催者に対して無料電話番号が無効になっている場合: 
 - その開催者の招待状に、無料電話番号は記載されなくなります。 
 - 無料電話番号は、開催者の招待状に参照先として含まれる「電話番号の検索」ページにリストされなくなります。 
 - 出席者は、指定された開催者の会議に、組織の無料電話番号にダイヤルして参加することはできなくなります。 
 - 開催者のすべての会議は自動的に再スケジュールされ、無料電話番号はそれらの会議から削除されます。  

    > [!IMPORTANT]
    > これにより、開催者のすべてのメールの招待状が、該当する会議の出席者に再送信されます。 

 - 出席者は、有料電話番号を使用して、引き続きその開催者の会議に参加することができます。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーの無料電話番号を無効にする 

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の隣で、[**編集**] をクリックします。

4. [**Include toll-free numbers in meeting requests from this user (このユーザーからの会議依頼に無料電話番号を含める)**] をオフにします。 

5. [**保存**] をクリックします。 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell を使用する**  

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。
