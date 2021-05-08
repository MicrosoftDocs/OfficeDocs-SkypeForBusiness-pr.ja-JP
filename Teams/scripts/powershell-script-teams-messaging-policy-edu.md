---
title: PowerShell のサンプル スクリプト - メッセージング ポリシー&を作成する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、メッセージング ポリシーを Teams作成し、組織内のユーザーに割り当てる必要があります。
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

この PowerShell スクリプトを使用して、メッセージング ポリシーを作成し、Microsoft Teamsに割り当てします。 

この PowerShell スクリプトの使用の詳細については、「クイック スタート - Teams for Education 」[を参照してください](../teams-quick-start-edu.yml)。

このスクリプトでは、オンライン PowerShell モジュールの一覧にある[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy)コマンドレットSkype for Business使用します。 PowerShell [Teams管理の詳細については、「PowerShell](../teams-powershell-overview.md)の概要」Teams参照してください。


## <a name="before-you-start"></a>開始する前に

Skype for Business Online PowerShell モジュール をダウンロード[してインストールし](https://www.microsoft.com/download/details.aspx?id=39366)、メッセージが表示されたらコンピューターを再起動します。

さらに詳しくは[、「PowerShell を使用して Skype for Business Online を管理する」Office 365してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> また、バッチ ポリシーの割り当てによって、またはユーザーがメンバーであるグループに大規模なメッセージング ポリシーを直接ユーザーに割り当てすることもできます。 詳細については、「学校の大規模なユーザーに[ポリシー](../batch-group-policy-assignment-edu.md)を割り当てる」と「グループ内のユーザーにポリシーを割り当てる[」をTeams。](../assign-policies.md)