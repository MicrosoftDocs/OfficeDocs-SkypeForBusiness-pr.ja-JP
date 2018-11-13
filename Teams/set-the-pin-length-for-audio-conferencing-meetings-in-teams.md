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
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて、および Microsoft Teams の会議での長さを設定する方法について、説明します。
ms.openlocfilehash: 8e0be3a904f4172aa0f92c1632ad37992a36ab5f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296427"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

Microsoft Teams の電話会議をセットアップしている場合、電話会議ブリッジを取得します。 電話会議ブリッジには、1 つまたは複数の電話番号を含めることができます。 設定する電話番号は、Microsoft Teams アプリの会議の招待状に含まれます。
  
電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。 発信者に自動応答の音声案内で応答し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録するように求めます。 **Microsoft のブリッジの設定**により、会議の通知の設定や会議参加のエクスペリエンスを変更したり、会議の開催者によって使用される PIN の長さを設定したりすることができます。 会議の開催者は、Microsoft Teams アプリを使用して会議に参加することができない場合に、PIN を使用して会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. **ブリッジ設定**ペインで、[**暗証番号 (pin) の長さ**PIN の桁数を選択します。

4. [**保存**] をクリックします。

> [!NOTE]
> PIN とは異なる、会議の id です。 会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。 ミーティングに使用されます。 暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。 

## <a name="want-to-know-more-about-pin-settings"></a>暗証番号 (pin) の設定の詳細を知りたいとしていますか。

- ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。 番号は、ピンを作成するときにのみ使用されます。 文字と特殊文字は使用されません。
    
- のみ、暗証番号 (pin) は、マイクロソフトのチームのユーザーが会議を既に開始していないときに、会議の開催者に必要な。 場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。
    
- 暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。 各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
    
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
