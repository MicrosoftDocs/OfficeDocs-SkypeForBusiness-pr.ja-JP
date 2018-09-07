---
title: Skype for Business Online で PIN を使用せずに電話で電話会議を開始する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '匿名の発信者による Skype for Business 管理センターからの会議への参加や PowerShell スクリプトの使用を有効または無効にする方法を説明します。 '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858707"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Skype for Business Online で PIN を使用せずに電話で電話会議を開始する

> [!Note]
> Microsoft Teams で PIN を使用せずに電話会議を開始する場合の詳細については、「[Microsoft Teams で PIN を使用せずに 電話で電話会議を開始する](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)」をご覧ください。

会議にダイヤルインしたのに、Skype for Business 会議の開催者が会議を開始していないために、保留音の音楽を聞きながら会議のロビーで待たされるのは、ユーザーにとって不快な場合があります。 
  
会議の開催者が会議にダイヤルインする場合、既定では、会議を始めるには PIN が必要です。 管理者は、どのようなユーザーが会議にダイヤルインしても会議の開始に PIN を求められることがないように、会議を設定できます。 Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
あるユーザーが Skype for Business アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。音声ユーザーに **電話会議**ライセンスが割り当てられているか、ユーザーがダイヤルイン会議で有効である場合、会議の PIN はそのユーザーに送信されます。「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」および「[電話会議の設定が変更されたユーザーにメールを自動的に送信する](emails-sent-to-users-when-their-settings-change.md)」をご覧ください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする
    
1. **[Skype for Business 管理センター]** の左側のナビゲーションで **[電話会議]** > **[ダイヤルイン ユーザー]** と選択します。 
    
2. 一覧でユーザーを選び、操作ウィンドウで [ **編集**] をクリックします。 
    
3. ユーザーのプロパティのページの [ **会議のオプション**] で、[ **認証されていない発信者が、会議に出席する最初の人物になることを許可します。許可しない場合、認証されていない発信者は、認証されたユーザーが参加するまでロビーで待機します。**] をオンまたはオフにします。
    
4. [**保存**] をクリックします。 


    
 **Windows Powershell を使用する**
  
- 次のコマンドレットを実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする必要がある場合は、「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」をご覧ください。
    
- 匿名アクセスが有効、または会議の開始に PIN が必要でない設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者には開催者であるかどうかを確認するメッセージが表示されます。発信者が「はい」と答えると、PIN の入力を求められます。PIN を入力した後、会議が始まり、そのユーザーが会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
- 匿名アクセスが無効、または会議の開始に PIN が必要な設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell のご使用をお勧めする理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 
    
  - [Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
