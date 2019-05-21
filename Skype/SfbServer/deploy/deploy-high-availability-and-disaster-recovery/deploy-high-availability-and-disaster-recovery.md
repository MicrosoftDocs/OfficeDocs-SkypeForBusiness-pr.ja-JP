---
title: 高可用性および障害復旧の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。
ms.openlocfilehash: 7997f71fb1f45801436caa50c4d6b258cc1b843b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306679"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="69a3f-103">高可用性および障害復旧の展開</span><span class="sxs-lookup"><span data-stu-id="69a3f-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="69a3f-104">Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="69a3f-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="69a3f-105">高可用性とは、1つまたは複数のサーバーが停止した場合でも、Skype for Business Server サービスが利用可能であることを確認することを意味します。災害復旧とは、自然災害または人的災害の発生時にサービスを継続させ、できるだけ多くのデータを可能な限り維持することを意味します。</span><span class="sxs-lookup"><span data-stu-id="69a3f-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="69a3f-106">このセクションでは、これらの機能の展開方法について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="69a3f-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="69a3f-107">SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="69a3f-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="69a3f-108">AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。</span><span class="sxs-lookup"><span data-stu-id="69a3f-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="69a3f-109">関連セクション</span><span class="sxs-lookup"><span data-stu-id="69a3f-109">Related sections</span></span>

[<span data-ttu-id="69a3f-110">Skype for Business Server で高可用性と障害回復を計画する</span><span class="sxs-lookup"><span data-stu-id="69a3f-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="69a3f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="69a3f-111">See also</span></span>

[<span data-ttu-id="69a3f-112">Skype for Business Server のバックエンドサーバーに AlwaysOn 可用性グループを展開する</span><span class="sxs-lookup"><span data-stu-id="69a3f-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="69a3f-113">Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開</span><span class="sxs-lookup"><span data-stu-id="69a3f-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="69a3f-114">Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="69a3f-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
