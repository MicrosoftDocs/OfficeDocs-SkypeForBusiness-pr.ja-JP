---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。
ms.openlocfilehash: a551e2568b814f1811ebc84a8d187c8554cc1542
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274262"
---
# <a name="director-planning-tool"></a><span data-ttu-id="bcefb-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="bcefb-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="bcefb-104">ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。</span><span class="sxs-lookup"><span data-stu-id="bcefb-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="bcefb-105">この役割はオプションであり、次の2つのシナリオでディレクターを展開することを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcefb-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="bcefb-106">エッジサーバーを展開して外部ユーザーからのアクセスを有効にする場合は、ディレクターも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcefb-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="bcefb-107">このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="bcefb-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="bcefb-108">ディレクターを使用して外部ユーザーを認証すると、フロントエンドプールサーバーは、これらのユーザーの認証を実行するオーバーヘッドから解放されます。</span><span class="sxs-lookup"><span data-stu-id="bcefb-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="bcefb-109">また、サービス拒否攻撃などの悪意のあるトラフィックから、内部のフロントエンドプールを分離することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcefb-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="bcefb-110">このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、このトラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="bcefb-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="bcefb-111">セントラルサイトに複数のフロントエンドプールを展開している場合、そのサイトにディレクターを追加すると、認証要求が簡素化され、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="bcefb-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="bcefb-112">このシナリオでは、すべての要求が最初にディレクターに送られ、適切なフロントエンドプールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="bcefb-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

