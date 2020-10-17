---
title: 'Lync Server 2013: 新しいトランク機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0feda45fd6c035209783d173da3a85dec3876e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505284"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="d9d25-102">Lync Server 2013 の新しいトランク機能</span><span class="sxs-lookup"><span data-stu-id="d9d25-102">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9d25-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d9d25-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d9d25-104">Microsoft Lync Server 2013 では、仲介サーバーとゲートウェイ間の複数のトランクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d9d25-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="d9d25-105">Microsoft Lync Server 2010 は、仲介サーバーと PSTN ゲートウェイ間で1つのトランクに対してのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="d9d25-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="d9d25-106">これにより、必要に応じて追加のトランクを定義できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d9d25-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="d9d25-107">トランクとは、仲介サーバーの FQDN とリスニングポート、および PSTN ゲートウェイの FQDN とリッスンポートとの間の論理的な関連付けのことです。</span><span class="sxs-lookup"><span data-stu-id="d9d25-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="d9d25-108">この新しい機能により、弾力性 (複数の仲介サーバーを使用して、同じ PSTN ゲートウェイへの通話をルーティングすることができます)、PBX 相互運用性、および異なるサイトの仲介サーバーが、同じ carrier FQDN によって参照される carrier に対して SIP トランクを使用する SIP トランク構成に対応できます。</span><span class="sxs-lookup"><span data-stu-id="d9d25-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d9d25-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9d25-109">See Also</span></span>


[<span data-ttu-id="d9d25-110">Lync Server 2013 の新しいエンタープライズ Voip 機能</span><span class="sxs-lookup"><span data-stu-id="d9d25-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

