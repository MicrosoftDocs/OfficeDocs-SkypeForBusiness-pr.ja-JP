---
title: 'Lync Server 2013: 管理者トポロジの権限をテストする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 365c879678ff3fd51dcaaf89d4b2593eccf645f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="05acb-102">Lync Server 2013 で管理者トポロジのテスト権限をテストする</span><span class="sxs-lookup"><span data-stu-id="05acb-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05acb-103">_**最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="05acb-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05acb-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="05acb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="05acb-105">最初の Lync Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="05acb-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="05acb-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="05acb-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05acb-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="05acb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="05acb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05acb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05acb-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="05acb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="05acb-110">Lync Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="05acb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="05acb-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsSetupPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="05acb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="05acb-112">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="05acb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="05acb-113">説明</span><span class="sxs-lookup"><span data-stu-id="05acb-113">Description</span></span>

<span data-ttu-id="05acb-114">既定では、ドメイン管理者のみが Lync Server トポロジを有効にして、Lync Server インフラストラクチャに大きな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="05acb-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="05acb-115">この問題は、ドメイン管理者と Lync Server の管理者が同じものである限り、問題になりません。多くの組織では、Lync Server の管理者は、ドメイン全体の管理権限を保持していません。</span><span class="sxs-lookup"><span data-stu-id="05acb-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="05acb-116">既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されます) は、Lync Server のトポロジを変更できません。</span><span class="sxs-lookup"><span data-stu-id="05acb-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="05acb-117">トポロジを変更する権利を RTCUniversalServerAdmins グループのメンバーに付与するには、[グラント Setuppermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="05acb-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="05acb-118">"CsSetupPermission テスト" コマンドレットは、Lync Server またはそのいずれかのコンポーネントのインストールに必要なアクセス許可が、指定された Active Directory コンテナーで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05acb-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="05acb-119">アクセス許可が割り当てられていない場合は、グラント Setuppermissions コマンドレットを実行して、Lync Server をインストールして有効にする権利を RTCUniversalServerAdmins グループのメンバーに付与することができます。</span><span class="sxs-lookup"><span data-stu-id="05acb-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05acb-120">Grant (CsSetupPermission アクセス許可によって割り当てられたアクセス許可の詳細<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx"></A>な一覧については、「ブログ投稿のアクセス許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05acb-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="05acb-121">テストの実行</span><span class="sxs-lookup"><span data-stu-id="05acb-121">Running the test</span></span>

<span data-ttu-id="05acb-122">Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、CsSetupPermission コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="05acb-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="05acb-123">確認するコンテナーの識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="05acb-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="05acb-124">たとえば、次のコマンドは、コンテナー ou = CsServers、dc = litwareinc、dc = com のセットアップアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="05acb-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="05acb-125">詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05acb-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="05acb-126">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="05acb-126">Determining success or failure</span></span>

<span data-ttu-id="05acb-127">Active Directory コンテナーで必要なアクセス許可が既に設定されていることを確認した場合、コマンドレットは値 True を返します。</span><span class="sxs-lookup"><span data-stu-id="05acb-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="05acb-128">True</span><span class="sxs-lookup"><span data-stu-id="05acb-128">True</span></span>

<span data-ttu-id="05acb-129">権限が設定されていない場合は、CsSetupPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="05acb-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="05acb-130">通常、この値は多くの警告メッセージで囲まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="05acb-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="05acb-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="05acb-131">For example:</span></span>

<span data-ttu-id="05acb-132">警告: アクセス制御エントリ (ACE) atl-cs-001\\RTCUniversalServerAdmins;許可ExtendedRight;--1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="05acb-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="05acb-133">警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="05acb-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="05acb-134">False</span><span class="sxs-lookup"><span data-stu-id="05acb-134">False</span></span>

<span data-ttu-id="05acb-135">警告: "Test-CsSetupPermission" 処理は、警告と共に完了します。</span><span class="sxs-lookup"><span data-stu-id="05acb-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="05acb-136">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="05acb-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="05acb-137">警告: 詳細な結果は、"C\\: Users\\管理者\\向け\\AppData\\ローカル\\一時テスト-cssetuppermission-1da99ba6-abe2-45e4-8b16-dfd244763118" にあります。</span><span class="sxs-lookup"><span data-stu-id="05acb-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="05acb-138">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="05acb-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="05acb-139">例外はまれにありますが、通常は、指定した Active Directory コンテナーに対するセットアップアクセス許可が割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="05acb-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="05acb-140">これらのアクセス許可を割り当てるには、グラント Setuppermission コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="05acb-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="05acb-141">たとえば、次のコマンドを実行すると、domain litwareinc.com の Computers コンテナーのセットアップ権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="05acb-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="05acb-142">詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05acb-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

