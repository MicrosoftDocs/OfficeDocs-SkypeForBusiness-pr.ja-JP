---
title: 'Lync Server 2013: 管理者トポロジのテスト権限'
description: 'Lync Server 2013: 管理者トポロジのテスト権限。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d713297d0e944c7acbc5efcb11b21ea1b26639
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568563"
---
# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="1977c-103">Lync Server 2013 での管理者トポロジのテスト権限</span><span class="sxs-lookup"><span data-stu-id="1977c-103">Test admin topology rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1977c-104">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="1977c-104">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1977c-105">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="1977c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1977c-106">最初の Lync Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="1977c-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="1977c-107">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1977c-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1977c-108">テストツール</span><span class="sxs-lookup"><span data-stu-id="1977c-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1977c-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1977c-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1977c-110">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1977c-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1977c-111">Lync Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1977c-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1977c-112">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには Test-CsSetupPermission コマンドレットを実行するためのアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1977c-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1977c-113">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1977c-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1977c-114">説明</span><span class="sxs-lookup"><span data-stu-id="1977c-114">Description</span></span>

<span data-ttu-id="1977c-115">既定では、ドメイン管理者のみが Lync Server トポロジを有効にし、Lync Server インフラストラクチャに大きな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="1977c-115">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="1977c-116">ドメイン管理者と Lync Server 管理者が同一である限り、これは問題になりません。多くの組織では、Lync Server 管理者はドメイン全体に対する管理権限を保持していません。</span><span class="sxs-lookup"><span data-stu-id="1977c-116">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="1977c-117">既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されている) が Lync Server トポロジを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1977c-117">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="1977c-118">RTCUniversalServerAdmins グループのメンバーがトポロジを変更できるようにするには、必要な Active Directory アクセス許可を付与するために、 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1977c-118">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="1977c-119">Test-CsSetupPermission コマンドレットは、Lync Server またはそのコンポーネントのいずれかをインストールするために必要なアクセス許可が、指定された Active Directory コンテナーに対して構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1977c-119">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="1977c-120">アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Lync Server をインストールして有効にする権限を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="1977c-120">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1977c-121">Grant-CsSetupPermission によって割り当てられるアクセス許可の詳細な一覧については、ブログ投稿 <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">付与-cssetuppermission および grant-Cssetuppermission</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1977c-121">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1977c-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="1977c-122">Running the test</span></span>

<span data-ttu-id="1977c-123">Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを確認するには、Test-CsSetupPermission コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1977c-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1977c-124">確認するコンテナーの識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1977c-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="1977c-125">たとえば、次のコマンドは、コンテナー ou = CsServers, dc = litwareinc, dc = com: に対するセットアップのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="1977c-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="1977c-126">詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1977c-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1977c-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="1977c-127">Determining success or failure</span></span>

<span data-ttu-id="1977c-128">Active Directory コンテナーで必要なアクセス許可が既に設定されていることが Test-CsSetupPermission 場合は、コマンドレットは値 True を返します。</span><span class="sxs-lookup"><span data-stu-id="1977c-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="1977c-129">正</span><span class="sxs-lookup"><span data-stu-id="1977c-129">True</span></span>

<span data-ttu-id="1977c-130">アクセス許可が設定されていない場合、Test-CsSetupPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="1977c-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="1977c-131">この値は通常、多くの警告メッセージで囲まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1977c-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="1977c-132">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1977c-132">For example:</span></span>

<span data-ttu-id="1977c-133">警告: アクセス制御エントリ (ACE) atl-fs-01 \\ RTCUniversalServerAdmins;使うExtendedRight;該当該当1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="1977c-133">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="1977c-134">警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="1977c-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="1977c-135">False</span><span class="sxs-lookup"><span data-stu-id="1977c-135">False</span></span>

<span data-ttu-id="1977c-136">警告: "Test-CsSetupPermission" 処理は完了しましたが、警告があります。</span><span class="sxs-lookup"><span data-stu-id="1977c-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="1977c-137">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="1977c-137">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="1977c-138">警告: 詳細な結果は、「C: \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」にあります。</span><span class="sxs-lookup"><span data-stu-id="1977c-138">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1977c-139">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="1977c-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="1977c-140">まれに例外がありますが、Test-CsSetupPermission 失敗した場合は、指定された Active Directory コンテナーにセットアップのアクセス許可が割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1977c-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="1977c-141">これらのアクセス許可は Grant-CsSetupPermission コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1977c-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="1977c-142">たとえば、次のコマンドは、ドメイン litwareinc.com の Computers コンテナーに対するセットアップのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1977c-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="1977c-143">詳細については、 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1977c-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

