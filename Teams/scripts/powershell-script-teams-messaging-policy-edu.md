---
title: PowerShell スクリプトのサンプル-メッセージポリシーの作成 & 割り当てる
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teams でメッセージングポリシーを作成し、組織内のユーザーに割り当てます。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c1df183046dc2378081382e2a8b46c9b3b92c80a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938196"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て

この PowerShell スクリプトを使用して、Microsoft Teams でメッセージングポリシーを作成し、ユーザーに割り当てます。 

この PowerShell スクリプトの使い方について詳しくは、「[クイックスタート-教育機関向けチーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)」をご覧ください。

このスクリプトは、Skype for Business Online PowerShell モジュールの[Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy)コマンドレットを使用します。 PowerShell を使用したチーム管理の詳細については、「 [Teams PowerShell の概要](../teams-powershell-overview.md)」を参照してください。


## <a name="before-you-start"></a>始める前に

[Skype For Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、メッセージが表示されたら、コンピューターを再起動します。

詳細については、「 [Office 365 PowerShell を使って Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。


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
> また、バッチポリシーの割り当てまたはユーザーがメンバーになっているグループによって、メッセージングポリシーをユーザーに直接割り当てることもできます。 詳細については、「[学校の多数のユーザーにポリシーを割り当て](../batch-policy-assignment-edu.md)、 [Teams のユーザーにポリシーを割り当てる](../assign-policies.md)」を参照してください。
