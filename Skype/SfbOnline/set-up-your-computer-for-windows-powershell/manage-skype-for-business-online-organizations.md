---
title: "Skype のオンライン ビジネスの組織を管理します。"
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
description: "オンライン ビジネスのテナントに、Skype に関する情報を取得するのにには、Windows PowerShell と Get CsTenant と Get CsTenantLicensingConfiguration コマンドレットを使用します。"
ms.openlocfilehash: 484911da152ce4bd8f682321575c0cfecafd4e73
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype のオンライン ビジネスの組織を管理します。

**Get CsTenant**と**Get CsTenantLicensingConfiguration**コマンドレットを使用して、情報のオンライン ビジネスのテナントに、Skype のご覧ください。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype のオンライン ビジネスのテナントを管理します。

オンライン ビジネスのテナントに、Skype に関する情報を返すには、追加パラメーターを指定せず[取得 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。
  
```
Get-CsTenant
```

名前と ID は、テナントだけを返す、このコマンドを使用します。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

[セット CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) [セット CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行する場合、 _TenantID_パラメーターの値が必要です。
  
指定したテナントのライセンス情報は、Skype のオンライン ビジネスの管理センターで使用できるかどうかに関する情報を検索するには、 [Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)
