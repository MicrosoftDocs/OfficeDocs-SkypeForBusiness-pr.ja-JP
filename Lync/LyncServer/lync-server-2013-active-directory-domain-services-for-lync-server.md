---
title: 'Lync Server 2013: Lync Server の Active Directory ドメインサービス'
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
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="e379e-102">Lync Server 2013 の Active Directory ドメインサービス</span><span class="sxs-lookup"><span data-stu-id="e379e-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e379e-103">_**トピックの最終更新日:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="e379e-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="e379e-104">Active Directory ドメインサービスは、Windows Server 2003、Windows Server 2008、Windows Server 2012、および Windows Server 2012 R2 ネットワークのディレクトリサービスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e379e-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="e379e-105">Active Directory ドメインサービスは、Microsoft Lync Server 2013 セキュリティインフラストラクチャを構築する基礎としても機能します。</span><span class="sxs-lookup"><span data-stu-id="e379e-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="e379e-106">このセクションの目的は、Lync Server 2013 が Active Directory ドメインサービスを使用して IM、Web 会議、メディア、および音声の信頼できる環境を作成する方法について説明することです。</span><span class="sxs-lookup"><span data-stu-id="e379e-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="e379e-107">Active Directory ドメインサービスに対する Lync Server extensions の詳細、および Active Directory ドメインサービス用の環境の準備については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="e379e-108">Windows Server のネットワークにおける Active Directory ドメイン サービスの役割の詳細については、お使いのバージョンのオペレーティング システムのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="e379e-109">Lync Server 2013 は、Active Directory ドメインサービスを使用して次のものを格納します。</span><span class="sxs-lookup"><span data-stu-id="e379e-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="e379e-110">フォレスト内の Lync Server 2013 を実行しているすべてのサーバーに必要なグローバル設定。</span><span class="sxs-lookup"><span data-stu-id="e379e-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="e379e-111">フォレスト内の Lync Server 2013 を実行しているすべてのサーバーの役割を識別するサービス情報。</span><span class="sxs-lookup"><span data-stu-id="e379e-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="e379e-112">一部のユーザー設定。</span><span class="sxs-lookup"><span data-stu-id="e379e-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="e379e-113">Active Directory のインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="e379e-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="e379e-114">Active Directory のインフラストラクチャ要件には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e379e-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="e379e-115">ドメイン コントローラーのオペレーティング システム要件</span><span class="sxs-lookup"><span data-stu-id="e379e-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="e379e-116">ドメインとフォレストの機能レベルの要件</span><span class="sxs-lookup"><span data-stu-id="e379e-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="e379e-117">グローバル カタログ ドメインの要件</span><span class="sxs-lookup"><span data-stu-id="e379e-117">Global catalog domain requirements</span></span>

<span data-ttu-id="e379e-118">詳細については、「展開」のドキュメントの「 [Lync Server 2013 の Active Directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="e379e-119">Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="e379e-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e379e-120">グローバル設定はシステム コンテナーではなく構成コンテナーに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e379e-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="e379e-121">これによってセキュリティが向上するわけではありませんが、一部の Active Directory ドメイン サービスのトポロジではスケーラビリティが向上することがあります。</span><span class="sxs-lookup"><span data-stu-id="e379e-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="e379e-122">Microsoft Office Communications Server 2007 から移行していて、システムコンテナーを使用していて、構成コンテナーの使用を計画している場合は、アップグレードの準備を行う前に、システムコンテナーで設定を移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e379e-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="e379e-123">システムコンテナー設定を構成コンテナーに移行するには、「Office Communications Server 2007 グローバル設定移行ツール<A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="e379e-124">Lync Server 2013 を展開する場合、最初の手順として、Active Directory ドメインサービスを準備します。</span><span class="sxs-lookup"><span data-stu-id="e379e-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="e379e-125">Lync Server 2013 用の Active Directory ドメインサービスの準備は、次の3つの手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="e379e-126">**スキーマを準備**します。</span><span class="sxs-lookup"><span data-stu-id="e379e-126">**Prepare Schema**.</span></span> <span data-ttu-id="e379e-127">このタスクは、Active Directory ドメインサービスのスキーマを拡張して、Lync Server 2013 に固有のクラスと属性を含めます。</span><span class="sxs-lookup"><span data-stu-id="e379e-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="e379e-128">スキーマの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 での Active Directory スキーマの準備の実行](lync-server-2013-running-schema-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="e379e-129">詳細については、「 [Office Communications server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="e379e-130">**フォレストを準備**します。</span><span class="sxs-lookup"><span data-stu-id="e379e-130">**Prepare Forest**.</span></span> <span data-ttu-id="e379e-131">このタスクは、フォレストのルートドメインにグローバル設定とオブジェクトを作成し、これらの設定およびオブジェクトへのアクセスを管理するユニバーサルサービスおよび管理グループと共に作成します。</span><span class="sxs-lookup"><span data-stu-id="e379e-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="e379e-132">フォレストの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 の実行フォレストの準備](lync-server-2013-running-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e379e-133">**ドメインを準備**します。</span><span class="sxs-lookup"><span data-stu-id="e379e-133">**Prepare Domain**.</span></span> <span data-ttu-id="e379e-134">このタスクは、ドメイン内のユーザーをホストおよび管理するためのアクセス許可を付与するユニバーサルグループに必要なアクセス制御エントリ (Ace) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e379e-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="e379e-135">このタスクは、Lync Server 2013 を実行しているサーバーを展開するすべてのドメインで、および Lync Server ユーザーが存在するすべてのドメインで完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e379e-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="e379e-136">ドメインの準備の詳細については、「展開」のドキュメントの「 [Lync Server 2013 の実行ドメインの準備](lync-server-2013-running-domain-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e379e-137">Active Directory を準備するための完全なプロセス、および各手順を実行するために必要な権限とアクセス許可の概要については、「展開」のドキュメントの「 [Lync Server 2013 の Active directory インフラストラクチャ要件](lync-server-2013-active-directory-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="e379e-138">ユニバーサル グループ</span><span class="sxs-lookup"><span data-stu-id="e379e-138">Universal Groups</span></span>

<span data-ttu-id="e379e-139">フォレストの準備時に、Lync Server 2013 は、グローバル設定とサービスにアクセスして管理するためのアクセス許可を持つ Active Directory ドメインサービス内にさまざまなユニバーサルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e379e-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="e379e-140">作成されるユニバーサル グループには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e379e-140">These universal groups include:</span></span>

  - <span data-ttu-id="e379e-141">**管理グループ**。</span><span class="sxs-lookup"><span data-stu-id="e379e-141">**Administrative groups**.</span></span> <span data-ttu-id="e379e-142">これらのグループは、Lync Server ネットワークの基本的な管理者の役割を定義します。</span><span class="sxs-lookup"><span data-stu-id="e379e-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="e379e-143">フォレストの準備中に、これらの管理者グループが Lync Server インフラストラクチャグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="e379e-144">**サービスグループ**。</span><span class="sxs-lookup"><span data-stu-id="e379e-144">**Service groups**.</span></span> <span data-ttu-id="e379e-145">これらのグループは、Lync Server で提供されるさまざまなサービスにアクセスするために必要なサービスアカウントです。</span><span class="sxs-lookup"><span data-stu-id="e379e-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="e379e-146">**インフラストラクチャグループ**。</span><span class="sxs-lookup"><span data-stu-id="e379e-146">**Infrastructure groups**.</span></span> <span data-ttu-id="e379e-147">これらのグループは、Lync Server インフラストラクチャの特定の領域にアクセスするためのアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="e379e-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="e379e-148">変更したり、ユーザーを直接追加したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="e379e-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="e379e-149">フォレストの準備時に、特定のサービスおよび管理グループが適切なインフラストラクチャグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="e379e-150">Lync Server 用の AD の準備時に作成される特定のユニバーサルグループと、インフラストラクチャグループに追加されるサービスおよび管理グループの詳細については、「展開」のドキュメントの「 [Lync server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e379e-151">Lync Server 2013 は、Windows server 2012 のユニバーサルグループをサポートしています。また、Lync Server 2013 を実行しているサーバーと、ドメインコントローラーの Windows Server 2003 オペレーティングシステムもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e379e-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="e379e-152">ユニバーサルグループのメンバーには、ドメインツリーまたはフォレスト内の任意のドメインの他のグループとアカウントを含めることができます。また、ドメインツリーまたはフォレスト内の任意のドメインでアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e379e-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="e379e-153">ユニバーサルグループのサポートを管理者の委任と組み合わせて使用すると、Lync Server の展開の管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e379e-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="e379e-154">たとえば、あるドメインを別のドメインに追加して、管理者が両方を管理できるようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e379e-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="e379e-155">役割ベースのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="e379e-155">Role-Based Access Control</span></span>

<span data-ttu-id="e379e-156">ユニバーサルサービスグループと管理グループの作成、および適切なユニバーサルグループへのサービスと管理グループの追加に加えて、フォレストの準備で役割ベースのアクセス制御 (RBAC) グループも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="e379e-157">フォレストの準備で作成された特定の RBAC グループの詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="e379e-158">RBAC グループの詳細については、「 [Lync Server 2013 の役割ベースのアクセス制御 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="e379e-159">アクセス制御エントリ (ACE) と継承</span><span class="sxs-lookup"><span data-stu-id="e379e-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="e379e-160">フォレストの準備では、プライベート ACE とパブリック ACE の両方が作成され、ユニバーサル グループの ACE が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="e379e-161">Lync Server によって使用されるグローバル設定コンテナーに特定のプライベート Ace を作成します。</span><span class="sxs-lookup"><span data-stu-id="e379e-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="e379e-162">このコンテナーは、Lync Server によってのみ使用され、グローバル設定を格納する場所に応じて、構成コンテナーまたはルートドメインのシステムコンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="e379e-p114">ドメインの準備ステップでは、ドメイン内のユーザーをホストおよび管理するアクセス許可を与えるアクセス制御エントリ (ACE) をユニバーサル グループに追加します。ドメインの準備で、ドメイン ルートと 3 つの組み込みコンテナー (ユーザー、コンピューター、およびドメイン コントローラー) に対する ACE が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="e379e-165">フォレストの準備およびドメインの準備で作成および追加されるパブリック Ace の詳細については、「展開」のドキュメントの「 [Lync server 2013 でのフォレストの準備](lync-server-2013-changes-made-by-forest-preparation.md)に加えられた変更」および「 [lync server 2013 のドメイン準備による変更](lync-server-2013-changes-made-by-domain-preparation.md)点」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e379e-166">組織では、セキュリティ リスクを軽減するために Active Directory ドメイン サービス (AD DS) をロックダウンすることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e379e-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="e379e-167">ただし、ロックダウンされた Active Directory 環境では、Lync Server 2013 に必要なアクセス許可を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e379e-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="e379e-168">たとえば、コンテナーと OU からの ACE の削除や、ユーザー、連絡先、InetOrgPerson、コンピューターの各オブジェクトでのアクセス許可の継承の無効化などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="e379e-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="e379e-169">ロックダウンされた Active Directory 環境では、コンテナーと OU のアクセス許可を必要に応じて手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e379e-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="e379e-170">詳細については、「展開」のドキュメントの「 [Lync Server 2013 でロックダウンされた Active Directory ドメインサービスを準備する](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="e379e-171">サーバー情報</span><span class="sxs-lookup"><span data-stu-id="e379e-171">Server Information</span></span>

<span data-ttu-id="e379e-172">ライセンス認証時に、Lync Server 2013 は、Active Directory ドメインサービス内の次の3つの場所にサーバー情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="e379e-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="e379e-173">Lync Server 2013 がインストールされている物理コンピューターに対応する各 Active Directory コンピューターオブジェクトのサービス接続ポイント (SCP)。</span><span class="sxs-lookup"><span data-stu-id="e379e-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="e379e-174">**msRTCSIP-Pools** クラスのコンテナーに作成されるサーバー オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e379e-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="e379e-175">トポロジビルダーで指定されている信頼されたサーバー。</span><span class="sxs-lookup"><span data-stu-id="e379e-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="e379e-176">サービス接続ポイント</span><span class="sxs-lookup"><span data-stu-id="e379e-176">Service Connection Points</span></span>

<span data-ttu-id="e379e-177">Active Directory ドメインサービスの各 Lync Server 2013 オブジェクトには、RTC Services という名前の SCP があります。これには、各コンピューターを識別して、提供されるサービスを指定するいくつかの属性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e379e-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="e379e-178">より重要な SCP 属性には、 *serviceDNSName*、 *serviceDNSNameType*、 *serviceClassname*、および*serviceBindingInformation*があります。</span><span class="sxs-lookup"><span data-stu-id="e379e-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="e379e-179">サードパーティ製のアセット管理アプリケーションは、これらの属性とその他の SCP 属性を照会することによって、展開全体でサーバー情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e379e-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="e379e-180">Active Directory サーバー オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e379e-180">Active Directory Server Objects</span></span>

<span data-ttu-id="e379e-181">各 Lync Server 2013 のサーバーの役割には、その役割によって提供されるサービスを定義する属性を持つ、対応する Active Directory オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="e379e-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="e379e-182">また、Standard Edition サーバーがアクティブになったとき、または Enterprise Edition プールが作成されたときに、Lync Server 2013 は、 **msRTCSIP**コンテナーに新しい**msRTCSIP**オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e379e-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="e379e-183">**MsRTCSIP**クラスは、プールの完全修飾ドメイン名 (FQDN) と、プールのフロントエンドおよびバックエンドのコンポーネント間の関連付けを指定します。</span><span class="sxs-lookup"><span data-stu-id="e379e-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="e379e-184">(Standard Edition サーバーは、1台のコンピューターにフロントおよびバックエンドが併置されている論理プールと見なされます)。</span><span class="sxs-lookup"><span data-stu-id="e379e-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="e379e-185">信頼済みのサーバー</span><span class="sxs-lookup"><span data-stu-id="e379e-185">Trusted Servers</span></span>

<span data-ttu-id="e379e-186">Lync Server 2013 では、[信頼されたサーバー] は、トポロジビルダーを実行してトポロジを公開するときに指定されるものです。</span><span class="sxs-lookup"><span data-stu-id="e379e-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="e379e-187">公開したトポロジは、すべてのサーバー情報を含めて、中央管理ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="e379e-188">中央管理ストアで定義されているサーバーのみが信頼されます。</span><span class="sxs-lookup"><span data-stu-id="e379e-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="e379e-189">Lync Server 2013 では、信頼されたサーバーは次の条件を満たすものです。</span><span class="sxs-lookup"><span data-stu-id="e379e-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="e379e-190">サーバーの FQDN が、中央管理ストアに格納されているトポロジに出現する。</span><span class="sxs-lookup"><span data-stu-id="e379e-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="e379e-191">サーバーが、信頼されている CA からの有効な証明書を提示している。</span><span class="sxs-lookup"><span data-stu-id="e379e-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="e379e-192">詳細については、「 [Lync Server 2013 の証明書インフラストラクチャ要件](lync-server-2013-certificate-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="e379e-p120">このどちらかの条件が満たされていない場合、サーバーは信頼されず、サーバーとの接続は拒否されます。この二重の要件により、悪意のあるサーバーが有効なサーバーの FQDN を乗っ取ろうとする攻撃を (たとえ攻撃の可能性が低くても) 防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e379e-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="e379e-195">また、lync server 2013 サーバーと通信するために Microsoft Office Communications Server 2007 R2 および Microsoft Office Communications Server 2007 の展開を有効にするために、Lync Server 2013 は、のリストを保持するためのフォレストの準備中にコンテナーを作成します。以前のリリースの信頼されたサーバー。</span><span class="sxs-lookup"><span data-stu-id="e379e-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="e379e-196">次の表は、以前の展開との互換性維持のために作成されるコンテナーを示しています。</span><span class="sxs-lookup"><span data-stu-id="e379e-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="e379e-197">信頼済みのサーバーのリストと、以前のリリースとの互換性を維持するための Active Directory コンテナー</span><span class="sxs-lookup"><span data-stu-id="e379e-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e379e-198">信頼済みのサーバーのリスト</span><span class="sxs-lookup"><span data-stu-id="e379e-198">Trusted server list</span></span></th>
<th><span data-ttu-id="e379e-199">Active Directory コンテナー</span><span class="sxs-lookup"><span data-stu-id="e379e-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e379e-200">Standard Edition サーバーおよびエンタープライズ プールのフロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="e379e-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="e379e-201">RTC サービス/グローバル設定</span><span class="sxs-lookup"><span data-stu-id="e379e-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e379e-202">会議サーバー</span><span class="sxs-lookup"><span data-stu-id="e379e-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="e379e-203">RTC サービス/信頼済み MCU</span><span class="sxs-lookup"><span data-stu-id="e379e-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e379e-204">Web コンポーネント サーバー</span><span class="sxs-lookup"><span data-stu-id="e379e-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="e379e-205">RTC サービス/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="e379e-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e379e-206">仲介サーバーと Communicator Web Access サーバー、アプリケーション サーバー、レジストラーと QoE、音声ビデオ会議サービス (サードパーティの SIP サーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="e379e-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="e379e-207">RTC サービス/信頼済みサービス</span><span class="sxs-lookup"><span data-stu-id="e379e-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e379e-208">プロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="e379e-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="e379e-209">Lync Server 2013 は、プロキシサーバーの下位互換性をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e379e-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e379e-210">以前のリリースの信頼済みサーバーをサポートするには、ベストプラクティスアナライザーツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e379e-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="e379e-211">ベストプラクティスアナライザーの実行の詳細について[https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633)は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e379e-211">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

