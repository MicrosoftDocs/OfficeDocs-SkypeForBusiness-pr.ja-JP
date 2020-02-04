---
title: 'Lync Server 2013: ミラー化データベースのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Lync Server 2013 でのミラー化データベースのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-14_

バックエンドデータベースが監視との同期ミラーリングを使用するように構成されている場合、フェールオーバーは自動的に設定されます。 ミラーリングを監視せずに同期ミラーリングを構成した場合は、次の手順を使用してデータベースのフェールオーバーとフェールバックを行うことができます。 また、監視を構成している場合でも、これらの手順を使用して手動でデータベースのフェールオーバーとフェールバックを行うことができます。

<div>

## <a name="to-fail-over-your-back-end-database"></a>バックエンドデータベースをフェールオーバーするには

1.  フェールオーバーする前に、次のコマンドレットを入力して、どのバックエンドデータベースがプリンシパルであり、ミラーであるかを判断します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  このプールで中央管理ストアがホストされている場合は、次のコマンドレットを入力して、どのプリンシパルが中央管理ストアのミラーであるかを判断します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  ユーザーデータベースのフェールオーバーを実行します。
    
      - プライマリに障害が発生し、ミラーにフェイルオーバーする場合は、次のように入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - ミラーが失敗し、プライマリにフェイルオーバーする場合は、次のように入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  プールで中央管理サーバーがホストされている場合は、中央管理ストアのフェールオーバーを実行します。
    
      - プライマリに障害が発生し、ミラーにフェイルオーバーする場合は、次のように入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - ミラーが失敗し、プライマリにフェイルオーバーする場合は、次のように入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

