---
title: ディレクター プールを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: ディレクター プールの FQDN を定義するには、負荷分散されたプール内の 2 つ以上の取締役で構成される複数のコンピューター プール] または [単一コンピューターのプールを選択します。 ディレクター プールまたは 1 つのディレクターの FQDN への接続に使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。 ディレクターのコンピューターのプールのハードウェア ロード バランサーの仮想 ip アドレスのドメイン ネーム システム (DNS) エントリまたは DNS の負荷分散のための共有の DNS エントリになります。
ms.openlocfilehash: 7ba0efad72094fba880058e81ff701453d9e8252
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992288"
---
# <a name="add-director-pool"></a><span data-ttu-id="ea08a-105">ディレクター プールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ea08a-105">Add Director Pool</span></span>
 
<span data-ttu-id="ea08a-106">**ディレクター プールの FQDN を定義する**、負荷分散されたプール内の 2 つ以上の取締役で構成される**複数のコンピューター プール**または**1 台のコンピューターのプール**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea08a-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="ea08a-107">ディレクター プールまたは 1 つのディレクターの FQDN への接続に使用される完全修飾ドメイン名 (FQDN) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea08a-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="ea08a-108">ディレクターのコンピューターのプールのハードウェア ロード バランサーの仮想 ip アドレスのドメイン ネーム システム (DNS) エントリまたは DNS の負荷分散のための共有の DNS エントリになります。</span><span class="sxs-lookup"><span data-stu-id="ea08a-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="ea08a-109">将来的にディレクター プールを実装する場合は、**複数コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea08a-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="ea08a-110">プールが負荷分散されている 2 つまたは複数のコンピューターとして定義される場合でも 1 台のコンピューターのプールを作成し、1 台のコンピューター用にプールの FQDN を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea08a-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="ea08a-111">プールに後でより多くのコンピューターを追加する準備ができたら、新しいプールのメンバーを定義して、新しいトポロジを公開し、ビジネス サーバーの展開ウィザードは、セットアップは、Skype を使用して新しいディレクター プール メンバー、トポロジ ビルダーを実行してください。</span><span class="sxs-lookup"><span data-stu-id="ea08a-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="ea08a-112">適切な負荷分散装置のプールとして、ドメイン ネーム システム (DNS) 負荷分散の場合に、新しいプールのメンバーを追加またはハードウェアのロード バランサーもください。</span><span class="sxs-lookup"><span data-stu-id="ea08a-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="ea08a-113">多くの場合、両方の負荷分散のシステムにするがあります。</span><span class="sxs-lookup"><span data-stu-id="ea08a-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="ea08a-114">両方に新しいメンバー サーバーを追加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea08a-114">Be sure that you are adding the new member server to both.</span></span> 
  

