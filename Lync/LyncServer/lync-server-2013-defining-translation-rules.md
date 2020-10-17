---
title: 'Lync Server 2013: 変換ルールの定義'
description: 'Lync Server 2013: 変換ルールの定義。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c59225c8dc74d7d97bf3536c7b7073bc977925
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568393"
---
# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="1a42e-103">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="1a42e-103">Defining translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a42e-104">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1a42e-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1a42e-105">Lync Server 2013 エンタープライズ Voip は、e.164 形式に正規化された電話番号に基づいて通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="1a42e-105">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="1a42e-106">つまり、逆引き番号検索 (RNL) を実行して、一致する SIP URI に変換できるようにするには、すべてのダイヤル文字列を e.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a42e-106">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="1a42e-107">Lync Server 2013 には、呼び出し元 ID と発信者番号のプレゼンテーションを操作する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1a42e-107">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="1a42e-108">このセクションでは、呼び出し先 id と発信者番号を操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a42e-108">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1a42e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1a42e-109">In This Section</span></span>

  - [<span data-ttu-id="1a42e-110">Lync Server 2013 の発信者番号のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="1a42e-110">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="1a42e-111">Lync Server 2013 での ID のプレゼンテーションの呼び出し</span><span class="sxs-lookup"><span data-stu-id="1a42e-111">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a42e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a42e-112">See Also</span></span>


[<span data-ttu-id="1a42e-113">Lync Server 2013 での正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="1a42e-113">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

