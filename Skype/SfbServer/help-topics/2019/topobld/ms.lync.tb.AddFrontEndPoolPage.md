---
title: フロントエンド プールの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 作成しているフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。 フロント エンド プールを含むトポロジを公開した後は、プールの FQDN を変更できません。 プールの名前を変更する場合は、プールを削除し、新しい FQDN を持つ新しいプールを追加します。
ms.openlocfilehash: f11d45c881053298374f92f692b623f5cee2e183
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888997"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="04968-105">フロントエンド プールの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="04968-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="04968-106">作成しているフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="04968-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="04968-107">フロント エンド プールを含むトポロジを公開した後は、プールの FQDN を変更できません。</span><span class="sxs-lookup"><span data-stu-id="04968-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="04968-108">プールの名前を変更する場合は、プールを削除し、新しい FQDN を持つ新しいプールを追加します。</span><span class="sxs-lookup"><span data-stu-id="04968-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="04968-109">フロント エンド プールを将来的に実装する場合は、**複数コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04968-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="04968-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="04968-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="04968-111">プールに後でより多くのコンピューターを追加する準備ができたら、新しいプールのメンバーを定義、ビジネス サーバーの展開ウィザードは、Skype を使用して新しいフロント エンド プール メンバーを設定して、新しいトポロジを公開するもう一度トポロジ ビルダーを実行してください。</span><span class="sxs-lookup"><span data-stu-id="04968-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="04968-112">プール、ドメイン ネーム システム (DNS) 負荷分散またはハードウェア ロード バランサーの適切な負荷分散装置に新しいプールのメンバーを追加することもあります。</span><span class="sxs-lookup"><span data-stu-id="04968-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="04968-113">多くの場合に、両方の負荷分散のシステムで必要があります。</span><span class="sxs-lookup"><span data-stu-id="04968-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="04968-114">両方に新しいメンバー サーバーを追加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04968-114">Be sure that you are adding the new member server to both.</span></span> 
  

