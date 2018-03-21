---
title: "ユーザーのダイヤルイン会議の PIN をリセットする"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: 2244e23c1eed616ba5bf4832e634e7a796dfd8b7
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>ユーザーのダイヤルイン会議の PIN をリセットする

PIN は、電話会議が有効になっているビジネスおよびマイクロソフトのチームのユーザーの各 Skype 用に作成される番号のコードです。 オーディオ会議のピンは、会議の開催者は、電話会議を開始することを許可することを識別するミーティングの開催者によって使用されます。 会議を開始するビジネスまたはマイクロソフトのチームのアプリに Skype を使用する場合、暗証番号 (pin) は必要ありません。 ユーザーが PIN を忘れたり、電話会議を有効になっていなかったときに送信された電子メールで見つけられないという場合は、管理者が PIN をリセットする必要があります。 ユーザーは、自分の PIN をリセットできません。
  
ビジネスまたはマイクロソフトのチームのアプリケーションまたは開催者が自分の PIN と電話で参加するときに、Skype を使用して認証されたユーザーが参加するとき、会議を開始できます。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。
  
## <a name="reset-a-conference-organizers-pin"></a>会議開催者の PIN をリセットする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. [**ユーザー**] をクリックして、ユーザーの PIN をリセットするを選択します。
    
4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。
    
## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 暗証番号 (pin) は、管理者がリセットされますが後の暗証番号 (pin) が表示されます。**ビジネス管理センターの Skype**では Windows PowerShell で Get CsCsOnlineDialInConfencingUser を使用する場合の結果にします。
    
- デフォルトで有効化は自動的にユーザーに電子メールを送信して、ユーザー音声会議や、PIN をリセットする場合は有効にしている場合、PIN の電子メールが送信されます。 自動的に無効にした場合電子メールを送信するユーザーに PIN リセットの電子メールを送信しないユーザーに暗証番号 (pin) の情報を手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 匿名の呼び出しを開始するための会議を許可する既定の設定をします。
    
- オーディオ会議のユーザーを有効にすると、既定で送信される会議の情報と PIN を含む電子メール。 ユーザーは PIN をリセットすると、新しい暗証番号 (pin) はでは、プライマリ SMTP アドレス (エイリアス)、ユーザーに設定されている電子メールのユーザーに送信されますので、Office 365 のメールボックスに必要です。
    
- オーディオ会議を設定するときは、組織内のピンに必要な数字を設定します。 ピンは 12 桁、4 - デフォルトは 5 です。 暗証番号 (pin) の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、オーディオ会議を有効になっている既存のユーザーの暗証番号 (pin) の設定に適用されていません。 [オーディオ会議の会議の暗証番号 (pin) の長さの設定](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)を参照してください。
    
- 既定で電子メールは、ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。 Office 365 以外のアドレス、Hotmail または MSN の電子メール アドレスに電子メールを送信できます。 デフォルトの電子メール アドレスは、Windows PowerShell を使用してオーバーライドできます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。
    
- テナント管理者に電子メールを送信する場合、既定のユーザー アドレスをオーバーライドするには、次のコマンドレットを使用できます: セット-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN-SendEmail-SendEmailToAddress"u@hotmail.com"です。 ユーザーの電子メール アドレスを上書きするには、SendEmail パラメーターが必要です。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
- 次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。
    
  - Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)
