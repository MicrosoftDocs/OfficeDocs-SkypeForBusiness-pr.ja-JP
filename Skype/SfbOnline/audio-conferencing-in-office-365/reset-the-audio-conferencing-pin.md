---
title: Skype for Business Online で電話会議の PIN をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin について知っておくべきことと、Skype for Business Online で Pin をリセットする方法について説明します。 '
ms.openlocfilehash: 11fafd6d79236fdddf3f73f384e9c339a5a775fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299088"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Skype for Business Online で電話会議の PIN をリセットする

> [!Note]
> Microsoft Teams で電話会議の pin をリセットする方法については、「 [Microsoft teams で電話会議の pin をリセットする](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)」を参照してください。

PIN は、電話会議用に有効になっている各 Skype for Business ユーザー用に作成された番号で構成されるコードです。 電話会議の Pin は、会議の開催者が会議の開催者であり、電話で会議を開始できることを示すために使用されます。 Skype for Business アプリを使用して会議を開始する場合、PIN は必要ありません。 ユーザーが PIN を忘れた場合、電話会議用に有効にしたときに送信されたメールでその PIN が見つからない場合は、管理者が自分の pin をリセットするか、自分の pin をリセットすることができます。
  
認証されたユーザーが Skype for Business アプリを使用して参加している場合、または開催者が電話を介して自分の PIN を使って参加している場合、会議を開始できます。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。
  
## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター** > **Skype for business**に移動し、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. [**ユーザー**] をクリックし、PIN をリセットするユーザーを選びます。
    
4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。********
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーが自分の PIN をリセットする

ユーザーは、**ダイヤルイン会議**ページの [ **pin のリセット**] オプションを使用して pin をリセットできます。 このページにアクセスするには、次の3つの方法があります。

* ブラウザーで、に[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)アクセスします。
* Skype for business で、[**オプション**] の横にある [**メニューを表示する]** 矢印をクリックし、[**ツール** > ] の [**ダイヤルイン会議の設定**] をクリックします。
* Skype for Business で、[**オプション**] をクリックし、左側のメニューの [**着信の転送**] をクリックします。次に、[**通話の詳細設定**] セクションで、[**オンラインで設定を編集**する] をクリックします。 

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 PIN が管理者によってリセットされた後は、Windows PowerShell で CsCsOnlineDialInConfencingUser を使用すると、 **Skype For business 管理センター**と結果に pin が * * * * * * * * * * * * * と表示されます。
    
- ユーザーにメールを自動的に送信する機能は既定で有効になっています。電話会議が有効になっているか、PIN がリセットされると、ユーザーは PIN を含むメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN のリセットメールはユーザーに送信されず、ユーザーに PIN 情報を手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者が会議を開始することは許可されていません。
    
- 電話会議のユーザーを有効にすると、既定では、会議の情報とその PIN を含むメールが送信されます。 PIN がリセットされると、ユーザーに対して設定されているプライマリ SMTP アドレス (エイリアス) 宛てに、ユーザーに Office 365 メールボックスがある必要があります。
    
- 電話会議をセットアップするときには、組織内の Pin に必要な数字を設定します。 Pin は 4 ~ 12 桁にすることができます。既定値は5です。 PIN の長さの設定を変更した場合、設定は新しく生成された Pin にのみ適用され、電話会議用に有効になっている既存のユーザーの PIN の設定には適用されません。 「[電話会議の PIN の長さを設定](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)する」を参照してください。
    
- 既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに設定されます。 Hotmail または MSN のメールアドレスなど、Office 以外の365のアドレスにメールを送信することができます。 Windows PowerShell を使用して、既定のメールアドレスを上書きできます。 これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。
    
- メールを送信する既定のユーザーアドレスを上書きするには、テナント管理者が次のコマンドレットを使用できます: Get-csonlinedialinconferencinguser-amos-SendEmail-SendEmailToAddress "u@hotmail.com" ユーザーのメールアドレスを上書きするには、SendEmail パラメーターが必要です。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
- 次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)
