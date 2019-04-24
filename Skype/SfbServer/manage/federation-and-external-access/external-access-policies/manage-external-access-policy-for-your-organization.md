---
title: 組織の外部アクセス ポリシーの管理
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 1 つまたは複数のエッジ サーバーを展開するには後、は、組織でサポートされる外部からのアクセスの種類を有効にする必要があります。
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199885"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="c365f-103">組織の外部アクセス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="c365f-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="c365f-104">1 つまたは複数のエッジ サーバーを展開するには後、は、組織でサポートされる外部からのアクセスの種類を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c365f-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="c365f-105">既定では、場合でも、組織の外部ユーザー アクセスのサポートを有効にしたが既にリモート ユーザー アクセス、フェデレーション ユーザーのアクセスを含む、外部ユーザー アクセスをサポートするために構成されているポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="c365f-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="c365f-106">外部ユーザー アクセスの使用を制御するためには各ポリシーに対してサポートされている外部ユーザー アクセスの種類を指定する 1 つまたは複数のポリシーを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c365f-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="c365f-107">作成と構成の範囲は、次のポリシーを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c365f-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="c365f-108">既定では、グローバル ポリシーは作成しますが、削除できません。</span><span class="sxs-lookup"><span data-stu-id="c365f-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="c365f-109">**グローバル ポリシー**   、エッジ サーバーを展開するときに、グローバル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c365f-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="c365f-110">既定では、外部ユーザー アクセスのオプションが許可されていないグローバル ポリシーにします。</span><span class="sxs-lookup"><span data-stu-id="c365f-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="c365f-111">グローバル レベルでの外部ユーザー アクセスをサポートするには、外部ユーザー アクセス オプションの 1 つまたは複数の種類をサポートするグローバル ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c365f-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="c365f-112">グローバル ポリシーは、組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーは、グローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c365f-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="c365f-113">グローバル ポリシーを削除する場合、削除しません。</span><span class="sxs-lookup"><span data-stu-id="c365f-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="c365f-114">代わりに、既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="c365f-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="c365f-115">**サイト ポリシー**   を制限するための複数のサイト ポリシーを特定のサイトへの外部ユーザー アクセスのサポート、または作成し、いずれかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c365f-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="c365f-116">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="c365f-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="c365f-117">などのグローバル ポリシーでリモート ユーザー アクセスを有効にした場合は、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c365f-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="c365f-118">既定では、サイト ポリシーは、そのサイトのすべてのユーザーに適用されるが、ユーザーがサイトのポリシー設定を無効にするユーザー ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c365f-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="c365f-119">**ユーザー ポリシー**   を制限するための複数のユーザー ポリシーを特定のユーザーへのリモート ユーザー アクセスのサポート、または作成し、いずれかを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c365f-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="c365f-120">ユーザー ポリシーが割り当てられる特定のユーザーに対してのみが、ユーザー ポリシーの上書き、グローバルおよびサイト ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c365f-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="c365f-121">たとえば、グローバル ポリシーおよびサイト ポリシーでリモート ユーザー アクセスを有効にした場合はリモート ユーザー アクセスを無効にするユーザー ポリシーを指定し、し、そのポリシーを割り当てるユーザーを特定のユーザー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c365f-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="c365f-122">ユーザー ポリシーを作成する場合する必要がありますに適用する 1 つまたは複数のユーザーに有効にするにします。</span><span class="sxs-lookup"><span data-stu-id="c365f-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="c365f-123">あるポリシー レベルで適用されているポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c365f-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c365f-124">ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="c365f-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c365f-125">つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c365f-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="c365f-126">これらのオプションには、次の種類の外部からのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="c365f-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="c365f-127">**フェデレーション ユーザーとの通信を有効にする**   、フェデレーション パートナーのドメインへのユーザー アクセスをサポートする場合にこれを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c365f-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="c365f-128">この設定は、ユーザーが SIP フェデレーションの Microsoft Office 365 のようなホスト プロバイダーと同様に、ドメイン間で通信する機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="c365f-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="c365f-129">**リモート ユーザーとの通信を有効にする**   在宅勤務者、出張中には、Business Server のインターネット経由での Skype に接続できるようにするユーザーなど、ファイアウォールの外側には、組織内のユーザーの場合、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c365f-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="c365f-130">**パブリック ユーザーとの通信を有効にする**   内部のユーザーがパブリック IM プロバイダーの連絡先と通信できるようにする場合にこのオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c365f-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="c365f-131">サポートして外部ユーザー アクセスを有効にするだけでなく、任意の種類の外部ユーザー アクセスのユーザーが利用できる前に、組織内の外部ユーザー アクセスの使用を制御するポリシーを構成することもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c365f-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="c365f-132">作成、構成、および外部ユーザー アクセスのポリシーの適用の詳細については、[有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c365f-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="c365f-133">**Windows PowerShell コマンドレットを使用して、外部アクセス ポリシーを表示するのには**</span><span class="sxs-lookup"><span data-stu-id="c365f-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="c365f-134">Skype ビジネス サーバー管理シェルと**Get CsExternalAccessPolicy**コマンドレットを使用して、外部アクセス ポリシーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c365f-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="c365f-135">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c365f-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="c365f-136">すべての外部アクセス ポリシーに関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c365f-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="c365f-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c365f-137">This command returns information similar to the following:</span></span>
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
