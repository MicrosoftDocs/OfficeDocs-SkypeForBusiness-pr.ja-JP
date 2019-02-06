---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
- skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Teams_ITAdmin_Help
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: ffb6082a613587b654f997bc2b2154bfeade15bf
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754737"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>チーム ポリシー内の特殊文字の制限は?

**作成することはできません、または中央にマイクロソフトのチームの管理者の名前に特殊文字がある (メッセージ、会議など) 用のポリシーを編集**します。 

ポリシー名に特殊文字が含まれている場合は、マイクロソフトのチームの管理センターでこれらのポリシーを管理するうえで制限されます。 **よう、強くお勧めポリシー名に特殊文字を含めない**。 

会議、メッセージング チームには特殊文字など、PowerShell を使用して作成されているポリシー名 @、#、$。 ただし、マイクロソフト チームの管理センターのポリシーに変更を加えるしようとしている場合することはできませんにします。 

特殊文字を含むポリシーを使っている場合は、(無限) に Windows PowerShell を使用してポリシーを編集するか、または古いポリシーと同じ設定を持つマイクロソフトのチーム管理センターで新しいポリシーを作成し、同じユーザーのグループに割り当てること必要があります。

## <a name="to-remove-special-characters"></a>特殊文字を削除するのには

**手順 1 - PowerShell でリモート接続を確立します**。
まだしていない場合は、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をします。
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**手順 2 - 以前のポリシーの設定を取得し、出力をキャプチャします。**

> [!NOTE]
> この例では、[メッセージング](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)ポリシーがあります。  その他のポリシーの種類の同じ手順になりますが、適切なコマンドレットを使用する必要があります。 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**手順 3: 新しいポリシーを作成します。**

マイクロソフトのチーム管理センターまたは PowerShell を使用して同じ設定を持つか、新しいポリシーを作成できます。

新しいポリシーを作成、これを実行しているが、[セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)を表示し、後に実行する適切な設定を追加する必要があります。

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**ステップ 4: ポリシーを割り当てます。**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
参照してください、このコマンドレットの詳細については[Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。

**手順 5: 古いポリシーを削除します。**

特殊文字を含む古いポリシーを削除します。
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
このコマンドレットの詳細については[削除 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)を参照します。

このコマンドが成功した場合は終了しました。 上記のコマンドでは、エラーが返された場合は、割り当てられたすべてのユーザーをポリシーから削除するために実行する必要がありますので、古いポリシーがユーザーに割り当てられますため。

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [なぜ Office 365 の PowerShell を使用する必要がありますか。](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。
    
  - [Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > ビジネス オンラインの Skype については、Windows PowerShell モジュールを使用すると、Skype のビジネスをオンラインで、マイクロソフトのチームに接続するリモートの Windows PowerShell セッションを作成できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  

