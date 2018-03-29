---
title: Skype でビジネス サーバーは、フォレストの準備によって加えられた変更
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順で作成されたユニバーサル サービスと管理グループについて説明します。
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="7a7db-103">Skype でビジネス サーバーは、フォレストの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="7a7db-103">Changes made by forest preparation in Skype for Business Server</span></span>
 
<span data-ttu-id="7a7db-104">このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順で作成されたユニバーサル サービスと管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>
  
## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="7a7db-105">Active Directory のグローバル設定とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="7a7db-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="7a7db-106">場合 (同様にビジネスのサーバーの展開のすべての新しい Skype の)、構成コンテナーにグローバル設定を保存すると、フォレストの準備が既存のサービス コンテナーを使用し、Configuration\Services の下にある**RTC サービス**オブジェクトを追加オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7a7db-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="7a7db-107">RTC サービス オブジェクトの下は、フォレストの準備は、型 msRTCSIP ・ GlobalContainer の**グローバル設定**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="7a7db-108">グローバル設定オブジェクトは、ビジネスのサーバーの展開の Skype に適用されるすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="7a7db-109">システム コンテナーにグローバル設定を保存する場合、フォレストの準備は、ルート ドメイン システム コンテナーの下の Microsoft コンテナーと System\Microsoft オブジェクトの下にある RTC サービス オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>
  
<span data-ttu-id="7a7db-110">フォレストの準備は、プロシージャが実行されるルート ドメインの新しい**ドメインを msRTCSIP**オブジェクトにも追加されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>
  
## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="7a7db-111">Active Directory ユニバーサル サービスと管理グループ</span><span class="sxs-lookup"><span data-stu-id="7a7db-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="7a7db-112">フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (Ace) を追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="7a7db-113">この手順では、指定したドメインのユーザー コンテナーにユニバーサル グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span> 
  
<span data-ttu-id="7a7db-114">ユニバーサル グループには、アクセスし、グローバル設定とサービスを管理する管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="7a7db-115">フォレストの準備は、次の種類のユニバーサル グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-115">Forest preparation adds the following types of universal groups:</span></span>
  
- <span data-ttu-id="7a7db-116">**管理グループ**これらのグループは、ビジネス サーバー ネットワークでの Skype の管理者の役割を定義します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>
    
- <span data-ttu-id="7a7db-117">**インフラストラクチャ ・ グループ**これらのグループは、ビジネスのサーバー インフラストラクチャの Skype の特定の領域にアクセスするアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="7a7db-118">管理グループの構成要素として機能します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-118">They function as components of administrative groups.</span></span> <span data-ttu-id="7a7db-119">これらのグループを変更しなかったり、それらに直接ユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a7db-119">You should not modify these groups or add users directly to them.</span></span>
    
- <span data-ttu-id="7a7db-120">**サービス グループ**これらのグループは、ビジネス サービスのさまざまな Skype にアクセスするために必要なサービス アカウントです。</span><span class="sxs-lookup"><span data-stu-id="7a7db-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>
    
<span data-ttu-id="7a7db-121">次の表では、管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-121">The following table describes the administrative groups.</span></span>
  
<span data-ttu-id="7a7db-122">**フォレストの準備時に作成された管理グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="7a7db-123">**管理グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-123">**Administrative group**</span></span>|<span data-ttu-id="7a7db-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a7db-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a7db-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a7db-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="7a7db-126">サーバーとすべてのサーバー ロールを含む、プールの設定、グローバル設定、およびユーザーを管理するためにメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="7a7db-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7a7db-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="7a7db-128">ユーザー設定を管理し、1 つのサーバーまたはプールからユーザーを移動するメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="7a7db-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="7a7db-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="7a7db-130">メンバー サーバー、プール、およびユーザーの設定を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |
   
<span data-ttu-id="7a7db-131">次の表では、インフラストラクチャ グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-131">The following table describes the infrastructure groups.</span></span>
  
<span data-ttu-id="7a7db-132">**フォレストの準備時に作成されるインフラストラクチャ グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="7a7db-133">**インフラストラクチャ グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-133">**Infrastructure group**</span></span>|<span data-ttu-id="7a7db-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a7db-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a7db-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="7a7db-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="7a7db-136">Skype のビジネスのサーバーのグローバル設定オブジェクトに対する書き込みアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="7a7db-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7a7db-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="7a7db-138">Skype のビジネスのサーバーのグローバル設定オブジェクトへの読み取り専用アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="7a7db-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7a7db-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="7a7db-140">Skype をビジネスのサーバーのユーザー設定の読み取り専用アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="7a7db-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="7a7db-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="7a7db-142">Skype をビジネスのサーバー設定の読み取り専用アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="7a7db-143">このグループには、プール レベルの設定、個々 のサーバーに固有の設定にのみへのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="7a7db-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="7a7db-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="7a7db-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="7a7db-145">Skype をビジネスのサーバー構成の読み取り専用アクセスを付与し、インストール時に、リカバリ性に優れたブランチ アプライアンスのローカル管理者グループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |
   
<span data-ttu-id="7a7db-146">次の表では、サービス グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-146">The following table describes the service groups.</span></span>
  
<span data-ttu-id="7a7db-147">**フォレストの準備時に作成されるサービス グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="7a7db-148">**サービス グループ**</span><span class="sxs-lookup"><span data-stu-id="7a7db-148">**Service group**</span></span>|<span data-ttu-id="7a7db-149">**説明**</span><span class="sxs-lookup"><span data-stu-id="7a7db-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a7db-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7a7db-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="7a7db-151">フロント エンド サーバーと Standard Edition サーバーの実行に使用されるサービス アカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a7db-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="7a7db-152">このグループでは、ビジネスのサーバーのグローバル設定および Active Directory ユーザー オブジェクトの Skype にサーバーの読み取り/書き込みアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="7a7db-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7a7db-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="7a7db-154">A を実行するために使用するサービス アカウントが含まれています/V 会議サーバー、Web サービス、仲介サーバー、アーカイブ サーバー、およびサーバーを監視します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="7a7db-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7a7db-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="7a7db-156">Skype をビジネス サーバーのエッジ サーバーの実行に使用されるサービス アカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a7db-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="7a7db-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="7a7db-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="7a7db-158">ビジネス サーバーの中央管理ストアのレプリケーションの Skype にはサポートしているサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="7a7db-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="7a7db-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="7a7db-160">Skype をビジネスのサーバー設定の場合は、読み取り専用アクセスを付与しますが、リカバリ性に優れたブランチ サーバーとブランチのリカバリ性に優れた機器の配置のインストールの構成では。</span><span class="sxs-lookup"><span data-stu-id="7a7db-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |
   
<span data-ttu-id="7a7db-161">フォレストの準備をしは、次のように、適切なインフラストラクチャ グループにサービスと管理グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>
  
- <span data-ttu-id="7a7db-162">RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
- <span data-ttu-id="7a7db-163">RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
- <span data-ttu-id="7a7db-164">RTCHSUniversalServices、RTCComponentUniversalServices および RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
<span data-ttu-id="7a7db-165">フォレストの準備には、次の役割に基づくアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>
  
- <span data-ttu-id="7a7db-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-166">CSAdministrator</span></span>
    
- <span data-ttu-id="7a7db-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-167">CSArchivingAdministrator</span></span>
    
- <span data-ttu-id="7a7db-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="7a7db-168">CSHelpDesk</span></span>
    
- <span data-ttu-id="7a7db-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-169">CSLocationAdministrator</span></span>
    
- <span data-ttu-id="7a7db-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-170">CSResponseGroupAdministrator</span></span>
    
- <span data-ttu-id="7a7db-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-171">CSServerAdministrator</span></span>
    
- <span data-ttu-id="7a7db-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-172">CSUserAdministrator</span></span>
    
- <span data-ttu-id="7a7db-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-173">CSViewOnlyAdministrator</span></span>
    
- <span data-ttu-id="7a7db-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a7db-174">CSVoiceAdministrator</span></span>
    
- <span data-ttu-id="7a7db-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="7a7db-175">CsPersistentChatAdministator</span></span>
    
- <span data-ttu-id="7a7db-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="7a7db-176">CsResponseGroupManager</span></span>
    
<span data-ttu-id="7a7db-177">RBAC の役割と、それぞれのタスクについての詳細は、計画のドキュメントで[の役割ベースのアクセス制御](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a7db-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="7a7db-178">フォレストの準備では、プライベートとパブリックの両方の Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="7a7db-179">Skype によってビジネスのサーバーが使用するグローバル設定コンテナーに秘密の Ace が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="7a7db-180">このコンテナーでは、ビジネスのサーバーの Skype によってのみ使用され、構成コンテナーまたはグローバル設定を保存する場所によって、ルート ドメインのシステム コンテナーであります。</span><span class="sxs-lookup"><span data-stu-id="7a7db-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="7a7db-181">フォレストの準備によって作成されたパブリック Ace は、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a7db-181">The public ACEs created by forest preparation are listed in the following table.</span></span>
  
<span data-ttu-id="7a7db-182">**フォレストの準備によって作成するパブリック Ace**</span><span class="sxs-lookup"><span data-stu-id="7a7db-182">**Public ACEs created by Forest Preparation**</span></span>

|<span data-ttu-id="7a7db-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="7a7db-183">**ACE**</span></span>|<span data-ttu-id="7a7db-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="7a7db-184">**RTCUniversalGlobalReadOnlyGroup**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7a7db-185">ルート ドメイン システム コンテナーが (継承なし) を読む**\***</span><span class="sxs-lookup"><span data-stu-id="7a7db-185">Read root domain System Container (not inherited) **\***</span></span> <br/> |<span data-ttu-id="7a7db-186">X</span><span class="sxs-lookup"><span data-stu-id="7a7db-186">X</span></span>  <br/> |
|<span data-ttu-id="7a7db-187">構成の読み込みの DisplaySpecifiers のコンテナー (継承なし)</span><span class="sxs-lookup"><span data-stu-id="7a7db-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> |<span data-ttu-id="7a7db-188">X</span><span class="sxs-lookup"><span data-stu-id="7a7db-188">X</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="7a7db-189">**\***継承されない Ace では、これらのコンテナーの下の子オブジェクトへのアクセスは付与しません。</span><span class="sxs-lookup"><span data-stu-id="7a7db-189">**\***ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="7a7db-190">継承された Ace では、これらのコンテナーの下にある子オブジェクトへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-190">ACEs that are inherited grant access to child objects under these containers.</span></span> 
  
<span data-ttu-id="7a7db-191">構成名前付けコンテキストの下で、構成コンテナーには、フォレストの準備は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>
  
- <span data-ttu-id="7a7db-192">**{AB255F23-2DBD-4bb6-891D-38754AC280EF}** **、RTC プロパティ**ページの adminContextMenu の下にエントリを追加し、ユーザー、連絡先、および Inetorgperson の指定子を表示する言語の adminPropertyPages の属性 (たとえば、CN =ユーザーの表示、CN = 409、CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="7a7db-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>
    
- <span data-ttu-id="7a7db-193">ユーザーおよび連絡先のクラスに適用される**権限の拡張**では、型**controlAccessRight**の**RTCPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>
    
- <span data-ttu-id="7a7db-194">[ユーザー、連絡先、OU、および DomainDNS クラスに適用される**権限の拡張**型**controlAccessRight**の**RTCUserSearchPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a7db-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>
    
- <span data-ttu-id="7a7db-195">各言語の組織単位 (OU) の表示指定子の**extraColumns**属性] の下の**msRTCSIP PrimaryUserAddress**を追加する (たとえば、CN = 組織単位の表示、CN = 409、CN = DisplaySpecifiers) の値をコピーし、既定の表示の**extraColumns**属性 (たとえば、CN = の既定の表示、CN = 409、CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="7a7db-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>
    
- <span data-ttu-id="7a7db-196">**MsRTCSIP PrimaryUserAddress**、 **msRTCSIP PrimaryHomeServer**、および**msRTCSIP UserEnabled**の各言語の**attributeDisplayNames**属性の下の属性をフィルター処理は、ユーザー、連絡先、指定子を表示を追加します。および InetOrgPerson オブジェクト (たとえば、英語で: CN = ユーザーの表示、CN = 409、CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="7a7db-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>
    

