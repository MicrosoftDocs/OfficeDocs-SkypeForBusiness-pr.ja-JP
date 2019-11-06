---
title: Microsoft Teams で電話会議用の PIN の長さを設定する
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて説明し、「Microsoft Teams で会議の長さを設定する方法」を参照してください。
ms.openlocfilehash: 50c6ffe31e673dc7573ebb27f0eeb2ca78a30918
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571273"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

Microsoft Teams の電話会議をセットアップする場合は、電話会議ブリッジを取得します。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Microsoft Teams アプリの会議出席依頼に含まれます。
  
電話会議ブリッジは、電話を使って会議にダイヤルインしているユーザーに対して、通話に応答します。 自動応答からの音声プロンプトで、発信者に応答し、設定に応じて、通知を再生し、発信者に名前を記録するように依頼することができます。 **Microsoft bridge の設定**を使用すると、会議の通知と会議の参加エクスペリエンスの設定を変更したり、会議の開催者によって使用される pin の長さを設定したりすることができます。 会議の開催者が Microsoft Teams アプリを使って会議に参加できない場合は、Pin を使って会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ウィンドウの [ **pin の長さ**] で、pin に必要な数字の数を選びます。

4. [**保存**] をクリックします。

> [!NOTE]
> PIN が会議 ID とは異なります。 会議 Id は、発信者が会議に参加するときに使用されます。 会議を識別するために使用されます。 PIN は、会議の開催者として発信者を認証するために使用されます。 

## <a name="want-to-know-more-about-pin-settings"></a>PIN の設定について詳しく知りたいですか?

- Pin は 4 ~ 12 桁にすることができます。既定値は5です。 数値はピンの作成時にのみ使用されます。 文字と特殊文字は使用されません。
    
- PIN は、Microsoft Teams ユーザーが会議を開始していない場合に、会議の開催者にのみ必要です。 すべてのユーザーが会議にダイヤルインしている場合、会議の開催者が会議を開始するには、PIN が必要です。
    
- PIN のセキュリティ設定は、Microsoft bridge に関連付けられているすべての電話番号に適用されます。 これらは、特定のブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
