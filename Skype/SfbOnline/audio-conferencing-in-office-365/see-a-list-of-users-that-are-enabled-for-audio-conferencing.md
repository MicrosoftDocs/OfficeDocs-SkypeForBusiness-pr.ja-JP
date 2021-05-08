---
title: Skype for Business Online で電話会議が有効になっているユーザーの一覧を表示する
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
description: '管理者センター内からダイヤルイン会議が有効になっている組織内のユーザーの一覧Skype for Business説明します。 '
ms.openlocfilehash: 070b11c047ec90413128995196b99872a0884663
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237003"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議が有効になっているユーザーの一覧を表示する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Microsoft Teams で有効になっているユーザーの詳細については、「Microsoft Teams で電話会議が有効になっているユーザーの一覧を表示する[」を参照Microsoft Teams。](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

組織内のユーザー Skype for Business電話会議を有効にした後は、有効にしたユーザーの一覧を表示できます。 一覧を見ていると、ユーザーが使用している電話会議プロバイダーの種類、ユーザーの既定のダイヤルイン電話番号も一覧に表示され、組織で動的会議 ID が有効になっていない場合は、開催する電話会議の静的電話会議 ID が表示されます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>ユーザーの一覧を表示する

   
- 左側のナビゲーションで、[電話会議ユーザー **] に移動**  >  **します**。

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 有効になっているユーザーの一覧を表示する場合は、一覧からユーザーを選択し、[操作] ウィンドウを使用して、そのユーザーの電話会議設定を編集できます。
    
- 電話会議プロバイダーとして Microsoft を使用するように構成されている 1 人のユーザーを選択すると、既定の電話番号と、組織が動的会議 ID に対して有効になっているかどうかを確認できます。また、ユーザーが開催する会議の会議 ID をリセットできます。
    
- サードパーティの電話会議プロバイダーを使用するように構成されている 1 人のユーザーを選択すると、電話会議プロバイダーの名前、有料電話番号、無料電話番号 (設定されている場合) を表示できます。
    
- フィルター オプションを使用して、次の機能を持つユーザーを表示できます。
    
  - **電話会議**
    
  - **電話会議をオフにする**
    
  - **会議プロバイダー - Microsoft**
    
  - **会議プロバイダー - その他**
    
- 検索ボタンを使用して、リスト内の個々のユーザーを検索できます。
    
- 複数のユーザーを選択し、次の操作を行います。
    
  - これらのユーザーに対して別の既定の番号を選択します。
    
  - プロバイダーを [なし] に変更して、ユーザーの電話会議を **オフにします**。
    
  - ユーザーに電話会議ライセンスが割り当てられている場合は、電話会議プロバイダーとして **Microsoft に切り替** えます。
    
  - 選択したユーザーの電話会議のアクティブ化を匿名ユーザーに許可/禁止します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 Windows PowerShellでは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する場合は、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
