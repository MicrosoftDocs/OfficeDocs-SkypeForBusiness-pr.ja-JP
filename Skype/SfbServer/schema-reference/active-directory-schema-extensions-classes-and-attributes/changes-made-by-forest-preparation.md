---
title: Skype for Business Server でのフォレストの準備によって行われた変更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。
ms.openlocfilehash: b304dbb12cb7e05e7bc82bdc56ffc330ce0221c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098653"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="d4c0c-103">Skype for Business Server でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="d4c0c-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="d4c0c-104">ここでは、グローバル設定とオブジェクト、およびフォレストの準備中に作成するユニバーサル サービス グループとユニバーサル管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="d4c0c-105">Active Directory のグローバル設定とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d4c0c-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="d4c0c-106">構成コンテナーにグローバル設定を格納する場合 (すべての新しい Skype for Business Server 展開の場合と同様)、フォレストの準備では既存のサービス コンテナーを使用し、Configuration\Services オブジェクトの下に **RTC Service** オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="d4c0c-107">フォレストの準備では、msRTCSIP-GlobalContainer 型の **Global Settings** オブジェクトが RTC サービス オブジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="d4c0c-108">グローバル設定オブジェクトには、Skype for Business Server 展開に適用される設定すべてが保持されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="d4c0c-109">グローバル設定をシステム コンテナーに保存する場合は、フォレストの準備で新しい ルート ドメインのシステム コンテナーの下の Microsoft コンテナーと、システム\Microsoft オブジェクトの下の RTC サービス オブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="d4c0c-110">またフォレストの準備では、この手順が実行されるルート ドメインの新しい **msRTCSIP-Domain** オブジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="d4c0c-111">Active Directory のユニバーサル サービス グループとユニバーサル管理グループ</span><span class="sxs-lookup"><span data-stu-id="d4c0c-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="d4c0c-p102">フォレストの準備では、指定したドメインを基にユニバーサル グループを作成し、これらのグループのアクセス制御エントリ (ACE) を追加します。このステップにより、指定したドメインのユーザー コンテナーにユニバーサル グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="d4c0c-p103">ユニバーサル グループを使用すると、管理者はグローバル設定およびサービスにアクセスしてそれらを管理できます。フォレストの準備により、次の種類のユニバーサル グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="d4c0c-116">**管理グループ** これらのグループは、Skype for Business Server ネットワークの管理者の役割を定義します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="d4c0c-117">**インフラストラクチャ グループ** これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="d4c0c-118">管理グループのコンポーネントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-118">They function as components of administrative groups.</span></span> <span data-ttu-id="d4c0c-119">これらのグループを変更したり、ユーザーを直接追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="d4c0c-120">**サービス グループ** これらのグループは、さまざまな Skype for Business Server サービスにアクセスするために必要なサービス アカウントです。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="d4c0c-121">次の表では、管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="d4c0c-122">**フォレストの準備時に作成される管理グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="d4c0c-123">**管理グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-123">**Administrative group**</span></span>|<span data-ttu-id="d4c0c-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4c0c-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d4c0c-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="d4c0c-126">このグループのメンバーは、すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーおよびプールの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d4c0c-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="d4c0c-128">このグループのメンバーは、ユーザー設定を管理したり、あるサーバーまたはプールから、別のサーバーまたはプールにユーザーを移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="d4c0c-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="d4c0c-130">このグループのメンバーは、サーバー、プール、およびユーザーの設定を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="d4c0c-131">次の表では、インフラストラクチャ グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="d4c0c-132">**フォレストの準備時に作成されるインフラストラクチャ グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="d4c0c-133">**インフラストラクチャ グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-133">**Infrastructure group**</span></span>|<span data-ttu-id="d4c0c-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4c0c-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="d4c0c-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="d4c0c-136">Skype for Business Server のグローバル設定オブジェクトへの書き込みアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d4c0c-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="d4c0c-138">Skype for Business Server のグローバル設定オブジェクトへの読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d4c0c-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="d4c0c-140">Skype for Business Server ユーザー設定への読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="d4c0c-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="d4c0c-142">Skype for Business Server 設定への読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="d4c0c-143">このグループは、プール レベルの設定にはアクセスできず、個々のサーバーに固有の設定のみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="d4c0c-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="d4c0c-145">Skype for Business Server 構成への読み取り専用アクセスを許可し、インストール中に存続可能ブランチ アプライアンスのローカル管理者グループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="d4c0c-146">次の表では、サービス グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-146">The following table describes the service groups.</span></span>

<span data-ttu-id="d4c0c-147">**フォレストの準備時に作成されるサービス グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="d4c0c-148">**サービス グループ**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-148">**Service group**</span></span>|<span data-ttu-id="d4c0c-149">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4c0c-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d4c0c-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="d4c0c-151">フロントエンド サーバーと Standard Edition サーバーの実行に使用されるサービス アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="d4c0c-152">このグループでは、サーバーは Skype for Business Server のグローバル設定と Active Directory ユーザー オブジェクトへの読み取り/書き込みアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d4c0c-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="d4c0c-154">音声ビデオ会議サーバー、Web サービス、仲介サーバー、アーカイブ サーバー、監視サーバーの実行に使用されるサービス アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d4c0c-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="d4c0c-156">Skype for Business Server エッジ サーバーの実行に使用されるサービス アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="d4c0c-158">Skype for Business Server Central Management ストアレプリケーションに参加できるサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="d4c0c-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="d4c0c-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="d4c0c-160">Skype for Business Server 設定への読み取り専用アクセスを許可しますが、存続可能ブランチ サーバーと存続可能ブランチ アプライアンス展開のインストールの構成を許可します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="d4c0c-161">フォレストの準備では、次に示すサービス グループと管理グループをインフラストラクチャ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="d4c0c-162">RTCUniversalServerAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="d4c0c-163">RTCUniversalUserAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="d4c0c-164">RTCHSUniversalServices、RTCComponentUniversalServices、および RTCUniversalReadOnlyAdmins を、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="d4c0c-165">フォレストの準備によって、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="d4c0c-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-166">CSAdministrator</span></span>

- <span data-ttu-id="d4c0c-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="d4c0c-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="d4c0c-168">CSHelpDesk</span></span>

- <span data-ttu-id="d4c0c-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="d4c0c-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="d4c0c-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-171">CSServerAdministrator</span></span>

- <span data-ttu-id="d4c0c-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-172">CSUserAdministrator</span></span>

- <span data-ttu-id="d4c0c-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="d4c0c-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="d4c0c-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="d4c0c-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="d4c0c-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="d4c0c-176">CsResponseGroupManager</span></span>

<span data-ttu-id="d4c0c-177">RBAC の役割、および各役割で許可されるタスクの詳細については、「計画」のドキュメントの「[Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) in the Planning documentation.</span></span>

<span data-ttu-id="d4c0c-178">フォレストの準備では、プライベート ACE とパブリック ACE の両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="d4c0c-179">Skype for Business Server で使用されるグローバル設定コンテナーにプライベート ACEs を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="d4c0c-180">このコンテナーは Skype for Business Server でのみ使用され、グローバル設定の保存場所に応じて、構成コンテナーまたはルート ドメインの System コンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="d4c0c-181">フォレストの準備で作成するパブリック ACE の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="d4c0c-182">**フォレストの準備で作成するパブリック ACE**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="d4c0c-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-183">**ACE**</span></span>                                                                 | <span data-ttu-id="d4c0c-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="d4c0c-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="d4c0c-185">ルート ドメインのシステム コンテナーの読み取り (継承されません) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="d4c0c-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="d4c0c-186">○</span><span class="sxs-lookup"><span data-stu-id="d4c0c-186">X</span></span>  <br/>                            |
| <span data-ttu-id="d4c0c-187">構成の DisplaySpecifiers コンテナーの読み取り (継承されません)</span><span class="sxs-lookup"><span data-stu-id="d4c0c-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="d4c0c-188">○</span><span class="sxs-lookup"><span data-stu-id="d4c0c-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="d4c0c-189"><strong>\\</strong>継承されない \*ACEs は、これらのコンテナーの下の子オブジェクトへのアクセスを許可しません。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="d4c0c-190">継承された ACEs は、これらのコンテナーの下の子オブジェクトへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="d4c0c-191">フォレストの準備では、構成名前付けコンテキストの下の構成コンテナーで次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="d4c0c-192">**RTC property** ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を、ユーザー、連絡先、および InetOrgPersons の言語表示指定子の adminContextMenu および adminPropertyPages 属性に追加します (CN=user-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="d4c0c-193">User クラスと Contact クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCPropertySet** オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="d4c0c-194">User、Contact、OU、および DomainDNS クラスに適用される **Extended-Rights** に、**controlAccessRight** 型の **RTCUserSearchPropertySet** オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="d4c0c-195">各言語の組織単位 (OU) の表示指定子の **extraColumns** 属性に **msRTCSIP-PrimaryUserAddress** を追加し (CN=organizationalUnit-Display、CN=409、CN=DisplaySpecifiers など)、既定の表示の **extraColumns** 属性の値をコピーします (CN=default-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="d4c0c-196">**msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer**、および **msRTCSIP-UserEnabled** フィルター属性を、Users、Contacts、および InetOrgPerson オブジェクトの各言語表示指定子の **attributeDisplayNames** 属性に追加します (たとえば英語では、CN=user-Display、CN=409、CN=DisplaySpecifiers など)。</span><span class="sxs-lookup"><span data-stu-id="d4c0c-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>