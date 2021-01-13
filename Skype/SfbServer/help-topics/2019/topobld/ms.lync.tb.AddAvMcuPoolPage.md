---
title: A/V MCU プールの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。
ms.openlocfilehash: f0bfa6155320a23467545be19de290a3f1df19dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812027"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="50d57-104">A/V MCU プールの追加</span><span class="sxs-lookup"><span data-stu-id="50d57-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="50d57-p102">併置された音声ビデオ会議サービスのないセントラル サイトのすべての Enterprise Edition フロント エンド サーバーは、同じスタンドアロン音声ビデオ会議プールを使用できます。音声ビデオ会議プールごとに、プールの完全修飾ドメイン名 (FQDN) と、音声ビデオ会議サーバーが 1 つだけなのか、または負荷分散された複数の音声ビデオ会議サーバーが存在するのかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d57-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="50d57-p103">単一サーバー プールを複数サーバー プールに変換することはできません。その後、組織で複数サーバー プールが必要となった場合には、単一サーバー プールを削除してから複数サーバー プールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d57-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="50d57-109">将来的に音声ビデオ会議プールを実装する予定の場合は、[**複数コンピューターのプール**] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="50d57-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="50d57-110">プールを負荷分散された 2 つ以上のコンピューターとして定義する場合でも、単一コンピューターのプールを作成し、その単一コンピューターにプールの FQDN を作成できます。</span><span class="sxs-lookup"><span data-stu-id="50d57-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="50d57-111">後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーを再度使用して新しいプール メンバーを定義し、新しいトポロジを公開し、Skype for Business Server 展開ウィザードを使用して新しい音声ビデオ会議プール のメンバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50d57-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="50d57-112">音声ビデオ会議サーバー プールは、プールの作成にロード バランサーを必要としない特殊なプールです。</span><span class="sxs-lookup"><span data-stu-id="50d57-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="50d57-113">音声ビデオ会議プールでは負荷分散が内部的に行われるので、追加ハードウェアは不要です。</span><span class="sxs-lookup"><span data-stu-id="50d57-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

