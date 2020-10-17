---
title: System Center Operations Manager と連携するように Lync Server を構成する
description: System Center Operations Manager と連携するように Lync Server を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58126c9e56d48548ba5ce6d74059809c55fecf5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570773"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="409c5-103">Lync Server 2013 を System Center Operations Manager と連携するように構成する</span><span class="sxs-lookup"><span data-stu-id="409c5-103">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409c5-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="409c5-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="409c5-105">System Center Operations Manager と連携するように Microsoft Lync Server 2013 インフラストラクチャを構成するには、次の3つのことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="409c5-105">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="409c5-106">プライマリ System Center Operations Manager 管理サーバーを識別して構成します。</span><span class="sxs-lookup"><span data-stu-id="409c5-106">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="409c5-107">管理サーバーの構成には、System Center Operations Manager 2012 または System Center Operations manager 2007 R2 のインストール、および SQL Server を使用したバックエンドデータベースの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="409c5-107">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="409c5-108">使用する必要がある SQL Server の実際のバージョンは、使用している System Center Operations Manager のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="409c5-108">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="409c5-109">詳細については、「 [Lync server 2013 でプライマリ管理サーバーを構成する](lync-server-2013-configuring-the-primary-management-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409c5-109">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="409c5-110">監視する Lync Server コンピューターを特定し、構成します。</span><span class="sxs-lookup"><span data-stu-id="409c5-110">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="409c5-111">System Center Operations manager を使用して Lync Server コンピューターを監視するには、System Center Operations Manager エージェントファイルをインストールし、プロキシとして動作するように各サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="409c5-111">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="409c5-112">Lync Server *監視ノード*として動作するコンピューターを識別して構成します。</span><span class="sxs-lookup"><span data-stu-id="409c5-112">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="409c5-113">監視ノードは、定期的に Lync Server 代理トランザクションを実行するコンピューターです。これは、Windows PowerShell コマンドレットで、システムへのログオン、またはインスタントメッセージの交換機能などの主要な Lync Server コンポーネントが期待どおりに動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="409c5-113">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="409c5-114">このセクションのトピックでは、これらの各タスクを実行するための手順について説明しています。</span><span class="sxs-lookup"><span data-stu-id="409c5-114">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="409c5-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="409c5-115">In This Section</span></span>

  - [<span data-ttu-id="409c5-116">Lync Server 2013 でのプライマリ管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="409c5-116">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="409c5-117">Lync Server 2013 管理パックのインストール</span><span class="sxs-lookup"><span data-stu-id="409c5-117">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="409c5-118">Lync Server 2013 で監視される Lync Server コンピューターの構成</span><span class="sxs-lookup"><span data-stu-id="409c5-118">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="409c5-119">Lync Server 2013 での監視ノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="409c5-119">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

