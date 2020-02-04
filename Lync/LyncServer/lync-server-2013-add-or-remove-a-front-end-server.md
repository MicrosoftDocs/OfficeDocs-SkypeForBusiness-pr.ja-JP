---
title: 'Lync Server 2013: フロントエンドサーバーを追加または削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078c3d8eed34e7fb6fd98d2d7c12014b87a0497b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="3fc7a-102">Add or remove a Front End Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fc7a-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fc7a-103">_**最終更新日:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="3fc7a-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="3fc7a-104">フロントエンドサーバーをプールに追加する場合、またはプールからフロントエンドサーバーを削除する場合は、プールを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="3fc7a-105">ユーザーによるサービスの中断を防ぐには、フロントエンドサーバーを追加または削除するときに、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fc7a-106">プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="3fc7a-107">フロントエンドサーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="3fc7a-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="3fc7a-108">フロントエンドサーバーを削除する場合は、まず、それらのサーバーへの新しい接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="3fc7a-109">これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="3fc7a-110">削除するサーバーに現在のセッションがない場合は、Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="3fc7a-111">トポロジビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="3fc7a-112">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-112">Publish the topology.</span></span>

5.  <span data-ttu-id="3fc7a-113">プールの2台以上のフロントエンドサーバーを2つ以上にしたり、2つ以上のサーバーから2台以上のサーバーを使用していなかったりする場合は、次のコマンドレットを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="3fc7a-114">プールに3つ以上のサーバーがある場合は、このコマンドレットを入力するときに、これらのサーバーの少なくとも3つを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="3fc7a-115">プール内のすべてのフロントエンドサーバーを一度に1つずつ再起動します。</span><span class="sxs-lookup"><span data-stu-id="3fc7a-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

