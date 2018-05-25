---
title: 追加の A/V MCU のプール
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: すべてエンタープライズ エディション フロント エンド サーバーのセントラル サイトに配置されている必要はありませんが A V 会議サービスの使用同じスタンドアロン A/V 会議のプールです。 各 A の V 会議のプール、プールおよび A は 1 つだけ必要があるかどうかの完全修飾ドメイン名 (FQDN) を指定する必要があります V 会議サーバーまたは複数の負荷分散/A/V 会議サーバーです。
ms.openlocfilehash: d1712829030836446c06a2e335c424d51a19e466
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="e8d0b-104">追加の A/V MCU のプール</span><span class="sxs-lookup"><span data-stu-id="e8d0b-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="e8d0b-105">すべてエンタープライズ エディション フロント エンド サーバーのセントラル サイトに配置されている必要はありませんが A V 会議サービスの使用同じスタンドアロン A/V 会議のプールです。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="e8d0b-106">各 A の V 会議のプール、プールおよび A は 1 つだけ必要があるかどうかの完全修飾ドメイン名 (FQDN) を指定する必要があります V 会議サーバーまたは複数の負荷分散/A/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8d0b-107">単一サーバー プールは、複数サーバーのプールに変換できません。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="e8d0b-108">後で、組織が複数のサーバー プールを必要がある場合、1 台のサーバー プールを削除し、複数のサーバー プールを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="e8d0b-109">A の実装を計画する場合は、/V 会議のプールは、今後、**複数コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="e8d0b-110">プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="e8d0b-111">トポロジ ビルダーは、新しいプールのメンバーを定義し、新しいトポロジを公開し、新しい A をセットアップしをもう一度行う必要がありますより多くのコンピューターを後でプールに追加する準備ができたら、V 会議ビジネス サーバーの展開ウィザードの Skype を通じてメンバーをプールするとします。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="e8d0b-112">A/V 会議サーバー プール一意する必要がありますを読み込まないようにプールを作成することにします。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="e8d0b-113">A/V 会議プール内部での負荷を分散し、ハードウェアを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e8d0b-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

