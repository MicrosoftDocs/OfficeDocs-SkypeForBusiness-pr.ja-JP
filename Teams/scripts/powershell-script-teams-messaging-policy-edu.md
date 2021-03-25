---
title: PowerShell スクリプトのサンプル - メッセージング &割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teams でメッセージング ポリシーを作成し、組織内のユーザーに割り当てします。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117275"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て

Microsoft Teams でメッセージング ポリシーを作成し、ユーザーに割り当てるには、この PowerShell スクリプトを使用します。 

この PowerShell スクリプトの使用の詳細については、「クイック スタート [- Teams for Education」を参照してください](../teams-quick-start-edu.yml)。

このスクリプトでは、Skype for Business Online PowerShell モジュールにある [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) コマンドレットを使用します。 PowerShell [を使用した Teams の](../teams-powershell-overview.md) 管理の詳細については、Teams PowerShell の概要を参照してください。


## <a name="before-you-start"></a>始める前に

Skype for [Business Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)モジュールをダウンロードしてインストールし、メッセージが表示されたらコンピューターを再起動します。

さらに詳しくは [、「Skype for Business Online with Office 365 PowerShell」をご覧ください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> また、バッチ ポリシーの割り当てまたはユーザーがメンバーであるグループに対して、大規模なメッセージング ポリシーをユーザーに直接割り当てすることもできます。 詳細については、「学校の大規模 [な](../batch-group-policy-assignment-edu.md) ユーザー セットにポリシーを割り当てる」および「Teams のユーザーにポリシーを割り当てる」 [を参照してください](../assign-policies.md)。