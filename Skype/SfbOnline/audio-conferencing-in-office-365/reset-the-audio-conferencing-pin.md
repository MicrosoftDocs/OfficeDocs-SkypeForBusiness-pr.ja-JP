---
title: Skype for Business Online で電話会議 PIN をリセットする
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'PIN について知っている必要がある情報と、PIN をリセットする方法については、Skype for Businessしてください。 '
ms.openlocfilehash: 95c2d19a7d867d97ab977b722648de1373a4739b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237753"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Skype for Business Online で電話会議 PIN をリセットする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 電話会議 PIN をリセットする方法については、「Microsoft Teams で電話会議 PIN をリセットする[」を](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)Microsoft Teams。

PIN は、電話会議を有効にしているユーザーごとにSkype for Business番号で構成されるコードです。 電話会議 PIN は、会議の開催者が会議の開催者を識別し、電話で会議を開始するために使用されます。 ユーザーが会議を開始Skype for Businessアプリを使用する場合、PIN は必要ありません。 ユーザーが自分の PIN を忘れて、電話会議を有効にした場合に送信されたメールで PIN が見つからなかった場合、管理者は PIN をリセットするか、自分の PIN をリセットできます。
  
認証されたユーザーが Skype for Business アプリを使用して参加した場合、または開催者が電話で PIN を使用して参加するときに、会議を開始できます。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。
  
## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

1. 仕事用または学校用のアカウントでサインインします。
    
2. 管理センターに移動> Skype for Business **し、** 左側のナビゲーションで [電話会議]**をクリックします**。
    
3. [ユーザー **] を** クリックし、PIN をリセットするユーザーを選択します。
    
4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーに自分の PIN をリセットする

ユーザーは、[ダイヤルイン会議] ページの **[PIN** のリセット] オプションを使用して PIN **をリセット** できます。 このページには、次の 3 つの方法のいずれかを使用してアクセスできます。

* ブラウザーで に移動します [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) 。
* [Skype for Business オプション] の横にある [メニューの表示] 矢印をクリックし、[ツール] の [ダイヤルイン会議] を  >  **設定。**
* [Skype for Business オプション] を **クリック** し、左側のメニューで [通話の転送] をクリックし、[その他の通話] セクションで設定設定をオンラインで編集]**を** クリック **します**。 

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 管理者が PIN をリセットすると **、Skype for Business** 管理センターで PIN が *********** と表示され、Windows PowerShell で Get-CsCsOnlineDialInConfencingUser を使用すると結果に表示されます。
    
- ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議を有効にした場合、または PIN がリセットされた場合、ユーザーは PIN を含むメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報をユーザーに手動で送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者による会議の開始を許可しません。
    
- ユーザーが電話会議を有効にした場合、既定では、会議情報と PIN を含むメールが送信されます。 PIN をリセットすると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN が電子メールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。
    
- 電話会議を設定するときに、組織内の PIN に必要な数字を設定します。 PIN は 4 桁から 12 桁まで指定できます。既定値は 5 です。 PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議が有効になっている既存のユーザーの PIN 設定には適用されません。 「 [電話会議会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 既定では、メールはユーザーのプライマリ SMTP Microsoft 365またはOffice 365に設定されます。 メールアドレスは、Microsoft 365または MSN メール Office 365アドレスなど、Hotmailアドレスに送信できます。 既定のメール アドレスは、既定のメール アドレスを無効にWindows PowerShell。 これは、ユーザーがメールボックス内にメールボックスを持Exchange持Microsoft 365場合Office 365。
    
- メールが送信される既定のユーザー アドレスをオーバーライドするには、テナント管理者は、Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com" コマンドレットを使用できます。 ユーザーのメール アドレスをオーバーライドするには、SendEmail パラメーターが必要です。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。
    
- 次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)
