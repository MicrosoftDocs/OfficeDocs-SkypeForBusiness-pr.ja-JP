---
title: "ユーザーの音声会議の PIN をリセットします。"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: "ピンに関する重要事項とユーザー向けにリセットする方法を確認します。 "
ms.openlocfilehash: 1deacb0a00ccef585e220752ea94c678d1d5a4d3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>ユーザーの音声会議の PIN をリセットします。

PIN は、各 Skype は電話会議用に有効なビジネスや Microsoft チームのユーザー用に作成される数値のコードです。電話会議の Pin が使用会議の開催者を特定してれており、会議の開催者は、電話で会議を開始することを許可します。会議を開始する Skype for Business または Microsoft チームのアプリを使用する場合、暗証番号 (pin) は必要ありません。ユーザーが自分の PIN を忘れた、電話会議が有効なときに送信されたメールで見つからない場合は、管理者が自分の PIN をリセットする必要があります。ユーザーが自分の PIN を再設定できません。
  
認証されたユーザーに Business または Microsoft チームのアプリや、開催者が自分の PIN と、電話で参加するときに、Skype を使用して参加するときは、会議を開始することができます。会議に必要と PIN を開始する、電話で参加はロビーとは、ユーザー、会議まで保留中の音楽を聴くを開始します。会議の開催者が、電話で会議を開始する暗証番号 (pin) を必要としない場合は、会議に参加するとき、暗証番号 (pin) を発信者を求められるされません。
  
## <a name="reset-a-conference-organizers-pin"></a>会議の開催者の PIN をリセットします。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。
    
3. [**ユーザー**] をクリックしての PIN をリセットするユーザーを選択します。
    
4. 操作ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。
    
## <a name="what-else-should-you-know-about-pins"></a>ピンについて他を把握してする必要がありますか。

- セキュリティのために、PIN にのみ表示管理者 PIN をリセットすると、1 つの時間にします。管理者による PIN をリセットすると、として、暗証番号 (pin) が表示されます。 **Skype for Business 管理センター**で、Windows PowerShell で取得 CsCsOnlineDialInConfencingUser を使用する場合の結果にします。
    
- 既定では、有効になっているユーザーにメールを自動的に送信して、電話会議の PIN をリセットするときの有効なしているとき、ユーザーは自分の PIN を含む電子メールに届きます。自動的に無効にした場合、メールを送信する PIN リセットのメールをユーザーに送られませんし、手動で PIN 情報をユーザーに送信する必要があります。
    
- 会議を起動すると、すべてのユーザーがロビー内で自動的に参加します。たとえば場合は、次の 2 つの参加者が開始する前に、会議に参加しようとするがロビー内で配置されます保留中の音楽を聴くし、会議の開催者は、電話で自分の PIN を使用して参加する場合、会議が開始されますロビー内で参加者に参加 会議します。
    
- 匿名の呼び出しが開始されるように会議に参加を許可する既定の設定。
    
- 電話会議のユーザーを有効にしたときに既定で、送信された会議の情報と自分の PIN を含むメールします。ユーザーは、PIN をリセットすると、新しい PIN がユーザーのプライマリ SMTP アドレス (alias) ユーザー用に設定されているへのメールに送られますので、Office 365 メールボックスが必要です。
    
- 電話会議を設定する際に、組織内のピンのために必要な数字を設定します。Pin は 4 ~ 12 桁に必要]: 既定値は 5 します。PIN の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、電話会議を有効になっている既存のユーザーに対して PIN の設定に適用されないです。[電話会議の会議の PIN の長さを設定する](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)を参照してください。
    
- 既定のメール ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。Hotmail などの Office 365 以外のアドレスまたは MSN メール アドレスにメールを送信できます。Windows PowerShell を使用して既定のメール アドレスを上書きできます。これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。
    
- 電子メールを送信する先の既定のユーザーのアドレスを上書きするには、テナント管理者が、次のコマンドレットを使用できます。 セット CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN-SendEmail SendEmailToAddress"u@hotmail.com"します。ユーザーのメール アドレスを上書きするため、SendEmail パラメーターが必要です。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。
    
- 実行して Amos 大理石の PIN を設定できます。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットします。](reset-a-conference-id-for-a-user.md)
