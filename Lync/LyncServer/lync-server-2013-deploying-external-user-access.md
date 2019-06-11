---
title: 'Lync Server 2013: 外部ユーザー アクセスの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e8522eac5ace72f615cc3cb7b9271981d1b84c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d0dae-102">Lync Server 2013 での外部ユーザー アクセスの展開</span><span class="sxs-lookup"><span data-stu-id="d0dae-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0dae-103">_**最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="d0dae-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="d0dae-104">Microsoft Lync Server 2013 用のエッジコンポーネントを展開すると、認証されたリモートユーザー、フェデレーションパートナー (XMPP パートナーを含む) など、組織の内部ネットワークにログインしていない外部ユーザーが可能になります。Lync Server を使用して組織内の他のユーザーと通信するための、モバイルクライアントとパブリックインスタントメッセージング (IM) サービスのユーザー。</span><span class="sxs-lookup"><span data-stu-id="d0dae-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="d0dae-105">Lync Server 2013 の展開と構成のプロセスは、Lync Server 2010 とは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="d0dae-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="d0dae-106">インストールと管理のためのツールは、Lync Server 2010 とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="d0dae-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0dae-107">Microsoft Lync Server 2013&nbsp;Edge server のインストールと構成は、社内のチームとの計画や調整を大量に行う必要がある複雑なプロセスである可能性があります。たとえば、セキュリティ、ネットワーク、ファイアウォール、ドメインネームシステム (DNS)、ロードバランサー、および公開キー基盤 (PKI) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d0dae-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="d0dae-108">外部アクセスコンポーネントを展開する前に、記載されている計画プロセスとドキュメントを確認して使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0dae-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="d0dae-109">これにより、展開プロセスを実行するときに、不要な変更や問題の数と頻度を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="d0dae-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="d0dae-110">外部ユーザーアクセスの計画については、「 <A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dae-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0dae-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="d0dae-111">In This Section</span></span>

  - [<span data-ttu-id="d0dae-112">Lync Server 2013 の外部ユーザー アクセスの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d0dae-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="d0dae-113">Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件</span><span class="sxs-lookup"><span data-stu-id="d0dae-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="d0dae-114">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</span><span class="sxs-lookup"><span data-stu-id="d0dae-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="d0dae-115">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</span><span class="sxs-lookup"><span data-stu-id="d0dae-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="d0dae-116">[Lync Server 2013 でのディレクターの](lync-server-2013-setting-up-the-director.md)セットアップ省略</span><span class="sxs-lookup"><span data-stu-id="d0dae-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="d0dae-117">Lync Server 2013 でのエッジ サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="d0dae-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="d0dae-118">Lync Server 2013 のリバース プロキシ サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="d0dae-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="d0dae-119">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</span><span class="sxs-lookup"><span data-stu-id="d0dae-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="d0dae-120">Lync Server 2013 での Lync と Skype の接続のプロビジョニング ガイド</span><span class="sxs-lookup"><span data-stu-id="d0dae-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="d0dae-121">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="d0dae-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="d0dae-122">Lync Server 2013 でのモビリティの展開</span><span class="sxs-lookup"><span data-stu-id="d0dae-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="d0dae-123">Lync Server 2013 でのエッジの展開の検証</span><span class="sxs-lookup"><span data-stu-id="d0dae-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

