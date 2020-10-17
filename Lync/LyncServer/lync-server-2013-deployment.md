---
title: 'Lync Server 2013: 展開'
description: 'Lync Server 2013: 展開。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555363"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="1e2ea-103">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e2ea-104">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1e2ea-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1e2ea-105">Lync Server 2013 通信ソフトウェアの展開には、Active Directory ドメインサービスの準備、フロントエンドサーバーおよびその他の主要な Lync Server 2013 内部コンポーネントの展開、および組織が必要とするその他のサーバーの役割と機能の展開 (外部ユーザーアクセスやエンタープライズ Voip など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e2ea-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="1e2ea-106">このドキュメントでは、Lync Server 2013 を展開するための3つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1e2ea-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="1e2ea-107">Lync Server 2013、Enterprise Edition の新しい展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="1e2ea-108">Lync Server 2013 の新しい展開、Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1e2ea-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="1e2ea-109">既存の Lync Server 2010 Standard Edition または Enterprise Edition 展開への Lync Server 2013 Standard Edition または Enterprise Edition の新しい展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="1e2ea-110">既存の Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 環境での Lync Server 2013 の展開については、 [移行](migration.md) に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e2ea-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e2ea-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1e2ea-111">In This Section</span></span>

  - [<span data-ttu-id="1e2ea-112">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="1e2ea-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="1e2ea-113">Lync Server 2013 での外部ユーザーアクセスの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="1e2ea-114">Lync Server 2013 でのエンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="1e2ea-115">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="1e2ea-116">Lync Server 2013 でのアーカイブの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="1e2ea-117">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="1e2ea-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="1e2ea-118">Lync Server 2013 でのビデオの計画と展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="1e2ea-119">Lync Server 2013 でのブランチサイトの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="1e2ea-120">Lync Server 2013 での常設チャットサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="1e2ea-121">Lync Server 2013 でのクライアントとデバイスの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="1e2ea-122">Lync Server 2013 での統合連絡先ストアの計画と展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="1e2ea-123">Lync Server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="1e2ea-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="1e2ea-124">Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="1e2ea-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="1e2ea-125">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="1e2ea-126">Lync Server 2013 でのモビリティの展開</span><span class="sxs-lookup"><span data-stu-id="1e2ea-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="1e2ea-127">Office Web Apps Server および Lync Server 2013 との統合の構成</span><span class="sxs-lookup"><span data-stu-id="1e2ea-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="1e2ea-128">Lync Server 2013 の正常性構成</span><span class="sxs-lookup"><span data-stu-id="1e2ea-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

