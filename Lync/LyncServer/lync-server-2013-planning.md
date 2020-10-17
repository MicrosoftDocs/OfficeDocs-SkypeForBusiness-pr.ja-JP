---
title: Lync Server 2013 の計画
description: Lync Server 2013 の計画。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning
ms:assetid: 6398cd91-8773-41bc-9b66-725d65ba9d66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398447(v=OCS.15)
ms:contentKeyID: 48184302
ms.date: 12/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4468300195760e7e994087875b5f49489828d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563973"
---
# <a name="planning-for-lync-server-2013"></a><span data-ttu-id="23a09-103">Lync Server 2013 の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-103">Planning for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23a09-104">_**トピックの最終更新日:** 2014-12-09_</span><span class="sxs-lookup"><span data-stu-id="23a09-104">_**Topic Last Modified:** 2014-12-09_</span></span>

<span data-ttu-id="23a09-105">このセクションのトピックでは、Lync Server の展開を成功させるための計画方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23a09-105">The topics in this section describe how to plan for a successful Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="23a09-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="23a09-106">In This Section</span></span>

  - [<span data-ttu-id="23a09-107">Lync Server 2013 の組織の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-107">Organization planning for Lync Server 2013</span></span>](lync-server-2013-planning-for-your-organization.md)

  - [<span data-ttu-id="23a09-108">Lync Server 2013 のインフラストラクチャ要件の決定</span><span class="sxs-lookup"><span data-stu-id="23a09-108">Determining your infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-determining-your-infrastructure-requirements.md)

  - [<span data-ttu-id="23a09-109">Lync Server 2013 のネットワーク計画</span><span class="sxs-lookup"><span data-stu-id="23a09-109">Network planning for Lync Server 2013</span></span>](lync-server-2013-network-planning.md)

  - [<span data-ttu-id="23a09-110">Lync Server 2013 の容量計画</span><span class="sxs-lookup"><span data-stu-id="23a09-110">Capacity planning for Lync Server 2013</span></span>](lync-server-2013-capacity-planning.md)

  - [<span data-ttu-id="23a09-111">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-111">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="23a09-112">Lync Server 2013 での管理および仮想化の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-112">Planning for manageability and virtualization in Lync Server 2013</span></span>](lync-server-2013-planning-for-manageability-and-virtualization.md)

  - [<span data-ttu-id="23a09-113">Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-113">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

  - [<span data-ttu-id="23a09-114">Lync Server 2013 での会議の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-114">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)

  - [<span data-ttu-id="23a09-115">Lync Server 2013 での外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-115">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)

  - [<span data-ttu-id="23a09-116">Lync Server 2013 でのエンタープライズ Voip の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-116">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)

  - [<span data-ttu-id="23a09-117">Lync Server 2013 での監視の計画</span><span class="sxs-lookup"><span data-stu-id="23a09-117">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)

  - [<span data-ttu-id="23a09-118">Lync Server 2013 でのアーカイブの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-118">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)

  - [<span data-ttu-id="23a09-119">Lync Server 2013 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-119">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)

  - [<span data-ttu-id="23a09-120">Exchange Server と Lync Server の統合の計画2013</span><span class="sxs-lookup"><span data-stu-id="23a09-120">Planning for Exchange Server integration with Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-server-integration.md)

  - [<span data-ttu-id="23a09-121">Lync Server 2013 でのクライアントとデバイスの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-121">Planning for clients and devices in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients-and-devices.md)

  - [<span data-ttu-id="23a09-122">Lync Server 2013 でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-122">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

  - [<span data-ttu-id="23a09-123">Lync Server 2013 でのモビリティの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-123">Planning for mobility in Lync Server 2013</span></span>](lync-server-2013-planning-for-mobility.md)

  - [<span data-ttu-id="23a09-124">Lync Server 2013 でのセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="23a09-124">Planning for security in Lync Server 2013</span></span>](lync-server-2013-planning-for-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

