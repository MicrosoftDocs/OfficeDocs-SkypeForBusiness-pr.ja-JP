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
description: Windows PowerShell と CsTenant と CsTenantLicensingConfiguration コマンドレットを使用して、Skype for Business Online テナントに関する情報を取得します。
ms.openlocfilehash: 3c4a8f72caca634b208de5cf4aa555b88518f4da
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706252"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="7558f-103">Skype for Business Online 組織を管理する</span><span class="sxs-lookup"><span data-stu-id="7558f-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="7558f-104">Skype for Business Online テナントに関する情報は、 **CsTenant**と**CsTenantLicensingConfiguration**コマンドレットを使って確認できます。</span><span class="sxs-lookup"><span data-stu-id="7558f-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="7558f-105">Skype for Business Online テナントを管理する</span><span class="sxs-lookup"><span data-stu-id="7558f-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="7558f-106">Skype for Business Online テナントに関する情報を取得するには、追加のパラメーターを指定せずに[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7558f-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="7558f-107">テナント名と ID のみを返すには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7558f-107">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="7558f-108">[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)や[CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)などのコマンドレットを実行する場合は、 _TenantID_パラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="7558f-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="7558f-109">指定したテナントのライセンス情報が Skype for Business Online 管理センターで利用できるかどうかに関する情報を見つけるには、 [CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7558f-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7558f-110">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7558f-110">Related topics</span></span>
[<span data-ttu-id="7558f-111">Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7558f-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
