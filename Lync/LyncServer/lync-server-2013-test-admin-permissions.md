---
title: 'Lync Server 2013: 管理者権限をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="51349-102">Lync Server 2013 で管理者権限をテストする</span><span class="sxs-lookup"><span data-stu-id="51349-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51349-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="51349-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51349-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="51349-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="51349-105">最初の Lync Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="51349-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="51349-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="51349-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51349-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="51349-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="51349-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51349-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51349-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="51349-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="51349-110">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="51349-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="51349-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsOUPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="51349-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="51349-112">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="51349-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="51349-113">説明</span><span class="sxs-lookup"><span data-stu-id="51349-113">Description</span></span>

<span data-ttu-id="51349-114">セットアッププログラムによって実行されたタスクの Lync Server 2013 1 をインストールすると、RTCUniversalUserAdmins グループにユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg の管理に必要な Active Directory のアクセス許可が与えられます。</span><span class="sxs-lookup"><span data-stu-id="51349-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="51349-115">Active Directory で権限の継承を無効にしている場合は、セットアップでそれらのアクセス許可を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="51349-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="51349-116">この結果、RTCUniversalUserAdmins グループのメンバーは Lync Server のエンティティを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="51349-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="51349-117">これらの管理権限は、ドメイン管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="51349-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="51349-118">ユーザー、コンピューター、その他のオブジェクトを管理するために必要な権限が Active Directory コンテナーに設定されているかどうかを確認するため、CsOUPermission のテストコマンドレットを確認します。</span><span class="sxs-lookup"><span data-stu-id="51349-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="51349-119">これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)コマンドレットを実行することで、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="51349-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="51349-120">ただし、権限の付与は、RTCUniversalUserAdmins グループのメンバーに対してのみ権限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="51349-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="51349-121">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="51349-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="51349-122">別のユーザーまたはグループにユーザー管理のアクセス許可を与える必要がある場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51349-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="51349-123">OU のアクセス許可の詳細については、「 [Lync Server 2013 のコンピューター、ユーザー、または InetOrgPerson コンテナーでアクセス許可の継承が無効になっている](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51349-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="51349-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="51349-124">Running the test</span></span>

<span data-ttu-id="51349-125">コンテナーに管理権限が設定されていることを確認するには、CsOUPermission コマンドレットを実行し、その後に、コンテナーの識別名と確認するアクセス許可の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="51349-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="51349-126">たとえば、次のコマンドは、ユーザー権限が OU ou で設定されているかどうかを確認します。 Redmond、dc = litwareinc、dc = com:</span><span class="sxs-lookup"><span data-stu-id="51349-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="51349-127">1つのコマンドを使用して複数のアクセス許可を確認するには、それぞれのアクセス許可の種類を引用符で囲んで囲み、コンマを使用してそれらの型を区切ります。</span><span class="sxs-lookup"><span data-stu-id="51349-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="51349-128">たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="51349-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="51349-129">詳細については、「 [CsOUPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51349-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="51349-130">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="51349-130">Determining success or failure</span></span>

<span data-ttu-id="51349-131">必要な権限が既に設定されている場合は、次のようにして、Test-CsOUPermission は1単語の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="51349-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="51349-132">True</span><span class="sxs-lookup"><span data-stu-id="51349-132">True</span></span>

<span data-ttu-id="51349-133">必要なアクセス許可が設定されていない場合は、"False" という値が返されます。</span><span class="sxs-lookup"><span data-stu-id="51349-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="51349-134">この値を検索するには、少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51349-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="51349-135">通常は、いくつかの関連する警告内に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="51349-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="51349-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="51349-136">For example:</span></span>

<span data-ttu-id="51349-137">警告: アクセス制御エントリ (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup;許可ReadProperty;ContainerInherit;フォルダーbf967aba-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="51349-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="51349-138">警告: オブジェクト "OU = NorthAmerica, DC = atl-\\litwareinc, dc = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="51349-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="51349-139">False</span><span class="sxs-lookup"><span data-stu-id="51349-139">False</span></span>

<span data-ttu-id="51349-140">警告: "Test-CsOUPermission" 処理は警告で完了しています。</span><span class="sxs-lookup"><span data-stu-id="51349-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="51349-141">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="51349-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="51349-142">警告: 詳細\\な結果は "C: Users\\管理者\\向け AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de" にあります。</span><span class="sxs-lookup"><span data-stu-id="51349-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="51349-143">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="51349-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="51349-144">RTCUniversalUserAdmins のテストに失敗した場合、通常は、指定したアクセス許可がグループに割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="51349-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="51349-145">この問題を解決して、必要なアクセス許可を割り当てるには、アクセス許可の付与コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51349-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="51349-146">たとえば、次のコマンドを実行すると、ユーザー、連絡先、inetOrgPersons に対して、RTCUniversalUserAdmins グループに OU 権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="51349-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="51349-147">詳細については、「Grant-CsOUPermission」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51349-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

