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
description: PIN の長さと要件のパラメーターについて説明し、会議の期間を設定する方法Microsoft Teams。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117165"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

会議用に電話会議を設定Microsoft Teams、電話会議ブリッジが表示されます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、新しいアプリの会議出席Microsoft Teamsされます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで呼び出し元に応答し、設定に応じて通知を再生し、発信者に自分の名前を記録するよう要求できます。 **Microsoft Bridge の設定** を使用すると、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。 会議の開催者は、新しいアプリを使用して会議に参加できない場合、PIN を使用してMicrosoft Teamsします。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さの設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [ブリッジ **設定] ウィンドウ** の [PIN の長さ] **で、PIN** に使用する桁数を選択します。

4. **[保存]** をクリックします。

> [!NOTE]
> PIN は会議 ID とは異なります。 会議 ID は、発信者が会議に参加するときに使用されます。 会議を識別するために使用されます。 PIN は、発信者を会議開催者として認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 設定の詳細については、次のページを参照してください。

- PIN は 4 ~ 12 桁です。既定値は 5 です。 数値は、PIN を作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- PIN は、ユーザーが会議を開始していないMicrosoft Teams開催者にのみ必要です。 全員が会議にダイヤルインしている場合、会議の開催者が会議を開始するには PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。 特定のブリッジに関連付けられている電話番号を使用する会議に適用されます。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)