---
title: 'Lync Server 2013: コールパークの正規化ルールの確認'
description: 'Lync Server 2013: コールパークの正規化ルールを確認します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ac4c15091141e3069e7b77533d0e4148459f570
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547063"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="52421-103">Lync Server 2013 でのコールパークの正規化ルールの確認</span><span class="sxs-lookup"><span data-stu-id="52421-103">Verify normalization rules for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52421-104">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="52421-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="52421-105">コールパークオービットを正規化することはできません。</span><span class="sxs-lookup"><span data-stu-id="52421-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="52421-106">オービット番号が正規化されていないことを確認するには、ダイヤルプランを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52421-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="52421-107">オービットが正規化されないようにするために追加の正規化ルールを作成する必要がある場合は、「 [create a dial plan In Lync Server 2013](lync-server-2013-create-a-dial-plan.md) 」の手順に従って新しい正規化ルールを定義します。これにより、 **一致するパターン** でオービット範囲と **変換パターン** が **$1**になります。</span><span class="sxs-lookup"><span data-stu-id="52421-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="52421-108">たとえば、コールパークオービット範囲が7000–7999の場合、 **照合するパターン** は **^ (7 \\ d {3} ) $** 、 **変換パターン** は **$1**になります。</span><span class="sxs-lookup"><span data-stu-id="52421-108">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52421-109">ダイヤルプランの既定の正規化ルールに <STRONG>^ (\d \*)</STRONG>が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52421-109">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="52421-110">それ以外の場合、コールパーク正規化ルールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="52421-110">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52421-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="52421-111">See Also</span></span>


[<span data-ttu-id="52421-112">Lync Server 2013 でダイヤルプランを作成する</span><span class="sxs-lookup"><span data-stu-id="52421-112">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

