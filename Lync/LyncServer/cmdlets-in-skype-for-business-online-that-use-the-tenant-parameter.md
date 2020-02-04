---
title: テナントパラメーターを使う Skype for Business Online のコマンドレット
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
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728017"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="65a39-102">テナントパラメーターを使う Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="65a39-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="65a39-103">パブリックプロバイダーの設定を変更する場合は、常にテナント id を指定する必要があります。これは、1つのテナントのみがある場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="65a39-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="65a39-104">たとえば、次のコマンドは、Windows Live を、ユーザーが通信できる唯一のパブリックプロバイダーとして設定します。</span><span class="sxs-lookup"><span data-stu-id="65a39-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="65a39-105">ただし、これらのコマンドレットのいずれかを実行するたびに、テナント ID (bf19b7db-6960-41e5-a139-2aa373474354 など) を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65a39-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="65a39-106">代わりに、 [CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))コマンドレットを実行し、テナント id を変数に保存してから、他のコマンドレットのいずれかを呼び出すときにその変数を使用して、テナント id を取得できます。</span><span class="sxs-lookup"><span data-stu-id="65a39-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="65a39-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65a39-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="65a39-108">または、1つのコマンドでテナント ID を取得し、その値を CsTenantPublicProvider コマンドレットにパイプすることで、この操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="65a39-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="65a39-109">**Get-CsTenant**コマンドレットを呼び出すときに、テナント ID を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65a39-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="65a39-110">このコマンドは、テナントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="65a39-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="65a39-111">次のコマンドレットは、テナント id を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="65a39-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="65a39-112">ただし、この場合、パラメーターは省略可能であり、コマンドレットを呼び出すときに入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65a39-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="65a39-113">代わりに、Windows PowerShell は、現在接続している Skype for Business Online テナントに基づいて、適切にテナント id を入力します。</span><span class="sxs-lookup"><span data-stu-id="65a39-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="65a39-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="65a39-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="65a39-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="65a39-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="65a39-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="65a39-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="65a39-120">たとえば、 **CsTenantFederationConfiguration**コマンドレットは、次のコマンドを使って呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="65a39-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="65a39-121">必須ではありませんが、CsTenantFederationConfiguration を呼び出すときにテナントパラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="65a39-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="65a39-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="65a39-122">See Also</span></span>


[<span data-ttu-id="65a39-123">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="65a39-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="65a39-124">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="65a39-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

