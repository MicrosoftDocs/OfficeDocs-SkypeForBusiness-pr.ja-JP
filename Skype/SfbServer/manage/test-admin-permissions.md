---
title: Skype for Business Server での管理アクセス許可のテスト
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
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122401"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="79ddd-103">Skype for Business Server での管理アクセス許可のテスト</span><span class="sxs-lookup"><span data-stu-id="79ddd-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="79ddd-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="79ddd-104">Verification schedule</span></span>|<span data-ttu-id="79ddd-105">Skype for Business Server の初期展開後。</span><span class="sxs-lookup"><span data-stu-id="79ddd-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="79ddd-106">必要に応じて、アクセス許可に関連する問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="79ddd-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="79ddd-107">テスト ツール</span><span class="sxs-lookup"><span data-stu-id="79ddd-107">Testing tool</span></span>|<span data-ttu-id="79ddd-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ddd-108">Windows PowerShell</span></span>|
|<span data-ttu-id="79ddd-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="79ddd-109">Permissions required</span></span>|<span data-ttu-id="79ddd-110">Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="79ddd-111">リモート インスタンスを使用して Windows PowerShellを実行する場合、ユーザーには、このコマンドレットを実行するアクセス許可を持つ RBAC ロールTest-CsOUPermissionがあります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="79ddd-112">このコマンドレットを使用できるすべての RBAC 役割の一覧を表示するには、次のコマンドをプロンプトからWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="79ddd-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="79ddd-113">Get-CsAdminRoleWhere-Object \| {$_.コマンドレット -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="79ddd-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="79ddd-114">説明</span><span class="sxs-lookup"><span data-stu-id="79ddd-114">Description</span></span>

<span data-ttu-id="79ddd-115">Skype for Business Server をインストールすると、セットアップ プログラムによって実行されたタスクの 1 つが、ユーザー、コンピューター、連絡先、アプリケーション連絡先、および InetOrg ユーザーを管理するために必要な Active Directory アクセス許可を RTCUniversalUserAdmins グループに与えます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="79ddd-116">Active Directory でアクセス許可の継承を無効にしている場合、セットアップではこれらのアクセス許可を割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="79ddd-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="79ddd-117">その結果、RTCUniversalUserAdmins グループのメンバーは Skype for Business Server エンティティを管理できません。</span><span class="sxs-lookup"><span data-stu-id="79ddd-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="79ddd-118">これらの管理特権は、ドメイン管理者だけが利用できます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="79ddd-119">このTest-CsOUPermissionコマンドレットは、ユーザー、コンピューター、その他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="79ddd-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="79ddd-120">これらのアクセス許可が設定されていない場合は [、Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission)コマンドレットを実行して、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="79ddd-121">RTCUniversalUserAdmins グループのメンバーにのみアクセス許可を割り当てGrant-CsOUPermissionに注意してください。</span><span class="sxs-lookup"><span data-stu-id="79ddd-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="79ddd-122">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="79ddd-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="79ddd-123">別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="79ddd-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="79ddd-124">Running the test</span></span>

<span data-ttu-id="79ddd-125">管理アクセス許可がコンテナーに設定されているのを確認するには、Test-CsOUPermission コマンドレットの後にコンテナーの識別名と、確認するアクセス許可の種類を指定して実行します。</span><span class="sxs-lookup"><span data-stu-id="79ddd-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="79ddd-126">たとえば、次のコマンドは、OU ou=Redmond、dc=litwareinc、dc=com でユーザーアクセス許可が設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="79ddd-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="79ddd-127">1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符で囲まれた各アクセス許可の種類を囲み、コンマを使用してそれらの種類を区切ります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="79ddd-128">たとえば、次の 1 つのコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="79ddd-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="79ddd-129">詳細については、このコマンドレットの [ヘルプ トピックをTest-CsOUPermissionしてください](/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="79ddd-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="79ddd-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="79ddd-130">Determining success or failure</span></span>

<span data-ttu-id="79ddd-131">必要なアクセス許可が既に設定されている場合、Test-CsOUPermission応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="79ddd-132">True</span><span class="sxs-lookup"><span data-stu-id="79ddd-132">True</span></span>

<span data-ttu-id="79ddd-133">必要なアクセス許可が設定されていない場合、Test-CsOUPermission False が返されます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="79ddd-134">この値を見つけるには、しばらく検索する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="79ddd-135">通常、いくつかの付随する警告の内部に埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ddd-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="79ddd-136">例:</span><span class="sxs-lookup"><span data-stu-id="79ddd-136">For example:</span></span>

<span data-ttu-id="79ddd-137">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;allow;ReadProperty;ContainerInherit;Descendents;bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="79ddd-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="79ddd-138">警告: オブジェクト "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" のアクセス制御エントリ (ACEs) は準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="79ddd-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="79ddd-139">False</span><span class="sxs-lookup"><span data-stu-id="79ddd-139">False</span></span> 

<span data-ttu-id="79ddd-140">警告: "Test-CsOUPermission" 処理が完了し、警告が表示されました。</span><span class="sxs-lookup"><span data-stu-id="79ddd-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="79ddd-141">"2" 警告は、この実行時に記録されました。</span><span class="sxs-lookup"><span data-stu-id="79ddd-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="79ddd-142">警告: 詳細な結果は"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" で確認できます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="79ddd-143">テストが失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="79ddd-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="79ddd-144">エラーTest-CsOUPermission場合は、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="79ddd-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="79ddd-145">この問題を解決し、必要なアクセス許可を割り当てるには、このコマンドレットを使用Grant-CsOUPermissionできます。</span><span class="sxs-lookup"><span data-stu-id="79ddd-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="79ddd-146">たとえば、このコマンドは、ユーザー、連絡先、および inetOrgPersons に対する OU アクセス許可を RTCUniversalUserAdmins グループに付与します。</span><span class="sxs-lookup"><span data-stu-id="79ddd-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="79ddd-147">詳細については、このコマンドレットの [ヘルプ トピックをTest-CsOUPermissionしてください](/powershell/module/skype/test-csoupermission)。</span><span class="sxs-lookup"><span data-stu-id="79ddd-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>