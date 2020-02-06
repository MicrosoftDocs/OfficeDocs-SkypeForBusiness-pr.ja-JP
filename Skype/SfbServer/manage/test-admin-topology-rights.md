---
title: Skype for Business Server で管理者トポロジの権限をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server でトポロジの権限をテストする方法
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817313"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="b2198-103">Skype for Business Server で管理者トポロジの権限をテストする</span><span class="sxs-lookup"><span data-stu-id="b2198-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="b2198-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="b2198-104">Verification schedule</span></span>|<span data-ttu-id="b2198-105">初めての Skype for Business Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="b2198-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="b2198-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="b2198-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="b2198-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="b2198-107">Testing tool</span></span>|<span data-ttu-id="b2198-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2198-108">Windows PowerShell</span></span>|
|<span data-ttu-id="b2198-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b2198-109">Permissions required</span></span>|<span data-ttu-id="b2198-110">Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2198-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="b2198-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsSetupPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2198-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b2198-112">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2198-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="b2198-113">を\|取得します。-オブジェクト {$ _コマンドレット-match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="b2198-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="b2198-114">説明</span><span class="sxs-lookup"><span data-stu-id="b2198-114">Description</span></span>

<span data-ttu-id="b2198-115">既定では、ドメイン管理者のみが Skype for business Server のトポロジを有効にして、Skype for Business Server インフラストラクチャに大きな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="b2198-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="b2198-116">これは、ドメイン管理者と Skype for Business Server の管理者がどちらも同じである限り、問題になりません。</span><span class="sxs-lookup"><span data-stu-id="b2198-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="b2198-117">多くの組織では、Skype for Business Server の管理者は、ドメイン全体の管理権限を保持していません。</span><span class="sxs-lookup"><span data-stu-id="b2198-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="b2198-118">既定では、これらの管理者 (RTCUniversalServerAdmins グループのメンバーとして定義されます) は、Skype for Business Server のトポロジを変更できません。</span><span class="sxs-lookup"><span data-stu-id="b2198-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="b2198-119">トポロジを変更する権利を RTCUniversalServerAdmins グループのメンバーに付与するには、[グラント Setuppermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2198-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="b2198-120">テスト用のセットアップアクセス許可コマンドレットを使用して、Skype for Business Server またはそのコンポーネントのいずれかをインストールするために必要なアクセス許可が、指定した Active Directory コンテナーで構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2198-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="b2198-121">アクセス許可が割り当てられていない場合は、グラント Setuppermission コマンドレットを実行して、RTCUniversalServerAdmins グループのメンバーに Skype for Business Server をインストールして有効にする権利を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="b2198-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="b2198-122">テストの実行</span><span class="sxs-lookup"><span data-stu-id="b2198-122">Running the test</span></span>

<span data-ttu-id="b2198-123">Active Directory コンテナーにセットアップのアクセス許可が割り当てられているかどうかを判断するには、CsSetupPermission コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b2198-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b2198-124">確認するコンテナーの識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2198-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="b2198-125">たとえば、次のコマンドは、コンテナー ou = CsServers、dc = litwareinc、dc = com のセットアップアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2198-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="b2198-126">詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2198-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b2198-127">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="b2198-127">Determining success or failure</span></span>

<span data-ttu-id="b2198-128">Active Directory コンテナーで必要なアクセス許可が既に設定されていることを確認した場合、コマンドレットは値 True を返します。</span><span class="sxs-lookup"><span data-stu-id="b2198-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="b2198-129">True</span><span class="sxs-lookup"><span data-stu-id="b2198-129">True</span></span> 

<span data-ttu-id="b2198-130">権限が設定されていない場合は、CsSetupPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="b2198-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="b2198-131">通常、この値は多くの警告メッセージで囲まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2198-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="b2198-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b2198-132">For example:</span></span>

<span data-ttu-id="b2198-133">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalServerAdmins許可ExtendedRight;--1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="b2198-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="b2198-134">警告: オブジェクト "CN = Computers, DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="b2198-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="b2198-135">False</span><span class="sxs-lookup"><span data-stu-id="b2198-135">False</span></span> 

<span data-ttu-id="b2198-136">警告: "Test-CsSetupPermission" 処理は、警告と共に完了します。</span><span class="sxs-lookup"><span data-stu-id="b2198-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="b2198-137">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="b2198-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="b2198-138">警告: 詳細な結果は "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" に記載されています。</span><span class="sxs-lookup"><span data-stu-id="b2198-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b2198-139">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="b2198-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="b2198-140">例外はまれにありますが、通常は、指定した Active Directory コンテナーに対するセットアップアクセス許可が割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b2198-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="b2198-141">これらのアクセス許可を割り当てるには、グラント Setuppermission コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2198-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="b2198-142">たとえば、次のコマンドを実行すると、domain litwareinc.com の Computers コンテナーのセットアップ権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="b2198-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="b2198-143">詳細については、「 [CsSetupPermission のテスト](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2198-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
