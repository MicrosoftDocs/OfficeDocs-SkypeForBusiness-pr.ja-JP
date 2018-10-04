---
title: PowerShell スクリプトのサンプルを作成し、メッセージング ポリシーを割り当てる
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: この PowerShell スクリプトを使用して、チームにメッセージング ポリシーを作成し、組織内のユーザーに割り当てることにします。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 282a5442b6d4bf64771e741e75fab45bc87f6bd4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371239"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell スクリプトのサンプルを作成し、メッセージング ポリシーを割り当てる
-------------------------------------------------------------------------

この PowerShell スクリプトを使用して、マイクロソフトのチームでのメッセージング ポリシーを作成し、ユーザーに割り当てることにします。 

この PowerShell スクリプトを使用しての詳細については、[教育用のクイック ・ スタート ・ チーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)を参照してください。

PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。


## <a name="sample-script"></a>サンプル スクリプト

````powershell
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
````


