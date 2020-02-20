---
title: 'Lync Server 2013: コールパークオービットテーブルの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="d27c9-102">Lync Server 2013 でコールパークオービットテーブルを構成する</span><span class="sxs-lookup"><span data-stu-id="d27c9-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d27c9-103">_**トピックの最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d27c9-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d27c9-104">コールパークは、オービットを使用してパーキング呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="d27c9-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="d27c9-105">ユーザーが通話をパークおよび取得できるようにするには、コールパークオービットテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27c9-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="d27c9-106">組織がパーキング呼び出しに対して予約する内線番号の範囲 (オービット) を指定し、各範囲のルーティングを定義する必要があります。その範囲には、各範囲で処理するコールパークプールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d27c9-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="d27c9-107">オービット範囲を定義するときには、1つのオービットが短時間で再利用されないように、また、ユーザーまたはその他のサービスで使用できる拡張機能の数を制限するために、多くのオービットを使用するのではなく、十分なオービットを使用することを目標にします。</span><span class="sxs-lookup"><span data-stu-id="d27c9-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="d27c9-108">コールパークアプリケーションが展開されている Lync Server プールごとに、複数のコールパークオービット範囲を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d27c9-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="d27c9-109">各コールパークオービット範囲には、グローバルに一意の名前と、固有の拡張子のセットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27c9-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d27c9-p102">一般的にオービット範囲には 100 未満のオービットが含まれます。 1 つの範囲の上限は 10,000 オービットです。1 つのプールに含まれるオービットの数は 50,000 未満です。 範囲が小さすぎると、オービットが再び使用されるまでの時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="d27c9-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="d27c9-113">オービット範囲には、仮想内線番号ブロック (ユーザーまたは電話機が割り当てられていない内線番号) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d27c9-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d27c9-114">コールパークオービットテーブルでは、Direct 内ダイヤル (DID) 番号をオービット番号として割り当てることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d27c9-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d27c9-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d27c9-115">In This Section</span></span>

[<span data-ttu-id="d27c9-116">Lync Server 2013 でのコールパークオービット範囲の作成または変更</span><span class="sxs-lookup"><span data-stu-id="d27c9-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

