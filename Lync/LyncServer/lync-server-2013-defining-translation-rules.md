---
title: 'Lync Server 2013: 変換ルールの定義'
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
ms.openlocfilehash: 4082e5ff206a25269e54062add6fcd49c8d22108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="bf4fb-102">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="bf4fb-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf4fb-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="bf4fb-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bf4fb-104">Lync Server 2013 エンタープライズ Voip は、e.164 形式に正規化された電話番号に基づいて通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bf4fb-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="bf4fb-105">つまり、逆引き番号検索 (RNL) を実行して、一致する SIP URI に変換できるようにするには、すべてのダイヤル文字列を e.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf4fb-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="bf4fb-106">Lync Server 2013 には、呼び出し元 ID と発信者番号のプレゼンテーションを操作する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf4fb-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="bf4fb-107">このセクションでは、呼び出し先 id と発信者番号を操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf4fb-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf4fb-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bf4fb-108">In This Section</span></span>

  - [<span data-ttu-id="bf4fb-109">Lync Server 2013 の発信者番号のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="bf4fb-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="bf4fb-110">Lync Server 2013 での ID のプレゼンテーションの呼び出し</span><span class="sxs-lookup"><span data-stu-id="bf4fb-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf4fb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf4fb-111">See Also</span></span>


[<span data-ttu-id="bf4fb-112">Lync Server 2013 での正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="bf4fb-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

