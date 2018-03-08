---
title: "会議の出席と退席のお知らせ無効を切り替える"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: "エントリを有効にして、終了する Skype for Business 管理センターの Skype を使用してビジネスのオンライン会議で発表をオンまたはオフにする方法について説明します。 "
ms.openlocfilehash: ca353400d78a37a4b7cc362df6ed44a7f25fd869
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>会議の出席と退席のお知らせ無効を切り替える

Office 365 での電話会議をセットアップするときに、電話会議ブリッジが表示されます。会議ブリッジには、Skype for Business または Microsoft チーム会議にコールインするユーザーを使用する 1 つ以上の電話番号を含めることができます。 
  
会議ブリッジが電話を使って会議にダイヤルインしたユーザーが呼び出しに応答します。会議ブリッジ、会議の自動応答からを促すボイス メッセージと発信者に応答しの設定によってできる再生、通知、発信者に相手の名前を記録し、暗証番号 (pin) のセキュリティ設定を依頼します。PIN を Skype for Business または Microsoft チーム会議の開催者、され for Business または Microsoft チーム アプリ Skype を使用して、会議を開始することができない場合は、会議を開始することができます。PIN は、会議を開始する要求されないように、それを設定ただし、できます。
  
## <a name="setting-meeting-join-options"></a>会議に参加するオプションを設定します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [**会議参加エクスペリエンス**をオンまたは**会議のエントリを有効にして終了通知をオンになって**をオフにします。これが既定で選択されます。場合は、このオプションをオフにすると、会議に参加しているユーザーはデータを入力したり、会議のままである場合に通知されません。
    
5. [**開始/終了のお知らせの種類**] で、**名前または電話番号**または**音**を選択します。
    
6. オンまたは**Ask の発信者**をオフにします。
    
7. 変更が終了したら、[**保存**] をクリックします。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。
    
-  Windows PowerShell する際に、Skype for Business Online はすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[音声会議よく寄せられる質問](audio-conferencing-common-questions.md)

