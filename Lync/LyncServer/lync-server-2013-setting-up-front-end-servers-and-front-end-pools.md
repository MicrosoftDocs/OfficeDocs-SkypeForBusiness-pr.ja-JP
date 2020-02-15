---
title: 'Lync Server 2013: フロントエンドサーバーおよびフロントエンドプールの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c615d383d2eedf1c24e2da2ddb2561476f4c8db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="56d1b-102">Lync Server 2013 のフロントエンドサーバーおよびフロントエンドプールの設定</span><span class="sxs-lookup"><span data-stu-id="56d1b-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d1b-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="56d1b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="56d1b-104">このセクションでは、Lync Server 2013 をインストールする方法と、Standard Edition サーバーとフロントエンドプールのサーバーの役割を設定する方法について説明します。これにはフロントエンドサーバーと、フロントエンドサーバーに併置されているすべてのサーバーの役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56d1b-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="56d1b-105">サーバーの役割をインストールしてセットアップするには、サーバーの役割をインストールする各コンピューターで Lync Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="56d1b-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="56d1b-106">展開ウィザードを使用して、ローカル構成ストアのインストール、フロントエンドサーバーのインストール、証明書の構成、サービスの開始など、4つの展開手順をすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="56d1b-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56d1b-107">サーバーの役割を設定するには、まずトポロジを正常に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d1b-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="56d1b-108">トポロジの公開の詳細については、「 <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Lync Server 2013 でのトポロジ設計の最終処理と実装</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d1b-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="56d1b-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56d1b-109">In This Section</span></span>

  - [<span data-ttu-id="56d1b-110">Lync Server 2013 でのローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="56d1b-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="56d1b-111">Lync Server 2013 のサーバーコンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="56d1b-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="56d1b-112">Lync Server 2013 のサーバーの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="56d1b-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="56d1b-113">Lync Server 2013 のサーバーでのサービスの開始</span><span class="sxs-lookup"><span data-stu-id="56d1b-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="56d1b-114">Lync Server 2013 でプール展開をテストする</span><span class="sxs-lookup"><span data-stu-id="56d1b-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="56d1b-115">Lync Server 2013 での Standard Edition サーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="56d1b-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

