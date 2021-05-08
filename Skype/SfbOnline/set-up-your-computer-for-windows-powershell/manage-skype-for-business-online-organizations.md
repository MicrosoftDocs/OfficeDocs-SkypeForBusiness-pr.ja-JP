---
title: オンラインSkype for Business組織を管理する
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
description: Windows PowerShell と Get-CsTenant コマンドレットと Get-CsTenantLicensingConfiguration コマンドレットを使用して、Skype for Business Online テナントに関する情報を取得します。
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238787"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="412d4-103">オンラインSkype for Business組織を管理する</span><span class="sxs-lookup"><span data-stu-id="412d4-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="412d4-104">最新の[PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースは Skype for Business Online Connector と統合され、PowerShell 管理用に 1 Teams提供されます。</span><span class="sxs-lookup"><span data-stu-id="412d4-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="412d4-105">Skype for Business Online テナントに関する情報は **、Get-CsTenant** コマンドレットと **Get-CsTenantLicensingConfiguration** コマンドレットを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="412d4-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="412d4-106">Skype for Business Online テナントを管理する</span><span class="sxs-lookup"><span data-stu-id="412d4-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="412d4-107">Skype for Business Online テナントに関する情報を返す場合は、追加のパラメーターを指定せずに[Get-CsTenant](/powershell/module/skype/Get-CsTenant)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="412d4-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="412d4-108">テナント名と ID を返す場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="412d4-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="412d4-109">[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)や [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)などのコマンドレットを実行する場合は _、TenantID_ パラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="412d4-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="412d4-110">指定したテナントのライセンス情報が Skype for Business Online 管理センターで使用できるかどうかに関する情報を確認するには[、Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="412d4-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="412d4-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="412d4-111">Related topics</span></span>
[<span data-ttu-id="412d4-112">Skype for Business Online 管理用にコンピューターをセットアップするには、Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="412d4-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
