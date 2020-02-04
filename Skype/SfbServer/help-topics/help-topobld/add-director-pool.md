---
title: ディレクター プールの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: ディレクタープールの FQDN を定義するには、負荷分散プール内の2つ以上のディレクターで構成される複数のコンピュータープール、または単一のコンピュータープールを選択します。 また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。 ディレクターコンピューターのプールの場合、これは、ハードウェアロードバランサーの仮想 IP のドメインネームシステム (DNS) エントリ、DNS ロードバランシング用の共有 DNS エントリのいずれかです。
ms.openlocfilehash: 150975cedf09c19acac1afffab25f5becf053fe3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698572"
---
# <a name="add-director-pool"></a><span data-ttu-id="a2260-105">ディレクター プールの追加</span><span class="sxs-lookup"><span data-stu-id="a2260-105">Add Director Pool</span></span>
 
<span data-ttu-id="a2260-106">**ディレクタープールの FQDN を定義**するには、負荷分散プール内の2つ以上のディレクターで構成される複数の**コンピュータープール**、または**単一のコンピュータープール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2260-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="a2260-107">また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2260-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="a2260-108">ディレクターコンピューターのプールの場合、これは、ハードウェアロードバランサーの仮想 IP のドメインネームシステム (DNS) エントリ、DNS ロードバランシング用の共有 DNS エントリのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="a2260-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="a2260-109">将来ディレクタープールを実装する予定の場合は、[**複数のコンピュータープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a2260-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="a2260-110">プールは負荷分散されている2台以上のコンピューターとして定義されていますが、単一のコンピュータープールを作成し、単一のコンピューターのプール FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a2260-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="a2260-111">後でプールにコンピューターを追加する準備ができたら、トポロジビルダーをもう一度実行して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しいディレクタープールメンバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2260-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="a2260-112">また、プールの適切なロードバランサーに、ドメインネームシステム (DNS) 負荷分散、またはハードウェアロードバランサー用の新しいプールメンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2260-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="a2260-113">多くの場合、両方の負荷分散システムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a2260-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="a2260-114">新しいメンバーサーバーを両方に追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2260-114">Be sure that you are adding the new member server to both.</span></span> 
  

