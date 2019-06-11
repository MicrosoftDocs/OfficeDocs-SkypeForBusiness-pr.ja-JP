---
title: 'Lync Server 2013: フォレストの準備によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="91e86-102">Lync Server 2013 でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="91e86-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91e86-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="91e86-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="91e86-104">このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91e86-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="91e86-105">Active Directory のグローバル設定とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="91e86-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="91e86-106">すべての新しい Lync Server 2013 の展開の場合と同様に、構成コンテナーにグローバル設定を保存している場合、フォレストの準備では既存のサービスコンテナーが使用され\\、構成サービスの下に**RTC サービス**オブジェクトが追加されます。オブジェクト.</span><span class="sxs-lookup"><span data-stu-id="91e86-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="91e86-107">RTC Service オブジェクトの下で、フォレストの準備によって型が Msrtcsip-userenabled true-GlobalContainer の**グローバル設定**オブジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="91e86-108">グローバル設定オブジェクトには、Lync Server の展開に適用されるすべての設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91e86-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="91e86-109">システムコンテナーにグローバル設定を保存する場合、フォレストの準備では、ルートドメインシステムコンテナーの下に Microsoft コンテナー、System\\microsoft オブジェクトの下に RTC サービスオブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="91e86-110">フォレストの準備では、この手順を実行するルートドメイン用の新しい**msrtcsip-userenabled true**オブジェクトも追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="91e86-111">Active Directory ユニバーサルサービスと管理グループ</span><span class="sxs-lookup"><span data-stu-id="91e86-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="91e86-112">フォレストの準備によって、指定したドメインに基づいてユニバーサルグループが作成され、これらのグループにアクセス制御エントリ (Ace) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="91e86-113">この手順では、指定したドメインのユーザーコンテナーでユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="91e86-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="91e86-114">ユニバーサルグループを使用すると、管理者はグローバル設定とサービスにアクセスして管理することができます。</span><span class="sxs-lookup"><span data-stu-id="91e86-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="91e86-115">フォレストの準備によって、次の種類のユニバーサルグループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="91e86-116">**管理グループ**   これらのグループは、Lync Server ネットワークの管理者ロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="91e86-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="91e86-117">**インフラストラクチャグループ**   これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="91e86-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="91e86-118">これらは、管理グループのコンポーネントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="91e86-118">They function as components of administrative groups.</span></span> <span data-ttu-id="91e86-119">これらのグループを変更したり、これらのグループにユーザーを直接追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="91e86-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="91e86-120">**サービスグループ**   これらのグループは、さまざまな Lync Server サービスへのアクセスに必要なサービスアカウントです。</span><span class="sxs-lookup"><span data-stu-id="91e86-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="91e86-121">次の表では、管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91e86-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="91e86-122">フォレストの準備中に作成された管理グループ</span><span class="sxs-lookup"><span data-stu-id="91e86-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91e86-123">管理グループ</span><span class="sxs-lookup"><span data-stu-id="91e86-123">Administrative group</span></span></th>
<th><span data-ttu-id="91e86-124">説明</span><span class="sxs-lookup"><span data-stu-id="91e86-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91e86-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="91e86-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="91e86-126">すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーとプールの設定を管理することをメンバーに許可します。</span><span class="sxs-lookup"><span data-stu-id="91e86-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="91e86-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="91e86-128">メンバーがユーザー設定を管理し、あるサーバーまたはプール間でユーザーを移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="91e86-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e86-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="91e86-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="91e86-130">サーバー、プール、ユーザー設定の読み取りをメンバーに許可します。</span><span class="sxs-lookup"><span data-stu-id="91e86-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91e86-131">次の表では、インフラストラクチャグループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91e86-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="91e86-132">フォレストの準備中に作成されたインフラストラクチャグループ</span><span class="sxs-lookup"><span data-stu-id="91e86-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91e86-133">インフラストラクチャグループ</span><span class="sxs-lookup"><span data-stu-id="91e86-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="91e86-134">説明</span><span class="sxs-lookup"><span data-stu-id="91e86-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91e86-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="91e86-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="91e86-136">Lync Server のグローバル設定オブジェクトへの書き込みアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="91e86-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="91e86-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="91e86-138">Lync Server のグローバル設定オブジェクトへの読み取り専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="91e86-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e86-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="91e86-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="91e86-140">Lync Server のユーザー設定に対する読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="91e86-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="91e86-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="91e86-142">Lync Server の設定に対する読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="91e86-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="91e86-143">このグループは、個々のサーバーに固有の設定のみに、プールレベルの設定にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="91e86-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e86-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="91e86-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="91e86-145">インストール時に、Lync Server 構成への読み取り専用アクセスを許可し、survivable branch アプライアンスのローカル管理者グループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91e86-146">次の表では、サービスグループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91e86-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="91e86-147">フォレストの準備中に作成されたサービスグループ</span><span class="sxs-lookup"><span data-stu-id="91e86-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91e86-148">サービスグループ</span><span class="sxs-lookup"><span data-stu-id="91e86-148">Service group</span></span></th>
<th><span data-ttu-id="91e86-149">説明</span><span class="sxs-lookup"><span data-stu-id="91e86-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91e86-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="91e86-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="91e86-151">フロントエンドサーバーおよび Standard Edition サーバーの実行に使用するサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91e86-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="91e86-152">このグループでは、Lync Server のグローバル設定と Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されています。</span><span class="sxs-lookup"><span data-stu-id="91e86-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="91e86-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="91e86-154">A/V 会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、監視サーバーの実行に使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91e86-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e86-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="91e86-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="91e86-156">Lync Server Edge サーバーを実行するために使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91e86-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="91e86-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="91e86-158">Lync Server 全体管理ストアのレプリケーションに参加できるサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91e86-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e86-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="91e86-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="91e86-160">Lync Server の設定への読み取り専用アクセス権を付与しますが、survivable branch Server と survivable branch appliance の展開のインストールの構成を許可します。</span><span class="sxs-lookup"><span data-stu-id="91e86-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91e86-161">次に示すように、フォレストの準備によって、適切なインフラストラクチャグループにサービスグループと管理グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="91e86-162">RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="91e86-163">RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="91e86-164">RTCHSUniversalServices、RTCComponentUniversalServices、RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="91e86-165">フォレストの準備では、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="91e86-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-166">CSAdministrator</span></span>

  - <span data-ttu-id="91e86-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="91e86-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="91e86-168">CSHelpDesk</span></span>

  - <span data-ttu-id="91e86-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="91e86-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="91e86-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="91e86-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="91e86-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="91e86-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="91e86-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="91e86-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="91e86-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="91e86-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="91e86-176">CsResponseGroupManager</span></span>

<span data-ttu-id="91e86-177">RBAC の役割と、それぞれに対して許可されるタスクの詳細については、計画ドキュメントの「 [Lync Server 2013 での役割ベースのアクセス制御の計画](lync-server-2013-planning-for-role-based-access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e86-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="91e86-178">フォレストの準備では、プライベート Ace とパブリック Ace の両方が作成されます。</span><span class="sxs-lookup"><span data-stu-id="91e86-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="91e86-179">Lync Server によって使用されるグローバル設定コンテナーにプライベート Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="91e86-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="91e86-180">このコンテナーは、Lync Server によってのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーのいずれかにあります。</span><span class="sxs-lookup"><span data-stu-id="91e86-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="91e86-181">次の表に、フォレストの準備によって作成されたパブリック Ace を示します。</span><span class="sxs-lookup"><span data-stu-id="91e86-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="91e86-182">フォレストの準備によって作成されたパブリック Ace</span><span class="sxs-lookup"><span data-stu-id="91e86-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91e86-183">AS</span><span class="sxs-lookup"><span data-stu-id="91e86-183">ACE</span></span></th>
<th><span data-ttu-id="91e86-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="91e86-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91e86-185">ルートドメインシステムコンテナーを読み取ります (継承されません)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="91e86-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="91e86-186">X</span><span class="sxs-lookup"><span data-stu-id="91e86-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e86-187">構成の DisplaySpecifiers 子コンテナーを読み取ります (継承されません)</span><span class="sxs-lookup"><span data-stu-id="91e86-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="91e86-188">X</span><span class="sxs-lookup"><span data-stu-id="91e86-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="91e86-189"><STRONG>\*</STRONG>継承されない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与しません。</span><span class="sxs-lookup"><span data-stu-id="91e86-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="91e86-190">継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="91e86-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="91e86-191">構成コンテナーでは、構成の名前付けコンテキストの下で、フォレストの準備で次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="91e86-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="91e86-192">ユーザー、連絡先、InetOrgPersons の言語表示指定子の adminContextMenu 属性と adminPropertyPages 属性の下に、[ **RTC] プロパティ**ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を追加します (例: CN =ユーザーによる表示、CN = 409、CN = DisplaySpecifiers 子</span><span class="sxs-lookup"><span data-stu-id="91e86-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="91e86-193">ユーザークラスと連絡先クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="91e86-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="91e86-194">ユーザー、連絡先、OU、および DomainDNS クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCUserSearchPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="91e86-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="91e86-195">各言語の組織単位 (OU) 表示指定子の**extraColumns**属性の下に**Msrtcsip-userenabled true-primaryuseraddress**を追加します (例: CN = ORGANIZATIONALUNIT-display、CN = 409、cn = displayspecifiers 子)。既定の表示の**extraColumns**属性 (たとえば、cn = Default-DISPLAY、cn = 409、Cn = displayspecifiers 子)。</span><span class="sxs-lookup"><span data-stu-id="91e86-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="91e86-196">ユーザー、連絡先、Msrtcsip-userenabled true の各言語表示指定子の**Attributedisplaynames**属性で、 **-primaryuseraddress**、 **Msrtcsip-userenabled true-PrimaryHomeServer**、および**msrtcsip-userenabled true-userenabled**フィルター属性を追加します。および InetOrgPerson オブジェクト (たとえば、英語: CN = ユーザー表示、CN = 409、CN = DisplaySpecifiers 子)。</span><span class="sxs-lookup"><span data-stu-id="91e86-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

