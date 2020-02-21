---
title: 'Lync Server 2013: メディアバイパスのためにサブネットをネットワークサイトに関連付ける'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5565be047443ebb0bf84358a592dc0b1f9314c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d3a40-102">Lync Server 2013 でのメディアバイパスのためにサブネットをネットワークサイトに関連付ける</span><span class="sxs-lookup"><span data-stu-id="d3a40-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a40-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d3a40-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3a40-104">ここでは、メディア バイパス グローバル設定を構成しており、メディア バイパスのネットワーク地域とネットワーク サイトを構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d3a40-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="d3a40-p101">ネットワーク内のすべてのサブネットが、特定のネットワーク サイトに関連付けられている必要があります。 これは、サブネット情報を使用して、エンドポイントが存在するネットワーク サイトを判断するためです。 セッション内の両方のユーザーの場所が認識されている場合、メディア バイパスはメディアの送信先を判断して処理を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="d3a40-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="d3a40-108">メディア バイパスには、サブネットをネットワーク サイトに関連付けるための特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="d3a40-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="d3a40-109">トポロジ内のサブネットとネットワークサイトの間の関連付けを作成するには、「 [Lync Server 2013 のネットワークサイトにサブネットを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d3a40-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="d3a40-110">次のステップ:  帯域幅ポリシー プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d3a40-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="d3a40-p103">サブネットをメディア バイパスのネットワーク サイトに関連付けたら、メディア バイパスのために、サブネットを接続が良好なサブネットと良好でないサブネットに区分する、1 つ以上の帯域幅ポリシー プロファイルを作成する必要があります。帯域幅制限のないネットワーク サイトが含まれたネットワーク地域内のサブネットはすべて接続が良好であるため、それらのサブネットではメディア バイパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3a40-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="d3a40-113">帯域幅ポリシープロファイルを構成する手順については、「 [Lync Server 2013 での帯域幅ポリシープロファイルの作成](lync-server-2013-create-bandwidth-policy-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3a40-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

