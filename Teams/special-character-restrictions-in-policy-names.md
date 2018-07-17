---
title: チーム ポリシー内の特殊文字の制限は?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: ポリシーおよびその修正を行うことができますの名前に特殊文字を含むが、どのような問題を参照してください。
ms.openlocfilehash: 4ddd6a618c42f629acd64162ad608aede6b1819f
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "20397090"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>チーム ポリシー内の特殊文字の制限は?

**ビジネス管理センターは、マイクロソフトのチームと Skype で名前に特殊文字がある (メッセージ、会議など) 用のポリシーを編集または作成できません。** 

ポリシー名に特殊文字が含まれている場合は、マイクロソフトのチームとビジネス管理センターの Skype でこれらのポリシーを管理するうえで制限されます。 **よう、強くお勧めポリシー名に特殊文字を含めない**。 

会議、メッセージング チームには特殊文字など、PowerShell を使用して作成されているポリシー名 @、#、$。 ただし場合は、マイクロソフトのチームと Skype のビジネス管理センターでポリシーを変更するためのお問い合わせは、することはできませんにします。 

特殊文字を含むポリシーがあれば、(無限) に Windows PowerShell を使用して、ポリシーを編集するか、または古いポリシーと同じ設定で、マイクロソフトのチームとビジネス管理センターの Skype の新しいポリシーを作成し、同じグループに割り当てることする必要があります。ユーザーの p です。

## <a name="to-remove-special-characters"></a>特殊文字を削除するのには



**手順 1 - PowerShell でリモート接続を確立します**。
まだしていない場合は、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をします。
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

ビジネス管理センターまたは PowerShell のマイクロソフトのチームと Skype を使用して同じ設定で新しいポリシーを作成できますか。

新しいポリシーを作成、これを実行しているが、[セット CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)を表示し、後に実行する適切な設定を追加する必要があります。

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**ステップ 4: ポリシーを割り当てます。**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
参照してください、このコマンドレットの詳細については[Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。

**手順 5: 古いポリシーを削除します。**

特殊文字を含む古いポリシーを削除します。
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
このコマンドレットの詳細については[削除 CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)を参照します。

このコマンドが成功した場合は終了しました。 上記のコマンドでは、エラーが返された場合は、割り当てられたすべてのユーザーをポリシーから削除するために実行する必要がありますので、古いポリシーがユーザーに割り当てられますため。

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [なぜ Office 365 の PowerShell を使用する必要がありますか。](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。
    
  - Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > ビジネス オンラインの Skype については、Windows PowerShell モジュールを使用すると、Skype のビジネスをオンラインで、マイクロソフトのチームに接続するリモートの Windows PowerShell セッションを作成できます。 Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。
  
### <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
