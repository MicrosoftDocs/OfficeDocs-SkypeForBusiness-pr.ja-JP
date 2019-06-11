---
title: 'Lync Server 2013: コール パーク オービット テーブルの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="047da-102">Lync Server 2013 でのコール パーク オービット テーブルの構成</span><span class="sxs-lookup"><span data-stu-id="047da-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="047da-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="047da-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="047da-104">コールパークでは、orbits を使用してパーキング通話を行います。</span><span class="sxs-lookup"><span data-stu-id="047da-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="047da-105">ユーザーが通話をパークして取得するには、その前に、コールパークの軌道テーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="047da-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="047da-106">組織がパーキング通話のために予約する内線番号 (orbits) の範囲を指定し、各範囲に対してどのコールパークプールを処理するかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="047da-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="047da-107">軌道の範囲を定義する場合は、1つの軌道がすぐに再利用されることがないように、1つの orbits を使用することをお勧めします。ただし、ユーザーまたは他のサービスで使用可能な拡張機能の数を制限する orbits はあまり多くありません。</span><span class="sxs-lookup"><span data-stu-id="047da-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="047da-108">コールパークアプリケーションが展開されている Lync サーバープールごとに、複数のコールパークの範囲を作成できます。</span><span class="sxs-lookup"><span data-stu-id="047da-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="047da-109">各 Call パーク範囲には、グローバルに一意の名前と一連の固有の拡張子を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="047da-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="047da-p102">一般的にオービット範囲には 100 未満のオービットが含まれます。1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="047da-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="047da-113">オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。</span><span class="sxs-lookup"><span data-stu-id="047da-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="047da-114">コールパークの軌道テーブルでは、内側の市内ダイヤル (DID) 番号を軌道番号として割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="047da-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="047da-115">このセクション中</span><span class="sxs-lookup"><span data-stu-id="047da-115">In This Section</span></span>

[<span data-ttu-id="047da-116">通話パークの作成または変更 Lync Server 2013 の範囲の軌道</span><span class="sxs-lookup"><span data-stu-id="047da-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

