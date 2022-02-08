---
title: PowerShell のサンプル スクリプト - メッセージング ポリシー&を作成する
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teamsメッセージ ポリシーを作成し、組織内のユーザーに割り当てします。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6c1faaff2ce252b1363fab149c7d168c5e042e5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390839"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て

この PowerShell スクリプトを使用して、メッセージング ポリシーを Microsoft Teamsユーザーに割り当てします。 

この PowerShell スクリプトの使用の詳細については、「クイック スタート - Microsoft Teams for Education」[を参照してください](../teams-quick-start-edu.yml)。

このスクリプトでは、PowerShell Online モジュールの一覧にある [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) コマンドレットSkype for Business使用します。 PowerShell [をTeams管理](../teams-powershell-overview.md)する方法の詳細については、「PowerShell の概要」Teams参照してください。


## <a name="before-you-start"></a>開始する前に

Skype for Business [Online PowerShell モジュールをダウンロードしてインストールし](https://www.microsoft.com/download/details.aspx?id=39366)、メッセージが表示されたらコンピューターを再起動します。

さらに詳しくは、「[PowerShell を使用したオンライン Skype for Businessの管理Office 365参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> また、バッチ ポリシーの割り当てまたはユーザーがメンバーであるグループに大規模なメッセージング ポリシーを直接ユーザーに割り当てすることもできます。 詳細については、「学校の大規模なユーザーに[ポリシー](../batch-group-policy-assignment-edu.md)を割り当てる」と「ポリシーをユーザーに割り当てる」を[参照](../policy-assignment-overview.md)Teams。