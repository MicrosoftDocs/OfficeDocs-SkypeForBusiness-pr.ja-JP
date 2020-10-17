---
title: テナントパラメーターを使用する Skype for Business Online のコマンドレット
description: テナントパラメーターを使用する Skype for Business Online のコマンドレット。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546803"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>テナントパラメーターを使用する Skype for Business Online のコマンドレット

 


パブリックプロバイダーの設定を変更するときは、常にテナント id を指定する必要があります。これは、テナントが1つだけの場合でも同様です。 たとえば、次のコマンドは、ユーザーが通信できるパブリックプロバイダーとして Windows Live を設定します。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

これらのコマンドレットのいずれかを実行するたびに、テナント ID (たとえば、bf19b7db-6960-41e5-a139-2aa373474354) を入力する必要はありません。 その代わりに、 [get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) コマンドレットを実行してテナント id を変数に格納し、他のコマンドレットのいずれかを呼び出すときにその変数を使用することで、テナント id を取得できます。 以下に例を示します。

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

または、テナント ID を取得し、その値を Set-CsTenantPublicProvider コマンドレットにパイプ処理することで、この操作を1つのコマンドで行うこともできます。

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

**Get-cstenant**コマンドレットを呼び出すときに、テナント ID を指定する必要はありません。 このコマンドは、テナントに関する情報を返します。

    Get-CsTenant

次のコマンドレットは、テナント id を受け入れます。 ただし、このような場合、パラメーターは省略可能であり、コマンドレットを呼び出すときに入力する必要はありません。 代わりに、Windows PowerShell は、現在接続されている Skype for Business Online テナントに基づいて、次のようなテナント id を実際に入力します。

  - [Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

たとえば、 **CsTenantFederationConfiguration** コマンドレットは、次のコマンドを使用して呼び出すことができます。

    Get-CsTenantFederationConfiguration

必須ではありませんが、Get-CsTenantFederationConfiguration を呼び出すときにテナントパラメータを含めることができます。

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>関連項目


[Skype for Business Online の id、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online のコマンドレット](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

