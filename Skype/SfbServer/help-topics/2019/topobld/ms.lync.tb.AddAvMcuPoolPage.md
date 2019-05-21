---
title: 音声ビデオ MCU プールの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 一元管理されていない A/V 会議サービスがない中央サイトのすべての Enterprise Edition のフロントエンドサーバーは、同じスタンドアロンの A/V 会議プールを使用できます。 各 A/V の会議プールについては、プールに完全修飾ドメイン名 (FQDN) を指定する必要があります。また、1つの A/V 会議サーバーのみを使用するか、または複数の負荷分散された A/V 会議サーバーのみを使用するかを指定する必要があります。
ms.openlocfilehash: dfd1fd056e015ed4d6ed1344384efa485e65f318
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304057"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="d6f5d-104">音声ビデオ MCU プールの追加</span><span class="sxs-lookup"><span data-stu-id="d6f5d-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="d6f5d-105">一元管理されていない A/V 会議サービスがない中央サイトのすべての Enterprise Edition のフロントエンドサーバーは、同じスタンドアロンの A/V 会議プールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="d6f5d-106">各 A/V の会議プールについては、プールに完全修飾ドメイン名 (FQDN) を指定する必要があります。また、1つの A/V 会議サーバーのみを使用するか、または複数の負荷分散された A/V 会議サーバーのみを使用するかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6f5d-107">単一サーバープールを複数サーバープールに変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="d6f5d-108">組織に複数のサーバープールが必要であると判断された場合は、単一サーバープールを削除してから、複数サーバープールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d6f5d-109">今後、A/V 会議プールを実装する予定がある場合は、[**複数のコンピュータープール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="d6f5d-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="d6f5d-111">後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを使用して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しい A/V 会議プールメンバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d6f5d-112">A/V 会議サーバープールは、プールを作成するためにロードバランサーが不要であるという点で固有です。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="d6f5d-113">A/V 会議プールでは、内部での負荷分散が行われ、追加のハードウェアは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d6f5d-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

