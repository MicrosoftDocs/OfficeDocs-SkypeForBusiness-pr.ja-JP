---
title: サービスのセッションの禁止
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
description: 従来のインストールのコントロールパネルを使用すると、特定のコンピューターで実行されているすべてのレガシサービスの新しいセッションを禁止したり、特定のレガシサービスの新しいセッションを禁止したりすることができます。
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752289"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="20445-103">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="20445-103">Prevent sessions for services</span></span>

<span data-ttu-id="20445-104">従来のインストールのコントロールパネルを使用すると、特定のコンピューターで実行されているすべてのレガシサービスの新しいセッションを禁止したり、特定のレガシサービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="20445-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="20445-105">コンピューター上のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="20445-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="20445-106">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザーアカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Skype for Business Server 2019 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="20445-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="20445-107">Skype for Business のコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="20445-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="20445-108">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="20445-109">[**状態**] ページで、必要に応じてリストを並べ替えまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを見つけてクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="20445-110">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="20445-111">[**すべてのサービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="20445-112">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="20445-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="20445-113">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザーアカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントから、Skype for Business Server 2019 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="20445-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="20445-114">Skype for Business のコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="20445-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="20445-115">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="20445-116">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="20445-117">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="20445-118">必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="20445-119">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="20445-120">[**サービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="20445-121">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20445-121">Click **Close**.</span></span>
    

