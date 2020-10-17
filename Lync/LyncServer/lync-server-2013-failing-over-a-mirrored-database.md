---
title: 'Lync Server 2013: ミラー化されたデータベースのフェールオーバー'
description: 'Lync Server 2013: ミラーリングされたデータベースのフェールオーバー。'
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
ms.openlocfilehash: fc7c401157c79762f674721ca717296c0fe502db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567693"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Lync Server 2013 でのミラー化されたデータベースのフェールオーバー

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-14_

ミラーリング監視を伴う同期されたミラーリングを使用するようにバックエンド データベースを構成している場合、フェールオーバーは自動で行われます。ミラーリング監視を伴わない同期されたミラーリングを構成している場合は、以下の手順を使用して、データベースのフェールオーバーとフェールバックを実行できます。また、これらの手順を使用すると、ミラーリング監視を構成している場合でも、データベースのフェールオーバーとフェールバックを手動で実行できます。

<div>

## <a name="to-fail-over-your-back-end-database"></a>バックエンド データベースをフェールオーバーするには

1.  フェールオーバーを行う前に、次のコマンドレットを入力して、どのバックエンド データベースがプリンシパルでどれがミラーであるかを確認します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  中央管理ストアがこのプールにホストされている場合は、次のコマンドレットを入力して、どのがプリンシパルで、中央管理ストアのミラーであるかを確認します。
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  ユーザー データベースのフェールオーバーを以下のように実行します。
    
      - プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  プールが中央管理サーバーをホストしている場合は、中央管理ストアのフェールオーバーを実行します。
    
      - プライマリに障害が発生してミラーにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - ミラーに障害が発生してプライマリにフェールオーバーする場合は、次のコマンドレットを入力します。
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

