---
title: テナントパラメーターを使用する Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121133ce163b73bd0ddf49faa1db03ae352056d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000932"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="dadd3-102">テナントパラメーターを使用する Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="dadd3-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="dadd3-103">パブリックプロバイダーの設定を変更するときは、常にテナント id を指定する必要があります。これは、テナントが1つだけの場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="dadd3-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="dadd3-104">たとえば、次のコマンドは、ユーザーが通信できるパブリックプロバイダーとして Windows Live を設定します。</span><span class="sxs-lookup"><span data-stu-id="dadd3-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="dadd3-105">これらのコマンドレットのいずれかを実行するたびに、テナント ID (たとえば、bf19b7db-6960-41e5-a139-2aa373474354) を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dadd3-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="dadd3-106">その代わりに、 [get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))コマンドレットを実行してテナント id を変数に格納し、他のコマンドレットのいずれかを呼び出すときにその変数を使用することで、テナント id を取得できます。</span><span class="sxs-lookup"><span data-stu-id="dadd3-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="dadd3-107">例:</span><span class="sxs-lookup"><span data-stu-id="dadd3-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="dadd3-108">または、テナント ID を取得し、その値を CsTenantPublicProvider コマンドレットにパイプ処理することによって、この操作を1つのコマンドで行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="dadd3-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="dadd3-109">**Get-cstenant**コマンドレットを呼び出すときに、テナント ID を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dadd3-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="dadd3-110">このコマンドは、テナントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="dadd3-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="dadd3-111">次のコマンドレットは、テナント id を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="dadd3-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="dadd3-112">ただし、このような場合、パラメーターは省略可能であり、コマンドレットを呼び出すときに入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dadd3-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="dadd3-113">代わりに、Windows PowerShell は、現在接続されている Skype for Business Online テナントに基づいて、次のようなテナント id を実際に入力します。</span><span class="sxs-lookup"><span data-stu-id="dadd3-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="dadd3-114">[Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dadd3-115">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dadd3-116">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dadd3-117">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dadd3-118">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dadd3-119">[Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="dadd3-120">たとえば、 **CsTenantFederationConfiguration**コマンドレットは、次のコマンドを使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dadd3-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="dadd3-121">必須ではありませんが、CsTenantFederationConfiguration を呼び出すときにテナントパラメータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dadd3-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="dadd3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dadd3-122">See Also</span></span>


[<span data-ttu-id="dadd3-123">Skype for Business Online の id、スコープ、およびテナント</span><span class="sxs-lookup"><span data-stu-id="dadd3-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="dadd3-124">[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dadd3-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

