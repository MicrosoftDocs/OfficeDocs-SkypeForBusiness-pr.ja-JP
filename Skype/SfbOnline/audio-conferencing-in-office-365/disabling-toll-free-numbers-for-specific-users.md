---
title: フリー ダイヤルの番号を特定のユーザーを無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>フリー ダイヤルの番号を特定のユーザーを無効にします。

組織では、その Microsoft オーディオ会議用ブリッジにフリー ダイヤル番号が含まれる場合は、許可または特定の開催者の会議での使用を防止できます。  

既定では、組織内のすべてのユーザーはこれらの数値では、可能な場合、使えることの参加者が、会議に参加するためのフリー ダイヤル番号を使用するために有効です。 これは、組織内の一部のユーザーに目的の動作ではない場合、フリー ダイヤル番号の有効化コントロールを使用して、会議でそれらの数値を使用して特定のユーザーを制限できます。 

特定の開催者のフリー ダイヤル番号を無効にした場合。 
 - フリー ダイヤル番号は彼には含まれなく、または自分の会議への招待します。 
 - フリー ダイヤル番号は自分で参照されている"電話番号を検索] ページに表示されなくまたは自分の会議に招待します。 
 - 参加者は、組織のすべてのフリー ダイヤル番号をダイヤルする場合、特定の開催者のミーティングに参加することはできません。 
 - すべての会議の開催者は自動的に再スケジュール、およびフリー ダイヤルの番号は、それらから削除されます。  

    > [!IMPORTANT]
    > すべての開催者の電子メールの招待を再送信、その会議のすべての参加者にこれは。 

 - 参加者は、有料電話番号を使用して、開催者の会議への参加を継続できます。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>フリー ダイヤルの番号を特定のユーザーを無効にします。 

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **会議ブリッジ**の横にあるメニューをクリックし、ドロップダウン リストで [**編集**] をクリックします。

4. **会議ブリッジのプロバイダー**のウィンドウで**このユーザーのミーティングに参加するのには、組織の会議用ブリッジ内のフリー ダイヤル番号を使用して許可する**オフにします。 

5. クリックして**を適用します**。 

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**

1. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。 

2. In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user. 

3. **このユーザーのミーティングに参加するのにはフリー ダイヤルの番号を使用して許可する**をオフにします。 
 
4. [ **保存**] をクリックします。 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**PowerShell を使用します。**  

セット CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用するには有効またはこのコントロールを無効にします。 例: 

 - セット CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
