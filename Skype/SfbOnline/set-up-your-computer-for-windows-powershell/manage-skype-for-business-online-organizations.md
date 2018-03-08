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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="e12f6-103">Skype for Business Online 組織を管理します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="e12f6-104">**Get CsTenant**と**Get CsTenantLicensingConfiguration**コマンドレットを使用して、Skype for Business Online のテナントに関する情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e12f6-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="e12f6-105">Skype for Business Online のテナントを管理します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="e12f6-106">Skype for Business Online のテナントに関する情報を取得するには、パラメーターを追加せずに[取得 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="e12f6-107">名前と ID テナントだけを取得するには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="e12f6-108">[セット CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) [セット CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行しているときに、 _TenantID_パラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="e12f6-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="e12f6-109">ライセンスについてを指定したテナントは Skype for Business Online 管理センターで利用できるかどうかに関する情報を検索するには、 [Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e12f6-110">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e12f6-110">Related topics</span></span>
[<span data-ttu-id="e12f6-111">Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="e12f6-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
