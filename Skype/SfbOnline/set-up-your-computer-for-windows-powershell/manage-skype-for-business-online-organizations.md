---
title: "Skype for Business Online 組織を管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Skype for Business Online のテナントに関する情報を入手するのにには、Windows PowerShell と Get CsTenant と Get CsTenantLicensingConfiguration コマンドレットを使用します。"
ms.openlocfilehash: 484911da152ce4bd8f682321575c0cfecafd4e73
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype for Business Online 組織を管理します。

**Get CsTenant**と**Get CsTenantLicensingConfiguration**コマンドレットを使用して、Skype for Business Online のテナントに関する情報を見つけることができます。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype for Business Online のテナントを管理します。

Skype for Business Online のテナントに関する情報を取得するには、パラメーターを追加せずに[取得 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。
  
```
Get-CsTenant
```

名前と ID テナントだけを取得するには、このコマンドを使用します。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

[セット CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) [セット CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行しているときに、 _TenantID_パラメーターの値が必要です。
  
ライセンスについてを指定したテナントは Skype for Business Online 管理センターで利用できるかどうかに関する情報を検索するには、 [Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。
  
## <a name="related-topics"></a>関連トピック
[Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。](set-up-your-computer-for-windows-powershell.md)
