---
title: PowerShell スクリプト サンプル - メッセージング ポリシーを割り当てる&作成する
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teamsでメッセージング ポリシーを作成し、それを組織内のユーザーに割り当てます。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823708"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て

この PowerShell スクリプトを使用して、Microsoft Teamsでメッセージング ポリシーを作成し、それをユーザーに割り当てます。 

この PowerShell スクリプトの使用の詳細については、「[クイック スタート - Microsoft Teams for Education」を](../teams-quick-start-edu.yml)参照してください。

このスクリプトでは、Skype for Business Online PowerShell モジュールにある [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) コマンドレットを使用します。 [PowerShell を使用したTeams](../teams-powershell-overview.md)の管理の詳細については、PowerShell の概要Teams参照してください。


## <a name="before-you-start"></a>開始する前に

[Skype for Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=54616)をダウンロードしてインストールし、メッセージが表示されたらコンピューターを再起動します。

詳細については、「[Office 365 PowerShell を使用したオンラインSkype for Business管理](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。

## <a name="sample-script"></a>サンプル スクリプト

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

> [!NOTE]
> また、バッチ ポリシーの割り当てまたはユーザーがメンバーであるグループに、大規模なユーザーにメッセージング ポリシーを直接割り当てることもできます。 詳細については、「[学校内の大規模なユーザー セットにポリシーを割り当てる](../batch-group-policy-assignment-edu.md)」と「[Teamsのユーザーにポリシーを割り当てる」を参照してください](../policy-assignment-overview.md)。