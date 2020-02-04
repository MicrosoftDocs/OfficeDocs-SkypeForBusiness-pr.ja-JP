---
title: フロントエンド プールの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 作成するフロントエンドプールの完全修飾ドメイン名 (FQDN) を指定します。 プールの FQDN は、フロントエンドプールが含まれているトポロジを公開した後に変更することはできません。 プールの名前を変更する必要がある場合は、プールを削除し、新しい FQDN で新しいプールを追加する必要があります。
ms.openlocfilehash: e9e420956656d7bd0217f122844ea222f6bd2b40
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698232"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="283af-105">フロントエンド プールの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="283af-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="283af-106">作成するフロントエンドプールの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="283af-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="283af-107">プールの FQDN は、フロントエンドプールが含まれているトポロジを公開した後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="283af-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="283af-108">プールの名前を変更する必要がある場合は、プールを削除し、新しい FQDN で新しいプールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="283af-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="283af-109">今後、フロントエンドプールを実装する予定がある場合は、[**複数のコンピュータープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="283af-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="283af-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="283af-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="283af-111">後でプールにコンピューターを追加する準備ができたら、トポロジビルダーをもう一度実行して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しいフロントエンドプールメンバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="283af-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="283af-112">プール、ドメインネームシステム (DNS) 負荷分散、またはハードウェアロードバランサーの適切なロードバランサーに新しいプールメンバーを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="283af-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="283af-113">多くの場合、両方の負荷分散システムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="283af-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="283af-114">新しいメンバーサーバーを両方に追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="283af-114">Be sure that you are adding the new member server to both.</span></span> 
  

