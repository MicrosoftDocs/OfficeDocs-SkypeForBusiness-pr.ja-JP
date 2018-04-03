---
title: Skype のオンライン ビジネスの組織を管理します。
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
description: オンライン ビジネスのテナントに、Skype に関する情報を取得するのにには、Windows PowerShell と Get CsTenant と Get CsTenantLicensingConfiguration コマンドレットを使用します。
ms.openlocfilehash: 53043fbf623ce2cc7342bf5ac7b32c363927def5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="94111-103">Skype のオンライン ビジネスの組織を管理します。</span><span class="sxs-lookup"><span data-stu-id="94111-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="94111-104">**Get CsTenant**と**Get CsTenantLicensingConfiguration**コマンドレットを使用して、情報のオンライン ビジネスのテナントに、Skype のご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94111-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="94111-105">Skype のオンライン ビジネスのテナントを管理します。</span><span class="sxs-lookup"><span data-stu-id="94111-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="94111-106">オンライン ビジネスのテナントに、Skype に関する情報を返すには、追加パラメーターを指定せず[取得 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94111-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="94111-107">名前と ID は、テナントだけを返す、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="94111-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="94111-108">[セット CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) [セット CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行する場合、 _TenantID_パラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="94111-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="94111-109">指定したテナントのライセンス情報は、Skype のオンライン ビジネスの管理センターで使用できるかどうかに関する情報を検索するには、 [Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="94111-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="94111-110">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="94111-110">Related topics</span></span>
[<span data-ttu-id="94111-111">Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します</span><span class="sxs-lookup"><span data-stu-id="94111-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 