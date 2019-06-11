---
title: 'Lync Server 2013: データベースと管理サーバーのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database and Management Server cmdlets
ms:assetid: b323bd59-8f71-4f03-af94-f3afb8620f4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415671(v=OCS.15)
ms:contentKeyID: 48185174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b970f55a8389af757d2a55a2255e8028bb78a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-and-management-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b88b5-102">Lync Server 2013 のデータベースと管理サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b88b5-102">Database and Management Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b88b5-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b88b5-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b88b5-104">データベースと管理サーバーのコマンドレットを使用して、Microsoft Lync Server 2013 バックエンドデータベースとフロントエンド管理サービスの両方を管理します。</span><span class="sxs-lookup"><span data-stu-id="b88b5-104">The database and Management Server cmdlets are used to manage both your Microsoft Lync Server 2013 back-end databases and your front-end management services.</span></span> <span data-ttu-id="b88b5-105">これらのコマンドレットを使用して、Lync Server 2013 で使用されているデータベースをインストールまたはアンインストールすることができます。また、中央管理ストアの Active Directory サービス制御ポイントを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b88b5-105">You can use these cmdlets to install or uninstall any of the databases used by Lync Server 2013, in addition to configuring the Active Directory service control point for the Central Management store.</span></span>

<div>

## <a name="database-and-management-server-cmdlets"></a><span data-ttu-id="b88b5-106">データベースと管理サーバーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b88b5-106">Database and Management Server Cmdlets</span></span>

<span data-ttu-id="b88b5-107">データベースと管理サーバーの管理に直接関連するコマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b88b5-107">The following is a list of cmdlets that relate directly to managing databases and the Management Server:</span></span>

<span data-ttu-id="b88b5-108">**データベースと管理サーバー**</span><span class="sxs-lookup"><span data-stu-id="b88b5-108">**Databases and Management Server**</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-109">[Get-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-110">[Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-111">[Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b88b5-112">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-112">[Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-113">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-113">[Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-114">[Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b88b5-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-115">[Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b88b5-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-116">[Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b88b5-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-117">[Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

  - <span data-ttu-id="b88b5-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-118">[Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b88b5-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-119">[Get-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-120">[設定-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-120">[Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b88b5-121">[CsUserDatabase の更新](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-121">[Update-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b88b5-122">[CsManagementServer の移動](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-122">[Move-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b88b5-123">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-123">[Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b88b5-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b88b5-124">[Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b88b5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b88b5-125">See Also</span></span>


[<span data-ttu-id="b88b5-126">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="b88b5-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

