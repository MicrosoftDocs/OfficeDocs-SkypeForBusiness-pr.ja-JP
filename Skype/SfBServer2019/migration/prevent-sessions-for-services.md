---
title: サービスのセッションの禁止
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: コントロール パネルのバージョンのインストールを使用するには、特定のコンピューターで実行されているすべての従来のサービスの新しいセッションを防止する、または特定のレガシー サービスの新しいセッションを防止します。
ms.openlocfilehash: 9f3f9bb301841d7e71c18f4d3ca052f3d0c74dce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875533"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="80f5e-103">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="80f5e-103">Prevent sessions for services</span></span>

<span data-ttu-id="80f5e-104">コントロール パネルのバージョンのインストールを使用するには、特定のコンピューターで実行されているすべての従来のサービスの新しいセッションを防止する、または特定のレガシー サービスの新しいセッションを防止します。</span><span class="sxs-lookup"><span data-stu-id="80f5e-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="80f5e-105">コンピューター上のサービスの新しいセッションを防止するには</span><span class="sxs-lookup"><span data-stu-id="80f5e-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="80f5e-106">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2019。</span><span class="sxs-lookup"><span data-stu-id="80f5e-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="80f5e-107">Skype をビジネス コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="80f5e-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="80f5e-108">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="80f5e-109">[**状態**] ページで、並べ替えまたはとしてリストを検索は、新しいセッションを禁止し、クリックするサービスを実行しているコンピューターを検索するのには必要です。</span><span class="sxs-lookup"><span data-stu-id="80f5e-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="80f5e-110">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="80f5e-111">**すべてのサービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="80f5e-112">特定のサービスの新しいセッションを防止するには</span><span class="sxs-lookup"><span data-stu-id="80f5e-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="80f5e-113">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2019。</span><span class="sxs-lookup"><span data-stu-id="80f5e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="80f5e-114">Skype をビジネス コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="80f5e-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="80f5e-115">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="80f5e-116">**状態**] ページで、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="80f5e-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="80f5e-117">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="80f5e-118">必要に応じて、サービスの一覧を並べ替えるし、サービスの新しいセッションを禁止する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="80f5e-119">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="80f5e-120">**サービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="80f5e-121">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80f5e-121">Click **Close**.</span></span>
    

