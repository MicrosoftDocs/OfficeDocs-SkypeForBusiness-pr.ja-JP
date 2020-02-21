---
title: 'Lync Server 2013: Lync Server の Windows Update'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ad3a87c865b987e73c78192b3b2bfc719777cf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="8ea4d-102">Lync Server 2013 の Windows Update</span><span class="sxs-lookup"><span data-stu-id="8ea4d-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ea4d-103">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="8ea4d-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="8ea4d-104">Windows Update サービスを使用して、更新プログラムおよびセキュリティ更新プログラムの確認と適用を頻繁に行ってください。</span><span class="sxs-lookup"><span data-stu-id="8ea4d-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="8ea4d-105">これにより、管理者権限を持つ Microsoft Lync Server 2013 を実行しているサーバーにアクセスでき、Lync Server 2013 を侵害する可能性がある他のシステムコンポーネントの脆弱性を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="8ea4d-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="8ea4d-106">Microsoft SQL Server 2008 Express (64 ビット版) の更新プログラムは、各 Lync Server 2013 Standard Edition サーバー (バックエンドデータベースの場合) とその他のすべての Lync Server 2013 サーバーロール (ローカル構成ストアの場合) のいずれかをアップグレードしていない限り、実行されます。データベースを SQL Server 2008 R2 Express に。</span><span class="sxs-lookup"><span data-stu-id="8ea4d-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="8ea4d-107">このようなデータベースは、フロントエンドプールのバックエンドデータベース、監視データベース、およびアーカイブデータベースに SQL Server が必要となるように、定期的なセキュリティ更新プログラムの保守の一部として考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4d-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="8ea4d-108">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8ea4d-108">Best Practice</span></span>

  - <span data-ttu-id="8ea4d-109">Windows Update を使用して、コンピューターを常に最新の状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="8ea4d-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

