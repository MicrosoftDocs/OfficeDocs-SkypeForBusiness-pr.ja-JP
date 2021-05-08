---
title: Skype for Business Online で電話会議会議の PIN の長さを設定する
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
description: PIN の長さと要件のパラメーターについて説明し、会議の長さを設定する方法Skype for Business。
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238602"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Skype for Business Online で電話会議会議の PIN の長さを設定する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> PIN の長さを設定する方法については、「Microsoft Teams で電話会議の PIN の長さを設定する[」をMicrosoft Teams。](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)

会議用に電話会議を設定Skype for Business、電話会議ブリッジが表示されます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、新しいアプリの会議出席Skype for Businessされます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで呼び出し元に応答し、設定に応じて通知を再生し、発信者に自分の名前を記録するよう要求できます。 **Microsoft Bridge の設定** を使用すると、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。 会議の開催者は、新しいアプリを使用して会議に参加できない場合、PIN を使用してSkype for Businessします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さの設定
 
1. **Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [**セキュリティ**  >  **PIN の長さ**] で、PIN に使用する桁数を選択し、[保存] を **クリックします**。
    
> [!NOTE]
> PIN は会議 ID とは異なります。 会議 ID は、発信者が会議に参加するときに使用されます。 会議を識別するために使用されます。 PIN は、発信者を会議開催者として認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 設定の詳細については、次のページを参照してください。

- PIN は 4 ~ 12 桁です。既定値は 5 です。 数値は、PIN を作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- PIN は、ユーザーが会議を開始していないSkype for Business開催者にのみ必要です。 全員が会議にダイヤルインしている場合、会議の開催者が会議を開始するには PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。 特定のブリッジに関連付けられている電話番号を使用する会議に適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには [、Set-CsOnlineDialInConferencingTenantSettings コマンドレットを使用](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) できます。
    
- PIN の桁数を 8 に設定するには:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="see-also"></a>関連項目

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
