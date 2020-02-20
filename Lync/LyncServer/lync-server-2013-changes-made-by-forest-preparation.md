---
title: 'Lync Server 2013: フォレストの準備によって加えられた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709263aeffe1a8681275d943da702242944868b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="bce3a-102">Lync Server 2013 でのフォレストの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="bce3a-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bce3a-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="bce3a-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="bce3a-104">ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="bce3a-105">Active Directory のグローバル設定とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="bce3a-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="bce3a-106">構成コンテナーにグローバル設定を格納する場合 (すべての新しい Lync Server 2013 展開の場合と同様)、フォレストの準備では、既存のサービスコンテナーを使用し、構成\\サービスオブジェクトの下に**RTC Service**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="bce3a-107">フォレストの準備では、msRTCSIP-GlobalContainer 型の **Global Settings** オブジェクトが RTC サービス オブジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="bce3a-108">グローバル設定オブジェクトには、Lync Server の展開に適用されるすべての設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce3a-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="bce3a-109">システムコンテナーにグローバル設定を格納すると、フォレストの準備では、ルートドメインシステムコンテナーの下の Microsoft コンテナーと、System\\microsoft オブジェクトの下にある RTC サービスオブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="bce3a-110">またフォレストの準備では、この手順が実行されるルート ドメインの新しい **msRTCSIP-Domain** オブジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="bce3a-111">Active Directory のユニバーサル サービス グループとユニバーサル管理グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="bce3a-p102">フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (ACE) を追加します。このステップにより、指定したドメインのユーザー コンテナーにユニバーサル グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="bce3a-p103">ユニバーサル グループを使用すると、管理者はグローバル設定およびサービスにアクセスしてそれらを管理できます。フォレストの準備により、次の種類のユニバーサル グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="bce3a-116">**管理グループ**   これらのグループは、Lync Server ネットワークの管理者の役割を定義します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="bce3a-117">**インフラストラクチャグループ**   これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="bce3a-118">これらは、管理グループのコンポーネントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-118">They function as components of administrative groups.</span></span> <span data-ttu-id="bce3a-119">これらのグループを変更したり、ユーザーを直接追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bce3a-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="bce3a-120">**サービスグループ**   これらのグループは、さまざまな Lync Server サービスにアクセスするために必要なサービスアカウントです。</span><span class="sxs-lookup"><span data-stu-id="bce3a-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="bce3a-121">次の表では、管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="bce3a-122">フォレストの準備時に作成される管理グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bce3a-123">管理グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-123">Administrative group</span></span></th>
<th><span data-ttu-id="bce3a-124">説明</span><span class="sxs-lookup"><span data-stu-id="bce3a-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bce3a-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="bce3a-126">このグループのメンバーは、すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーおよびプールの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bce3a-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="bce3a-128">このグループのメンバーは、ユーザー設定を管理したり、あるサーバーまたはプールから、別のサーバーまたはプールにユーザーを移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="bce3a-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="bce3a-130">このグループのメンバーは、サーバー、プール、およびユーザーの設定を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bce3a-131">次の表では、インフラストラクチャ グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="bce3a-132">フォレストの準備時に作成されるインフラストラクチャ グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bce3a-133">インフラストラクチャ グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="bce3a-134">説明</span><span class="sxs-lookup"><span data-stu-id="bce3a-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="bce3a-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="bce3a-136">Lync Server のグローバル設定オブジェクトへの書き込みアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bce3a-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bce3a-138">Lync Server のグローバル設定オブジェクトへの読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bce3a-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bce3a-140">Lync Server ユーザー設定への読み取り専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bce3a-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="bce3a-142">Lync Server 設定への読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="bce3a-143">このグループは、プール レベルの設定にはアクセスできず、個々のサーバーに固有の設定のみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="bce3a-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="bce3a-145">Lync Server 構成への読み取り専用アクセスを許可し、インストール中に存続可能 branch アプライアンスのローカルの Administrators グループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bce3a-146">次の表では、サービス グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="bce3a-147">フォレストの準備時に作成されるサービス グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bce3a-148">サービス グループ</span><span class="sxs-lookup"><span data-stu-id="bce3a-148">Service group</span></span></th>
<th><span data-ttu-id="bce3a-149">説明</span><span class="sxs-lookup"><span data-stu-id="bce3a-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bce3a-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bce3a-151">フロントエンドサーバーおよび Standard Edition サーバーの実行に使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce3a-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="bce3a-152">このグループでは、Lync Server のグローバル設定および Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bce3a-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bce3a-154">音声ビデオ会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、および監視サーバーの実行に使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce3a-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bce3a-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bce3a-156">Lync Server エッジサーバーを実行するために使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce3a-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="bce3a-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="bce3a-158">Lync Server Central Management store のレプリケーションに参加できるサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce3a-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="bce3a-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="bce3a-160">Lync Server 設定への読み取り専用アクセスが許可されますが、存続可能 branch server と存続可能 branch appliance の展開のインストールのための構成を許可します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bce3a-161">フォレストの準備では、次に示すサービス グループと管理グループをインフラストラクチャ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="bce3a-162">RTCUniversalServerAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="bce3a-163">RTCUniversalUserAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="bce3a-164">RTCHSUniversalServices、RTCComponentUniversalServices、および RTCUniversalReadOnlyAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="bce3a-165">フォレストの準備によって、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="bce3a-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-166">CSAdministrator</span></span>

  - <span data-ttu-id="bce3a-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="bce3a-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="bce3a-168">CSHelpDesk</span></span>

  - <span data-ttu-id="bce3a-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="bce3a-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="bce3a-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="bce3a-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="bce3a-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="bce3a-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bce3a-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="bce3a-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="bce3a-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="bce3a-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="bce3a-176">CsResponseGroupManager</span></span>

<span data-ttu-id="bce3a-177">RBAC の役割および各に対して許可されるタスクの詳細については、「計画」のドキュメントの「 [planning for roles based access control In Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce3a-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="bce3a-178">フォレストの準備では、プライベート ACE とパブリック ACE の両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="bce3a-179">Lync Server によって使用されるグローバル設定コンテナーにプライベートの Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="bce3a-180">このコンテナーは、Lync Server によってのみ使用され、グローバル設定を格納する場所に応じて、構成コンテナーまたはルートドメインのシステムコンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bce3a-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="bce3a-181">フォレストの準備で作成するパブリック ACE の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="bce3a-182">フォレストの準備で作成するパブリック ACE</span><span class="sxs-lookup"><span data-stu-id="bce3a-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bce3a-183">ACE</span><span class="sxs-lookup"><span data-stu-id="bce3a-183">ACE</span></span></th>
<th><span data-ttu-id="bce3a-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="bce3a-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bce3a-185">ルート ドメインのシステム コンテナーの読み取り (継承されない)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="bce3a-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="bce3a-186">X</span><span class="sxs-lookup"><span data-stu-id="bce3a-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bce3a-187">構成の DisplaySpecifiers コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="bce3a-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="bce3a-188">X</span><span class="sxs-lookup"><span data-stu-id="bce3a-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bce3a-189"><STRONG>\*</STRONG>継承されていない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセスを許可しません。</span><span class="sxs-lookup"><span data-stu-id="bce3a-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="bce3a-190">継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="bce3a-191">フォレストの準備では、構成名前付けコンテキストの下の構成コンテナーで次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="bce3a-192">**RTC property** ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を、ユーザー、連絡先、および InetOrgPersons の言語表示指定子の adminContextMenu および adminPropertyPages 属性に追加します (CN=user-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="bce3a-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="bce3a-193">User クラスと Contact クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCPropertySet** オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="bce3a-194">User、Contact、OU、および DomainDNS クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCUserSearchPropertySet** オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="bce3a-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="bce3a-195">各言語の組織単位 (OU) の表示指定子の **extraColumns** 属性に **msRTCSIP-PrimaryUserAddress** を追加し (CN=organizationalUnit-Display、CN=409、CN=DisplaySpecifiers など)、既定の表示の **extraColumns** 属性の値をコピーします (CN=default-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="bce3a-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="bce3a-196">**msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer**、および **msRTCSIP-UserEnabled** フィルター属性を、Users、Contacts、および InetOrgPerson オブジェクトの各言語表示指定子の **attributeDisplayNames** 属性に追加します (たとえば英語では、CN=user-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="bce3a-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

