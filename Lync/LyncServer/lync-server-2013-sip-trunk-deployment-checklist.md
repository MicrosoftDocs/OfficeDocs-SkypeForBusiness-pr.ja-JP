---
title: 'Lync Server 2013: SIP トランクの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d584b507f677632b28deb1cae28ebfa4cc7bfa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="5d1f3-102">Lync Server 2013 の SIP トランクの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5d1f3-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d1f3-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5d1f3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5d1f3-104">SIP トランクを展開する前に、ユーザーとサービスプロバイダーは、それぞれの SIP トランクエンドポイントに関する基本的な接続情報を交換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="5d1f3-105">接続する各 ITSP ゲートウェイについて、次の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="5d1f3-106">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5d1f3-106">IP address</span></span>

  - <span data-ttu-id="5d1f3-107">完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5d1f3-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d1f3-108">サービスプロバイダーから、複数の ITSP ゲートウェイに接続するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="5d1f3-109">その場合は、プール内の各 ITSP ゲートウェイと各仲介サーバー間の接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="5d1f3-110">サービスプロバイダーに提供する情報は、SIP トランク接続の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="5d1f3-111">マルチプロトコルラベル切り替え (MPLS) またはプライベートネットワーク接続の場合、ITSP は境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のルーターのパブリックルーティング可能な IP アドレスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="5d1f3-112">ITSP のゲートウェイまたはセッションボーダーコントローラー (SBC) がこのアドレスに到達できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="5d1f3-113">また、ITSP に仲介サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="5d1f3-114">仮想プライベートネットワーク (VPN) 接続の場合は、ITSP に VPN サーバーの IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="5d1f3-115">証明書に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5d1f3-115">Certificate Considerations</span></span>

<span data-ttu-id="5d1f3-116">SIP トランキング用の証明書が必要かどうかを判断するには、ITSP にプロトコルのサポートがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="5d1f3-117">ITSP が伝送制御プロトコル (TCP) のみをサポートしている場合は、証明書は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="5d1f3-118">ITSP がトランスポート層セキュリティ (TLS) をサポートしている場合は、ITSP が証明書を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d1f3-119">SIP は、リアルタイム転送プロトコル (RTP) またはセキュアリアルタイム転送プロトコル (SRTP) (ボイスオーバー Ip (VoIP) 呼び出しで実際の音声データを管理するプロトコル) と連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="5d1f3-120">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="5d1f3-120">Deployment Process</span></span>

<span data-ttu-id="5d1f3-121">SIP トランク接続の Lync Server 側を実装するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="5d1f3-122">Lync Server トポロジビルダーを使用して、SIP ドメイントポロジを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="5d1f3-123">詳細については、「展開」のドキュメントの「 [Define and configure Topology Builder In Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="5d1f3-124">Lync Server コントロールパネルを使用して、新しい SIP ドメインの音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="5d1f3-125">詳細については、「展開」のドキュメントの「[構成トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="5d1f3-126">**テスト-CsPstnOutboundCall**コマンドレットを使用して、接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="5d1f3-127">詳細については、「lync Server Management Shell」ドキュメントまたは「Lync Server 管理シェルのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d1f3-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

