---
title: 高可用性および障害復旧の展開
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: bbd3c4092962e757a7565f1da054c82438a79ded
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225498"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="d7f76-103">高可用性および障害復旧の展開</span><span class="sxs-lookup"><span data-stu-id="d7f76-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="d7f76-104">Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7f76-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="d7f76-105">高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。災害復旧とは、自然または人間による障害が発生した場合、可能な限り障害発生以前から多くのデータを保持し、保持するサービスです。</span><span class="sxs-lookup"><span data-stu-id="d7f76-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="d7f76-106">このセクションでは、これらの機能の展開方法について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="d7f76-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="d7f76-107">SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d7f76-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d7f76-108">AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。</span><span class="sxs-lookup"><span data-stu-id="d7f76-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="d7f76-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f76-109">Related sections</span></span>

[<span data-ttu-id="d7f76-110">ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。</span><span class="sxs-lookup"><span data-stu-id="d7f76-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="d7f76-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7f76-111">See also</span></span>

[<span data-ttu-id="d7f76-112">ビジネス サーバーの Skype でのバック エンド サーバー上の AlwaysOn 可用性グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="d7f76-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="d7f76-113">ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="d7f76-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="d7f76-114">Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="d7f76-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
