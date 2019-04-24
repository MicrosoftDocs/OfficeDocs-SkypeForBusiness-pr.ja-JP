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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: パラメーターの長さと、PIN の要件を説明し、マイクロソフトのチームでの会議の長さを設定する方法を参照してください。
ms.openlocfilehash: f18abb0601a624ca3b33304e45aaa1aacf0ee838
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204833"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

Microsoft Teams の電話会議をセットアップしている場合、電話会議ブリッジを取得します。 電話会議ブリッジには、1 つまたは複数の電話番号を含めることができます。 設定する電話番号は、Microsoft Teams アプリの会議の招待状に含まれます。
  
電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。 発信者に自動応答の音声案内で応答し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録するように求めます。 **Microsoft のブリッジの設定**により、会議の通知の設定や会議参加のエクスペリエンスを変更したり、会議の開催者によって使用される PIN の長さを設定したりすることができます。 会議の開催者は、Microsoft Teams アプリを使用して会議に参加することができない場合に、PIN を使用して会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. **ブリッジ設定**ペインで、[**暗証番号 (pin) の長さ**PIN の桁数を選択します。

4. **[保存]** をクリックします。

> [!NOTE]
> PIN とは異なる、会議の id です。 会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。 ミーティングに使用されます。 暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。 

## <a name="want-to-know-more-about-pin-settings"></a>暗証番号 (pin) の設定の詳細を知りたいとしていますか。

- ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。 番号は、ピンを作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- のみ、暗証番号 (pin) は、マイクロソフトのチームのユーザーが会議を既に開始していないときに、会議の開催者に必要な。 場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。
    
- 暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。 各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
