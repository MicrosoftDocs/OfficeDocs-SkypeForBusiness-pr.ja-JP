---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクターは、Skype for Business Server 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。
ms.openlocfilehash: 529c9c0feea8d5ed3e28ee132f64c73228c6bd60
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689862"
---
# <a name="director-planning-tool"></a><span data-ttu-id="4049c-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="4049c-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="4049c-104">ディレクターは、Skype for Business Server 通信ソフトウェアを実行していて、ユーザー要求を認証することはできますが、ユーザーアカウントのホームにはなりません。</span><span class="sxs-lookup"><span data-stu-id="4049c-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="4049c-105">この役割はオプションであり、次の2つのシナリオでディレクターを展開することを選択します。</span><span class="sxs-lookup"><span data-stu-id="4049c-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="4049c-106">エッジサーバーを展開して外部ユーザーからのアクセスを有効にする場合は、ディレクターも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4049c-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="4049c-107">このシナリオでは、ディレクターが外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="4049c-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="4049c-108">ディレクターを使用して外部ユーザーを認証すると、フロントエンドプールサーバーは、これらのユーザーの認証を実行するオーバーヘッドから解放されます。</span><span class="sxs-lookup"><span data-stu-id="4049c-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="4049c-109">また、サービス拒否攻撃などの悪意のあるトラフィックから、内部のフロントエンドプールを分離することもできます。</span><span class="sxs-lookup"><span data-stu-id="4049c-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="4049c-110">このような攻撃で無効な外部トラフィックがネットワークにあふれている場合、このトラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="4049c-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="4049c-111">セントラルサイトに複数のフロントエンドプールを展開している場合、そのサイトにディレクターを追加すると、認証要求が簡素化され、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="4049c-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="4049c-112">このシナリオでは、すべての要求が最初にディレクターに送られ、適切なフロントエンドプールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="4049c-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

