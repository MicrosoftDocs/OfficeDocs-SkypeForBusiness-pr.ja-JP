---
title: 'Lync Server 2013: フロントエンドサーバーおよびフロントエンドプールの設定'
description: 'Lync Server 2013: フロントエンドサーバーおよびフロントエンドプールの設定'
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
ms.openlocfilehash: d746bf342f6937c068e32caddd484b708a123910
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577243"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="22b76-103">Lync Server 2013 のフロントエンドサーバーおよびフロントエンドプールの設定</span><span class="sxs-lookup"><span data-stu-id="22b76-103">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22b76-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="22b76-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="22b76-105">このセクションでは、Lync Server 2013 をインストールする方法と、Standard Edition サーバーとフロントエンドプールのサーバーの役割を設定する方法について説明します。これにはフロントエンドサーバーと、フロントエンドサーバーに併置されているすべてのサーバーの役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22b76-105">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="22b76-106">サーバーの役割をインストールしてセットアップするには、サーバーの役割をインストールする各コンピューターで Lync Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="22b76-106">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="22b76-107">展開ウィザードを使用して、ローカル構成ストアのインストール、フロントエンドサーバーのインストール、証明書の構成、サービスの開始など、4つの展開手順をすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="22b76-107">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22b76-108">サーバーの役割を設定するには、まずトポロジを正常に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22b76-108">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="22b76-109">トポロジの公開の詳細については、「 <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Lync Server 2013 でのトポロジ設計の最終処理と実装</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22b76-109">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="22b76-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="22b76-110">In This Section</span></span>

  - [<span data-ttu-id="22b76-111">Lync Server 2013 でのローカル構成ストアのインストール</span><span class="sxs-lookup"><span data-stu-id="22b76-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="22b76-112">Lync Server 2013 のサーバーコンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="22b76-112">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="22b76-113">Lync Server 2013 のサーバーの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="22b76-113">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="22b76-114">Lync Server 2013 のサーバーでのサービスの開始</span><span class="sxs-lookup"><span data-stu-id="22b76-114">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="22b76-115">Lync Server 2013 でプール展開をテストする</span><span class="sxs-lookup"><span data-stu-id="22b76-115">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="22b76-116">Lync Server 2013 での Standard Edition サーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="22b76-116">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

