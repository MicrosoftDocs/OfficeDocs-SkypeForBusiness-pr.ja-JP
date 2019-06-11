---
title: 'Lync Server 2013: 変換ルールの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining translation rules
ms:assetid: 4f6b975a-77e6-474c-9171-b139d84138c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398322(v=OCS.15)
ms:contentKeyID: 48184093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd10438fa469b7c6d6285a616d9b9f5f3a262c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-translation-rules-in-lync-server-2013"></a><span data-ttu-id="f7724-102">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="f7724-102">Defining translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7724-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f7724-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f7724-104">Lync Server 2013 エンタープライズボイスは、形式が164で正規化された電話番号に基づいて、通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="f7724-104">Lync Server 2013 Enterprise Voice routes calls based on phone numbers normalized to E.164 format.</span></span> <span data-ttu-id="f7724-105">つまり、電話番号参照 (RNL) を実行する目的で、すべてのダイヤルされた文字列を E-164 形式に正規化して、一致する SIP URI に翻訳することができます。</span><span class="sxs-lookup"><span data-stu-id="f7724-105">This means that all dialed strings must be normalized to E.164 format for the purpose of performing reverse number lookup (RNL) so they can be translated to their matching SIP URI.</span></span> <span data-ttu-id="f7724-106">Lync Server 2013 には、呼び出された ID と発信者番号通知のプレゼンテーションを操作する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f7724-106">Lync Server 2013 provides the ability to manipulate the called ID and the caller ID presentation.</span></span>

<span data-ttu-id="f7724-107">このセクションでは、呼び出された ID と発信者番号を操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7724-107">This section discusses how to manipulate the called ID and caller ID.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7724-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="f7724-108">In This Section</span></span>

  - [<span data-ttu-id="f7724-109">Lync Server 2013 での発信者番号通知のプレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="f7724-109">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)

  - [<span data-ttu-id="f7724-110">Lync Server 2013 の ID プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="f7724-110">Called ID presentation in Lync Server 2013</span></span>](lync-server-2013-called-id-presentation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7724-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7724-111">See Also</span></span>


[<span data-ttu-id="f7724-112">Lync Server 2013 の正規化ルールの定義</span><span class="sxs-lookup"><span data-stu-id="f7724-112">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

