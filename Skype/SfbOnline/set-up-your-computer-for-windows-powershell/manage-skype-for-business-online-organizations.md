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
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284692"
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype for Business Online 組織を管理する

Skype for Business Online テナントに関する情報は、 **CsTenant**と**CsTenantLicensingConfiguration**コマンドレットを使って確認できます。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype for Business Online テナントを管理する

Skype for Business Online テナントに関する情報を取得するには、追加のパラメーターを指定せずに[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。
  
```
Get-CsTenant
```

テナント名と ID のみを返すには、このコマンドを使用します。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)や[CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行する場合は、 _TenantID_パラメーターの値が必要です。
  
指定したテナントのライセンス情報が Skype for Business Online 管理センターで利用できるかどうかに関する情報を見つけるには、 [CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。
  
## <a name="related-topics"></a>関連トピック
[Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md)

  
 
