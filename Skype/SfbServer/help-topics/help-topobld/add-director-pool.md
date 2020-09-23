---
title: ディレクター プールを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: ディレクター プールの FQDN を定義するには、負荷分散されたプール内の 2 つ以上のディレクターで構成される複数コンピューター プールまたは単一コンピューター プールを選択します。 また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。 ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219488"
---
# <a name="add-director-pool"></a><span data-ttu-id="6e195-105">ディレクター プールを追加する</span><span class="sxs-lookup"><span data-stu-id="6e195-105">Add Director Pool</span></span>
 
<span data-ttu-id="6e195-106">**ディレクター プールの FQDN を定義する**には、負荷分散されたプール内の 2 つ以上のディレクターで構成される**複数コンピューター プール**または**単一コンピューター プール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e195-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="6e195-107">また、ディレクタープールまたは単一のディレクターの FQDN に接続するために使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e195-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="6e195-108">ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。</span><span class="sxs-lookup"><span data-stu-id="6e195-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="6e195-109">今後、ディレクター プールを実装することを予定している場合は、[**複数のコンピューター プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e195-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="6e195-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6e195-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="6e195-111">後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを実行して、新しいプールメンバーを定義し、新しいトポロジを公開した後、Skype for Business Server 展開ウィザードを使用して新しいディレクタープールメンバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e195-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="6e195-112">また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e195-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="6e195-113">多くの場合、両方の負荷分散システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e195-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="6e195-114">両方に新しいメンバー サーバーを追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e195-114">Be sure that you are adding the new member server to both.</span></span> 
  

