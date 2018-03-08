---
title: "電話会議の会議の PIN の長さを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business の会議の長さを設定する方法を参照してくださいし、長さと PIN の要件のパラメーターを学習します。"
ms.openlocfilehash: 308bce9196f085c1f9473e74746bccd2f0ca96c5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>電話会議の会議の PIN の長さを設定します。

セットアップしているで電話会議の Skype for Business または Microsoft チーム、ときに、電話会議ブリッジが表示されます。会議ブリッジには、1 つ以上の電話番号を含めることができます。設定した電話番号は、その skype for Business とチームの Microsoft アプリ会議の出席依頼に含まれます。
  
電話会議ブリッジ電話を使って会議にダイヤルインしているユーザーの通話に応答します。自動応答し、設定によってを促すボイス メッセージと発信者に応答、通知の再生および発信者が名前を記録するように依頼することができます。**Microsoft ブリッジの設定**を使用すると、会議の通知の設定を変更し、会議参加エクスペリエンス] と、会議の開催者によって使用される Pin の長さを設定します。会議の開催者は、会議を開始する場合は、Skype を for Business または Microsoft チームのアプリを使って会議に参加できないことの Pin を使用します。
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [**セキュリティ** > **PIN の長さ**、暗証番号 (pin)] の桁の番号を選択し、し、[**保存**] をクリックします。
    
> [!NOTE]
> PIN は、会議 ID の相違点します。会議 Id は、会議に参加するときに、発信者で使用されます。会議の確認に使用されます。PIN を使用して、会議の開催者の発信者番号を認証します。 
  
## <a name="want-to-know-more-about-pin-settings"></a>PIN の設定について詳しく知りたいとしていますか。

- Pin は 4 ~ 12 桁; に必要既定では 5 です。数値は、Pin を作成するときにのみ使用されます。文字と特殊文字は使用されません。
    
- PIN がのみが必要なときに Skype for Business または Microsoft チームのユーザー、会議の開催者が会議を既に開始していません。会議にダイヤルインすべてのユーザーがいる場合は、PIN 会議の開催者、会議を開始するために必要なです。
    
- PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられている電話番号のすべてに適用されます。指定されたブリッジに関連付けられている電話番号を使用するすべての会議が適用されます。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
- 8 暗証番号 (pin) では、以下の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="see-also"></a>関連項目

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

