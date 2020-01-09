---
title: 組織の外部アクセス ポリシーの管理
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 1つ以上のエッジサーバーを展開した後は、組織でサポートされる外部アクセスの種類を有効にする必要があります。
ms.openlocfilehash: f1f9798907f70893601a5dfe05b5045e484911e0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991752"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="62902-103">組織の外部アクセス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="62902-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="62902-104">1つ以上のエッジサーバーを展開した後は、組織でサポートされる外部アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62902-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="62902-105">既定では、組織の外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするように構成されたポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="62902-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="62902-106">外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62902-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="62902-107">作成と構成では、次のポリシースコープを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62902-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="62902-108">既定では、グローバルポリシーは作成されますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="62902-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="62902-109">**グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="62902-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="62902-110">既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="62902-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="62902-111">グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="62902-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="62902-112">グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="62902-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="62902-113">グローバルポリシーを削除しても、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="62902-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="62902-114">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="62902-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="62902-115">**サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="62902-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="62902-116">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="62902-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="62902-117">たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="62902-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="62902-118">既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="62902-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="62902-119">**ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="62902-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="62902-120">ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="62902-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="62902-121">たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="62902-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="62902-122">ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62902-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="62902-123">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="62902-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="62902-124">Skype for Business Server のポリシーの優先順位: ユーザーポリシー (ほとんどの影響) でサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。</span><span class="sxs-lookup"><span data-stu-id="62902-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="62902-125">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="62902-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="62902-126">これらのオプションには、次のような外部アクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="62902-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="62902-127">**フェデレーションされたユーザー**   との通信を有効にするフェデレーションパートナードメインへのユーザーアクセスをサポートする場合は、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62902-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="62902-128">この設定では、ユーザーが他の SIP フェデレーションドメインと、Microsoft Office 365 などのホストされるプロバイダーと通信する機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="62902-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="62902-129">**[リモートユーザー**   との通信を有効にする] 出張中の在宅勤務者やユーザーなど、組織内のユーザーがインターネット経由で Skype for business Server に接続できるようにする場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62902-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="62902-130">**[パブリックユーザー**   との通信を有効にする] 内部ユーザーがパブリック IM プロバイダーの連絡先と通信できるようにする場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62902-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="62902-131">外部ユーザーアクセスのサポートを有効にするだけでなく、ユーザーが外部ユーザーアクセスを利用できるようにする前に、組織で外部ユーザーアクセスの使用を制御するためのポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62902-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="62902-132">外部ユーザーアクセスのポリシーの作成、構成、および適用の詳細については、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62902-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="62902-133">**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**</span><span class="sxs-lookup"><span data-stu-id="62902-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="62902-134">外部アクセスポリシーは、Skype for Business Server 管理シェルと**CsExternalAccessPolicy**コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="62902-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="62902-135">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="62902-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="62902-136">すべての外部アクセスポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="62902-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="62902-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="62902-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
