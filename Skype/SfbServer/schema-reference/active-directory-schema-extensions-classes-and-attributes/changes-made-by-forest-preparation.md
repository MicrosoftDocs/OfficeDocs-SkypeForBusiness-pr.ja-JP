---
title: Skype for Business Server でのフォレストの準備によって行われた変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296701"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="3e57d-103">Skype for Business Server でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="3e57d-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="3e57d-104">このセクションでは、グローバル設定とオブジェクト、およびフォレストの準備手順によって作成されるユニバーサルサービスと管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="3e57d-105">Active Directory のグローバル設定とオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3e57d-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="3e57d-106">構成コンテナーにグローバル設定を保存している場合 (すべての新しい Skype for Business Server の展開の場合と同様に)、フォレストの準備で既存のサービスコンテナーが使用され、Configuration\Services の下に**RTC サービス**オブジェクトが追加されます。オブジェクト.</span><span class="sxs-lookup"><span data-stu-id="3e57d-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="3e57d-107">RTC Service オブジェクトの下で、フォレストの準備によって型が Msrtcsip-userenabled true-GlobalContainer の**グローバル設定**オブジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="3e57d-108">グローバル設定オブジェクトには、Skype for Business Server の展開に適用されるすべての設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="3e57d-109">システムコンテナーにグローバル設定を保存する場合、フォレストの準備では、ルートドメインシステムコンテナーと、System\Microsoft オブジェクトの下にある RTC サービスオブジェクトを使って Microsoft コンテナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="3e57d-110">フォレストの準備では、この手順を実行するルートドメイン用の新しい**msrtcsip-userenabled true**オブジェクトも追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="3e57d-111">Active Directory ユニバーサルサービスと管理グループ</span><span class="sxs-lookup"><span data-stu-id="3e57d-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="3e57d-112">フォレストの準備によって、指定したドメインに基づいてユニバーサルグループが作成され、これらのグループにアクセス制御エントリ (Ace) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="3e57d-113">この手順では、指定したドメインのユーザーコンテナーでユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="3e57d-114">ユニバーサルグループを使用すると、管理者はグローバル設定とサービスにアクセスして管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="3e57d-115">フォレストの準備によって、次の種類のユニバーサルグループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-115">Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="3e57d-116">**管理グループ**これらのグループは、Skype for Business Server ネットワークの管理者ロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="3e57d-117">**インフラストラクチャグループ**これらのグループは、Skype for Business Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="3e57d-118">これらは、管理グループのコンポーネントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-118">They function as components of administrative groups.</span></span> <span data-ttu-id="3e57d-119">これらのグループを変更したり、これらのグループにユーザーを直接追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e57d-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="3e57d-120">**サービスグループ**これらのグループは、さまざまな Skype for Business Server サービスへのアクセスに必要なサービスアカウントです。</span><span class="sxs-lookup"><span data-stu-id="3e57d-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="3e57d-121">次の表では、管理グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="3e57d-122">**フォレストの準備中に作成された管理グループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="3e57d-123">**管理グループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-123">**Administrative group**</span></span>|<span data-ttu-id="3e57d-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="3e57d-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e57d-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3e57d-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="3e57d-126">すべてのサーバーの役割、グローバル設定、ユーザーなど、サーバーとプールの設定を管理することをメンバーに許可します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="3e57d-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3e57d-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="3e57d-128">メンバーがユーザー設定を管理し、あるサーバーまたはプール間でユーザーを移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3e57d-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="3e57d-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="3e57d-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="3e57d-130">サーバー、プール、ユーザー設定の読み取りをメンバーに許可します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="3e57d-131">次の表では、インフラストラクチャグループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="3e57d-132">**フォレストの準備中に作成されたインフラストラクチャグループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="3e57d-133">**インフラストラクチャグループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-133">**Infrastructure group**</span></span>|<span data-ttu-id="3e57d-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="3e57d-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e57d-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="3e57d-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="3e57d-136">Skype for Business Server のグローバル設定オブジェクトへの書き込みアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="3e57d-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3e57d-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="3e57d-138">Skype for Business Server のグローバル設定オブジェクトへの読み取り専用アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="3e57d-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3e57d-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="3e57d-140">Skype for Business Server のユーザー設定への読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="3e57d-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3e57d-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="3e57d-142">Skype for Business Server の設定への読み取り専用アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="3e57d-143">このグループは、個々のサーバーに固有の設定のみに、プールレベルの設定にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e57d-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="3e57d-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="3e57d-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="3e57d-145">Skype for Business Server の設定への読み取り専用アクセス権を付与し、インストール中に survivable branch アプライアンスのローカル管理者グループに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="3e57d-146">次の表では、サービスグループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-146">The following table describes the service groups.</span></span>

<span data-ttu-id="3e57d-147">**フォレストの準備中に作成されたサービスグループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="3e57d-148">**サービスグループ**</span><span class="sxs-lookup"><span data-stu-id="3e57d-148">**Service group**</span></span>|<span data-ttu-id="3e57d-149">**説明**</span><span class="sxs-lookup"><span data-stu-id="3e57d-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e57d-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3e57d-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="3e57d-151">フロントエンドサーバーおよび Standard Edition サーバーの実行に使用するサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e57d-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="3e57d-152">このグループでは、Skype for Business Server のグローバル設定と Active Directory ユーザーオブジェクトへのサーバーの読み取り/書き込みアクセスが許可されています。</span><span class="sxs-lookup"><span data-stu-id="3e57d-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="3e57d-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3e57d-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="3e57d-154">A/V 会議サーバー、Web サービス、仲介サーバー、アーカイブサーバー、監視サーバーの実行に使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e57d-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="3e57d-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3e57d-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="3e57d-156">Skype for Business Server Edge サーバーを実行するために使用されるサービスアカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e57d-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="3e57d-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="3e57d-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="3e57d-158">Skype for Business Server 全体管理ストアのレプリケーションに参加できるサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e57d-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="3e57d-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3e57d-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="3e57d-160">Skype for Business Server の設定への読み取り専用アクセス権を付与しますが、survivable branch server と survivable branch appliance の展開をインストールするための構成を許可します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="3e57d-161">次に示すように、フォレストの準備によって、適切なインフラストラクチャグループにサービスグループと管理グループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="3e57d-162">RTCUniversalServerAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="3e57d-163">RTCUniversalUserAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="3e57d-164">RTCHSUniversalServices、RTCComponentUniversalServices、RTCUniversalReadOnlyAdmins は、RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup、および RTCUniversalUserReadOnlyGroup のメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="3e57d-165">フォレストの準備では、次の役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="3e57d-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-166">CSAdministrator</span></span>

- <span data-ttu-id="3e57d-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="3e57d-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="3e57d-168">CSHelpDesk</span></span>

- <span data-ttu-id="3e57d-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="3e57d-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="3e57d-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-171">CSServerAdministrator</span></span>

- <span data-ttu-id="3e57d-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-172">CSUserAdministrator</span></span>

- <span data-ttu-id="3e57d-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="3e57d-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3e57d-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="3e57d-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="3e57d-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="3e57d-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="3e57d-176">CsResponseGroupManager</span></span>

<span data-ttu-id="3e57d-177">RBAC の役割と、それぞれに対して許可されるタスクについて詳しくは、「計画ドキュメントの[役割ベースのアクセス制御](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e57d-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="3e57d-178">フォレストの準備では、プライベート Ace とパブリック Ace の両方が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3e57d-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="3e57d-179">Skype for Business Server で使用されるグローバル設定コンテナーにプライベート Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="3e57d-180">このコンテナーは、Skype for Business Server でのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーにあります。</span><span class="sxs-lookup"><span data-stu-id="3e57d-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="3e57d-181">次の表に、フォレストの準備によって作成されたパブリック Ace を示します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="3e57d-182">**フォレストの準備によって作成されたパブリック Ace**</span><span class="sxs-lookup"><span data-stu-id="3e57d-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="3e57d-183">**AS**</span><span class="sxs-lookup"><span data-stu-id="3e57d-183">**ACE**</span></span>                                                                 | <span data-ttu-id="3e57d-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="3e57d-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="3e57d-185">ルートドメインシステムコンテナーを読み取ります (継承されません)**\\**\*</span><span class="sxs-lookup"><span data-stu-id="3e57d-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="3e57d-186">X</span><span class="sxs-lookup"><span data-stu-id="3e57d-186">X</span></span>  <br/>                            |
| <span data-ttu-id="3e57d-187">構成の DisplaySpecifiers 子コンテナーを読み取ります (継承されません)</span><span class="sxs-lookup"><span data-stu-id="3e57d-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="3e57d-188">X</span><span class="sxs-lookup"><span data-stu-id="3e57d-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="3e57d-189"><strong>\\</strong>\* 継承されない Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与しません。</span><span class="sxs-lookup"><span data-stu-id="3e57d-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="3e57d-190">継承された Ace は、これらのコンテナーの下にある子オブジェクトへのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="3e57d-191">構成コンテナーでは、構成の名前付けコンテキストの下で、フォレストの準備で次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="3e57d-192">ユーザー、連絡先、InetOrgPersons の言語表示指定子の adminContextMenu 属性と adminPropertyPages 属性の下に、[ **RTC] プロパティ**ページのエントリ **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** を追加します (例: CN =ユーザーによる表示、CN = 409、CN = DisplaySpecifiers 子</span><span class="sxs-lookup"><span data-stu-id="3e57d-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="3e57d-193">ユーザークラスと連絡先クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="3e57d-194">ユーザー、連絡先、OU、および DomainDNS クラスに適用される**拡張権限**の下に、 **controlaccessright**型の**RTCUserSearchPropertySet**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e57d-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="3e57d-195">各言語の組織単位 (OU) 表示指定子の**extraColumns**属性の下に**Msrtcsip-userenabled true-primaryuseraddress**を追加します (例: CN = ORGANIZATIONALUNIT-display、CN = 409、cn = displayspecifiers 子)。既定の表示の**extraColumns**属性 (たとえば、cn = Default-DISPLAY、cn = 409、Cn = displayspecifiers 子)。</span><span class="sxs-lookup"><span data-stu-id="3e57d-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="3e57d-196">ユーザー、連絡先、Msrtcsip-userenabled true の各言語表示指定子の**Attributedisplaynames**属性で、 **-primaryuseraddress**、 **Msrtcsip-userenabled true-PrimaryHomeServer**、および**msrtcsip-userenabled true-userenabled**フィルター属性を追加します。および InetOrgPerson オブジェクト (たとえば、英語: CN = ユーザー表示、CN = 409、CN = DisplaySpecifiers 子)。</span><span class="sxs-lookup"><span data-stu-id="3e57d-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


