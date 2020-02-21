---
title: 'Lync Server 2013: プライマリ管理サーバーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18ec967418effe53399070bc8e6f414cd2d927cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="12a37-102">Lync Server 2013 でのプライマリ管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="12a37-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12a37-103">_**トピックの最終更新日:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="12a37-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="12a37-104">Microsoft Lync Server 2013 に含まれる新しい正常性監視機能を十分に活用するために、管理者はまず、プライマリ管理サーバーとして動作するコンピューターを指定する必要があります。そのコンピューターで、System Center Operations Manager 2007 R2 または System Center Operations Manager 2012 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="12a37-105">また、Operations Manager のバックエンドデータベースとして機能するために、サポートされているバージョンの SQL Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="12a37-106">System Center Operations Manager 2012 を使用している場合は、次のいずれかのバージョンの SQL Server をバックエンドデータベースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="12a37-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="12a37-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="12a37-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="12a37-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="12a37-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="12a37-109">System Center Operations Manager 2007 R2 を使用している場合は、SQL Server 2005 Service Pack 4 または SQL Server 2008 Service Pack 3 をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12a37-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="12a37-110">また、SQL Server 2008 R2 を System Center Operations Manager 2007 R2 のバックエンドデータベースとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="12a37-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="12a37-111">SQL Server 2008 R2 を System Center Operations Manager 2007 R2 と連携するように構成する方法の詳細については、このドキュメントの「付録1」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a37-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="12a37-112">System Center Operations Manager 2012 または System Center Operations manager 2007 R2 をインストールする場合は、次のような製品のすべてのコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="12a37-113">オペレーション データベース</span><span class="sxs-lookup"><span data-stu-id="12a37-113">Operational database</span></span>

  - <span data-ttu-id="12a37-114">サーバー</span><span class="sxs-lookup"><span data-stu-id="12a37-114">Server</span></span>

  - <span data-ttu-id="12a37-115">コンソール</span><span class="sxs-lookup"><span data-stu-id="12a37-115">Console</span></span>

  - <span data-ttu-id="12a37-116">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="12a37-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="12a37-117">Web コンソール</span><span class="sxs-lookup"><span data-stu-id="12a37-117">Web console</span></span>

  - <span data-ttu-id="12a37-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="12a37-118">Reporting</span></span>

  - <span data-ttu-id="12a37-119">データ ウェアハウス</span><span class="sxs-lookup"><span data-stu-id="12a37-119">Data warehouse</span></span>

<span data-ttu-id="12a37-120">これらのコンポーネントとそのインストールの詳細については、このドキュメントでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="12a37-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="12a37-121">System Center Operations Manager 2007 R2 の詳細については、Operations Manager 2007 R2 の<https://go.microsoft.com/fwlink/p/?linkid=257526>ドキュメントと、System Center operations manager 2012 の<https://go.microsoft.com/fwlink/p/?linkid=257527>マニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a37-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="12a37-122">SQL Server 2005 または SQL Server 2008 Service Pack 1 をバックエンドデータベースとして使用する場合は、これらの手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="12a37-123">System Center Operations Manager 2012 を使用している場合は、SQL Server 2012 をバックエンドデータベースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="12a37-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="12a37-124">SQL Server 2012 の詳細については、「Books Online for SQL [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)server 2012」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12a37-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="12a37-125">Lync Server の展開ごとに1つのプライマリ管理サーバーしか使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12a37-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="12a37-126">また、System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 のどちらかを使用できますが、2つのアプリケーションを同時に実行することはできません。どちらか一方を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="12a37-127">たとえば、System Center Operations Manager 2012 を実行している場合は、すべてのシステムセンターエージェントも System Center Operations Manager 2012 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="12a37-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="12a37-128">System Center Operations Manager 2012 と、System Center Operations Manager 2007 R2 を実行している他のエージェントを実行しているエージェントはありません。</span><span class="sxs-lookup"><span data-stu-id="12a37-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

