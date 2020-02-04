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
ms.openlocfilehash: 962da42567ffcc1c0d541b74266ac5bb1b4653c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="4f650-102">Lync Server 2013 の新しいトランク機能</span><span class="sxs-lookup"><span data-stu-id="4f650-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f650-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4f650-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4f650-104">Microsoft Lync Server 2013 では、仲介サーバーとゲートウェイ間の複数の trunks を定義できます。</span><span class="sxs-lookup"><span data-stu-id="4f650-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="4f650-105">Microsoft Lync Server 2010 は、仲介サーバーと PSTN ゲートウェイ間の1つのトランクでのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="4f650-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="4f650-106">この機能を使うと、追加の trunks を柔軟に定義できます。</span><span class="sxs-lookup"><span data-stu-id="4f650-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="4f650-107">トランクは、仲介サーバーの FQDN とリッスンポート、および PSTN ゲートウェイの FQDN とリッスンポートの間の論理的な関連付けです。</span><span class="sxs-lookup"><span data-stu-id="4f650-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="4f650-108">この新機能により、(複数の仲介サーバーを使用して同一の PSTN ゲートウェイへの通話をルーティングすることができます)、PBX の相互運用性を実現するために、より簡単にトランクの定義を行うことができます。これには、異なる関連ポリシーを持つ複数の trunks を andIP PBX と仲介サーバー、および異なるサイトの仲介サーバーが、同じキャリア FQDN によって参照されているキャリアに SIP trunks を持っている SIP トランク構成の場合。</span><span class="sxs-lookup"><span data-stu-id="4f650-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4f650-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f650-109">See Also</span></span>


[<span data-ttu-id="4f650-110">Lync Server 2013 の新しいエンタープライズ VoIP 機能</span><span class="sxs-lookup"><span data-stu-id="4f650-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

