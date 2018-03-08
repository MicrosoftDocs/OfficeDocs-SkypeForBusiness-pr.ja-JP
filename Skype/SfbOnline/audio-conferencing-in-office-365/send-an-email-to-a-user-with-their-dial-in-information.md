---
title: "ダイヤルイン情報を持つユーザーにメールを送信します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: "ユーザーを電話会議の情報を含む電子メールを送信します。"
ms.openlocfilehash: 7ca0a4f00f3a81cd865d65336a8be5702e620639
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>この情報は、電話会議情報を持つユーザーにメールを送信します。

あります Skype for Business または Microsoft チームのユーザーに、電話会議の情報を送信する必要があります。**Skype for Business 管理センター**を使用して、特定のユーザーのプロパティの下の [**会議情報を電子メールで送信する**] をクリックして、これを行うことができます。電子メールを送信する際にそれが含まれて、電話会議の情報がすべてなど。
  
- ユーザーの会議電話またはダイヤルイン電話番号です。
    
- ユーザーの会議 ID
    
    > [!NOTE]
    > 静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。 
  
送信されたメールの例を示します。
  
![ダイヤルイン会議メール](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>ユーザーに電話会議の情報を含む電子メールを送信します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、[ユーザーを選択します。
    
4. 操作ウィンドウで、**会議情報を電子メールで送信する**] をクリックします。
    
> [!TIP]
> メールを送信できるユーザーに電話会議の設定を含む、ユーザーのプロパティを編集して、**電話会議**をクリックして、 > **会議情報を電子メールで送信します**。 
  
## <a name="what-else-should-you-know-about-this-email"></a>このメールについて他を把握してする必要がありますか。

- 複数のメールに送信された、組織のユーザーが有効な後に電話会議があります。
    
  - **電話会議**のライセンスが割り当てられているとします。
    
  - 手動でをリセットすると、ユーザーの電話会議暗証番号 (pin)。
    
  - ユーザーの会議 ID を手動でリセットする場合
    
  - **電話会議**のライセンスは、それらから削除されます。
    
  - ユーザーの電話会議プロバイダーが変更された場合 Microsoft から別のプロバイダー [**なし]**にします。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
- 既定では、Office 365 からのメールの送信者になりますが、メール アドレスを変更し、Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用して名前を表示することができます。ユーザーにメールを送信するメール アドレスを変更するには、次の操作を行う必要があります。
    
  - SendEmailFromAddress パラメーターには、メール アドレスを入力します。
    
  - SendEmailOverride パラメーターが True に設定します。
    
  - SendEmailFromDisplayName パラメーターには、メールの表示名を入力します。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレスの情報を変更する場合は、組織のメールの受信ポリシーが設定されているユーザー設定のメール アドレスからメールを許可するかどうかを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。
    
    電話会議の情報をユーザーにメールを送信するのには次の手順を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

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
