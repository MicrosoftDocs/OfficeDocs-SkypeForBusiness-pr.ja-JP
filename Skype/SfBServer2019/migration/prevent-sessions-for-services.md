---
title: サービスのセッションの禁止
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来の [コントロールパネル] を使って、特定のコンピューターで実行されているすべてのレガシサービスの新しいセッションを禁止したり、特定のレガシサービスの新しいセッションを禁止したりすることができます。
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244366"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="47d5d-103">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="47d5d-103">Prevent sessions for services</span></span>

<span data-ttu-id="47d5d-104">従来の [コントロールパネル] を使って、特定のコンピューターで実行されているすべてのレガシサービスの新しいセッションを禁止したり、特定のレガシサービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="47d5d-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="47d5d-105">コンピューター上のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="47d5d-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="47d5d-106">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。2019。</span><span class="sxs-lookup"><span data-stu-id="47d5d-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="47d5d-107">Skype for Business コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="47d5d-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="47d5d-108">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="47d5d-109">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="47d5d-110">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="47d5d-111">[**すべてのサービスに対して新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="47d5d-112">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="47d5d-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="47d5d-113">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。2019。</span><span class="sxs-lookup"><span data-stu-id="47d5d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="47d5d-114">Skype for Business コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="47d5d-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="47d5d-115">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="47d5d-116">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="47d5d-117">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="47d5d-118">必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="47d5d-119">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="47d5d-120">[**サービスの新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="47d5d-121">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47d5d-121">Click **Close**.</span></span>
    

