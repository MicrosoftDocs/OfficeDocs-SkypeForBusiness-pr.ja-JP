---
title: アーカイブおよび監視サーバーの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 従来の環境でアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Skype for Business Server 2019 環境に展開できます。 ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752669"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="29697-104">アーカイブおよび監視サーバーの移行</span><span class="sxs-lookup"><span data-stu-id="29697-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="29697-105">従来の環境でアーカイブサーバーと監視サーバーを展開した場合は、フロントエンドプールを移行した後に、これらのサーバーを Skype for Business Server 2019 環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="29697-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="29697-106">ただし、アーカイブおよび監視機能が組織にとって重要な場合は、移行の前に Skype for Business Server 2019 パイロットプールにアーカイブと監視を追加して、移行プロセス中に機能を利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29697-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="29697-107">移行プロセスで、アーカイブ機能と監視機能が必要な場合は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="29697-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="29697-108">アーカイブデータと監視データは、Skype for Business Server 2019 展開には移動されません。</span><span class="sxs-lookup"><span data-stu-id="29697-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="29697-109">従来の環境を使用停止にする前にバックアップしたデータは、従来の環境でのアクティビティの履歴になります。</span><span class="sxs-lookup"><span data-stu-id="29697-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="29697-110">古いバージョンのアーカイブサーバーと監視サーバーは、従来のフロントエンドプールにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="29697-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="29697-111">Skype for Business Server 2019 では、アーカイブと監視はサーバーの役割ではなくなりますが、サービスが Skype for Business Server 2019 フロントエンドプールに統合されています。</span><span class="sxs-lookup"><span data-stu-id="29697-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="29697-112">従来の、または Skype for Business Server 2019 の展開が共存している間、従来のバージョンのアーカイブサーバーと監視サーバーは、従来のプールに所属するユーザーのためにデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="29697-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="29697-113">Skype for business server 2019 でのアーカイブと監視 Skype for business Server 2019 プールに所属するユーザーのためにデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="29697-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29697-114">移行のフェーズでは、新しい Skype for business Server 2019 パイロットプールで従来のエッジサーバーを使用していても、従来のバージョンのアーカイブサーバーは従来のプールに所属しているユーザーのデータ収集を続行し、skype for business server 2019 プールに所属するユーザーのために Skype for business Server 2019 のアーカイブデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="29697-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="29697-115">サードパーティ製のアーカイブおよび監視ソリューションを Skype for business Server 2019 のアーカイブおよび監視と組み合わせて使用する場合は、サードパーティ製ソリューションと Skype for Business Server 2019 を統合する時期と方法についてベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29697-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

