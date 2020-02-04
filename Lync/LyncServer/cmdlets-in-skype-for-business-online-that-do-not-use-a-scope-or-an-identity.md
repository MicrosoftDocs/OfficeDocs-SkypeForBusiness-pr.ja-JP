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
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>スコープまたは id を使用しない Skype for Business Online のコマンドレット

 


許可リストとブロックリスト (ユーザーが通信できる外部組織を決定するリスト) を変更するときに使用するコマンドレットは、スコープまたは Id のどちらも使用しません。 実際、 **CsEdgeAllowAllKnownDomains**コマンドレットには何のパラメーターもありません。 スコープまたは Id を使用しないコマンドレットは、次のようになります。

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

**CsEdgeAllowList**コマンドレットと**CsEdgeDomainPattern**コマンドレットの両方を使用して、ドメインパラメーターを含める必要があることに注意してください。 次に例を示します。

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

