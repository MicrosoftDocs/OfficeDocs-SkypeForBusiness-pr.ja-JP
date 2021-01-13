---
title: 組織の外部アクセス ポリシーの管理
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1 つ以上のエッジ サーバーを展開したら、組織でサポートする外部アクセスの種類を有効にする必要があります。
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817257"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="e3e62-103">組織の外部アクセス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="e3e62-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="e3e62-104">1 つ以上のエッジ サーバーを展開したら、組織でサポートする外部アクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e62-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="e3e62-p101">組織で外部ユーザー アクセス (リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど) のサポートを既に有効にしていても、既定では外部ユーザー アクセスをサポートするように構成されているポリシーはありません。外部ユーザー アクセスの使用を制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。ポリシーの作成および構成時に使用できるスコープを次に示します。既定では、グローバル ポリシーが作成されますが、このポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3e62-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="e3e62-109">**グローバル ポリシー**   グローバル ポリシーは、エッジ サーバーを展開するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="e3e62-110">既定では、グローバル ポリシーではどの外部ユーザー アクセス オプションも有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="e3e62-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="e3e62-111">グローバル レベルで外部ユーザー アクセスをサポートするには、1 つ以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e3e62-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="e3e62-112">グローバル ポリシーは組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="e3e62-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="e3e62-113">グローバル ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e3e62-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="e3e62-114">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="e3e62-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="e3e62-115">**サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに制限するために、1 つ以上のサイト ポリシーを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="e3e62-116">サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="e3e62-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="e3e62-117">たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。</span><span class="sxs-lookup"><span data-stu-id="e3e62-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="e3e62-118">既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="e3e62-119">**ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに制限するために、1 つ以上のユーザー ポリシーを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="e3e62-120">ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="e3e62-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="e3e62-121">たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。</span><span class="sxs-lookup"><span data-stu-id="e3e62-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="e3e62-122">ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3e62-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="e3e62-123">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定をオーバーライドすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3e62-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e3e62-124">Skype for Business Server ポリシーの優先順位: ユーザー ポリシー (最も高い) はサイト ポリシーをオーバーライドし、サイト ポリシーはグローバル ポリシーをオーバーライド (最も低い) します。</span><span class="sxs-lookup"><span data-stu-id="e3e62-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e3e62-125">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e3e62-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="e3e62-126">これらのオプションには、次の種類の外部アクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="e3e62-127">**フェデレーション ユーザーとの通信を有効にする**   フェデレーション パートナー ドメインへのユーザー アクセスをサポートする場合は、これを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="e3e62-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="e3e62-128">この設定では、ユーザーが他の SIP フェデレーション ドメイン、および Microsoft 365 や Office 365 などのホストされたプロバイダーと通信する機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="e3e62-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="e3e62-129">**リモート ユーザーとの通信を有効にする**   在宅勤務者や出張中のユーザーなど、ファイアウォールの外側に位置する組織内のユーザーがインターネット経由で Skype for Business Server に接続する場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3e62-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="e3e62-130">**パブリック ユーザーとの通信を有効にする**   内部ユーザーがパブリック IM プロバイダーの連絡先と通信できる場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3e62-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="e3e62-131">外部ユーザー アクセスのサポートを有効にするだけでなく、ユーザーが任意の種類の外部ユーザー アクセスを使用できるようにする前に、組織内での外部ユーザー アクセスの使用を制御するポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e62-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="e3e62-132">外部ユーザー アクセスのポリシーの作成、構成、適用の詳細については、[リモート ユーザー アクセスを有効または無効にする](../access-edge/enable-or-disable-remote-user-access.md)方法についての記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e62-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="e3e62-133">**Windows PowerShell コマンドレットを使用して外部アクセスポリシーを表示するには**</span><span class="sxs-lookup"><span data-stu-id="e3e62-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="e3e62-134">外部アクセス ポリシーは、Skype for Business Server 管理シェルと **Get-CsExternalAccessPolicy** コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="e3e62-135">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e3e62-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="e3e62-136">すべての外部アクセス ポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e3e62-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="e3e62-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e3e62-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
