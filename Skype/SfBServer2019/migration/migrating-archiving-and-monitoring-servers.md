---
title: アーカイブと監視サーバーの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来の環境でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能が利用できるようにする必要があります。
ms.openlocfilehash: f259a08d25c93467c79fdaf3550288c6208607c3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237892"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ea036-104">アーカイブと監視サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="ea036-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="ea036-105">従来の環境でアーカイブサーバーと監視サーバーを展開した場合、フロントエンドプールを移行した後で、これらのサーバーを Skype for Business Server 2019 環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="ea036-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ea036-106">ただし、アーカイブと監視の機能が組織にとって重要である場合は、移行前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能が利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea036-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="ea036-107">移行プロセス中にアーカイブと監視機能が必要な場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea036-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="ea036-108">データのアーカイブと監視は、Skype for Business Server 2019 の展開には移行されません。</span><span class="sxs-lookup"><span data-stu-id="ea036-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="ea036-109">従来の環境を廃止する前にバックアップしたデータは、従来の環境でのアクティビティの履歴となります。</span><span class="sxs-lookup"><span data-stu-id="ea036-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="ea036-110">古いバージョンのアーカイブサーバーと監視サーバーは、従来のフロントエンドプールにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ea036-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="ea036-111">Skype for Business Server 2019 では、アーカイブと監視はサーバーの役割ではなくなりましたが、Skype for Business Server 2019 フロントエンドプールに統合されたサービスです。</span><span class="sxs-lookup"><span data-stu-id="ea036-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="ea036-112">従来の、Skype for Business Server 2019 の展開が共存する間、古いバージョンのアーカイブサーバーと監視サーバーは、従来のプールに所属しているユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="ea036-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="ea036-113">Skype for Business Server 2019 でのアーカイブと監視 Skype for Business Server 2019 プールを使用しているユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="ea036-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea036-114">新しい Skype for Business Server 2019 パイロットプールで従来のエッジサーバーを使用している場合、移行のフェーズ中に、古いバージョンのアーカイブサーバーでは、従来のプールに所属していて、Skype for Business でアーカイブされているユーザーのデータを収集し続けることができます。サーバー2019は、Skype for Business Server 2019 プールに所属しているユーザーのためにデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="ea036-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="ea036-115">Skype for Business Server 2019 でのアーカイブと監視に関連して、サードパーティのアーカイブと監視ソリューションを使用している場合は、サードパーティのソリューションを Skype for Business Server 2019 と統合する時期とその方法について、ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ea036-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

