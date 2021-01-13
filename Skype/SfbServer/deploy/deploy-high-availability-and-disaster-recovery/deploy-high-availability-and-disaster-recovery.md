---
title: 高可用性および障害回復の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830617"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="0ffd7-103">高可用性および障害回復の展開</span><span class="sxs-lookup"><span data-stu-id="0ffd7-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="0ffd7-104">Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ffd7-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="0ffd7-105">高可用性とは、1 つ以上のサーバーがダウンした場合でも、Skype for Business Server サービスを確実に利用できる状態を指します。障害復旧とは、自然または人が引き起こした障害が発生した場合にサービスを維持し、災害前からのデータをできる限り多く保持することです。</span><span class="sxs-lookup"><span data-stu-id="0ffd7-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="0ffd7-106">このセクションでは、これらの機能を展開する方法について説明します。また、他のサーバーの役割の一部に対して、高可用性と障害復旧のために実行できる手順も説明します。</span><span class="sxs-lookup"><span data-stu-id="0ffd7-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="0ffd7-107">SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0ffd7-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0ffd7-108">Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="0ffd7-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="0ffd7-109">関連情報</span><span class="sxs-lookup"><span data-stu-id="0ffd7-109">Related sections</span></span>

[<span data-ttu-id="0ffd7-110">Skype for Business Server で高可用性と障害復旧を計画する</span><span class="sxs-lookup"><span data-stu-id="0ffd7-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="0ffd7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ffd7-111">See also</span></span>

[<span data-ttu-id="0ffd7-112">Skype for Business Server のバック エンド サーバーに AlwaysOn 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="0ffd7-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="0ffd7-113">Skype for Business Server で障害復旧用のペアのフロント エンド プールを展開する</span><span class="sxs-lookup"><span data-stu-id="0ffd7-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="0ffd7-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ffd7-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
