---
title: 'Lync Server 2013: 外部ユーザーアクセスの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4ca695ca711c66e529a4eccd43b650cffe1442
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e79e6-102">Lync Server 2013 での外部ユーザーアクセスの展開</span><span class="sxs-lookup"><span data-stu-id="e79e6-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e79e6-103">_**トピックの最終更新日:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="e79e6-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="e79e6-104">Microsoft Lync Server 2013 のエッジコンポーネントを展開すると、認証済みおよび匿名のリモートユーザー、フェデレーションパートナー (XMPP パートナーを含む) など、組織の内部ネットワークにログインしていない外部ユーザーが使用できるようになります。Lync Server を使用して組織内の他のユーザーと通信するための、モバイルクライアントおよびパブリックインスタントメッセージング (IM) サービスのユーザー。</span><span class="sxs-lookup"><span data-stu-id="e79e6-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="e79e6-105">Lync Server 2013 の展開および構成プロセスは、Lync Server 2010 とは大きく異なるものではありません。</span><span class="sxs-lookup"><span data-stu-id="e79e6-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="e79e6-106">インストールおよび管理用のツールは、Lync Server 2010 の場合とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="e79e6-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e79e6-107">Microsoft Lync Server 2013&nbsp;エッジサーバーのインストールと構成は、多くの場合、社内のチームとの間に多大な量の計画と調整を必要とする複雑なプロセスになることがあります。これには、セキュリティ、ネットワーク、ファイアウォール、ドメインネームシステム (DNS)、ロードバランサー、公開キー基盤 (PKI) の考慮事項などがあります。</span><span class="sxs-lookup"><span data-stu-id="e79e6-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="e79e6-108">外部アクセスコンポーネントを展開する前に、用意されている計画プロセスとドキュメントを確認して使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e79e6-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="e79e6-109">これにより、展開プロセスを進める際に望ましくない変更や問題の数と頻度を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e79e6-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="e79e6-110">外部ユーザーアクセスの計画の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e79e6-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e79e6-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e79e6-111">In This Section</span></span>

  - [<span data-ttu-id="e79e6-112">Lync Server 2013 での外部ユーザーアクセスの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="e79e6-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="e79e6-113">Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件</span><span class="sxs-lookup"><span data-stu-id="e79e6-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="e79e6-114">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</span><span class="sxs-lookup"><span data-stu-id="e79e6-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="e79e6-115">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</span><span class="sxs-lookup"><span data-stu-id="e79e6-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="e79e6-116">[Lync Server でのディレクターのセットアップ 2013](lync-server-2013-setting-up-the-director.md) (オプション)</span><span class="sxs-lookup"><span data-stu-id="e79e6-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="e79e6-117">Lync Server 2013 でのエッジサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e79e6-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="e79e6-118">Lync Server 2013 用のリバースプロキシサーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e79e6-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="e79e6-119">Lync Server 2013 での外部ユーザーアクセスのサポートの構成</span><span class="sxs-lookup"><span data-stu-id="e79e6-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="e79e6-120">Lync Server 2013 での Lync と Skype の接続のプロビジョニングガイド</span><span class="sxs-lookup"><span data-stu-id="e79e6-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="e79e6-121">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="e79e6-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="e79e6-122">Lync Server 2013 でのモビリティの展開</span><span class="sxs-lookup"><span data-stu-id="e79e6-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="e79e6-123">Lync Server 2013 でのエッジ展開の確認</span><span class="sxs-lookup"><span data-stu-id="e79e6-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

