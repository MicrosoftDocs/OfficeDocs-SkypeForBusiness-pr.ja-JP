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
description: 'Skype for Business 管理センター内からダイヤルイン会議が有効になっている組織内のユーザーの一覧を表示する方法について説明します。 '
ms.openlocfilehash: 2cb4481f480f5be9f45064aed1fd48f9f5c28496
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114133"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online で電話会議が有効になっているユーザーの一覧を表示する

> [!NOTE]
> Microsoft Teams で有効になっているユーザーの詳細については、「Microsoft Teams の電話会議に対して有効になっているユーザーの一覧」 [を参照してください](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)。

組織内の Skype for Business ユーザーが電話会議に対して有効にした後は、有効にされているユーザーの一覧を表示できます。 一覧を見ていると、ユーザーが使用している電話会議プロバイダーの種類、ユーザーの既定のダイヤルイン電話番号、組織で動的会議 ID が有効になっていない場合は、開催する電話会議の静的会議 ID も一覧に表示されます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>ユーザーのリストを表示する

   
- 左側のナビゲーションで、[電話会議ユーザー **] に移動**  >  **します**。

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 有効になっているユーザーの一覧を表示すると、一覧からユーザーを選択し、[操作] ウィンドウを使用して、そのユーザーの電話会議設定を編集できます。
    
- 電話会議プロバイダーとして Microsoft を使用するように構成されている 1 人のユーザーを選択すると、既定の電話番号と、組織が動的電話会議 ID に対して有効になっているかどうかを表示し、ユーザーが開催する会議の会議 ID をリセットできます。
    
- サードパーティの電話会議プロバイダーを使用するように構成されている 1 人のユーザーを選ぶと、電話会議プロバイダーの名前、有料電話番号、無料電話番号 (設定されている場合) を表示できます。
    
- フィルター オプションを使用して、次のユーザーを表示できます。
    
  - **電話会議のオン**
    
  - **電話会議をオフにする**
    
  - **会議プロバイダー - Microsoft**
    
  - **会議プロバイダー - その他**
    
- [検索] ボタンを使用して、リスト内の個々のユーザーを検索できます。
    
- 複数のユーザーを選び、次の操作を行います。
    
  - これらのユーザーに別の既定の番号を選択します。
    
  - プロバイダーを [なし] に変更して、ユーザーの電話会議をオフ **にします**。
    
  - ユーザーに電話会議ライセンスが割り当てられている場合は、電話会議プロバイダーとして Microsoft **に切り替** えます。
    
  - 匿名ユーザーが選択したユーザーの電話会議のアクティブ化を許可/禁止します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)