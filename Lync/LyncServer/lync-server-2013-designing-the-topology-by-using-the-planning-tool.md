---
title: 'Lync Server 2013: 計画ツールを使用したトポロジの設計'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="845d3-102">計画ツールを使用した、Lync Server 2013 のトポロジの設計</span><span class="sxs-lookup"><span data-stu-id="845d3-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="845d3-103">_**最終更新日:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="845d3-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="845d3-104">Microsoft Lync Server 2013 の計画ツールは、設計している Lync Server 2013 トポロジについて質問するための、ウィザードベースのインタビューのツールです。</span><span class="sxs-lookup"><span data-stu-id="845d3-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="845d3-105">計画ツールでは、提供された情報を使用して、トポロジの設計とキャパシティの推奨される方法と共に、指定された回答に基づいて推奨されるトポロジを提示します。</span><span class="sxs-lookup"><span data-stu-id="845d3-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="845d3-106">計画ツールは、Microsoft ダウンロードセンター ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="845d3-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="845d3-107">最終的に、計画ツールの目標は、完全な Lync Server 2013 トポロジの設計の複雑さを簡単にすることです。</span><span class="sxs-lookup"><span data-stu-id="845d3-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="845d3-108">このツールでは、(Microsoft TechNet Web サイトにインターネット接続できる場合は) ツール内で計画および展開ドキュメントへのコンテキスト参照も利用できます。</span><span class="sxs-lookup"><span data-stu-id="845d3-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="845d3-109">インフラストラクチャの TCP/IP アドレスと完全修飾ドメイン名 (Fqdn) を使用してトポロジをカスタマイズすると、計画ツールによって、ドメインネームシステム (DNS) 名前付け、ファイアウォールルール、証明書などの一連のレポートが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="845d3-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="845d3-110">計画ツールでは、次の2つの形式で情報をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="845d3-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="845d3-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="845d3-111">Microsoft Excel</span></span>

  - <span data-ttu-id="845d3-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="845d3-112">Microsoft Visio</span></span>

<span data-ttu-id="845d3-113">次のトピックでは、計画ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="845d3-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="845d3-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="845d3-114">In This Section</span></span>

  - [<span data-ttu-id="845d3-115">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="845d3-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="845d3-116">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="845d3-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="845d3-117">Lync Server 2013 の計画ツールに移動する</span><span class="sxs-lookup"><span data-stu-id="845d3-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="845d3-118">Lync Server 2013 用の最初のトポロジ設計を作成する</span><span class="sxs-lookup"><span data-stu-id="845d3-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="845d3-119">Lync Server 2013 での管理者レポートの確認</span><span class="sxs-lookup"><span data-stu-id="845d3-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="845d3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="845d3-120">See Also</span></span>


[<span data-ttu-id="845d3-121">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="845d3-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="845d3-122">Lync Server 2013 でのフロントエンド サーバー、インスタント メッセージングおよびプレゼンスの計画</span><span class="sxs-lookup"><span data-stu-id="845d3-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

