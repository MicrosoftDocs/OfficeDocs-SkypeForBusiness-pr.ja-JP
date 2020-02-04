---
title: 'Lync Server 2013: 展開'
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
ms.openlocfilehash: 40f77a307b516874449a86f42f84a3053e5f5914
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="93a40-102">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="93a40-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93a40-103">_**最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="93a40-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="93a40-104">Lync Server 2013 通信ソフトウェアの展開には、Active Directory ドメインサービスの準備、フロントエンドサーバーとその他のコア Lync Server 2013 内部コンポーネントの展開、その他のサーバーの役割と機能の展開が含まれます。組織では、外部ユーザーアクセスやエンタープライズ Voip など、必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="93a40-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="93a40-105">このドキュメントでは、Lync Server 2013 を展開するための3つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="93a40-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="93a40-106">Lync Server 2013 Enterprise Edition の新しい展開</span><span class="sxs-lookup"><span data-stu-id="93a40-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="93a40-107">Lync Server 2013、Standard Edition の新しい展開</span><span class="sxs-lookup"><span data-stu-id="93a40-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="93a40-108">Lync Server 2013 Standard Edition または Enterprise Edition が既存の Lync Server 2010 Standard Edition または Enterprise Edition の展開に新しく展開された</span><span class="sxs-lookup"><span data-stu-id="93a40-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="93a40-109">Lync Server 2013 を既存の Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 環境に展開する方法については、[移行](migration.md)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93a40-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93a40-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="93a40-110">In This Section</span></span>

  - [<span data-ttu-id="93a40-111">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="93a40-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="93a40-112">Lync Server 2013 での外部ユーザー アクセスの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="93a40-113">Lync Server 2013 でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="93a40-114">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="93a40-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="93a40-115">Lync Server 2013 でのアーカイブの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="93a40-116">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="93a40-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="93a40-117">Lync Server 2013 でのビデオの計画と展開</span><span class="sxs-lookup"><span data-stu-id="93a40-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="93a40-118">Lync Server 2013 でのブランチ サイトの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="93a40-119">Lync Server 2013 での常設チャット サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="93a40-120">Lync Server 2013 でのクライアントとデバイスの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="93a40-121">Lync Server 2013 での統合連絡先ストアの計画と展開</span><span class="sxs-lookup"><span data-stu-id="93a40-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="93a40-122">Lync Server 2013 でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="93a40-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="93a40-123">Lync Server 2013 の評価版からの更新</span><span class="sxs-lookup"><span data-stu-id="93a40-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="93a40-124">Lync Server 2013 でのリモート通話コントロールの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="93a40-125">Lync Server 2013 でのモビリティの展開</span><span class="sxs-lookup"><span data-stu-id="93a40-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="93a40-126">Lync Server 2013 と Office Web Apps サーバーの統合の構成</span><span class="sxs-lookup"><span data-stu-id="93a40-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="93a40-127">Lync Server 2013 の正常性構成</span><span class="sxs-lookup"><span data-stu-id="93a40-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

