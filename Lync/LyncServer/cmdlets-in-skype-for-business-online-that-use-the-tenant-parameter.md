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
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>テナントパラメーターを使う Skype for Business Online のコマンドレット

 


パブリックプロバイダーの設定を変更する場合は、常にテナント id を指定する必要があります。これは、1つのテナントのみがある場合にも当てはまります。 たとえば、次のコマンドは、Windows Live を、ユーザーが通信できる唯一のパブリックプロバイダーとして設定します。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

ただし、これらのコマンドレットのいずれかを実行するたびに、テナント ID (bf19b7db-6960-41e5-a139-2aa373474354 など) を入力する必要はありません。 代わりに、 [CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))コマンドレットを実行し、テナント id を変数に保存してから、他のコマンドレットのいずれかを呼び出すときにその変数を使用して、テナント id を取得できます。 次に例を示します。

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

または、1つのコマンドでテナント ID を取得し、その値を CsTenantPublicProvider コマンドレットにパイプすることで、この操作を行うこともできます。

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

**Get-CsTenant**コマンドレットを呼び出すときに、テナント ID を指定する必要はありません。 このコマンドは、テナントに関する情報を返します。

    Get-CsTenant

次のコマンドレットは、テナント id を受け取ります。 ただし、この場合、パラメーターは省略可能であり、コマンドレットを呼び出すときに入力する必要はありません。 代わりに、Windows PowerShell は、現在接続している Skype for Business Online テナントに基づいて、適切にテナント id を入力します。

  - [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))

  - [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))

  - [Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

たとえば、 **CsTenantFederationConfiguration**コマンドレットは、次のコマンドを使って呼び出すことができます。

    Get-CsTenantFederationConfiguration

必須ではありませんが、CsTenantFederationConfiguration を呼び出すときにテナントパラメーターを含めることができます。

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、テナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

