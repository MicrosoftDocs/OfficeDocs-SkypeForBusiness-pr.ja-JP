---
title: "フリー ダイヤルの番号を特定のユーザーを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。"
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
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

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a>ビジネス管理センターは、Skype を使用して特定のユーザー用のフリー ダイヤルの番号を無効にします。 
 1. Go to the **Office 365 admin center** > **Skype for Business**. 
 2. ビジネス管理センターでは、左側のナビゲーションでは、Skype で**電話会議**に移動する > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。 
 3. In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user. 
 4. 確認するか、**このユーザーのミーティングに参加するのにはフリー ダイヤルの番号を使用して許可する**をオフにします。 
 5. [ **保存**] をクリックします。 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a>PowerShell を使用して特定のユーザー用のフリー ダイヤルの番号を無効にします。  

セット CsOnlineDialInConferencingUser コマンドレットの AllowTollFreeDialIn パラメーターを使用するには有効またはこのコントロールを無効にします。 例: 

 - セット CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
