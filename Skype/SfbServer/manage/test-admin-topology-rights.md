---
title: Skype for Business Server での管理トポロジ権限のテスト
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
description: Skype for Business Server でトポロジ権限をテストする方法
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832847"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="165b5-103">Skype for Business Server での管理トポロジ権限のテスト</span><span class="sxs-lookup"><span data-stu-id="165b5-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="165b5-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="165b5-104">Verification schedule</span></span>|<span data-ttu-id="165b5-105">Skype for Business Server の初期展開後。</span><span class="sxs-lookup"><span data-stu-id="165b5-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="165b5-106">必要に応じて、アクセス許可関連の問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="165b5-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="165b5-107">テスト ツール</span><span class="sxs-lookup"><span data-stu-id="165b5-107">Testing tool</span></span>|<span data-ttu-id="165b5-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="165b5-108">Windows PowerShell</span></span>|
|<span data-ttu-id="165b5-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="165b5-109">Permissions required</span></span>|<span data-ttu-id="165b5-110">Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="165b5-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="165b5-111">Windows PowerShell のリモート インスタンスを使用して実行する場合、ユーザーには、Test-CsSetupPermission コマンドレットを実行するアクセス許可を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="165b5-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="165b5-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、次のコマンドをプロンプトWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="165b5-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="165b5-113">Get-CsAdminRoleWhere-Object \| {$_.Cmdlets -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="165b5-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="165b5-114">説明</span><span class="sxs-lookup"><span data-stu-id="165b5-114">Description</span></span>

<span data-ttu-id="165b5-115">既定では、ドメイン管理者だけが Skype for Business Server トポロジを有効にし、Skype for Business Server インフラストラクチャに大きな変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="165b5-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="165b5-116">ドメイン管理者と Skype for Business Server 管理者が同一である限り、これは問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="165b5-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="165b5-117">多くの組織では、Skype for Business Server 管理者はドメイン全体に対する管理者権限を保持しません。</span><span class="sxs-lookup"><span data-stu-id="165b5-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="165b5-118">既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されている管理者) は Skype for Business Server トポロジを変更できません。</span><span class="sxs-lookup"><span data-stu-id="165b5-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="165b5-119">RTCUniversalServerAdmins グループのメンバーにトポロジを変更する権限を付与するには [、Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) コマンドレットを使用して必要な Active Directory アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="165b5-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="165b5-120">次Test-CsSetupPermissionコマンドレットは、Skype for Business Server またはそのコンポーネントの 1 つをインストールするために必要なアクセス許可が、指定された Active Directory コンテナーに構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="165b5-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="165b5-121">アクセス許可が割り当てられていない場合は、Grant-CsSetupPermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Skype for Business Server をインストールして有効にする権限を付与できます。</span><span class="sxs-lookup"><span data-stu-id="165b5-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="165b5-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="165b5-122">Running the test</span></span>

<span data-ttu-id="165b5-123">Active Directory コンテナーに対してセットアップのアクセス許可が割り当てられているかどうかを確認するには、次のコマンドレットTest-CsSetupPermissionします。</span><span class="sxs-lookup"><span data-stu-id="165b5-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="165b5-124">確認するコンテナーの識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="165b5-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="165b5-125">たとえば、次のコマンドは、コンテナー ou=CsServers,dc=litwareinc,dc=com に対するセットアップのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="165b5-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="165b5-126">詳細については [、Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="165b5-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="165b5-127">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="165b5-127">Determining success or failure</span></span>

<span data-ttu-id="165b5-128">Active Directory Test-CsSetupPermissionに必要なアクセス許可が既に設定されている場合、コマンドレットは値 True を返します。</span><span class="sxs-lookup"><span data-stu-id="165b5-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="165b5-129">正</span><span class="sxs-lookup"><span data-stu-id="165b5-129">True</span></span> 

<span data-ttu-id="165b5-130">アクセス許可が設定されていない場合、Test-CsSetupPermission False が返されます。</span><span class="sxs-lookup"><span data-stu-id="165b5-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="165b5-131">通常、この値は多くの警告メッセージで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="165b5-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="165b5-132">例:</span><span class="sxs-lookup"><span data-stu-id="165b5-132">For example:</span></span>

<span data-ttu-id="165b5-133">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins;許可;ExtendedRight;なし。なし。1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="165b5-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="165b5-134">警告: オブジェクト "CN=Computers,DC=litwareinc,DC=com" のアクセス制御エントリ (ES) は準備ができていない。</span><span class="sxs-lookup"><span data-stu-id="165b5-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="165b5-135">False</span><span class="sxs-lookup"><span data-stu-id="165b5-135">False</span></span> 

<span data-ttu-id="165b5-136">警告: "Test-CsSetupPermission" 処理が完了し、警告が表示されました。</span><span class="sxs-lookup"><span data-stu-id="165b5-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="165b5-137">この実行時に"2" の警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="165b5-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="165b5-138">警告: 詳細な結果については、「C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="165b5-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="165b5-139">テストが失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="165b5-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="165b5-140">まれな例外は発生しますが、Test-CsSetupPermission失敗した場合は、通常、指定した Active Directory コンテナーに対してセットアップのアクセス許可が割り当てられていないという意味になります。</span><span class="sxs-lookup"><span data-stu-id="165b5-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="165b5-141">これらのアクセス許可は、次のコマンドレットを使用Grant-CsSetupPermissionできます。</span><span class="sxs-lookup"><span data-stu-id="165b5-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="165b5-142">たとえば、次のコマンドを実行すると、ドメイン ドメイン内の Computers コンテナーに対するセットアップアクセス許可がlitwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="165b5-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="165b5-143">詳細については [、Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="165b5-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
