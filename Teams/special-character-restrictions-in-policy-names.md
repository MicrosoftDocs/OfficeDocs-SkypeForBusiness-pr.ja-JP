---
title: Teams のポリシーでの特殊文字の制限
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: ポリシー名に特殊文字が含まれている問題と、その問題を修正する際の対処方法を確認します。
ms.openlocfilehash: 7358bd989b793e988f0a3dacdded275b5232c8cc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691513"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams のポリシーでの特殊文字の制限について

**Microsoft Teams 管理センターにある名前に特殊文字が含まれている（メッセージングや会議などの）ポリシーは、作成または編集できません**。 

ポリシー名に特殊文字が含まれている場合、Microsoft Teams 管理センターでの該当のポリシーの管理は制限されます。 **したがって、ポリシー名に特殊文字を入れないことを強くお勧めします**。 

PowerShell を使用して Teams での会議とメッセージング用に作成されたポリシー名には、@、#、$ などの特殊文字を含めることができます。 ただし、Microsoft Teams 管理センターでポリシーに変更を加える場合は、特殊文字を含めることはできません。 

特殊文字が含まれているポリシーがある場合は、Windows PowerShell (永続版) を使用してポリシーを編集するか、または以前のポリシーと同じ設定で Microsoft Teams 管理センターで新しいポリシーを作成し、同じグループのユーザーに割り当てる必要があります。

## <a name="to-remove-special-characters"></a>特殊文字を削除するには

**手順 1 - PowerShell でリモート接続を確立します。**
まだインストールしていない場合は、[Windows PowerShell 用にお使いのコンピューターを設定します。](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**手順 2 - 以前のポリシーの設定を取得し、出力をキャプチャします。**

> [!NOTE]
> この例は、[メッセージング](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) ポリシー向けです。  他のポリシーの種類でも同じ手順になりますが、適切なコマンドレットを使用する必要があります。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**手順 3 - 新しいポリシーを作成します。**

Microsoft Teams 管理センターまたは PowerShell を使用して同じ設定で、新しいポリシーを作成できます。

これを実行すると、新しいポリシーが作成されますが、[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) を確認し、次の手順を実行して、正しい設定を追加する必要があります。

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**手順 4 - ポリシーを割り当てます。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
このコマンドレットの詳細については、[Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) を参照してください。

**手順 5 - 以前のポリシーを削除します。**

これにより、特殊文字を含む以前のポリシーが削除されます。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
このコマンドレットの詳細については、[Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) を参照してください。

このコマンドが成功した場合は完了です。 上記のコマンドがエラーを返す場合、ユーザーに以前のポリシーが割り当てられているため、ポリシーから割り当てられているすべてのユーザーを削除する必要があります。

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常的な作業を簡略化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online と Microsoft Teams に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  

