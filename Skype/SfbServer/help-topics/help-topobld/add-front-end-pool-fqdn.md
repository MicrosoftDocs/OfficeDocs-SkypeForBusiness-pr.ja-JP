---
title: フロントエンド プールの FQDN を追加する
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
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 作成するフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。フロント エンド プールを含むトポロジを公開した後でプールの FQDN を変更することはできません。プールの名前変更が必要になった場合は、そのプールを削除してから、新しい FQDN で新しいプールを追加する必要があります。
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218858"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="4a6bf-105">フロントエンド プールの FQDN を追加する</span><span class="sxs-lookup"><span data-stu-id="4a6bf-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="4a6bf-p102">作成するフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。フロント エンド プールを含むトポロジを公開した後でプールの FQDN を変更することはできません。プールの名前変更が必要になった場合は、そのプールを削除してから、新しい FQDN で新しいプールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="4a6bf-109">将来的にフロント エンド プールを実装する予定の場合は、**[複数コンピューターのプール]** を選択してください。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="4a6bf-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューターのプールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="4a6bf-111">後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを実行して、新しいプールメンバーを定義し、新しいトポロジを公開した後、Skype for Business Server 展開ウィザードを使用して新しいフロントエンドプールメンバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="4a6bf-112">また、プールの該当するロード バランサー (ドメイン ネーム システム (DNS) 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="4a6bf-113">多くの場合は、両方の負荷分散システムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="4a6bf-114">両方に新しいメンバー サーバーを追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a6bf-114">Be sure that you are adding the new member server to both.</span></span> 
  

