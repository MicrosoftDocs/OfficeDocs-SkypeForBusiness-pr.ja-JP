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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Windows PowerShell コマンドレットと Get-CsTenant コマンドレットGet-CsTenantLicensingConfigurationを使用して、Skype for Business Online テナントに関する情報を取得します。
ms.openlocfilehash: e45f1bdd2c14aea34e07183dde86031a8c503476
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623089"
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype for Business Online 組織を管理する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> [PowerShell パブリック Teams最新](https://www.powershellgallery.com/packages/MicrosoftTeams/)のリリースは Skype for Business Online Connector と統合され、PowerShell 管理用の 1 つのモジュールTeams提供されます。

Skype for Business Online テナントに関する情報は **、Get-CsTenant** コマンドレットと **Get-CsTenantLicensingConfiguration** コマンドレットを使用して確認できます。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype for Business Online テナントを管理する

Skype for Business Online テナントに関する情報を返す場合は、追加のパラメーターを指定せずに[Get-CsTenant](/powershell/module/skype/Get-CsTenant)コマンドレットを呼び出します。
  
```PowerShell
Get-CsTenant
```

テナント名と ID を返す場合は、次のコマンドを使用します。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)や [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)などのコマンドレットを実行する場合は _、TenantID_ パラメーターの値が必要です。
  
指定したテナントのライセンス情報が Skype for Business Online 管理センターで使用できるかどうかに関する情報を確認するには[、Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration)コマンドレットを使用します。
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online Management 用にコンピューターをセットアップするには、Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
