---
title: 'Lync Server 2013: コールパークの正規化ルールを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="7a4ff-102">Lync Server 2013 でのコールパークの正規化ルールを確認する</span><span class="sxs-lookup"><span data-stu-id="7a4ff-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a4ff-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="7a4ff-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="7a4ff-104">コールパーク orbits は正規化されていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="7a4ff-105">ダイヤル プランでオービット番号が正規化されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="7a4ff-106">追加の正規化ルールを作成して、orbits が正規化されないようにする必要がある場合は、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」の手順に従って新しい正規化ルールを定義し、**一致させるパターン**でオービット範囲を指定します。**翻訳パターン**は **$1**です。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="7a4ff-107">たとえば、Call パークの軌道範囲が7000–7999の場合、**照合するパターン**は **^ (\\7 d{3}) $** で、**翻訳パターン**は **$1**です。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a4ff-108">ダイヤル プランの既定の正規化ルールに <STRONG>^(\d\*)</STRONG> が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="7a4ff-109">そうしないと、Call パークの正規化ルールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7a4ff-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a4ff-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a4ff-110">See Also</span></span>


[<span data-ttu-id="7a4ff-111">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="7a4ff-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

