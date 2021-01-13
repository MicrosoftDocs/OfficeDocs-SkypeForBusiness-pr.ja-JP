---
title: ディレクター (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは存在しません。
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834937"
---
# <a name="director-planning-tool"></a><span data-ttu-id="26ee0-103">ディレクター (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="26ee0-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="26ee0-104">ディレクターは、Skype for Business Server 2015 通信ソフトウェアを実行しているサーバーで、ユーザー要求を認証できますが、ユーザー アカウントは含めことはできません。</span><span class="sxs-lookup"><span data-stu-id="26ee0-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="26ee0-105">この役割は省略可能です。次の 2 つのシナリオでディレクターを展開します。</span><span class="sxs-lookup"><span data-stu-id="26ee0-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="26ee0-106">エッジ サーバーを展開して外部ユーザーによるアクセスを有効にする場合は、ディレクターも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26ee0-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="26ee0-107">このシナリオでは、ディレクターは外部ユーザーを認証し、そのトラフィックを内部サーバーに渡します。</span><span class="sxs-lookup"><span data-stu-id="26ee0-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="26ee0-108">ディレクターを使用して外部ユーザーを認証すると、フロントエンド プール サーバーがこれらのユーザーの認証を実行するオーバーヘッドを軽減します。</span><span class="sxs-lookup"><span data-stu-id="26ee0-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="26ee0-109">また、サービス拒否攻撃などの悪意のあるトラフィックから内部フロント エンド プールを保護するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="26ee0-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="26ee0-110">このような攻撃でネットワークに無効な外部トラフィックが殺到しても、このトラフィックはディレクターで終了します。</span><span class="sxs-lookup"><span data-stu-id="26ee0-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="26ee0-111">中央サイトに複数のフロントエンド プールを展開する場合は、ディレクターをそのサイトに追加することで、認証要求を合理化し、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="26ee0-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="26ee0-112">このシナリオでは、すべての要求が最初にディレクターに送信され、次に適切なフロントエンド プールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="26ee0-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

