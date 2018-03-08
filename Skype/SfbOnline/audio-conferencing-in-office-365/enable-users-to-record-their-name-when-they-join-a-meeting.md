---
title: "会議に参加するときに、相手の名前を記録するようにユーザーを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: "有効にする、またはユーザーが会議に参加するときの名前を記録できるかどうかを無効にする方法をについてください。 "
ms.openlocfilehash: 6fa5fe6968976bfc25b2ff8e1a2115ca2619f10a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>会議に参加するときに、相手の名前を記録するようにユーザーを有効にします。

Office 365 での電話会議をセットアップすると電話番号と、電話会議ブリッジと呼ばれるものが提供されます。会議ブリッジには、専用または共有の電話番号をことができる 1 つ以上の電話番号を含めることができます。
  
会議ブリッジが電話を使って会議にダイヤルインしたユーザーが呼び出しに応答します。会議ブリッジ、自動応答からを促すボイス メッセージと発信者に応答し、その設定に応じて再生できる、通知質問する相手の名前を記録し、会議の開催者 PIN のセキュリティ設定の発信者に応答します。Pin は、会議を開始するようにするため、会議の開催者に与えられます。ただし、することができます設定 PIN は、会議を開始する要求されないようにします。
  
## <a name="set-whether-callers-should-record-their-name"></a>発信者の名前を記録すべきかどうかを設定します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [**会議参加エクスペリエンス**を**会議のエントリを有効にして終了通知を有効にする**] チェック ボックスを参照してください。
    
  - **選択されています。**発信者は、会議に参加する前に、相手の名前を記録するように求められます。これが既定で選択されます。
    
  - **オフになっています。**発信者は、会議に参加する前に、相手の名前を記録するように依頼されません。
    
5. 変更が終了したら、[**保存**] をクリックします。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
-  Windows PowerShell がユーザーとは、ユーザーの許可を管理できます。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

