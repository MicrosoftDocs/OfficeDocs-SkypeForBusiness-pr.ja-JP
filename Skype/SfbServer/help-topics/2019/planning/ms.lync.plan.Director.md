---
title: ディレクター (計画ツール)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。
ms.openlocfilehash: a1920d11ed354cab3409a9f2a1fd39280ce2d29d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975989"
---
# <a name="director-planning-tool"></a><span data-ttu-id="8b883-103">ディレクター (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="8b883-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="8b883-104">ディレクターは、ユーザーの要求を認証することができますが、すべてのユーザー アカウントのホームがないビジネス サーバー通信ソフトウェアの Skype を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="8b883-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="8b883-105">この役割は、オプションですが、次の 2 つのシナリオでディレクターを展開するように選択します。</span><span class="sxs-lookup"><span data-stu-id="8b883-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="8b883-106">エッジ サーバーを展開することで外部のユーザーによるアクセスを有効にした場合もディレクターを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b883-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="8b883-107">このシナリオでは、ディレクターは、外部ユーザーの認証し、内部サーバーへのトラフィックを通過し。</span><span class="sxs-lookup"><span data-stu-id="8b883-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="8b883-108">ディレクターが使用すると、外部ユーザーを認証するためにフロント エンド プールのサーバーこれらのユーザーの認証を実行するためのオーバーヘッドからを緩和します。</span><span class="sxs-lookup"><span data-stu-id="8b883-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="8b883-109">サービス拒否の攻撃などの悪意のあるトラフィックから内部のフロント エンド プールを分離することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b883-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="8b883-110">ネットワークは、このような攻撃での無効な外部トラフィックであふれ、このトラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="8b883-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="8b883-111">セントラル サイトに複数のフロント エンド プールを展開する場合は、ディレクターをそのサイトに追加することによって認証要求を効率化してパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="8b883-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="8b883-112">このシナリオでは、すべての要求では、ディレクターでは、適切なフロント エンド プールにルーティングすることに最初に移動します。</span><span class="sxs-lookup"><span data-stu-id="8b883-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

