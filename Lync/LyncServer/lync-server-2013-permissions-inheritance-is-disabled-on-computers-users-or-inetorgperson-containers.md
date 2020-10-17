---
title: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている'
description: 'Lync Server 2013: コンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっています。'
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
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545163"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="9a6c3-103">Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている</span><span class="sxs-lookup"><span data-stu-id="9a6c3-103">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6c3-104">_**トピックの最終更新日:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="9a6c3-104">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="9a6c3-105">ロックダウンされた Active Directory ドメインサービスでは、アクセス許可の継承が無効になっている特定の組織単位 (Ou) にユーザーとコンピューターのオブジェクトが配置されることが多く、セキュリティポリシーを適用するために、グループポリシーオブジェクト (Gpo) の使用を有効にするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-105">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="9a6c3-106">ドメインの準備とサーバーのアクティブ化 Lync Server 2013 によって必要とされるアクセス制御エントリ (Ace) を設定します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-106">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="9a6c3-107">アクセス許可の継承が無効になっている場合、Lync Server のセキュリティグループはこれらの Ace を継承できません。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-107">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="9a6c3-108">これらのアクセス許可が継承されていない場合、Lync Server のセキュリティグループは設定にアクセスできず、次の2つの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-108">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="9a6c3-109">ユーザー、InetOrgPersons、および連絡先を管理し、サーバーを運用するには、Lync Server のセキュリティグループに、各ユーザーのプロパティセット、リアルタイム通信 (RTC)、RTC ユーザー検索、およびパブリック情報に関するドメインの準備手順によって設定された Ace が必要です。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-109">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="9a6c3-110">アクセス許可の継承が無効になっている場合、これらの ACE がセキュリティ グループに継承されないので、サーバーまたはユーザーを管理することができません。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-110">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="9a6c3-111">サーバーとプールを検出するために、Lync Server を実行しているサーバーは、Microsoft Container および Server オブジェクトを含む、コンピューターに関連するオブジェクトのアクティブ化によって設定された Ace に依存しています。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-111">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="9a6c3-112">アクセス許可の継承が無効になると、セキュリティ グループ、サーバー、プールがこれらの ACE を継承しないため、ACE を利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-112">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="9a6c3-113">これらの問題に対処するために、Lync Server は **Grant-CsOuPermission** コマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-113">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="9a6c3-114">このコマンドレットでは、指定したコンテナーと組織単位、およびコンテナーまたは組織単位内のオブジェクトに対して、必要な Lync Server Ace を直接設定します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-114">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="9a6c3-115">ドメインの準備手続き以後のユーザー、InetOrgPerson、および連絡先オブジェクトに対するアクセス許可の設定</span><span class="sxs-lookup"><span data-stu-id="9a6c3-115">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="9a6c3-116">ロックダウンされた Active Directory 環境では、アクセス許可の継承が無効になるため、ドメインの準備手続きの中で、ドメイン内のユーザー オブジェクトや InetOrgPerson オブジェクトを収容するコンテナーまたは組織単位に必要な ACE が設定されません。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-116">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="9a6c3-117">このような状況では、アクセス許可の継承が無効になっているユーザー オブジェクトや InetOrgPerson オブジェクトを収容する各コンテナーまたは OU に対して **Grant-CsOuPermission** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-117">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="9a6c3-118">展開形態が中央フォレスト トポロジの場合は、連絡先オブジェクトを収容するコンテナーまたは OU に対しても、この手続きを実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-118">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="9a6c3-119">中央フォレストトポロジの詳細については、「サポート」のドキュメントの「supported [Active Directory トポロジ (Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-119">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="9a6c3-120">ObjectType パラメーターは、オブジェクト タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-120">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="9a6c3-121">OU パラメーターは組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-121">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="9a6c3-122">このコマンドレットは、指定したコンテナーまたは OU、およびそのコンテナー内のユーザー オブジェクトまたは InetOrgPerson オブジェクトで、必要な ACE を直接追加します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-122">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="9a6c3-123">このコマンドが実行される OU に、ユーザーオブジェクトまたは InetOrgPerson オブジェクトを持つ子 Ou がある場合、アクセス許可はそれらに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-123">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="9a6c3-124">各子 OU でコマンドを個別に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-124">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="9a6c3-125">これは、Lync ホスティング展開の一般的なシナリオです。たとえば、親 OU = OCS テナント、DC = CONTOSO、DC = ローカルおよび子 OU = Tenant1、OU = OCS テナント、DC = CONTOSO、DC = ローカルです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-125">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="9a6c3-126">このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-126">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="9a6c3-127">認証済みユーザーの Ace がロックダウンされた環境でも削除されている場合は、「 [認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md) されているか、または Enterprise Admins グループのメンバーであるアカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-127">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="9a6c3-128">**ユーザー、InetOrgPerson、および連絡先オブジェクトに必要な ACE を設定するには**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-128">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="9a6c3-129">Domain Admins グループのメンバー アカウントか、それと同等のユーザー権限を持つアカウントを使用して、ドメインに参加しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-129">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="9a6c3-130">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a6c3-131">実行</span><span class="sxs-lookup"><span data-stu-id="9a6c3-131">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="9a6c3-132">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-132">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="9a6c3-133">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-133">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="9a6c3-134">ログファイルで、 **\<Success\>** 各タスクの最後にある実行結果を検索して、アクセス許可が設定されていることを確認してから、[ログ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-134">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="9a6c3-135">次のコマンドで、アクセス許可が設定されたかどうかを調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-135">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="9a6c3-136">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-136">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="9a6c3-137">ドメイン準備手続き以後のコンピューター オブジェクトに対するアクセス許可の設定</span><span class="sxs-lookup"><span data-stu-id="9a6c3-137">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="9a6c3-138">ロックダウンされた Active Directory 環境ではアクセス許可の継承が無効になるため、ドメインの準備では、ドメイン内のコンピューター オブジェクトを収容するコンテナーまたは OU で必要な ACE が設定されません。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-138">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="9a6c3-139">このような状況では、アクセス許可の継承が無効になっている、Lync Server を実行しているコンピューターがある各コンテナーまたは OU で **Grant-CsOuPermission** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-139">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="9a6c3-140">ObjectType パラメーターは、オブジェクト タイプを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-140">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="9a6c3-141">この手続きを実行すると、必要な ACE が、指定したコンテナーに直接追加されます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-141">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="9a6c3-142">このコマンドレットを実行するには、Domain Admins グループ メンバーシップと同等のユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-142">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="9a6c3-143">認証済みユーザーの Ace も削除されている場合は、「 [認証済みユーザーのアクセス許可が Lync Server 2013 で削除](lync-server-2013-authenticated-user-permissions-are-removed.md) されているか、Enterprise Admins グループのメンバーであるアカウントを使用しています」の説明に従って、フォレストルートドメイン内の関連するコンテナーに対して、このアカウントに読み取りアクセス ace を付与する必要があります</span><span class="sxs-lookup"><span data-stu-id="9a6c3-143">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="9a6c3-144">**コンピューター オブジェクトに必要な ACE を設定するには**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-144">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="9a6c3-145">Domain Admins グループのメンバー アカウント、またはそれと同等のユーザー権限を持つアカウントを使用して、ドメインのコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-145">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="9a6c3-146">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9a6c3-147">実行</span><span class="sxs-lookup"><span data-stu-id="9a6c3-147">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="9a6c3-148">Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-148">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="9a6c3-149">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-149">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="9a6c3-150">ログファイル C: LogsOUPermissions.xml の例では \\ \\ 、 **\<Success\>** 各タスクの最後に実行結果を検索し、エラーがないことを確認してからログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-150">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="9a6c3-151">次のコマンドレットを実行してアクセス許可をテストできます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-151">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="9a6c3-152">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-152">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a6c3-153">ロックダウンされた Active Directory 環境で、フォレストのルートドメインでドメインの準備を実行する場合は、Lync Server に Active Directory スキーマおよび構成コンテナーへのアクセスが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-153">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="9a6c3-154">既定の認証済みユーザーのアクセス許可がスキーマまたは AD DS の構成コンテナーから削除された場合は、 &nbsp; スキーマ管理者グループ (スキーマコンテナーの場合) または Enterprise Admins グループ (構成コンテナーの場合) のメンバーのみが、指定したコンテナーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-154">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="9a6c3-155">Setup.exe、Lync Server 管理シェルコマンドレット、および Lync Server コントロールパネルでは、これらのコンテナーにアクセスする必要があるため、インストールを実行しているユーザーがスキーマ管理者と Enterprise Admins グループのメンバーシップに相当するユーザー権限を持っていない限り、管理ツールのセットアップとインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-155">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="9a6c3-156">この状況に対処するには、RTCUniversalGlobalWriteGroup グループに、スキーマ コンテナーと構成コンテナーへの読み取りおよび書き込みアクセス権を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-156">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

