---
title: Skype for Business Online での電話会議の PIN の長さを設定する
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
description: PIN の長さと要件のパラメーターについて説明し、「Skype for Business での会議の長さを設定する方法」を参照してください。
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164536"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Skype for Business Online での電話会議の PIN の長さを設定する


> [!NOTE]
> Microsoft Teams で PIN の長さを設定する方法については、「 [Microsoft teams で電話会議の pin の長さを設定](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)する」を参照してください。

Skype for Business の電話会議をセットアップするときには、電話会議ブリッジを取得します。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Skype for Business アプリの会議出席依頼に含まれます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで、発信者に応答し、設定に応じて、通知を再生し、発信者に名前を記録するように依頼することができます。 **Microsoft bridge の設定**を使用すると、会議の通知と会議の参加エクスペリエンスの設定を変更したり、会議の開催者によって使用される pin の長さを設定したりすることができます。 会議の開催者が Skype for Business アプリを使って会議に参加できない場合は、Pin を使って会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する
 
1. **Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [**セキュリティ** > **pin の長さ**] で、pin に必要な数字の数を選び、[**保存**] をクリックします。
    
> [!NOTE]
> PIN が会議 ID とは異なります。 会議 Id は、発信者が会議に参加するときに使用されます。 会議を識別するために使用されます。 PIN は、会議の開催者として発信者を認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN の設定について詳しく知りたいですか?

- Pin は 4 ~ 12 桁にすることができます。既定値は5です。 数値はピンの作成時にのみ使用されます。 文字と特殊文字は使用されません。
    
- PIN は、Skype for Business ユーザーが会議を開始していない場合に、会議の開催者にのみ必要です。 すべてのユーザーが会議にダイヤルインしている場合、会議の開催者が会議を開始するには、PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft bridge に関連付けられているすべての電話番号に適用されます。 これらは、特定のブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、 [-](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用します。
    
- PIN の桁の桁数を8に設定するには、次の操作を行います。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
