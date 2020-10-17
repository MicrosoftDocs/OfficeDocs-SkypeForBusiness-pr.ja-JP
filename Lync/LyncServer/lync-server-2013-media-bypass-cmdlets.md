---
title: 'Lync Server 2013: メディアバイパスのコマンドレット'
description: 'Lync Server 2013: メディアバイパスのコマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass cmdlets
ms:assetid: c3463dd2-2372-41b5-8b49-cbe5c2261b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415674(v=OCS.15)
ms:contentKeyID: 48185334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbfc8802df332e1887f95cae4bfe1b08519935f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556413"
---
# <a name="media-bypass-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a0184-103">Lync Server 2013 でのメディアバイパスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a0184-103">Media bypass cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0184-104">_**トピックの最終更新日:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="a0184-104">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="a0184-105">メディア バイパスとは、信号が仲介サーバーを通過する通話で、可能な場合にメディア パスから仲介サーバーを削除することです。</span><span class="sxs-lookup"><span data-stu-id="a0184-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<div>

## <a name="media-bypass-cmdlets"></a><span data-ttu-id="a0184-106">メディア バイパスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a0184-106">Media Bypass Cmdlets</span></span>

<span data-ttu-id="a0184-107">メディア バイパスを構成するには、以下のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0184-107">Use the following cmdlets to configure media bypass.</span></span>

<span data-ttu-id="a0184-108">**メディア バイパス**</span><span class="sxs-lookup"><span data-stu-id="a0184-108">**Media Bypass**</span></span>

  - <span></span>  
    <span data-ttu-id="a0184-109">[新しい-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a0184-109">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a0184-110">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a0184-110">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a0184-111">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a0184-111">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a0184-112">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a0184-112">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0184-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0184-113">See Also</span></span>


[<span data-ttu-id="a0184-114">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="a0184-114">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="a0184-115">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="a0184-115">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

