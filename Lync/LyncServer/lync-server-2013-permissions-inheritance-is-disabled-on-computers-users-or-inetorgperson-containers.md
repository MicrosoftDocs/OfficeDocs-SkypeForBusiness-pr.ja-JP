---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="14016-102">Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson のコンテナーでアクセス許可の継承が無効になっている</span><span class="sxs-lookup"><span data-stu-id="14016-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14016-103">_**最終更新日:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="14016-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="14016-104">ロックダウンされた Active Directory ドメインサービスでは、管理者の委任をセキュリティで保護し、グループポリシーオブジェクト (Gpo) の使用を可能にするために、アクセス許可の継承が無効になっている特定の組織単位 (Ou) に、ユーザーとコンピューターオブジェクトが配置されることがよくあります。セキュリティポリシーを適用するには</span><span class="sxs-lookup"><span data-stu-id="14016-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="14016-105">ドメインの準備とサーバーのアクティブ化 Lync Server 2013 に必要なアクセス制御エントリ (Ace) を設定します。</span><span class="sxs-lookup"><span data-stu-id="14016-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="14016-106">権限の継承が無効になっている場合、Lync Server のセキュリティグループはこれらの Ace を継承することはできません。</span><span class="sxs-lookup"><span data-stu-id="14016-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="14016-107">これらのアクセス許可が継承されない場合、Lync Server セキュリティグループは設定にアクセスできません。次の2つの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="14016-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="14016-108">ユーザー、InetOrgPersons、連絡先を管理したり、サーバーを操作したりするには、Lync Server のセキュリティグループで、各ユーザーのプロパティセット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック情報のドメインの準備手順によって設定された Ace が必要です。.</span><span class="sxs-lookup"><span data-stu-id="14016-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="14016-109">権限の継承が無効になっている場合、セキュリティグループはこれらの Ace を継承せず、サーバーまたはユーザーを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="14016-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="14016-110">サーバーとプールを見つけるために、Lync Server を実行しているサーバーは、Microsoft Container および Server オブジェクトを含む、コンピューターに関連するオブジェクトのアクティベーションによって設定された Ace に依存しています。</span><span class="sxs-lookup"><span data-stu-id="14016-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="14016-111">権限の継承が無効になっている場合、セキュリティグループ、サーバー、およびプールにはこれらの Ace は継承されず、これらの Ace を利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="14016-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="14016-112">これらの問題に対処するために、Lync Server では、**グラント Oupermission**コマンドレットが提供されています。</span><span class="sxs-lookup"><span data-stu-id="14016-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="14016-113">このコマンドレットは、必要な Lync Server Ace を、指定したコンテナーと組織単位、およびコンテナーまたは組織単位内のオブジェクトに直接設定します。</span><span class="sxs-lookup"><span data-stu-id="14016-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="14016-114">ドメインの準備が実行された後に、ユーザー、InetOrgPerson、連絡先オブジェクトのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="14016-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="14016-115">権限の継承が無効になっているロックダウンされた Active Directory 環境では、ドメインの準備によって、ドメイン内のユーザーまたは InetOrgPerson オブジェクトを保持しているコンテナーまたは組織単位の必要な Ace は設定されません。</span><span class="sxs-lookup"><span data-stu-id="14016-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="14016-116">この場合は、権限の継承が無効になっているユーザーまたは InetOrgPerson オブジェクトを持つ各コンテナーまたは OU に対して、**グラント Ou権限**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="14016-117">中央フォレストトポロジを使用している場合は、連絡先オブジェクトを保持するコンテナーまたは Ou でもこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="14016-118">セントラルフォレストトポロジの詳細については、サポートドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14016-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="14016-119">ObjectType パラメーターは、オブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="14016-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="14016-120">OU パラメーターは、組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="14016-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="14016-121">このコマンドレットは、指定したコンテナーまたは Ou と、コンテナー内のユーザーまたは InetOrgPerson オブジェクトに、必要な Ace を直接追加します。</span><span class="sxs-lookup"><span data-stu-id="14016-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="14016-122">このコマンドが実行される OU にユーザーオブジェクトまたは InetOrgPerson オブジェクトを持つ子 Ou がある場合、そのアクセス許可は適用されません。</span><span class="sxs-lookup"><span data-stu-id="14016-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="14016-123">コマンドは、各子 OU で個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="14016-124">これは、次のような Lync ホスティング展開 (親 OU = OCS テナント、DC = CONTOSO, dc = LOCAL and child OU = テナント1、OU = OCS テナント、DC = CONTOSO、DC = LOCAL) で一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="14016-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="14016-125">このコマンドレットを実行するには、ドメイン管理者グループのメンバーシップに相当するユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="14016-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="14016-126">ロックダウン環境で認証されたユーザーの Ace も削除された場合は、「[認証されたユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md)される」または「Enterprise Admins グループのメンバーであるアカウントを使用する」のように、フォレストルートドメイン内の関連するコンテナーまたは ou に対して、このアカウントの読み取りアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="14016-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="14016-127">**ユーザー、InetOrgPerson、連絡先オブジェクトに必要な Ace を設定するには**</span><span class="sxs-lookup"><span data-stu-id="14016-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="14016-128">ドメイン管理者グループのメンバーであるか、同等のユーザー権限を持っているアカウントで、ドメインに参加しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="14016-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="14016-129">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14016-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="14016-130">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14016-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="14016-131">Domain パラメーターを指定しない場合、既定値はローカルドメインです。</span><span class="sxs-lookup"><span data-stu-id="14016-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="14016-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14016-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="14016-133">ログファイルで、各タスクの最後で\*\* \<成功\> \*\*した実行の結果を探して、アクセス許可が設定されていることを確認し、[ログ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="14016-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="14016-134">または、次のコマンドを実行して、アクセス許可が設定されているかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="14016-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="14016-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14016-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="14016-136">ドメインの準備が実行された後に、コンピューターオブジェクトのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="14016-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="14016-137">権限の継承が無効になっているロックダウンされた Active Directory 環境では、ドメインの準備によって、ドメイン内のコンピューターオブジェクトを保持するコンテナーまたは Ou に必要な Ace は設定されません。</span><span class="sxs-lookup"><span data-stu-id="14016-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="14016-138">この場合は、権限の継承が無効になっている Lync Server を実行しているコンピューターを持つ各コンテナーまたは OU に対して、**グラント Ou権限**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="14016-139">ObjectType パラメーターは、オブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="14016-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="14016-140">この手順では、指定したコンテナーに必要な Ace を直接追加します。</span><span class="sxs-lookup"><span data-stu-id="14016-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="14016-141">このコマンドレットを実行するには、ドメイン管理者グループのメンバーシップに相当するユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="14016-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="14016-142">認証済みユーザーの Ace も削除された場合は、「[認証されたユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md)される」または「エンタープライズ管理者グループのメンバーであるアカウントを使用する」の説明に従って、フォレストルートドメイン内の関連するコンテナーに対して、このアカウントの読み取りアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="14016-143">**コンピューターオブジェクトに必要な Ace を設定するには**</span><span class="sxs-lookup"><span data-stu-id="14016-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="14016-144">Domain Admins グループのメンバーであるか、同等のユーザー権限を持つアカウントで、ドメインコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="14016-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="14016-145">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="14016-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="14016-146">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14016-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="14016-147">Domain パラメーターを指定しない場合、既定値はローカルドメインです。</span><span class="sxs-lookup"><span data-stu-id="14016-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="14016-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14016-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="14016-149">例として、「log\\file\\C:」と入力すると、各タスクの最後に\*\* \<成功\> \*\*の実行結果が表示され、エラーがないことを確認してから、ログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="14016-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="14016-150">権限をテストするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="14016-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="14016-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14016-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14016-152">ロックダウンされた Active Directory 環境でフォレストルートドメインでドメインの準備を実行している場合は、Lync Server で Active Directory スキーマと構成コンテナーへのアクセスが必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14016-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="14016-153">既定の認証済みユーザー権限が、スキーマまたは AD&nbsp;DS の構成コンテナーから削除された場合、指定されたコンテナーへのアクセスが許可されるのは、schema Admins グループ (スキーマコンテナーの場合) または Enterprise admins グループ (構成コンテナーの場合) のメンバーだけです。</span><span class="sxs-lookup"><span data-stu-id="14016-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="14016-154">Setup.exe、Lync Server 管理シェルコマンドレット、および Lync Server コントロールパネルでは、これらのコンテナーにアクセスする必要があるため、インストールを実行しているユーザーにスキーマに相当するユーザー権限がある場合を除き、管理ツールのセットアップとインストールは失敗します。管理者とエンタープライズ管理者グループのメンバーシップ。</span><span class="sxs-lookup"><span data-stu-id="14016-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="14016-155">この問題を解決するには、スキーマと構成コンテナーへの書き込みアクセス許可を RTCUniversalGlobalWriteGroup group に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14016-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

