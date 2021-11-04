---
title: PowerShell のサンプル スクリプト - メッセージング ポリシー&を作成する
author: serdars
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、メッセージング ポリシーを Teams作成し、組織内のユーザーに割り当てる必要があります。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 922bbd88f8a470a19edf799b737a349043ebfeed
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741553"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て

この PowerShell スクリプトを使用して、メッセージング ポリシーを Microsoft Teams作成し、ユーザーに割り当てします。 

この PowerShell スクリプトの使用の詳細については、「クイック スタート - Microsoft Teams for Education」[を参照してください](../teams-quick-start-edu.yml)。

このスクリプトでは、PowerShell Online モジュールの一覧にある[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy)コマンドレットSkype for Business使用します。 PowerShell [Teams管理の詳細については、「PowerShell](../teams-powershell-overview.md)の概要」Teams参照してください。


## <a name="before-you-start"></a>開始する前に

Skype for Business Online PowerShell モジュール をダウンロード[してインストールし](https://www.microsoft.com/download/details.aspx?id=39366)、メッセージが表示されたらコンピューターを再起動します。

さらに詳しくは[、「PowerShell を使用したオンライン Skype for Businessの管理」Office 365をご覧ください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> また、バッチ ポリシーの割り当てまたはユーザーがメンバーであるグループに大規模なメッセージング ポリシーを直接ユーザーに割り当てすることもできます。 詳細については、「学校の大規模なユーザーに[ポリシー](../batch-group-policy-assignment-edu.md)を割り当てる」と「グループ内のユーザーにポリシーを割り当てる[」をTeams。](../policy-assignment-overview.md)