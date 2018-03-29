---
title: Skype for Business Server 2015 での高可用性および障害復旧の計画
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="1ad25-103">Skype for Business Server 2015 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="1ad25-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1ad25-104">Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="1ad25-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="1ad25-105">高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。</span><span class="sxs-lookup"><span data-stu-id="1ad25-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="1ad25-106">障害復旧とは、自然災害または人災が発生した場合であってもサービスの稼働を維持し、災害前からのデータを可能な限り多く維持することです。</span><span class="sxs-lookup"><span data-stu-id="1ad25-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="1ad25-107">Lync Server の以前のバージョンのように Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性機能はプールを使用してサーバーの冗長性</span><span class="sxs-lookup"><span data-stu-id="1ad25-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="1ad25-108">特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="1ad25-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="1ad25-109">同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。</span><span class="sxs-lookup"><span data-stu-id="1ad25-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="1ad25-110">ビジネス サーバーの Skype は、リカバリ ・ オプションのフロント エンド プールの障害も提供します。</span><span class="sxs-lookup"><span data-stu-id="1ad25-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="1ad25-111">互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="1ad25-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="1ad25-112">これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。</span><span class="sxs-lookup"><span data-stu-id="1ad25-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="1ad25-113">Skype ビジネス サーバーのでは、バック エンド サーバーの高可用性の 4 つのモードもがサポートされています: データベース ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL のフェールオーバー クラスタ リングします。</span><span class="sxs-lookup"><span data-stu-id="1ad25-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ad25-114">AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1ad25-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="1ad25-115">このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="1ad25-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1ad25-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ad25-116">See also</span></span>

#### 

[<span data-ttu-id="1ad25-117">フロント エンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="1ad25-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="1ad25-118">ビジネス サーバー 2015 の前面の Skype で最後のプール災害復旧</span><span class="sxs-lookup"><span data-stu-id="1ad25-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="1ad25-119">ビジネス サーバー 2015 の Skype でのプールの障害発生時にユーザーの操作性</span><span class="sxs-lookup"><span data-stu-id="1ad25-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="1ad25-120">ビジネス サーバー 2015 の Skype でのバック エンド サーバー高可用性</span><span class="sxs-lookup"><span data-stu-id="1ad25-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="1ad25-121">ビジネス サーバー 2015 の Skype での高可用性の共有ファイル</span><span class="sxs-lookup"><span data-stu-id="1ad25-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

