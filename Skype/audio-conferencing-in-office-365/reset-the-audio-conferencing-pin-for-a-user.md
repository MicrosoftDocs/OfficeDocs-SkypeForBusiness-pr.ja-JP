---
title: "ユーザーのダイヤルイン会議の PIN をリセットする"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# ユーザーのダイヤルイン会議の PIN をリセットする

PIN は、数値から構成されるコードで、ダイヤルイン会議の有効な各ユーザーに対して作成されます。 ダイヤルイン会議の PIN は、会議の開催者により使用されます。その目的は、自分が会議の開催者であることを識別し、電話で会議を開始できるようにすることです。 Skype for Business クライアントを使用して会議を開始する場合、PIN は必要ありません。 ユーザーが自分の PIN を忘れて、ダイヤルイン会議で有効になった時点で送信されたメールで PIN を確認できない場合は、管理者がそのユーザーの PIN をリセットする必要があります。 ユーザーが自分の PIN をリセットすることはできません。
  
会議を開始できるのは、認証済みユーザーが Skype for Business クライアントを使用して参加する場合か、開催者が自分の PIN を使用して電話で参加する場合です。会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。
  
## 

### 会議開催者の PIN をリセットする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **ダイヤルイン会議**] をクリックします。
    
3. [ **ダイヤルイン ユーザー**] をクリックし、PIN をリセットするユーザーを選びます。
    
4. 操作ウィンドウで [ **PIN のリセット**] をクリックします。
    
## PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 管理者により PIN がリセットされた後、Skype for Business 管理センターと、管理者が Windows PowerShell で **Get-CsCsOnlineDialInConfencingUser** を使用した場合の結果で、PIN は " ***********" と表示されます。
    
- ユーザーへのメールの自動送信は既定で有効です。ユーザーがダイヤルイン会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。 ただし、管理者がメールの自動送信を無効にしても、ユーザーには PIN リセットのメールは送信されません。管理者は、ユーザーに PIN 情報を手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者が会議を開始することはできません。
    
- ダイヤルイン会議でユーザーを有効にする場合、 既定では、ユーザーには会議の情報と自分の PIN が含まれるメールが送信されます。 ユーザーには Office 365 メールボックスが必要です。これは、PIN がリセットされると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) へのメールで、新しい PIN がユーザーに送信されるためです。
    
- ダイヤルイン会議を設定するときには、組織の PIN に必要な桁数を設定します。 PIN は 4 ～ 12 桁にすることができます。既定値は 5 桁です。 PIN の長さの設定を変更した場合、その設定は新しく生成された PIN に対してのみ適用され、ダイヤルイン会議で有効である既存のユーザーの PIN の設定には適用されません。 「[ダイヤルイン会議の PIN の長さを設定する](set-the-length-of-the-pin-for-audio-conferencing-meetings.md)」を参照してください。
    
- 既定では、ユーザーの Office 365 プライマリ SMTP アドレスにメールが送信されますが、Hotmail や MSN のメール アドレスなど、Office 365 以外のアドレスにメールを送信することもできます。 Windows PowerShell を使用すると、既定のメール アドレスを上書きできます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。
    
- メールの送信先である既定のユーザー アドレスを上書きするには、テナント管理者は次のコマンドレットを使用できます。 `Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"` ユーザーのメール アドレスを上書きするために、 _SendEmail_ パラメーターが必要です。
    
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
- 次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理する 6 つの理由](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](http://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Lync Online の管理](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](http://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  

