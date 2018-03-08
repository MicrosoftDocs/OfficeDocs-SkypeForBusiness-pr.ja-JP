---
title: "PIN なし、電話で音声、会議を開始します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: "有効にする、または会議に参加する Skype for Business 管理センターからまたは PowerShell スクリプトを使用してから、匿名の呼び出しを無効にする方法について説明します。 "
ms.openlocfilehash: 57e1e209180cb5811556cdd29a5d45a77302eb22
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>PIN なし、電話で音声、会議を開始します。

Skype for Business または Microsoft チーム会議の開催者が会議を開始していないために、音楽を聴く、会議のロビー内で保持する会議にダイヤルインするユーザーに不満がある場合があります。 
  
会議の開催者通話、会議に既定では、会議を開始する PIN が必要です。誰でも会議にダイヤルインできますをいない会議を開始するピンのように求められますようにをそれを設定できます。有効にするか、1 人のユーザーには、この設定を無効にするのには、Skype for Business 管理センターを使用できます。
  
PIN は、他のユーザーには、Skype for Business または Microsoft チームのアプリから、会議が開始した場合に会議の開催者の必要ありません。PIN は、会議の開催者、電話で自分の会議に参加するときに必要です。会議の PIN は、**電話会議**のライセンスが割り当てられている電話会議が有効なときに、オーディオのユーザーに送信されます。[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)し、[ユーザーの電話会議の設定を変更するときに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change.md)を参照してください。
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>有効にする、またはから会議に参加する匿名の発信者に応答を無効にします。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**。 
    
4. 一覧で、ユーザーを選択し、操作ウィンドウで [**編集**] をクリックします。 
    
5. [**会議のオプション**] で、ユーザーのプロパティ ページを選択または**許可認証されていない会議内の最初のユーザーに発信者に応答をオフにします。かどうかは、[はロビーで待機認証済みユーザーに参加するまで**します。
    
6. {[**保存**] をクリックします。} 
    
 **有効にするまたは、すべての Windows Powershell を使用して、ユーザーの会議に匿名の発信者に応答を無効にするには**
  
- 次を実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>他かする必要がありますか。

- PIN をリセットする場合は、[ユーザーの音声会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。
    
- 匿名アクセス、または会議を開始する暗証番号 (pin) を必要としない] がオンの場合
    
  - 会議を開始していない場合 (は誰で、会議にまだ): 場合は、開催者の発信者が求められるPIN は、のように求められます彼場合は、彼には、[はい] と表示されるとミーティングを開始し、ユーザーが会議に参加する、暗証番号 (pin) を入力しています。
    
  - 会議を既に開始している場合 (他のユーザーが既に、会議中): 開催者は、彼ことがないように求められます PIN の場合、発信者が求められるはありません。会議がすでに開始されたら、および発信者に参加します。
    
- 匿名アクセス、または会議を開始する暗証番号 (pin) を必要としないが無効の場合
    
  - 会議を開始していない場合 (は誰で、会議にまだ): は、開催者と彼女ことがないように求められます PIN の場合、発信者が求められるはありません。開催者の設定はオフ] に設定されているため、ミーティングを開始し、匿名の発信者が会議への参加します。
    
  - 会議を既に開始している場合 (他のユーザーが既に、会議中): は、開催者と彼女ことがないように求められます、PIN の場合、発信者が求められるはありません。 会議がすでに開始されたら、および発信者に参加します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、1 つ以上のユーザーの自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。
    
-  Windows PowerShell する際に、Skype for Business Online はすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
