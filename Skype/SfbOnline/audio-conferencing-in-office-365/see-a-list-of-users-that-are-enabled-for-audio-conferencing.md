---
title: Skype for Business Online で電話会議用に有効になっているユーザーのリストを表示する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
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
description: 'Skype for Business 管理センターから、ダイヤルイン会議が有効になっている組織内のユーザーのリストを表示する方法について説明します。 '
ms.openlocfilehash: ffc5649a4dc37428fb64915ce6a8b38d0869f388
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680424"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議用に有効になっているユーザーのリストを表示する

> [!NOTE]
> Microsoft Teams で有効になっているユーザーについては、「 [Microsoft teams で電話会議用に有効になっているユーザーのリストを表示](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)する」を参照してください。

電話会議用に組織の Skype for Business ユーザーを有効にした後は、有効になっているユーザーの一覧を表示できます。 リストを見ると、使用している電話会議プロバイダーの種類、ユーザーの既定のダイヤルイン電話番号、組織で動的会議 id が有効になっていない場合は、リストの各ユーザーにも表示されます。開催した電話会議の場合。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>ユーザーのリストを表示する

   
- 左側のナビゲーションで、[**電話会議** > **ユーザー**] に移動します。

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 有効になっているユーザーのリストを表示すると、一覧からユーザーを選んで、操作ウィンドウを使ってそのユーザーの電話会議の設定を編集できます。
    
- 電話会議プロバイダーとして Microsoft を使用するように構成されている1人のユーザーを選ぶと、既定の電話番号と、組織で動的会議 Id が有効になっているかどうかが表示され、会議 ID をリセットすることができます。ユーザーが整理します。
    
- サードパーティの電話会議プロバイダーを使用するように構成されている1人のユーザーを選ぶと、電話会議プロバイダーの名前、有料電話番号、フリーダイヤル電話番号 (設定されている場合) を表示できます。
    
- フィルターオプションを使って、次のユーザーを表示できます。
    
  - **電話会議のオン**
    
  - **電話会議のオフ**
    
  - **会議プロバイダー-Microsoft**
    
  - **会議プロバイダー-その他**
    
- [検索] ボタンを使用して、リスト内の個々のユーザーを検索することができます。
    
- 複数のユーザーを選択して、次の操作を行うことができます。
    
  - これらのユーザーに別の既定の番号を選択します。
    
  - プロバイダーを **[なし**] に変更して、ユーザーの電話会議をオフにします。
    
  - ユーザーに**電話会議**ライセンスが割り当てられている場合は、電話会議プロバイダーとして Microsoft に切り替える。
    
  - 選択したユーザーの電話会議を匿名ユーザーが有効にすることを許可または禁止する。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。 次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
