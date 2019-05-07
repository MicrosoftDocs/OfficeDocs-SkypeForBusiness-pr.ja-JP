---
title: Teams のポリシーでの特殊文字の制限について
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
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
description: ポリシー名に特殊文字が含まれている問題と、その問題を修正する際の対処方法を確認します。
ms.openlocfilehash: 12d89c4956b2d076f7279506ccf32737d18d50e0
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632235"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams のポリシーでの特殊文字の制限について

**Microsoft Teams 管理センターにある名前に特殊文字が含まれている（メッセージングや会議などの）ポリシーは、作成または編集できません**。 

ポリシー名に特殊文字が含まれている場合、Microsoft Teams 管理センターでの該当のポリシーの管理は制限されます。 **したがって、ポリシー名に特殊文字を入れないことを強くお勧めします**。 

PowerShell を使用して Teams での会議とメッセージング用に作成されたポリシー名には、@、#、$ などの特殊文字を含めることができます。 ただし、Microsoft Teams 管理センターでポリシーに変更を加える場合は、特殊文字を含めることはできません。 

特殊文字が含まれているポリシーがある場合は、Windows PowerShell (永続版) を使用してポリシーを編集するか、または以前のポリシーと同じ設定で Microsoft Teams 管理センターで新しいポリシーを作成し、同じグループのユーザーに割り当てる必要があります。

## <a name="to-remove-special-characters"></a>特殊文字を削除するには

**手順 1 - PowerShell でリモート接続を確立します。**
まだインストールしていない場合は、[Windows PowerShell 用にお使いのコンピューターを設定します。](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**手順 2 - 以前のポリシーの設定を取得し、出力をキャプチャします。**

> [!NOTE]
> この例は、[メッセージング](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) ポリシー向けです。  他のポリシーの種類でも同じ手順になりますが、適切なコマンドレットを使用する必要があります。 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**手順 3 - 新しいポリシーを作成します。**

Microsoft Teams 管理センターまたは PowerShell を使用して同じ設定で、新しいポリシーを作成できます。

これを実行すると、新しいポリシーが作成されますが、[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) を確認し、次の手順を実行して、正しい設定を追加する必要があります。

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**手順 4 - ポリシーを割り当てます。**
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
このコマンドレットの詳細については、[Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) を参照してください。

**手順 5 - 以前のポリシーを削除します。**

これにより、特殊文字を含む以前のポリシーが削除されます。
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
このコマンドレットの詳細については、[Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) を参照してください。

このコマンドが成功した場合は完了です。 上記のコマンドがエラーを返す場合、ユーザーに以前のポリシーが割り当てられているため、ポリシーから割り当てられているすべてのユーザーを削除する必要があります。

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Microsoft 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online と Microsoft Teams に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  

