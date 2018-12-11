---
title: Skype のビジネス サーバーのトポロジの管理者権限をテスト
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype のビジネス サーバーのトポロジの権限をテストする方法
ms.openlocfilehash: 6a1bbd6c052acb6488189e466522edf1aa59f2cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222822"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="6d939-103">Skype のビジネス サーバーのトポロジの管理者権限をテスト</span><span class="sxs-lookup"><span data-stu-id="6d939-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="6d939-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="6d939-104">Verification schedule</span></span>|<span data-ttu-id="6d939-105">後ビジネス サーバーの展開の初期の Skype です。</span><span class="sxs-lookup"><span data-stu-id="6d939-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="6d939-106">必要に応じてアクセス許可に関連する問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="6d939-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="6d939-107">テスト ツール</span><span class="sxs-lookup"><span data-stu-id="6d939-107">Testing tool</span></span>|<span data-ttu-id="6d939-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d939-108">Windows PowerShell</span></span>|
|<span data-ttu-id="6d939-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="6d939-109">Permissions required</span></span>|<span data-ttu-id="6d939-110">ビジネス サーバー管理シェルには、Skype を使用してローカルで実行するとユーザーは RTCUniversalServerAdmins のセキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d939-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="6d939-111">実行すると、Windows PowerShell のリモート インスタンスを使用してユーザーがテスト CsSetupPermission コマンドレットを実行する権限を持っている RBAC の役割を割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d939-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6d939-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d939-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="6d939-113">Get CsAdminRole \| Where-object {$_ です。コマンドレットの「テスト CsSetupPermission」に一致。</span><span class="sxs-lookup"><span data-stu-id="6d939-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="6d939-114">説明</span><span class="sxs-lookup"><span data-stu-id="6d939-114">Description</span></span>

<span data-ttu-id="6d939-115">既定では、ドメイン管理者のみが、Skype ビジネス サーバー トポロジを有効にしてビジネスのサーバー インフラストラクチャの Skype に大きな変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="6d939-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="6d939-116">問題として、ドメイン管理者およびビジネスのサーバー管理者のため、Skype では、1 つ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6d939-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="6d939-117">多くの組織でビジネスのサーバー管理者のための Skype は、ドメイン全体に対する管理者権限を保持しないでください。</span><span class="sxs-lookup"><span data-stu-id="6d939-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="6d939-118">既定では、(RTCUniversalServerAdmins グループのメンバーとして定義されている)、これらの管理者がビジネスのサーバー トポロジの変更の Skype をすることはできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6d939-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="6d939-119">RTCUniversalServerAdmins グループ トポロジを変更する権限のメンバーを与えるには、 [Grant CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission)コマンドレットを使用して、必要な Active Directory のアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d939-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="6d939-120">テスト CsSetupPermission コマンドレットは、指定した Active Directory コンテナーに必要な Business Server またはそのコンポーネントのいずれかの Skype をインストールするために必要なアクセス許可が構成されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d939-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="6d939-121">アクセス許可が割り当てられていない場合は、RTCUniversalServerAdmins グループのメンバーにインストールし、ビジネスのサーバーで Skype を有効にする権限を付与する Grant CsSetupPermission コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d939-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="6d939-122">テストを実行しています。</span><span class="sxs-lookup"><span data-stu-id="6d939-122">Running the test</span></span>

<span data-ttu-id="6d939-123">セットアップ アクセス許可が Active Directory コンテナーに割り当てられたかどうかを確認するのには、テスト CsSetupPermission コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6d939-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6d939-124">チェックするコンテナーの識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d939-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="6d939-125">このコマンドがコンテナー ou のアクセス許可を設定を確認するたとえば、= CsServers、dc = litwareinc、dc = com。</span><span class="sxs-lookup"><span data-stu-id="6d939-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="6d939-126">詳細については、[テスト CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d939-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6d939-127">成功または失敗を決定します。</span><span class="sxs-lookup"><span data-stu-id="6d939-127">Determining success or failure</span></span>

<span data-ttu-id="6d939-128">必要なアクセス許可が Active Directory コンテナーに設定されている既にテスト CsSetupPermission と判断した場合、コマンドレットは True 値を返します。</span><span class="sxs-lookup"><span data-stu-id="6d939-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="6d939-129">True</span><span class="sxs-lookup"><span data-stu-id="6d939-129">True</span></span> 

<span data-ttu-id="6d939-130">アクセス許可が設定されていない場合、テスト CsSetupPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="6d939-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="6d939-131">この値が多くの警告メッセージで囲まれた通常は注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d939-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="6d939-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d939-132">For example:</span></span>

<span data-ttu-id="6d939-133">警告: アクセス制御エントリ (ACE) atl の cs-001\RTCUniversalServerAdmins です。許可します。ExtendedRight。[なし] です。[なし] です。1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="6d939-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="6d939-134">警告: アクセス制御エントリ (Ace) オブジェクトの"CN = Computers、DC = litwareinc、DC = com」準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="6d939-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="6d939-135">False</span><span class="sxs-lookup"><span data-stu-id="6d939-135">False</span></span> 

<span data-ttu-id="6d939-136">警告: 警告「テスト CsSetupPermission」の処理が完了しました。</span><span class="sxs-lookup"><span data-stu-id="6d939-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="6d939-137">この実行中に「2」の警告が記録されています。</span><span class="sxs-lookup"><span data-stu-id="6d939-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="6d939-138">警告:"C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"の結果の詳細を参照しています。</span><span class="sxs-lookup"><span data-stu-id="6d939-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6d939-139">なぜテストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="6d939-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="6d939-140">テスト CsSetupPermission が失敗した場合に通常は、まれな例外がありますが、指定した Active Directory コンテナーにはアクセス許可を設定することを意味は割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="6d939-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="6d939-141">許可 CsSetupPermission コマンドレットを使用してこれらのアクセス許可を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6d939-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="6d939-142">たとえば、このコマンドでは、ドメイン litwareinc.com のコンピューター コンテナーにセットアップの許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6d939-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="6d939-143">詳細については、[テスト CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d939-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
