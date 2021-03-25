---
title: Skype for Business Online の電話会議 PIN をリセットする
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
description: 'PIN について知るべきことを確認し、Skype for Business Online で PIN をリセットする方法について確認します。 '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114203"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Skype for Business Online の電話会議 PIN をリセットする

> [!Note]
> Microsoft Teams で電話会議 PIN をリセットする方法については、「Microsoft Teams で電話会議 PIN をリセットする」 [を参照してください](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。

PIN は、電話会議が有効になっている各 Skype for Business ユーザーに対して作成される番号で構成されるコードです。 電話会議 PIN は、会議の開催者が自分が会議の開催者であり、電話で会議を開始するために使用されます。 Skype for Business アプリを使用して会議を開始する場合、PIN は必要ありません。 ユーザーが自分の PIN を忘れて、電話会議で有効になっていたときに送信されたメールで PIN を見つからなかった場合、管理者は自分の PIN をリセットするか、自分の PIN をリセットできます。
  
認証されたユーザーが Skype for Business アプリを使用して参加する場合、または開催者が自分の PIN で電話で参加すると、会議を開始できます。 会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。 会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。
  
## <a name="reset-a-users-pin"></a>ユーザーの PIN をリセットする

1. 仕事用または学校用のアカウントでサインインします。
    
2. **Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。
    
3. [ユーザー **] を** クリックし、PIN をリセットするユーザーを選択します。
    
4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>ユーザーに自分の PIN をリセットする

ユーザーは、[ダイヤルイン会議] ページの **[PIN** のリセット] オプションを使用して PIN **をリセット** できます。 このページには、次の 3 つの方法のいずれかを使用してアクセスできます。

* ブラウザーで、 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)
* Skype for Business で、[オプション] の横にある [メニューの表示] 矢印をクリックし、[ツール] の [ダイヤルイン会議の設定]  >  **をクリックします**。
* Skype for Businessで、[オプション] をクリックし、左側のメニューで[通話の転送] をクリックし、[その他の通話設定] セクションで [オンラインで設定の編集] をクリック **します**。  

## <a name="what-else-should-you-know-about-pins"></a>PIN について知っておくべきその他のこと

- セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。 管理者によって PIN がリセットされた後 **、SKYPE for Business** 管理センターと、管理者が Windows PowerShell で Get-CsCsOnlineDialInConfencingUser を使用すると、PIN が *********** として表示されます。
    
- ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議で有効になっている場合、または PIN がリセットされた場合、ユーザーは自分の PIN が記載されたメールを受信します。 ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報を手動でユーザーに送信する必要があります。
    
- 会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。
    
- 既定の設定では、匿名の発信者による会議の開始を許可しません。
    
- ユーザーを電話会議用に有効にした場合、既定では、ユーザーは会議情報と PIN を含むメールを送信します。 PIN がリセットされた場合、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN がメールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。
    
- 電話会議をセットアップするときに、組織内の PIN に必要な数字を設定します。 PIN は 4 ~ 12 桁で指定できます。既定値は 5 です。 PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議で有効になっている既存のユーザーの PIN 設定には適用されません。 「 [電話会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 既定では、メールはユーザーの Microsoft 365 Office 365 プライマリ SMTP アドレスに設定されます。 Microsoft 365 以外のアドレスまたは Office 365 以外のアドレス (Hotmail や MSN のメール アドレスなど) にメールを送信できます。 既定のメール アドレスを上書きするには、既定のメール Windows PowerShell。 これは、ユーザーが Microsoft 365 または 365 に Exchange メールボックスを持Office便利です。
    
- メールが送信される既定のユーザー アドレスを上書きするには、テナント管理者は次のコマンドレットを使用できます: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com。 ユーザーのメール アドレスを上書きするには、SendEmail パラメーターが必要です。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。
    
- 次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)