---
title: アーカイブおよび監視サーバーを移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: レガシ環境でのアーカイブ サーバーと監視サーバーを展開した場合、フロント エンド プールを移行した後、サーバー 2019 のビジネス環境について、Skype でこれらのサーバーを展開できます。 ただし、アーカイブおよび監視機能は、組織にとって重要な場合は、アーカイブ、および機能は、移行プロセス中に使用できるように、移行する前に、Skype をビジネス サーバー 2019 パイロット プールの監視を追加します。
ms.openlocfilehash: cd6e3bf7ef04ca7906b707a30211d0c22d22d837
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028755"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="85b24-104">アーカイブおよび監視サーバーを移行します。</span><span class="sxs-lookup"><span data-stu-id="85b24-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="85b24-105">レガシ環境でのアーカイブ サーバーと監視サーバーを展開した場合、フロント エンド プールを移行した後、サーバー 2019 のビジネス環境について、Skype でこれらのサーバーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="85b24-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="85b24-106">ただし、アーカイブおよび監視機能は、組織にとって重要な場合は、アーカイブ、および機能は、移行プロセス中に使用できるように、移行する前に、Skype をビジネス サーバー 2019 パイロット プールの監視を追加します。</span><span class="sxs-lookup"><span data-stu-id="85b24-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="85b24-107">移行プロセス中に、アーカイブおよび監視の機能をする場合は、次の考慮事項に留意してください。</span><span class="sxs-lookup"><span data-stu-id="85b24-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="85b24-108">データをアーカイブし、監視データに移動されない、Skype サーバー 2019 のビジネス展開をします。</span><span class="sxs-lookup"><span data-stu-id="85b24-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="85b24-109">従来の環境の使用を停止する前にバックアップしたデータを従来の環境でのアクティビティの履歴となります。</span><span class="sxs-lookup"><span data-stu-id="85b24-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="85b24-110">アーカイブ サーバーと監視サーバーの従来のバージョンは、レガシーのフロント エンド プールのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="85b24-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="85b24-111">ビジネス サーバー 2019 の Skype は、アーカイブと監視は不要になったサーバーの役割が、Skype のビジネス サーバー 2019 のフロント エンド プールに統合するサービスです。</span><span class="sxs-lookup"><span data-stu-id="85b24-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="85b24-112">時間中をレガシ サーバー 2019 のビジネス展開では、Skype の共存しは、従来のプールに所属していたユーザーの古いバージョンのアーカイブ サーバーと監視サーバーがデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="85b24-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="85b24-113">アーカイブおよび監視サーバー 2019 のビジネス用の Skype では、ユーザーのデータは、Skype ビジネス サーバー 2019 プールのホームを収集します。</span><span class="sxs-lookup"><span data-stu-id="85b24-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85b24-114">パイロット プール、アーカイブ サーバーの従来のバージョンがユーザーのデータを収集するために引き続き、ビジネス サーバー 2019 の新しい Skype で、従来のエッジ サーバーが置かれている従来のプールを使用して、ビジネスの Skype でのアーカイブもできたら、移行のフェーズでは、2019 のサーバーは、ユーザーのデータは、Skype ビジネス サーバー 2019 プールのホームを収集します。</span><span class="sxs-lookup"><span data-stu-id="85b24-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="85b24-115">サード パーティのアーカイブとアーカイブや Skype での監視と連携してソリューションをビジネス サーバー 2019 の監視を使用する場合は、Skype ビジネス サーバー 2019 のサード ・ パーティ製ソリューションと統合する必要がある時期と方法について、製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="85b24-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

