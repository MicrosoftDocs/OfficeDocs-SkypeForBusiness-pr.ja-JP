---
title: Skype for Business Server での管理者アクセス許可のテスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server で管理者のアクセス許可をテストする方法
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800097"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="b57ab-103">Skype for Business Server での管理者アクセス許可のテスト</span><span class="sxs-lookup"><span data-stu-id="b57ab-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="b57ab-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="b57ab-104">Verification schedule</span></span>|<span data-ttu-id="b57ab-105">Skype for Business Server の初期展開後。</span><span class="sxs-lookup"><span data-stu-id="b57ab-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="b57ab-106">必要に応じて、アクセス許可関連の問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="b57ab-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="b57ab-107">テスト ツール</span><span class="sxs-lookup"><span data-stu-id="b57ab-107">Testing tool</span></span>|<span data-ttu-id="b57ab-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b57ab-108">Windows PowerShell</span></span>|
|<span data-ttu-id="b57ab-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b57ab-109">Permissions required</span></span>|<span data-ttu-id="b57ab-110">Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="b57ab-111">Windows PowerShell のリモート インスタンスを使用して実行する場合、ユーザーには、Test-CsOUPermission コマンドレットを実行するアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b57ab-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、コマンド プロンプトから次のコマンドWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="b57ab-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="b57ab-113">Get-CsAdminRoleWhere-Object \| {$_.Cmdlets -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="b57ab-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="b57ab-114">説明</span><span class="sxs-lookup"><span data-stu-id="b57ab-114">Description</span></span>

<span data-ttu-id="b57ab-115">Skype for Business Server をインストールすると、セットアップ プログラムによって実行されたタスクの 1 つが、RTCUniversalUserAdmins グループに、ユーザー、コンピューター、連絡先、アプリケーション連絡先、および InetOrg ユーザーを管理するために必要な Active Directory アクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="b57ab-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="b57ab-116">Active Directory でアクセス許可の継承を無効にした場合、セットアップはそれらのアクセス許可を割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="b57ab-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="b57ab-117">その結果、RTCUniversalUserAdmins グループのメンバーは Skype for Business Server エンティティを管理できません。</span><span class="sxs-lookup"><span data-stu-id="b57ab-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="b57ab-118">これらの管理特権は、ドメイン管理者だけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="b57ab-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="b57ab-119">このTest-CsOUPermissionコマンドレットは、ユーザー、コンピューター、および他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="b57ab-120">これらのアクセス許可が設定されていない場合は [、Grant-CsOUPermission コマンドレットを実行してこの問題を解決できます](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)。</span><span class="sxs-lookup"><span data-stu-id="b57ab-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="b57ab-121">アクセス許可Grant-CsOUPermission RTCUniversalUserAdmins グループのメンバーにのみ割り当て可能です。</span><span class="sxs-lookup"><span data-stu-id="b57ab-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b57ab-122">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="b57ab-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="b57ab-123">別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="b57ab-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="b57ab-124">Running the test</span></span>

<span data-ttu-id="b57ab-125">管理アクセス許可がコンテナーに設定されているのを確認するには、Test-CsOUPermission コマンドレットの後にコンテナーの識別名と、確認するアクセス許可の種類を指定して実行します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="b57ab-126">たとえば、次のコマンドは、OU ou=Redmond,dc=litwareinc,dc=com にユーザーのアクセス許可が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="b57ab-127">1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符で囲まれた各アクセス許可の種類を囲み、コンマを使用してそれらの種類を区切ります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="b57ab-128">たとえば、次の 1 つのコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="b57ab-129">詳細については、このコマンドレットの [ヘルプ トピックTest-CsOUPermissionしてください](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="b57ab-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b57ab-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="b57ab-130">Determining success or failure</span></span>

<span data-ttu-id="b57ab-131">必要なアクセス許可が既に設定されている場合、Test-CsOUPermission 1 単語の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="b57ab-132">正</span><span class="sxs-lookup"><span data-stu-id="b57ab-132">True</span></span>

<span data-ttu-id="b57ab-133">必要なアクセス許可が設定されていない場合、Test-CsOUPermission False が返されます。</span><span class="sxs-lookup"><span data-stu-id="b57ab-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="b57ab-134">この値を検索するには、しばらく検索する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="b57ab-135">通常は、いくつかの付随する警告の中に埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57ab-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="b57ab-136">例:</span><span class="sxs-lookup"><span data-stu-id="b57ab-136">For example:</span></span>

<span data-ttu-id="b57ab-137">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;allow;ReadProperty;ContainerInherit;子孫;bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="b57ab-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="b57ab-138">警告: オブジェクト "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" のアクセス制御エントリ (ACEs) は準備ができていない。</span><span class="sxs-lookup"><span data-stu-id="b57ab-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="b57ab-139">False</span><span class="sxs-lookup"><span data-stu-id="b57ab-139">False</span></span> 

<span data-ttu-id="b57ab-140">警告: "Test-CsOUPermission" 処理が完了し、警告が表示されました。</span><span class="sxs-lookup"><span data-stu-id="b57ab-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="b57ab-141">この実行時に"2" という警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="b57ab-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="b57ab-142">警告: 詳細な結果については、「C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b57ab-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b57ab-143">テストが失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="b57ab-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="b57ab-144">このTest-CsOUPermission、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="b57ab-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="b57ab-145">この問題を解決し、必要なアクセス許可を割り当てるには、次のコマンドレットGrant-CsOUPermissionします。</span><span class="sxs-lookup"><span data-stu-id="b57ab-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="b57ab-146">たとえば、次のコマンドは、ユーザー、連絡先、および inetOrgPersons の OU アクセス許可を RTCUniversalUserAdmins グループに付与します。</span><span class="sxs-lookup"><span data-stu-id="b57ab-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="b57ab-147">詳細については、このコマンドレットの [ヘルプ トピックTest-CsOUPermissionしてください](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="b57ab-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
