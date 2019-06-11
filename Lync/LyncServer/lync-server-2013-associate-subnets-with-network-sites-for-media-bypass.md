---
title: 'Lync Server 2013: サブネットをメディアバイパス用のネットワークサイトと関連付ける'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c0f2d6461264ff8b54609e280c59986e1a923c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a8f20-102">Lync Server 2013 で、サブネットをメディアバイパスのネットワークサイトと関連付ける</span><span class="sxs-lookup"><span data-stu-id="a8f20-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8f20-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a8f20-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8f20-104">このトピックでは、メディアバイパスのグローバル設定を構成しており、メディアをバイパスするためにネットワーク領域とネットワークサイトを構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a8f20-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="a8f20-105">ネットワーク内のすべてのサブネットは、特定のネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f20-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="a8f20-106">これは、エンドポイントが配置されているネットワークサイトを特定するためにサブネット情報が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="a8f20-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="a8f20-107">セッション内の両方の当事者の場所がわかっている場合は、メディアのバイパスによって、処理のためにメディアの送信先を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="a8f20-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="a8f20-108">メディアのバイパスには、サブネットとネットワークサイトを関連付けるための特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="a8f20-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="a8f20-109">トポロジのサブネットとネットワークサイトの間の関連付けを作成するには、「 [Lync Server 2013 でサブネットとネットワークサイトを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a8f20-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="a8f20-110">次の手順: 帯域幅ポリシープロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="a8f20-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="a8f20-111">サブネットをメディアバイパス用のネットワークサイトと関連付けると、メディアバイパスの目的で、サブネットを良好な接続性を持つユーザーに分類する1つまたは複数の帯域幅ポリシープロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f20-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="a8f20-112">帯域幅の制約がないネットワークサイトを含むネットワーク領域内のすべてのサブネットは、接続性が高く、そのため、これらのサブネットはメディアのバイパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8f20-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="a8f20-113">帯域幅ポリシープロファイルを構成する手順については、「 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f20-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

