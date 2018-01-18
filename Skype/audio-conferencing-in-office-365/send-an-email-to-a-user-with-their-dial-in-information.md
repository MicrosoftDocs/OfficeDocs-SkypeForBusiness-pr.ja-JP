---
title: "ダイヤルイン情報を持つユーザーに電子メールを送信します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ユーザーの音声会議情報を使用して電子メールを送信します。"
ms.openlocfilehash: cb7aaa956b6a679b918603e2aef2ff15ff04a779
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>ユーザーにダイヤルイン会議情報が含まれたメールを送信する

ビジネスまたはマイクロソフトのチームのユーザーの Skype の電話会議の情報を送信する必要があります。 **Skype**を使用してクリックして**電子メールを使用して会議情報を送信する**ユーザーのプロパティ] の下で、これを行うことができます。 この電子メールを送信するとき、すべてが含まれますのオーディオ会議の情報を含みます。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
    > [!NOTE]
    > 静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。 動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。 場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。 
  
送信されるメールの例を以下に示します。
  
![ダイヤルイン会議のメール](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>オーディオ会議の情報を使用して電子メールをユーザーに送信します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、ユーザーを選択します。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> 送信することも電子メール ユーザーに電話会議の設定を使用してユーザーのプロパティを編集し、[**電話会議**] をクリックして > **メールでの会議の情報を送信**します。 
  
## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- 送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。
    
  - ときに、**オーディオ会議**のライセンスが割り当てられます。
    
  - リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - これらのファイルから、**オーディオ会議**のライセンスが削除されます。
    
  - オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは**[なし]**にします。
    
  - マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。
    
- 既定では、電子メールの送信者は、Office 365 からされますが、メール アドレスの変更し、Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用して名前を表示できます。 ユーザーに電子メールを送信する電子メール アドレスを変更するには、次の操作を行う必要があります。
    
  - SendEmailFromAddress パラメーターでは、電子メール アドレスを入力します。
    
  - SendEmailOverride パラメーターを True に設定します。
    
  - SendEmailFromDisplayName パラメーターでは、電子メールの表示名を入力します。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
    音声会議情報を使用してユーザーに電子メールを送信するのには、次の手順を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
