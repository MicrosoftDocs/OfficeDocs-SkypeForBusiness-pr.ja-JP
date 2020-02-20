---
title: 'Lync Server 2013: 管理者のアクセス許可のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d12707cbbd03181b5606c835d50bb2f173f10da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="537fb-102">Lync Server 2013 での管理者権限のテスト</span><span class="sxs-lookup"><span data-stu-id="537fb-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="537fb-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="537fb-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="537fb-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="537fb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="537fb-105">最初の Lync Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="537fb-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="537fb-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="537fb-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="537fb-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="537fb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="537fb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="537fb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="537fb-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="537fb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="537fb-110">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="537fb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="537fb-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsOUPermission コマンドレットを実行する権限を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="537fb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="537fb-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="537fb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="537fb-113">説明</span><span class="sxs-lookup"><span data-stu-id="537fb-113">Description</span></span>

<span data-ttu-id="537fb-114">セットアッププログラムによって実行されたタスクの Lync Server 2013 1 をインストールすると、RTCUniversalUserAdmins グループに、ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg ユーザーを管理するために必要な Active Directory のアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="537fb-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="537fb-115">Active Directory セットアップでアクセス許可の継承を無効にした場合は、これらのアクセス許可を割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="537fb-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="537fb-116">その結果、RTCUniversalUserAdmins グループのメンバーは Lync Server エンティティを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="537fb-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="537fb-117">これらの管理権限は、ドメイン管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="537fb-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="537fb-118">Test-CsOUPermission コマンドレットは、Active Directory コンテナーに対して、ユーザー、コンピューター、およびその他のオブジェクトの管理に必要なアクセス許可が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="537fb-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="537fb-119">これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)コマンドレットを実行することによって、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="537fb-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="537fb-120">RTCUniversalUserAdmins グループのメンバーに対してアクセス許可を割り当てることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="537fb-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="537fb-121">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="537fb-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="537fb-122">別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザーまたはグループを RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="537fb-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="537fb-123">OU アクセス許可の詳細については、「 [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでのアクセス許可の継承が無効になっ](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)ています。」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="537fb-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="537fb-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="537fb-124">Running the test</span></span>

<span data-ttu-id="537fb-125">管理アクセス許可がコンテナーに設定されていることを確認するには、Test-CsOUPermission コマンドレットを実行した後に、コンテナーの識別名、および検証するアクセス許可の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="537fb-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="537fb-126">たとえば、次のコマンドは、ユーザーのアクセス許可が OU ou = Redmond, dc = litwareinc, dc = com で設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="537fb-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="537fb-127">単一のコマンドを使用して複数のアクセス許可を確認するには、各アクセス許可の種類を二重引用符で囲み、コンマを使用してそれらの種類を区切ります。</span><span class="sxs-lookup"><span data-stu-id="537fb-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="537fb-128">たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="537fb-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="537fb-129">詳細については、 [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="537fb-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="537fb-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="537fb-130">Determining success or failure</span></span>

<span data-ttu-id="537fb-131">必要なアクセス許可が既に設定されている場合、Test-CsOUPermission は1単語の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="537fb-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="537fb-132">はい</span><span class="sxs-lookup"><span data-stu-id="537fb-132">True</span></span>

<span data-ttu-id="537fb-133">必要なアクセス許可が設定されていない場合、Test-CsOUPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="537fb-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="537fb-134">この値を見つけるには、少し時間を置いて検索する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="537fb-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="537fb-135">通常は、いくつかの付随する警告に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="537fb-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="537fb-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="537fb-136">For example:</span></span>

<span data-ttu-id="537fb-137">警告: アクセス制御エントリ (ACE) atl-fs-01\\RTCUniversalUserReadOnlyGroup;使うReadPropertyContainerInherit;子孫bf967aba-0de6-11d0-00aa003049e2;d819615a-4738 3b9b-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="537fb-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="537fb-138">警告: オブジェクト "OU = NorthAmerica, DC =\\LITWAREINC, dc = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="537fb-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="537fb-139">False</span><span class="sxs-lookup"><span data-stu-id="537fb-139">False</span></span>

<span data-ttu-id="537fb-140">警告: "Test-CsOUPermission" 処理は完了しましたが、警告があります。</span><span class="sxs-lookup"><span data-stu-id="537fb-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="537fb-141">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="537fb-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="537fb-142">警告: 詳細な結果は、"C\\: Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de" にあります。</span><span class="sxs-lookup"><span data-stu-id="537fb-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="537fb-143">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="537fb-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="537fb-144">Test-CsOUPermission が失敗した場合は、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="537fb-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="537fb-145">この問題を解決して、Grant-CsOUPermission コマンドレットを使用して必要なアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="537fb-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="537fb-146">たとえば、次のコマンドを実行すると、ユーザー、連絡先、および inetOrgPersons の OU 権限が RTCUniversalUserAdmins グループに付与されます。</span><span class="sxs-lookup"><span data-stu-id="537fb-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="537fb-147">詳細については、Grant-CsOUPermission コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="537fb-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

