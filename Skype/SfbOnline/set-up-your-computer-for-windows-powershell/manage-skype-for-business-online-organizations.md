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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="f1d9a-103">Skype for Business Online 組織を管理する</span><span class="sxs-lookup"><span data-stu-id="f1d9a-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="f1d9a-104">最新の [Teams PowerShell パブリック](https://www.powershellgallery.com/packages/MicrosoftTeams/) プレビュー リリースは、Skype for Business Online Connector と統合され、Teams PowerShell 管理用の 1 つのモジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="f1d9a-105">**Get-CsTenant** コマンドレットと **Get-CsTenantLicensingConfiguration** コマンドレットを使用して、Skype for Business Online テナントに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="f1d9a-106">Skype for Business Online テナントを管理する</span><span class="sxs-lookup"><span data-stu-id="f1d9a-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="f1d9a-107">Skype for Business Online テナントに関する情報を返す場合は、追加のパラメーターなしで [Get-CsTenant](/powershell/module/skype/Get-CsTenant) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="f1d9a-108">テナント名と ID を返す場合は、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="f1d9a-109">[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)や [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)などのコマンドレットを実行する場合は _、TenantID_ パラメーターの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="f1d9a-110">指定したテナントのライセンス情報が Skype for Business Online 管理センターで使用できるかどうかに関する情報を見つけるには [、Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1d9a-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f1d9a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1d9a-111">Related topics</span></span>
[<span data-ttu-id="f1d9a-112">Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1d9a-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
