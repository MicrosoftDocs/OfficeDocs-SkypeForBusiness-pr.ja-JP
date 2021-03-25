---
title: 電話会議の PIN の長さを設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: PIN の長さと要件のパラメーターと、Microsoft Teams での会議の長さを設定する方法について説明します。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117165"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

Microsoft Teams の電話会議をセットアップするときに、電話会議ブリッジを取得します。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Microsoft Teams アプリの会議出席招待に含まれます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで発信者に応答し、設定に応じて通知を再生し、発信者に名前を記録するように求める。 **Microsoft Bridge の** 設定では、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。 会議の開催者は、Microsoft Teams アプリを使用して会議に参加できない場合に PIN を使用して会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [ブリッジの **設定]** ウィンドウの [PIN の長さ] で **、PIN** に必要な数字の数を選択します。

4. **[保存]** をクリックします。

> [!NOTE]
> PIN は会議 ID とは異なります。 会議 ID は、発信者が会議に参加するときに使用します。 会議の識別に使用されます。 PIN は、会議開催者として発信者を認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN の設定について詳しくは、

- PIN には 4 ~ 12 桁の数字を指定できます。既定値は 5 です。 数値は PIN を作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- PIN は、Microsoft Teams ユーザーが会議を開始していない場合にのみ、会議開催者に必要です。 全員が会議にダイヤルインしている場合は、会議の開催者が会議を開始するために PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft Bridge に関連付けられているすべての電話番号に適用されます。 特定のブリッジに関連付けられている電話番号を使用しているすべての会議に適用されます。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[Microsoft 365 または Office 365 で電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)