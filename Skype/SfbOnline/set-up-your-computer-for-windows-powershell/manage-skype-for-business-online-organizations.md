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
f1keywords: None
ms.custom:
- PowerShell
description: Windows PowerShell と CsTenant と CsTenantLicensingConfiguration コマンドレットを使用して、Skype for Business Online テナントに関する情報を取得します。
ms.openlocfilehash: 340ef9de0e793cbbed7d471754ebca715eb7eaf7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989232"
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype for Business Online 組織を管理する

Skype for Business Online テナントに関する情報は、 **CsTenant**と**CsTenantLicensingConfiguration**コマンドレットを使って確認できます。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype for Business Online テナントを管理する

Skype for Business Online テナントに関する情報を取得するには、追加のパラメーターを指定せずに[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。
  
```PowerShell
Get-CsTenant
```

テナント名と ID のみを返すには、このコマンドを使用します。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)や[CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行する場合は、 _TenantID_パラメーターの値が必要です。
  
指定したテナントのライセンス情報が Skype for Business Online 管理センターで利用できるかどうかに関する情報を見つけるには、 [CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。
  
## <a name="related-topics"></a>関連項目
[Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md)

  
 
