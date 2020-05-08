---
title: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: f2137d05ebe588a316704fabf4c8878910a40bc0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163904"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Skype for Business Online の電話会議情報を使って、ユーザーにメールを送信する

> [!Note]
> Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。

Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。 これを行うには、 **Skype For business 管理センター**を使用し、ユーザーのプロパティの下にある [**会議情報をメールで送信**] をクリックします。 このメールを送信すると、次のようなすべての電話会議情報が含まれます。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
   
送信されるメールの例を次に示します。
  
![ダイヤルイン会議のメール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が含まれるメールをユーザーに送信する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [**編集**] をクリックします。

3. [**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。

1. 職場または学校のアカウントを使用してサインインします。
    
2. **Skype For business**> 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. [**ユーザー**] をクリックし、ユーザーを選びます。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> 電話会議の設定を使用してユーザーにメールを送信することもできます。そのためには、ユーザーのプロパティを編集してから、[**電話****会議** > ] をクリックします。 

## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- 電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議** のライセンスがユーザーから削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
- 既定では、メールの送信者は、Microsoft 365 または Office 365 から送信されますが、Windows PowerShell と[-](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用して、メールアドレスと表示名を変更することができます。 ユーザーにメールを送信するメールアドレスを変更するには、次のことを行う必要があります。
    
  - SendEmailFromAddress パラメーターにメールアドレスを入力します。
    
  - メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。
    
  - SendEmailFromDisplayName パラメーターにメールの表示名を入力します。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
    電話会議の情報を使用してユーザーにメールを送信するには、次の操作を実行します。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
