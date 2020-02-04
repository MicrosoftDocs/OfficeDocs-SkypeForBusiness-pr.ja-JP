---
title: 'Lync Server 2013: Lync Server 用 Active Directory ドメインサービス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="36db8-102">Lync Server 2013 用 Active Directory ドメインサービス</span><span class="sxs-lookup"><span data-stu-id="36db8-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36db8-103">_**最終更新日:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="36db8-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="36db8-104">Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="36db8-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="36db8-105">Active Directory ドメインサービスは、Microsoft Lync Server 2013 セキュリティインフラストラクチャを構築する基盤としても機能します。</span><span class="sxs-lookup"><span data-stu-id="36db8-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="36db8-106">このセクションの目的は、Lync Server 2013 で Active Directory ドメインサービスを使って、IM、Web 会議、メディア、音声の信頼できる環境を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="36db8-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="36db8-107">Active Directory ドメインサービスの Lync Server extensions、および Active directory ドメインサービスの環境の準備について詳しくは、展開ドキュメントの「 [Lync server 2013 用 Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36db8-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="36db8-108">Windows Server ネットワークの Active Directory ドメインサービスの役割の詳細については、使用しているオペレーティングシステムのバージョンのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="36db8-109">Lync Server 2013 は、次のように Active Directory ドメインサービスを使用して保存します。</span><span class="sxs-lookup"><span data-stu-id="36db8-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="36db8-110">フォレスト内の Lync Server 2013 を実行しているすべてのサーバーが必要とするグローバル設定。</span><span class="sxs-lookup"><span data-stu-id="36db8-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="36db8-111">フォレストで Lync Server 2013 を実行しているすべてのサーバーの役割を特定するサービス情報。</span><span class="sxs-lookup"><span data-stu-id="36db8-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="36db8-112">一部のユーザー設定。</span><span class="sxs-lookup"><span data-stu-id="36db8-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="36db8-113">Active Directory インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="36db8-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="36db8-114">Active Directory のインフラストラクチャ要件には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="36db8-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="36db8-115">ドメイン コントローラーのオペレーティング システム要件</span><span class="sxs-lookup"><span data-stu-id="36db8-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="36db8-116">ドメインとフォレストの機能レベルの要件</span><span class="sxs-lookup"><span data-stu-id="36db8-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="36db8-117">グローバル カタログ ドメインの要件</span><span class="sxs-lookup"><span data-stu-id="36db8-117">Global catalog domain requirements</span></span>

<span data-ttu-id="36db8-118">詳細については、展開ドキュメントの「 [Lync Server 2013 の Active Directory インフラストラクチャの要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="36db8-119">Active Directory ドメインサービスの準備</span><span class="sxs-lookup"><span data-stu-id="36db8-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36db8-120">システムコンテナーの代わりに、構成コンテナーにグローバル設定を展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36db8-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="36db8-121">これにより、セキュリティが強化されることはありませんが、一部の Active Directory ドメインサービストポロジのスケーラビリティが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="36db8-122">Microsoft Office Communications Server 2007 から移行していて、システムコンテナーを使っていて、構成コンテナーの使用を計画している場合は、アップグレード準備を行う前に、システムコンテナーの設定を移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="36db8-123">構成コンテナーにシステムコンテナーの設定を移行するには、「Office Communications Server 2007 の<A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>グローバル設定移行ツール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="36db8-124">Lync Server 2013 を展開する場合、最初の手順として Active Directory ドメインサービスを準備します。</span><span class="sxs-lookup"><span data-stu-id="36db8-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="36db8-125">Lync Server 2013 用の Active Directory ドメインサービスの準備は、次の3つの手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="36db8-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="36db8-126">**スキーマを準備**します。</span><span class="sxs-lookup"><span data-stu-id="36db8-126">**Prepare Schema**.</span></span> <span data-ttu-id="36db8-127">このタスクによって、Active Directory ドメインサービスのスキーマが拡張され、Lync Server 2013 に固有のクラスと属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36db8-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="36db8-128">スキーマの準備の詳細については、展開ドキュメントの「 [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="36db8-129">詳細については、「 [Office Communications server 2007 R2 から Lync Server 2013 に移行する](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="36db8-130">**フォレストを準備**します。</span><span class="sxs-lookup"><span data-stu-id="36db8-130">**Prepare Forest**.</span></span> <span data-ttu-id="36db8-131">このタスクでは、フォレストのルートドメインにグローバル設定とオブジェクトを作成し、これらの設定とオブジェクトへのアクセスを管理するユニバーサルサービスと管理グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="36db8-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="36db8-132">フォレストの準備について詳しくは、展開ドキュメントで「 [Lync Server 2013 用のフォレストの準備を実行](lync-server-2013-running-forest-preparation.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36db8-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="36db8-133">**ドメインを準備**します。</span><span class="sxs-lookup"><span data-stu-id="36db8-133">**Prepare Domain**.</span></span> <span data-ttu-id="36db8-134">このタスクは、必要なアクセス制御エントリ (Ace) をユニバーサルグループに追加します。これにより、ドメイン内でのユーザーのホストと管理のアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="36db8-135">このタスクは、Lync Server 2013 を実行しているサーバーおよび Lync Server ユーザーが存在するすべてのドメインで展開するすべてのドメインで完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="36db8-136">ドメインの準備について詳しくは、展開ドキュメントで「 [Lync Server 2013 のドメインの準備を実行](lync-server-2013-running-domain-preparation.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36db8-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="36db8-137">Active Directory を準備するための完全なプロセスと、各手順を実行するために必要な権限と権限については、展開ドキュメントの「 [Lync Server 2013 の Active directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="36db8-138">ユニバーサル グループ</span><span class="sxs-lookup"><span data-stu-id="36db8-138">Universal Groups</span></span>

<span data-ttu-id="36db8-139">Lync Server 2013 は、フォレストの準備中に、グローバル設定とサービスにアクセスして管理するためのアクセス許可を持つ、Active Directory ドメインサービス内でさまざまなユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="36db8-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="36db8-140">作成されるユニバーサル グループには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="36db8-140">These universal groups include:</span></span>

  - <span data-ttu-id="36db8-141">**管理グループ**。</span><span class="sxs-lookup"><span data-stu-id="36db8-141">**Administrative groups**.</span></span> <span data-ttu-id="36db8-142">これらのグループは、Lync Server ネットワークの基本的な管理者の役割を定義します。</span><span class="sxs-lookup"><span data-stu-id="36db8-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="36db8-143">フォレストの準備中に、これらの管理者グループが Lync Server インフラストラクチャグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="36db8-144">**サービスグループ**。</span><span class="sxs-lookup"><span data-stu-id="36db8-144">**Service groups**.</span></span> <span data-ttu-id="36db8-145">これらのグループは、Lync Server によって提供されるさまざまなサービスにアクセスするために必要なサービスアカウントです。</span><span class="sxs-lookup"><span data-stu-id="36db8-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="36db8-146">**インフラストラクチャグループ**。</span><span class="sxs-lookup"><span data-stu-id="36db8-146">**Infrastructure groups**.</span></span> <span data-ttu-id="36db8-147">これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="36db8-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="36db8-148">変更したり、ユーザーを直接追加したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="36db8-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="36db8-149">フォレストの準備時に、特定のサービス グループと管理グループが、対応するインフラストラクチャ グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="36db8-150">Lync Server 用の広告を準備するときに作成される特定のユニバーサルグループ、およびインフラストラクチャグループに追加されるサービスと管理グループの詳細については、「展開ドキュメントの[Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36db8-151">Lync server 2013 2012 では、Lync Server 2013 を実行しているサーバーと、Windows Server 2003 オペレーティングシステムがドメインコントローラーで使用するユニバーサルグループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="36db8-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="36db8-152">ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができ、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="36db8-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="36db8-153">ユニバーサルグループのサポートは、管理者の委任と組み合わせて、Lync Server の展開の管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="36db8-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="36db8-154">たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36db8-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="36db8-155">役割ベースのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="36db8-155">Role-Based Access Control</span></span>

<span data-ttu-id="36db8-156">ユニバーサル サービス グループと管理グループを作成し、サービス グループと管理グループを対応するユニバーサル グループに追加することに加えて、フォレストの準備では役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="36db8-157">フォレストの準備によって作成された特定の RBAC グループの詳細については、展開ドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="36db8-158">RBAC グループの詳細については、「 [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="36db8-159">アクセス制御エントリ (ACE) と継承</span><span class="sxs-lookup"><span data-stu-id="36db8-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="36db8-160">フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="36db8-161">Lync Server で使用されるグローバル設定コンテナーに特定のプライベート Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="36db8-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="36db8-162">このコンテナーは、Lync Server によってのみ使用され、グローバル設定を保存する場所に応じて、構成コンテナーまたはルートドメイン内のシステムコンテナーのいずれかにあります。</span><span class="sxs-lookup"><span data-stu-id="36db8-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="36db8-p114">ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="36db8-165">フォレストの準備とドメインの準備によって作成および追加されたパブリック Ace の詳細については、「 [Lync server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」および「展開ドキュメントの[lync server 2013 でのドメインの準備](lync-server-2013-changes-made-by-domain-preparation.md)によって行われた変更」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="36db8-166">組織は、セキュリティリスクを軽減するために Active Directory ドメインサービス (AD DS) をロックダウンすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="36db8-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="36db8-167">ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 で必要なアクセス許可を制限できます。</span><span class="sxs-lookup"><span data-stu-id="36db8-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="36db8-168">たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="36db8-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="36db8-169">ロックダウンされた Active Directory 環境では、アクセス許可を必要とするコンテナーと Ou に対して手動でアクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="36db8-170">詳細については、展開ドキュメントの「 [Lync Server 2013 でロックダウン Active Directory ドメインサービスを準備する](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="36db8-171">サーバー情報</span><span class="sxs-lookup"><span data-stu-id="36db8-171">Server Information</span></span>

<span data-ttu-id="36db8-172">ライセンス認証の際に、Lync Server 2013 は、Active Directory ドメインサービスの次の3つの場所にサーバー情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="36db8-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="36db8-173">Lync Server 2013 がインストールされている物理コンピューターに対応した各 Active Directory コンピューターオブジェクトのサービス接続ポイント (SCP)。</span><span class="sxs-lookup"><span data-stu-id="36db8-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="36db8-174">**msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="36db8-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="36db8-175">トポロジビルダーで指定された信頼できるサーバー。</span><span class="sxs-lookup"><span data-stu-id="36db8-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="36db8-176">サービス接続ポイント</span><span class="sxs-lookup"><span data-stu-id="36db8-176">Service Connection Points</span></span>

<span data-ttu-id="36db8-177">Active Directory ドメインサービス内の各 Lync Server 2013 オブジェクトには、RTC サービスという SCP があります。これには、各コンピューターを識別し、提供するサービスを指定するための多数の属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36db8-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="36db8-178">さらに重要な SCP 属性には、 *serviceDNSName*、 *serviceDNSNameType*、 *serviceClassname*、および*serviceBindingInformation*があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="36db8-179">サードパーティの資産管理アプリケーションは、このような SCP の属性を照会することによって、展開を通じてサーバーの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="36db8-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="36db8-180">Active Directory Server オブジェクト</span><span class="sxs-lookup"><span data-stu-id="36db8-180">Active Directory Server Objects</span></span>

<span data-ttu-id="36db8-181">各 Lync Server 2013 サーバーの役割には、その役割によって提供されるサービスを定義する属性を持つ Active Directory オブジェクトがそれぞれ含まれています。</span><span class="sxs-lookup"><span data-stu-id="36db8-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="36db8-182">また、Standard Edition サーバーがアクティブ化されたとき、または Enterprise Edition プールを作成したときに、Lync Server 2013 は、 **msrtcsip-userenabled true**コンテナーに新しい**msrtcsip-userenabled true**オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="36db8-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="36db8-183">**Msrtcsip-userenabled true**クラスは、プールの完全修飾ドメイン名 (FQDN) を、プールのフロントエンドコンポーネントとバックエンドコンポーネントの間の関連付けと共に指定します。</span><span class="sxs-lookup"><span data-stu-id="36db8-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="36db8-184">(Standard Edition サーバーは、フロントエンドとバックエンドが1台のコンピュータに併置されている論理プールと見なされます)。</span><span class="sxs-lookup"><span data-stu-id="36db8-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="36db8-185">信頼済みのサーバー</span><span class="sxs-lookup"><span data-stu-id="36db8-185">Trusted Servers</span></span>

<span data-ttu-id="36db8-186">Lync Server 2013 の [信頼済みサーバー] は、トポロジビルダーを実行してトポロジを公開するときに指定されたものです。</span><span class="sxs-lookup"><span data-stu-id="36db8-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="36db8-187">公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="36db8-188">中央管理ストアで定義されているサーバーのみが信頼されます。</span><span class="sxs-lookup"><span data-stu-id="36db8-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="36db8-189">Lync Server 2013 の信頼できるサーバーは、次の条件を満たしているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="36db8-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="36db8-190">サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。</span><span class="sxs-lookup"><span data-stu-id="36db8-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="36db8-191">サーバーが、信頼されている CA からの有効な証明書を提示している。</span><span class="sxs-lookup"><span data-stu-id="36db8-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="36db8-192">詳細については、「 [Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="36db8-p120">このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。この二重の要件により、悪意のあるサーバーが有効なサーバーの FQDN を乗っ取ろうとする攻撃を (たとえ攻撃の可能性が低くても) 防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="36db8-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="36db8-195">さらに、Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 の展開を有効にして、Lync Server 2013 サーバーと通信するために、Lync Server 2013 はフォレストの作成時にコンテナーを作成します。以前のリリース向けの信頼されたサーバー。</span><span class="sxs-lookup"><span data-stu-id="36db8-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="36db8-196">次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="36db8-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="36db8-197">以前のリリースとの互換性を確保するために、信頼されたサーバーの一覧とその Active Directory コンテナー</span><span class="sxs-lookup"><span data-stu-id="36db8-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36db8-198">信頼済みのサーバーのリスト</span><span class="sxs-lookup"><span data-stu-id="36db8-198">Trusted server list</span></span></th>
<th><span data-ttu-id="36db8-199">Active Directory コンテナー</span><span class="sxs-lookup"><span data-stu-id="36db8-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36db8-200">Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="36db8-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="36db8-201">RTC サービス/グローバル設定</span><span class="sxs-lookup"><span data-stu-id="36db8-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36db8-202">会議サーバー</span><span class="sxs-lookup"><span data-stu-id="36db8-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="36db8-203">RTC サービス/信頼済み MCU</span><span class="sxs-lookup"><span data-stu-id="36db8-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36db8-204">Web コンポーネント サーバー</span><span class="sxs-lookup"><span data-stu-id="36db8-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="36db8-205">RTC サービス/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="36db8-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36db8-206">仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="36db8-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="36db8-207">RTC サービス/信頼済みサービス</span><span class="sxs-lookup"><span data-stu-id="36db8-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36db8-208">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="36db8-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="36db8-209">Lync Server 2013 は、プロキシサーバーの下位互換性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="36db8-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36db8-210">以前のリリースの信頼されたサーバーをサポートするには、ベストプラクティスアナライザーツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36db8-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="36db8-211">ベストプラクティスアナライザーの実行の詳細について[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36db8-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

