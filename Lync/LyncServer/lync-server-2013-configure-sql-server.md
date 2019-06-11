---
title: 'Lync Server 2013: SQL Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da3cea6019b6314eccb2968f9b05ef44e7de75e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="7dc12-102">Lync Server 2013 での SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="7dc12-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dc12-103">_**最終更新日:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="7dc12-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="7dc12-104">展開するデータベースごとに、Lync Server 2013 の展開用のすべてのデータベースに対して1つの SQL Server インスタンスを使用できます。これは、データベースサーバー上で併置できます。</span><span class="sxs-lookup"><span data-stu-id="7dc12-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="7dc12-105">データベースの配置の詳細については、サポート対象ドキュメントの「 [Lync server 2013 でサポートされているサーバーの検索場所](lync-server-2013-supported-server-collocation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc12-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="7dc12-106">また、データベースをセットアップするトポロジビルダーの手順を完了する前に、または Windows PowerShell コマンドレットを使用して手動でデータベースを作成する前に、各 SQL Server インスタンスをインストールして使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dc12-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7dc12-107">SQL Server のサポートの詳細については、「 [Lync server 2013 用のハードウェアのセットアップ](lync-server-2013-hardware-setup.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc12-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="7dc12-108">Microsoft SQL Server 2012 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="7dc12-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="7dc12-109">Microsoft SQL Server 2012 のドキュメントについて<https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>は、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dc12-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

