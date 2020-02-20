---
title: 'Lync Server 2013: SQL Server の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d46a857f0f9ef55dc375b4d465205668fe5f79e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="0fff5-102">Lync Server 2013 での SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="0fff5-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fff5-103">_**トピックの最終更新日:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="0fff5-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="0fff5-104">展開するデータベースごとに、データベースサーバーに併置できる Lync Server 2013 展開のすべてのデータベースに対して1つの SQL Server インスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fff5-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="0fff5-105">データベースの併置の詳細については、「サポート」のドキュメントの「supported [server 併置 in Lync server 2013](lync-server-2013-supported-server-collocation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fff5-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0fff5-106">また、データベースをセットアップするトポロジビルダーの手順を完了する前に、または Windows PowerShell コマンドレットを使用してデータベースを手動で作成する前に、各 SQL Server インスタンスをインストールして使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fff5-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0fff5-107">SQL Server のサポートの詳細については、「 [Lync Server 2013 のハードウェアのセットアップ](lync-server-2013-hardware-setup.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fff5-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="0fff5-108">Microsoft SQL Server 2012 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="0fff5-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="0fff5-109">Microsoft SQL Server 2012 のドキュメント<https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fff5-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

