---
title: "PIN を使用せずに電話で音声会議を開始する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# PIN を使用せずに電話で音声会議を開始する

会議にダイヤルインしたのに、Skype for Business または Microsoft Teams 会議の開催者が会議を開始していないために、保留音の音楽を聞きながら会議のロビーで待たされるのは、ユーザーにとって不快な場合があります。
  
会議の開催者が会議にダイヤルインする場合、既定では、会議を始めるには PIN が必要です。管理者は、どのようなユーザーが会議にダイヤルインしても会議の開始に PIN を求められることがないように、会議を設定できます。また、組織の 1 人のユーザーまたはすべてのダイヤルイン ユーザーが PIN がなくても会議を開始できるように、会議を設定できます。Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。
  
あるユーザーが Skype for Business または Microsoft Teams アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。ダイヤルイン ユーザーに **電話会議**ライセンスが割り当てられているか、ユーザーがダイヤルイン会議で有効である場合、会議の PIN はそのユーザーに送信されます。「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」および「[ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)」をご覧ください。
  
## 匿名の発信者の会議への参加を有効または無効にする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. **[Skype for Business 管理センター]**の左のナビゲーションで、[ **電話会議**]、[ **ダイヤルイン ユーザー**] の順に移動します。
    
4. 一覧でユーザーを選び、操作ウィンドウで [ **編集**] をクリックします。
    
5. ユーザーのプロパティのページの [ **会議のオプション**] で、[ **認証されていない発信者が、会議に出席する最初の人物になることを許可します。許可しない場合、認証されていない発信者は、認証されたユーザーが参加するまでロビーで待機します。**] をオンまたはオフにします。
    
6. [ **保存**] をクリックします。
    
 **Windows PowerShell を使用して、すべてのユーザーの会議に対して匿名の発信者を有効または無効にするには**
  
- 次のコマンドレットを実行します。
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## その他の情報

- PIN をリセットする必要がある場合は、「[ユーザーのダイヤルイン会議の PIN をリセットする](reset-the-audio-conferencing-pin-for-a-user.md)」をご覧ください。
    
- 匿名アクセスが有効、または会議の開始に PIN が必要でない設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者には開催者であるかどうかを確認するメッセージが表示されます。発信者が「はい」と答えると、PIN の入力を求められます。PIN を入力した後、会議が始まり、そのユーザーが会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
- 匿名アクセスが無効、または会議の開始に PIN が必要な設定になっている場合:
    
  - 会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。
    
  - 会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。
    
## Windows PowerShell で管理する方法

- 時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  

