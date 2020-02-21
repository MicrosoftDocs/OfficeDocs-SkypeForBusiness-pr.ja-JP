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
ms.openlocfilehash: 693b228eb0065375bd01cb9eedabed46ec1833a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="8c097-102">Lync Server 2013 の新しいトランク機能</span><span class="sxs-lookup"><span data-stu-id="8c097-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c097-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8c097-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8c097-104">Microsoft Lync Server 2013 では、仲介サーバーとゲートウェイ間の複数のトランクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8c097-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="8c097-105">Microsoft Lync Server 2010 は、仲介サーバーと PSTN ゲートウェイ間で1つのトランクに対してのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="8c097-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="8c097-106">これにより、必要に応じて追加のトランクを定義できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8c097-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="8c097-107">トランクとは、仲介サーバーの FQDN とリスニングポート、および PSTN ゲートウェイの FQDN とリッスンポートとの間の論理的な関連付けのことです。</span><span class="sxs-lookup"><span data-stu-id="8c097-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="8c097-108">この新しい機能により、(複数の仲介サーバーを使用して、同じ PSTN ゲートウェイへの通話をルーティングするために複数の仲介サーバーを使用できる) 復元に関するトランク定義が容易になります。また、PBX 相互運用性を確保するために、異なる関連ポリシーを持つ複数のトランクをとの間で使用できます。Ip-pbx と仲介サーバー、および異なるサイトの仲介サーバーが同じキャリア FQDN によって参照される carrier に対して SIP トランクを持つ SIP トランク構成用。</span><span class="sxs-lookup"><span data-stu-id="8c097-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8c097-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c097-109">See Also</span></span>


[<span data-ttu-id="8c097-110">Lync Server 2013 の新しいエンタープライズ Voip 機能</span><span class="sxs-lookup"><span data-stu-id="8c097-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

