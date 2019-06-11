---
title: 'Lync Server 2013: SQL Server のシステム要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8e8bb923fd10d505eb9e1b02b0b0ee31612d40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="d495c-102">Lync Server 2013 の SQL Server のシステム要件</span><span class="sxs-lookup"><span data-stu-id="d495c-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d495c-103">_**最終更新日:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="d495c-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="d495c-104">Enterprise Edition server を展開する前に、ハードウェア要件を満たす専用のコンピューターに Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d495c-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="d495c-105">ハードウェア要件の詳細については、サポートドキュメントの「[サーバーハードウェアプラットフォーム (Lync server 2013 の場合](lync-server-2013-server-hardware-platforms.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d495c-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="d495c-106">ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync Server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d495c-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="d495c-107">展開に必要なアクセス許可については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d495c-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="d495c-108">フロントエンドプールを作成する前に、SQL Server 構成マネージャーを使用してサーバーのポートを定義し、Windows ファイアウォールでポートを開くことで、特定のポート経由で Lync Server 2013 から SQL Server へのアクセスを許可するように Windows ファイアウォールを構成する必要もあります。高度なセキュリティ。</span><span class="sxs-lookup"><span data-stu-id="d495c-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

