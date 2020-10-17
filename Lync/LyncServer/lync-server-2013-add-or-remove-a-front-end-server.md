---
title: 'Lync Server 2013: フロントエンドサーバーの追加または削除'
description: 'Lync Server 2013: フロントエンドサーバーを追加または削除します。'
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
ms.openlocfilehash: 297bbf42dbba3d4f9926fd5ab9e0d7ed79349dc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572003"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="c4081-103">Lync Server 2013 でのフロントエンドサーバーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="c4081-103">Add or remove a Front End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4081-104">_**トピックの最終更新日:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="c4081-104">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="c4081-p101">フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。ユーザーへのサービスを中断しないようにするには、フロントエンド サーバーを追加または削除するときに次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4081-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4081-107">プールに新しいサーバーを追加している場合は、プール内の既存のサーバーと同じ累積更新レベルになるように、新しいプールサーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="c4081-107">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="c4081-108">フロントエンドサーバーを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="c4081-108">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="c4081-p102">フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4081-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="c4081-111">削除するサーバーに現在使用しているセッションがない場合、それらの Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="c4081-111">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="c4081-112">トポロジ ビルダーを開き、必要なサーバーを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="c4081-112">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="c4081-113">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="c4081-113">Publish the topology.</span></span>

5.  <span data-ttu-id="c4081-114">プールで2台以上のフロントエンドサーバーが2台以上になっていない場合、または2台以上のサーバーから完全に2台になった場合は、次のコマンドレットを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4081-114">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="c4081-115">プールに 3 つ以上のサーバーがある場合は、このコマンドレットを入力するとき、これらのサーバーのうち少なくとも 3 つのサーバーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4081-115">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="c4081-116">プール内のすべてのフロントエンドサーバーを1つずつ再起動します。</span><span class="sxs-lookup"><span data-stu-id="c4081-116">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

