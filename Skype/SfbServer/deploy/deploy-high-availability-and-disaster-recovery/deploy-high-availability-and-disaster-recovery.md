---
title: 高可用性および障害復旧の展開
ms.author: heidip
author: microsoftheidi
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server は、サーバー プーリングによる高可用性、プール ペアリングによる障害復旧、および複数のモードのバックエンド サーバーの高可用性を実現します。これには、AlwaysOn 可用性グループ、データベース ミラーリング、および SQL フェールオーバー クラスタリングが含まれます。
ms.openlocfilehash: 91324a4bbc0c6a2439a3190661320165670a6e11
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="1a516-103">高可用性および障害復旧の展開</span><span class="sxs-lookup"><span data-stu-id="1a516-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="1a516-104">Skype for Business Server は、サーバー プーリングによる高可用性、プール ペアリングによる障害復旧、および複数のモードのバックエンド サーバーの高可用性を実現します。これには、AlwaysOn 可用性グループ、データベース ミラーリング、および SQL フェールオーバー クラスタリングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a516-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availibility, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="1a516-105">高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。災害復旧とは、自然または人間による障害が発生した場合、可能な限り障害発生以前から多くのデータを保持し、保持するサービスです。</span><span class="sxs-lookup"><span data-stu-id="1a516-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="1a516-106">このセクションでは、これらの機能の展開方法について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="1a516-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="1a516-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a516-107">Related sections</span></span>

[<span data-ttu-id="1a516-108">ビジネス サーバー 2015 の Skype での高可用性と災害復旧の計画します。</span><span class="sxs-lookup"><span data-stu-id="1a516-108">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="1a516-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a516-109">See also</span></span>

#### 

[<span data-ttu-id="1a516-110">ビジネス サーバー 2015 の Skype でのバック エンド サーバー上の AlwaysOn 可用性グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="1a516-110">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="1a516-111">ビジネス サーバー 2015 に Skype での災害復旧のための一対のフロント エンド プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="1a516-111">Deploy paired Front End pools for disaster recovery in Skype for Business Server 2015</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="1a516-112">ビジネス サーバー 2015 の Skype のバック エンド サーバーの高可用性の SQL のミラーリングを導入します。</span><span class="sxs-lookup"><span data-stu-id="1a516-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
[<span data-ttu-id="1a516-113">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成します。</span><span class="sxs-lookup"><span data-stu-id="1a516-113">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

