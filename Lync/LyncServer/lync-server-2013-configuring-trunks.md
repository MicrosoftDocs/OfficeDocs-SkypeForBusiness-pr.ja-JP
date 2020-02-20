---
title: 'Lync Server 2013: トランクの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="4a56a-102">Lync Server 2013 でのトランクの構成</span><span class="sxs-lookup"><span data-stu-id="4a56a-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a56a-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a56a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4a56a-104">エンタープライズ Voip の展開の一部として、仲介サーバーと次の1つ以上のピアの間のトランクを構成して、組織内のエンタープライズ Voip クライアントおよびデバイスの公衆交換電話網 (PSTN) 接続を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="4a56a-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="4a56a-105">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="4a56a-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="4a56a-106">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="4a56a-106">PSTN gateway</span></span>

  - <span data-ttu-id="4a56a-107">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="4a56a-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="4a56a-108">詳細については、「計画」のドキュメントの「 [planning FOR PSTN connectivity In Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a56a-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a56a-109">トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a56a-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="4a56a-110">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 のトポロジビルダーでのゲートウェイの定義</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a56a-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4a56a-111">トランク構成の一環として、Lync Server 2013 media バイパス機能を有効にして、メディアが仲介サーバーをバイパスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a56a-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="4a56a-112">トランクは、メディアバイパスを有効にするかどうかにかかわらず構成できますが、有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4a56a-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="4a56a-113">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">planning for media バイパス In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a56a-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4a56a-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4a56a-114">In This Section</span></span>

  - [<span data-ttu-id="4a56a-115">Lync Server 2013 での複数トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="4a56a-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="4a56a-116">Lync Server 2013 でのトランク間ルーティング</span><span class="sxs-lookup"><span data-stu-id="4a56a-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="4a56a-117">Lync Server 2013 でのトランク構成情報の表示</span><span class="sxs-lookup"><span data-stu-id="4a56a-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="4a56a-118">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="4a56a-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="4a56a-119">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="4a56a-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="4a56a-120">Lync Server 2013 でのトランク構成設定の新しいコレクションの作成</span><span class="sxs-lookup"><span data-stu-id="4a56a-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="4a56a-121">Lync Server 2013 の SIP トランク構成設定の既存コレクションの削除</span><span class="sxs-lookup"><span data-stu-id="4a56a-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4a56a-122">Lync Server 2013 での SIP トランク構成設定の変更</span><span class="sxs-lookup"><span data-stu-id="4a56a-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4a56a-123">Lync Server 2013 での SIP トランク構成設定のテスト</span><span class="sxs-lookup"><span data-stu-id="4a56a-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="4a56a-124">Lync Server 2013 の個々の SIP トランクに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="4a56a-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a56a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a56a-125">See Also</span></span>


[<span data-ttu-id="4a56a-126">Lync Server 2013 のトポロジビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="4a56a-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="4a56a-127">Lync Server 2013 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="4a56a-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="4a56a-128">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="4a56a-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

