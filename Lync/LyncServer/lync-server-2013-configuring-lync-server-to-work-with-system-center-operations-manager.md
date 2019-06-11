---
title: System Center Operations Manager を使用するように Lync Server を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="cd075-102">System Center Operations Manager と連携するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="cd075-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd075-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cd075-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cd075-104">System Center Operations Manager と連携するように Microsoft Lync Server 2013 インフラストラクチャを構成するには、次の3つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd075-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="cd075-105">プライマリ System Center Operations Manager management server を特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="cd075-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="cd075-106">管理サーバーの構成には、System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 のインストール、SQL Server を使用したバックエンドデータベースのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd075-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="cd075-107">使用する必要がある実際の SQL Server バージョンは、使用している System Center Operations Manager のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cd075-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="cd075-108">詳細については、「 [Lync server 2013 でプライマリ管理サーバーを構成する](lync-server-2013-configuring-the-primary-management-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd075-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="cd075-109">監視する Lync Server コンピューターを特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="cd075-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="cd075-110">System Center Operations manager を使用して Lync Server コンピューターを監視するには、System Center Operations Manager エージェントファイルをインストールし、各サーバーがプロキシとして動作するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd075-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="cd075-111">Lync Server *watcher ノード*として機能するコンピューターを特定して構成します。</span><span class="sxs-lookup"><span data-stu-id="cd075-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="cd075-112">ウォッチャーノードは、Lync Server の代理トランザクションを定期的に実行するコンピューターであり、システムへのログオン機能やインスタントメッセージの交換機能などの主要な Lync Server コンポーネントを確認する Windows PowerShell コマンドレットです。期待どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="cd075-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="cd075-113">このセクションのトピックでは、これらの各タスクを実行するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd075-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cd075-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="cd075-114">In This Section</span></span>

  - [<span data-ttu-id="cd075-115">Lync Server 2013 でのプライマリ管理サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="cd075-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="cd075-116">Lync Server 2013 管理パックのインストール</span><span class="sxs-lookup"><span data-stu-id="cd075-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="cd075-117">Lync Server 2013 で監視される Lync Server コンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="cd075-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="cd075-118">Lync Server 2013 でのウォッチャーノードのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="cd075-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

