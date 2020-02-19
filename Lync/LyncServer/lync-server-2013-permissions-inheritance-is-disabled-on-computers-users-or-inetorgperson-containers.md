---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="8e7aa-102">Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている</span><span class="sxs-lookup"><span data-stu-id="8e7aa-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e7aa-103">_**トピックの最終更新日:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="8e7aa-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="8e7aa-104">ロックダウンされた Active Directory ドメインサービスでは、アクセス許可の継承が無効になっている特定の組織単位 (Ou) にユーザーとコンピューターオブジェクトが配置されることが多く、グループポリシーオブジェクト (Gpo) の使用を可能にするのに役立ちます。セキュリティポリシーを適用する。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="8e7aa-105">ドメインの準備とサーバーのアクティブ化 Lync Server 2013 によって必要とされるアクセス制御エントリ (Ace) を設定します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="8e7aa-106">アクセス許可の継承が無効になっている場合、Lync Server のセキュリティグループはこれらの Ace を継承できません。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="8e7aa-107">これらのアクセス許可が継承されていない場合、Lync Server のセキュリティグループは設定にアクセスできず、次の2つの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="8e7aa-108">ユーザー、InetOrgPersons、および連絡先を管理し、サーバーを操作するには、Lync Server セキュリティグループで、各ユーザーのプロパティセット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック情報のドメイン準備手順によって設定された Ace を必要とします。.</span><span class="sxs-lookup"><span data-stu-id="8e7aa-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="8e7aa-109">アクセス許可の継承が無効になっている場合、これらの ACE がセキュリティ グループに継承されないので、サーバーまたはユーザーを管理することができません。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="8e7aa-110">サーバーとプールを検出するために、Lync Server を実行しているサーバーは、Microsoft Container および Server オブジェクトを含む、コンピューターに関連するオブジェクトのアクティブ化によって設定された Ace に依存しています。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="8e7aa-111">アクセス許可の継承が無効になると、セキュリティ グループ、サーバー、プールがこれらの ACE を継承しないため、ACE を利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="8e7aa-112">これらの問題に対処するために、Lync Server は**Grant-CsOuPermission**コマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="8e7aa-113">このコマンドレットでは、指定したコンテナーと組織単位、およびコンテナーまたは組織単位内のオブジェクトに対して、必要な Lync Server Ace を直接設定します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="8e7aa-114">ドメインの準備手続き以後のユーザー、InetOrgPerson、および連絡先オブジェクトに対するアクセス許可の設定</span><span class="sxs-lookup"><span data-stu-id="8e7aa-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="8e7aa-115">ロックダウンされた Active Directory 環境では、アクセス許可の継承が無効になるため、ドメインの準備手続きの中で、ドメイン内のユーザー オブジェクトや InetOrgPerson オブジェクトを収容するコンテナーまたは組織単位に必要な ACE が設定されません。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="8e7aa-116">このような状況では、アクセス許可の継承が無効になっているユーザー オブジェクトや InetOrgPerson オブジェクトを収容する各コンテナーまたは OU に対して **Grant-CsOuPermission** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="8e7aa-117">展開形態が中央フォレスト トポロジの場合は、連絡先オブジェクトを収容するコンテナーまたは OU に対しても、この手続きを実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="8e7aa-118">中央フォレストトポロジの詳細については、「サポート」のドキュメントの「supported [Active Directory トポロジ (Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="8e7aa-119">ObjectType パラメーターは、オブジェクト タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="8e7aa-120">OU パラメーターは組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="8e7aa-121">このコマンドレットは、指定したコンテナーまたは OU、およびそのコンテナー内のユーザー オブジェクトまたは InetOrgPerson オブジェクトで、必要な ACE を直接追加します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="8e7aa-122">このコマンドが実行される OU に、ユーザーオブジェクトまたは InetOrgPerson オブジェクトを持つ子 Ou がある場合、アクセス許可はそれらに適用されません。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="8e7aa-123">各子 OU でコマンドを個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="8e7aa-124">これは、Lync ホスティング展開の一般的なシナリオです。たとえば、親 OU = OCS テナント、DC = CONTOSO、DC = ローカルおよび子 OU = Tenant1、OU = OCS テナント、DC = CONTOSO、DC = ローカルです。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="8e7aa-125">このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="8e7aa-126">認証済みユーザーの Ace がロックダウンされた環境でも削除されている場合は、「[認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md)されているか、または Enterprise Admins グループのメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="8e7aa-127">**ユーザー、InetOrgPerson、および連絡先オブジェクトに必要な ACE を設定するには**</span><span class="sxs-lookup"><span data-stu-id="8e7aa-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="8e7aa-128">Domain Admins グループのメンバー アカウントか、それと同等のユーザー権限を持つアカウントを使用して、ドメインに参加しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="8e7aa-129">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e7aa-130">実行</span><span class="sxs-lookup"><span data-stu-id="8e7aa-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="8e7aa-131">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="8e7aa-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="8e7aa-133">ログファイルで、各タスクの最後に\*\* \<成功\> \*\*した実行結果を探して、アクセス許可が設定されたことを確認した後、[ログ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="8e7aa-134">次のコマンドで、アクセス許可が設定されたかどうかを調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="8e7aa-135">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="8e7aa-136">ドメイン準備手続き以後のコンピューター オブジェクトに対するアクセス許可の設定</span><span class="sxs-lookup"><span data-stu-id="8e7aa-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="8e7aa-137">ロックダウンされた Active Directory 環境ではアクセス許可の継承が無効になるため、ドメインの準備では、ドメイン内のコンピューター オブジェクトを収容するコンテナーまたは OU で必要な ACE が設定されません。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="8e7aa-138">このような状況では、アクセス許可の継承が無効になっている、Lync Server を実行しているコンピューターがある各コンテナーまたは OU で**Grant-CsOuPermission**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="8e7aa-139">ObjectType パラメーターは、オブジェクト タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="8e7aa-140">この手続きを実行すると、必要な ACE が、指定したコンテナーに直接追加されます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="8e7aa-141">このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="8e7aa-142">認証済みユーザーの Ace も削除されている場合は、「[認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md)されているか、Enterprise Admins グループのメンバーであるアカウントを使用しています」の説明に従って、フォレストルートドメイン内の関連するコンテナーに対して、このアカウントに読み取りアクセス ace を付与する必要があります</span><span class="sxs-lookup"><span data-stu-id="8e7aa-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="8e7aa-143">**コンピューター オブジェクトに必要な ACE を設定するには**</span><span class="sxs-lookup"><span data-stu-id="8e7aa-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="8e7aa-144">Domain Admins グループのメンバー アカウント、またはそれと同等のユーザー権限を持つアカウントを使用して、ドメインのコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="8e7aa-145">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e7aa-146">実行</span><span class="sxs-lookup"><span data-stu-id="8e7aa-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="8e7aa-147">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="8e7aa-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="8e7aa-149">この例のログファイル C:\\の\\ログには、各タスクの最後に\*\* \<成功\> \*\*した実行結果が表示され、エラーが発生していないことを確認した後、ログを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="8e7aa-150">次のコマンドレットを実行してアクセス許可をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="8e7aa-151">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e7aa-152">ロックダウンされた Active Directory 環境で、フォレストのルートドメインでドメインの準備を実行する場合は、Lync Server に Active Directory スキーマおよび構成コンテナーへのアクセスが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="8e7aa-153">既定の認証済みユーザーのアクセス許可がスキーマまたは AD&nbsp;DS の構成コンテナーから削除された場合は、スキーマ管理者グループ (スキーマコンテナーの場合) または Enterprise Admins グループ (構成コンテナーの場合) のメンバーのみが、指定したコンテナーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="8e7aa-154">Setup.exe、Lync Server 管理シェルコマンドレット、および Lync Server コントロールパネルは、これらのコンテナーへのアクセスを必要とするため、インストールを実行しているユーザーがスキーマに相当するユーザー権限を持っていない限り、管理ツールのセットアップとインストールは失敗します。管理者およびエンタープライズ管理者グループのメンバーシップ。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="8e7aa-155">この状況に対処するには、RTCUniversalGlobalWriteGroup グループに、スキーマ コンテナーと構成コンテナーへの読み取りおよび書き込みアクセス権を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e7aa-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

