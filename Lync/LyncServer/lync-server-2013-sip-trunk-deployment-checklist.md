---
title: 'Lync Server 2013: SIP トランクの展開チェックリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="057e0-102">Lync Server 2013 に関する SIP トランクの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="057e0-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="057e0-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="057e0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="057e0-104">SIP トランクを展開する前に、お客様とサービスプロバイダがそれぞれの SIP トランクエンドポイントに関する基本的な接続情報を交換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057e0-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="057e0-105">接続する各 ITSP ゲートウェイについて次の情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="057e0-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="057e0-106">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="057e0-106">IP address</span></span>

  - <span data-ttu-id="057e0-107">完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="057e0-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="057e0-108">サービスプロバイダーから、複数の ITSP ゲートウェイに接続するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="057e0-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="057e0-109">その場合は、各 ITSP ゲートウェイとプール内の各仲介サーバー間の接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057e0-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="057e0-110">サービスプロバイダに提供する情報は、SIP トランク接続の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="057e0-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="057e0-111">マルチプロトコルラベル切り替え (MPLS) またはプライベートネットワーク接続の場合は、ITSP に境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) のルーターのパブリックルーティング可能な IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="057e0-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="057e0-112">ITSP のゲートウェイまたはセッション境界コントローラー (SBC) がこのアドレスに到達できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="057e0-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="057e0-113">また、ITSP に仲介サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="057e0-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="057e0-114">仮想プライベートネットワーク (VPN) 接続の場合、ITSP に VPN サーバーの IP アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="057e0-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="057e0-115">証明書に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="057e0-115">Certificate Considerations</span></span>

<span data-ttu-id="057e0-116">SIP トランク用の証明書が必要かどうかを判断するには、お使いの ITSP でプロトコルのサポートについて確認してください。</span><span class="sxs-lookup"><span data-stu-id="057e0-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="057e0-117">ITSP が伝送制御プロトコル (TCP) のみをサポートしている場合は、証明書は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="057e0-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="057e0-118">ITSP がトランスポート層セキュリティ (TLS) をサポートしている場合、ITSP は証明書を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057e0-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="057e0-119">SIP は、リアルタイムトランスポートプロトコル (RTP) またはセキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP) と連携し、ボイスオーバーインターネットプロトコル (VoIP) 通話で実際のボイスデータを管理するプロトコルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="057e0-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="057e0-120">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="057e0-120">Deployment Process</span></span>

<span data-ttu-id="057e0-121">SIP トランク接続の Lync サーバー側を実装するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="057e0-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="057e0-122">Lync Server Topology Builder を使用して、SIP ドメイントポロジを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="057e0-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="057e0-123">詳細については、展開ドキュメントの「トポロジ[ビルダーでの Lync Server 2013 のトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="057e0-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="057e0-124">Lync Server コントロールパネルを使用して、新しい SIP ドメインの音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="057e0-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="057e0-125">詳細については、展開ドキュメントの「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="057e0-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="057e0-126">**テスト-CsPstnOutboundCall**コマンドレットを使用して接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="057e0-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="057e0-127">詳細については、「Lync Server 管理シェルのドキュメント」または「Lync Server 管理シェルのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="057e0-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

