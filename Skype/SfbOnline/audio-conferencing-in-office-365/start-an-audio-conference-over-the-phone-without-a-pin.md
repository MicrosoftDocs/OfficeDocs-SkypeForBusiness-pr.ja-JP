---
title: "電話 PIN なしで、オーディオ会議の開始します。"
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 57e1e209180cb5811556cdd29a5d45a77302eb22
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>電話 PIN なしで、オーディオ会議の開始します。

[] 会議にダイヤルインしたのに、Skype for Business または Microsoft Teams 会議の開催者が会議を開始していないために、保留音の音楽を聞きながら会議のロビーで待たされるのは、ユーザーにとって不快な場合があります。 
  
会議の開催者を呼び出す場合、会議出席依頼には、既定では、会議を開始するのには、暗証番号 (pin) が必要です。 できますを設定することをだれでも会議にダイヤルイン会議を開始するのには暗証番号 (pin) には求められません。 Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
あるユーザーが Skype for Business または Microsoft Teams アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。 PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。 会議の暗証番号 (pin) は、**オーディオ会議**のライセンスが割り当てられている音声会議が有効になっていると、オーディオのユーザーに送信されます。 [オーディオ会議の情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)し、[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change.md)を参照してください。
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>匿名の発信者の会議への参加を有効または無効にする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**です。 
    
4. の一覧でユーザーを選択し、[操作] ウィンドウの [**編集**] をクリックします。 
    
5. ユーザーのプロパティ] ページで [**ミーティングのオプション**] でオンまたはオフ**許可が認証されていない呼び出し元は、会議の最初の人に。かどうか、ロビーで待機、認証されたユーザーが参加するまで**。
    
6. [ **保存**] をクリックします。 
    
 **Windows PowerShell を使用して、すべてのユーザーの会議に対して匿名の発信者を有効または無効にするには**
  
- 次のコマンドレットを実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>その他の情報

- PIN をリセットする必要がある場合は、「[ユーザーのダイヤルイン会議の PIN をリセットする](reset-the-audio-conferencing-pin-for-a-user.md)」をご覧ください。
    
- 匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としない] がオンの場合
    
  - 会議が開始されていない場合 (は誰もまだ会議で): 彼は、開催者の場合、呼び出し元が求められます、PIN のよう求められますその場合、[はい] と PIN を入力した後、ミーティングを開始し、ユーザーがミーティングに参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議): 開催者は、彼とはしないよう求められます暗証番号 (pin) の場合、呼び出し元は要求されません。会議は既に開始されていると、呼び出し元に参加します。
    
- 匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としないが無効の場合
    
  - 会議が開始されていない場合 (は誰もまだ会議で): 開催者は、彼女と彼女がするメッセージは表示されません、暗証番号 (pin) の場合、呼び出し元は要求されません。 開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始されている場合 (他のユーザーが既に会議): 場合は、開催者は、彼女と暗証番号 (pin) の彼女を求められますことはありませんが、呼び出し元は要求されません; 会議は既に開始されていると、呼び出し元に参加します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 
    
  - Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
