---
title: Skype for Business Online で電話会議の PIN の長さを設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: PIN の長さと要件のパラメーターと、Skype for Business の会議の長さを設定する方法について説明します。
ms.openlocfilehash: a2acaad15712621c33b275e914263f6781178d9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100793"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Skype for Business Online で電話会議の PIN の長さを設定する


> [!NOTE]
> Microsoft Teams で PIN の長さを設定する方法については、「Microsoft Teams で電話会議の PIN の長さを設定する」 [を参照してください](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。

Skype for Business の電話会議をセットアップするときに、電話会議ブリッジが表示されます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Skype for Business アプリの会議出席招待に含まれます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで発信者に応答し、設定に応じて通知を再生し、発信者に名前を記録するように求める。 **Microsoft Bridge の設定** では、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。 会議の開催者は、SKYPE for Business アプリを使用して会議に参加できない場合に PIN を使用して会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する
 
1. **Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [**セキュリティ**  >  **PIN の長さ**] で、PIN に使用する桁数を選び、[保存] をクリック **します**。
    
> [!NOTE]
> PIN は会議 ID とは異なります。 会議 ID は、発信者が会議に参加するときに使用します。 会議の識別に使用されます。 PIN は、会議開催者として発信者を認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN の設定について詳しくは、

- PIN は 4 ~ 12 桁です。既定値は 5 です。 数値は PIN を作成するときにのみ使用されます。 文字や特殊文字は使用されません。
    
- 会議の開催者に PIN が必要になるのは、Skype for Business ユーザーが会議を開始していない場合のみです。 全員が会議にダイヤルインしている場合は、会議の開催者が会議を開始するために PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft Bridge に関連付けられているすべての電話番号に適用されます。 特定のブリッジに関連付けられている電話番号を使用しているすべての会議に適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするために [、Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) コマンドレットを使用できます。
    
- PIN の桁数を 8 に設定するには:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)