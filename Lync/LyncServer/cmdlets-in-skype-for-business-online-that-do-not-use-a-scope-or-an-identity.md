---
title: スコープまたは id を使用しない Skype for Business Online のコマンドレット
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ade4dee78fff151530e0d76279fdbfaeade720b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755317"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>スコープまたは id を使用しない Skype for Business Online のコマンドレット

 


許可されたリストとブロックリストを変更するときに使用されるコマンドレット (ユーザーが通信を許可されている組織外を決定するリスト) は、スコープも Id も使用しません。 実際には、 **CsEdgeAllowAllKnownDomains**コマンドレットにはパラメーターはありません。 スコープまたは Id を使用しないコマンドレットは、次のとおりです。

  - [CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

**CsEdgeAllowList**コマンドレットと**CsEdgeDomainPattern**コマンドレットの両方を使用して、Domain パラメーターを含める必要があることに注意してください。 次に例を示します。

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

