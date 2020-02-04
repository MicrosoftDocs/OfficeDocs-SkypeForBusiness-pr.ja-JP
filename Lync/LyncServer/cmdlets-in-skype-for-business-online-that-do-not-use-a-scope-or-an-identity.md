---
title: スコープまたは id を使用しない Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727597"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="9de14-102">スコープまたは id を使用しない Skype for Business Online のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="9de14-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="9de14-103">許可リストとブロックリスト (ユーザーが通信できる外部組織を決定するリスト) を変更するときに使用するコマンドレットは、スコープまたは Id のどちらも使用しません。</span><span class="sxs-lookup"><span data-stu-id="9de14-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="9de14-104">実際、 **CsEdgeAllowAllKnownDomains**コマンドレットには何のパラメーターもありません。</span><span class="sxs-lookup"><span data-stu-id="9de14-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="9de14-105">スコープまたは Id を使用しないコマンドレットは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9de14-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="9de14-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9de14-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9de14-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9de14-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9de14-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9de14-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="9de14-109">**CsEdgeAllowList**コマンドレットと**CsEdgeDomainPattern**コマンドレットの両方を使用して、ドメインパラメーターを含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9de14-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="9de14-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9de14-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="9de14-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9de14-111">See Also</span></span>


[<span data-ttu-id="9de14-112">Skype for Business Online の id、スコープ、テナント</span><span class="sxs-lookup"><span data-stu-id="9de14-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="9de14-113">[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9de14-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

