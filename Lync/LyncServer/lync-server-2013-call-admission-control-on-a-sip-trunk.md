---
title: 'Lync Server 2013: SIP トランク上の通話受付管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8196070bbb7992aed915cf188d67e95912524a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="b59ea-102">Lync Server 2013 の SIP トランク上の通話受付管理</span><span class="sxs-lookup"><span data-stu-id="b59ea-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b59ea-103">_**最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b59ea-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b59ea-p101">SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="b59ea-106">次の図は、SIP トランクの CAC 展開の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b59ea-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="b59ea-107">**SIP トランクの CAC 構成**</span><span class="sxs-lookup"><span data-stu-id="b59ea-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="b59ea-108">![通話受付管理の SIP トランキングの図](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話受付管理の SIP トランキングの図")</span><span class="sxs-lookup"><span data-stu-id="b59ea-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="b59ea-109">SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b59ea-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="b59ea-110">ITSP を表すためのネットワーク サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="b59ea-111">ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="b59ea-112">詳細については、展開ドキュメントの「 [Lync Server 2013 で CAC 用のネットワークサイトを構成する](lync-server-2013-configure-network-sites-for-cac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b59ea-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b59ea-113">ITSP では、このネットワーク サイト構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="b59ea-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="b59ea-114">帯域幅ポリシーの値は、手順 2 で実際に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b59ea-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="b59ea-115">手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="b59ea-116">たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="b59ea-117">詳細については、展開ドキュメントの「 [Lync Server 2013 でのネットワークサイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b59ea-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="b59ea-118">また、CsNetworkInterSitePolicy コマンドレットの Lync Server 管理シェルドキュメントも参照してください。</span><span class="sxs-lookup"><span data-stu-id="b59ea-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="b59ea-119">ITSP からセッション ボーダー コントローラー (SCB) のメディア終端ポイントの IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="b59ea-120">サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b59ea-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="b59ea-121">詳細については、「 [Lync Server 2013 でサブネットとネットワークサイトを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b59ea-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

