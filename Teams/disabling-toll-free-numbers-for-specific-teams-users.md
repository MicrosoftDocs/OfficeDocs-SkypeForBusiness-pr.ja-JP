---
title: チームの特定のユーザーのフリー ダイヤル番号を無効にします。
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理者は、開催者が、ミーティングのフリー ダイヤル番号を使用する方法を制御できます。
ms.openlocfilehash: 8fafe87823308035d2626d891ae12b72c2bcfeca
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23852158"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>チームの特定のユーザーのフリー ダイヤル番号を無効にします。

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

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーのフリーダイヤル番号を無効にする 

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **オーディオ会議**の横にある [**編集**] をクリックします。

4. **このユーザーからの会議出席依頼のフリー ダイヤル番号は、** オフにします。 

5. クリックして**を保存します**。 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**PowerShell を使用します。**  

詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
