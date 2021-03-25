---
title: Skype for Business Online 組織を管理する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Skype for Business Online Windows PowerShellに関Get-CsTenantを取得Get-CsTenantLicensingConfigurationのコマンドレットとコマンドレットを使用します。
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113183"
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype for Business Online 組織を管理する
> [!NOTE]
> 最新の [Teams PowerShell パブリック](https://www.powershellgallery.com/packages/MicrosoftTeams/) プレビュー リリースは、Skype for Business Online Connector と統合され、Teams PowerShell 管理用の 1 つのモジュールを提供します。

**Get-CsTenant** コマンドレットと **Get-CsTenantLicensingConfiguration** コマンドレットを使用して、Skype for Business Online テナントに関する情報を確認できます。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype for Business Online テナントを管理する

Skype for Business Online テナントに関する情報を返す場合は、追加のパラメーターなしで [Get-CsTenant](/powershell/module/skype/Get-CsTenant) コマンドレットを呼び出します。
  
```PowerShell
Get-CsTenant
```

テナント名と ID を返す場合は、このコマンドを使用します。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)や [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)などのコマンドレットを実行する場合は _、TenantID_ パラメーターの値が必要です。
  
指定したテナントのライセンス情報が Skype for Business Online 管理センターで使用できるかどうかに関する情報を見つけるには [、Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) コマンドレットを使用します。
  
## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
