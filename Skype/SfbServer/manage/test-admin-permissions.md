---
title: Skype のビジネス サーバーの管理者のアクセス許可をテスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype のビジネス サーバーの管理者のアクセス許可をテストする方法
ms.openlocfilehash: f769870991cfd5578fc8bd809d26c0aea912d03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898291"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="2d4ee-103">Skype のビジネス サーバーの管理者のアクセス許可をテスト</span><span class="sxs-lookup"><span data-stu-id="2d4ee-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="2d4ee-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="2d4ee-104">Verification schedule</span></span>|<span data-ttu-id="2d4ee-105">後ビジネス サーバーの展開の初期の Skype です。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="2d4ee-106">必要に応じてアクセス許可に関連する問題が発生した場合。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="2d4ee-107">テスト ツール</span><span class="sxs-lookup"><span data-stu-id="2d4ee-107">Testing tool</span></span>|<span data-ttu-id="2d4ee-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d4ee-108">Windows PowerShell</span></span>|
|<span data-ttu-id="2d4ee-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2d4ee-109">Permissions required</span></span>|<span data-ttu-id="2d4ee-110">ビジネス サーバー管理シェルには、Skype を使用してローカルで実行するとユーザーは RTCUniversalServerAdmins のセキュリティ グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="2d4ee-111">実行すると、Windows PowerShell のリモート インスタンスを使用してユーザーがテスト CsOUPermission コマンドレットを実行する権限を持っている RBAC の役割を割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="2d4ee-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="2d4ee-113">Get CsAdminRole \| Where-object {$_ です。コマンドレットの「テスト CsOUPermission」に一致。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="2d4ee-114">説明</span><span class="sxs-lookup"><span data-stu-id="2d4ee-114">Description</span></span>

<span data-ttu-id="2d4ee-115">RTCUniversalUserAdmins グループ ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory アクセス許可は、セットアップ プログラムによって実行されたタスクのいずれかのビジネス サーバーの Skype をインストールするとき担当者です。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="2d4ee-116">Active Directory のアクセス許可の継承を無効にした場合、セットアップはこれらのアクセス許可を割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="2d4ee-117">その結果、RTCUniversalUserAdmins グループのメンバーは、サーバーのビジネス エンティティの Skype を管理するためにはできません。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="2d4ee-118">管理権限はドメイン管理者にのみできます。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="2d4ee-119">テスト CsOUPermission コマンドレットでは、Active Directory コンテナーにユーザー、コンピューター、およびその他のオブジェクトを管理するために必要なパーミッションが設定されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="2d4ee-120">これらのアクセス許可が設定されていない場合は、[補助金 CsOUPermission コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)を実行してこの問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="2d4ee-121">許可 CsOUPermission のみを割り当てることがアクセス許可、RTCUniversalUserAdmins グループのメンバーに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="2d4ee-122">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与できません。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="2d4ee-123">ユーザー管理権限を持っている別のユーザーまたはグループを選択する場合は、RTCUniversalUserAdmins グループにそのユーザー (またはグループ) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="2d4ee-124">テストを実行しています。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-124">Running the test</span></span>

<span data-ttu-id="2d4ee-125">コンテナーの管理アクセス許可が設定されていることを確認するには、コンテナーの識別名、および確認の対象とするアクセス許可の種類の後にテスト CsOUPermission コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="2d4ee-126">たとえば、このコマンドは、OU の ou にユーザーのアクセス許可を設定するかどうかをチェック = 東京都, dc = litwareinc、dc = com。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="2d4ee-127">1 つのコマンドを使用して複数のアクセス許可を確認するには、引用符、二重引用符で囲まれている各アクセス許可の種類し、コンマを使用して、これらの種類を区別します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="2d4ee-128">ユーザー、コンピューター、および取引先担当者に、この 1 つのコマンドを確認するなどのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="2d4ee-129">詳細については、[テスト CsOUPermission コマンドレットのヘルプ トピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2d4ee-130">成功または失敗を決定します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-130">Determining success or failure</span></span>

<span data-ttu-id="2d4ee-131">場合は既に設定されている必要なアクセス許可には、テスト CsOUPermission には、1 つの word の応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="2d4ee-132">True</span><span class="sxs-lookup"><span data-stu-id="2d4ee-132">True</span></span>

<span data-ttu-id="2d4ee-133">必要なアクセス許可が設定されていない場合、テスト CsOUPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="2d4ee-134">この値を検索するのには少しの間を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="2d4ee-135">付随するいくつかの警告の中に通常埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="2d4ee-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-136">For example:</span></span>

<span data-ttu-id="2d4ee-137">警告: アクセス制御エントリ (ACE) atl の cs-001\RTCUniversalUserReadOnlyGroup です。許可します。ReadProperty です。ContainerInherit です。サブフォルダーが存在します。-00aa003049e2 bf967aba-0de6-11 d 0 です。d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="2d4ee-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="2d4ee-138">警告: アクセス制御エントリ (Ace) オブジェクトの"OU = NorthAmerica、DC = atl の cs-001\DC = litwareinc、DC = com"準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="2d4ee-139">False</span><span class="sxs-lookup"><span data-stu-id="2d4ee-139">False</span></span> 

<span data-ttu-id="2d4ee-140">警告: 警告「テスト CsOUPermission」の処理が完了しました。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="2d4ee-141">この実行中に「2」の警告が記録されています。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="2d4ee-142">警告:"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"の結果の詳細を参照しています。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2d4ee-143">なぜテストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="2d4ee-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="2d4ee-144">CsOUPermission のテストが失敗した場合は、通常、RTCUniversalUserAdmins グループに指定したアクセス許可が割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="2d4ee-145">この問題を解決し、与える CsOUPermission コマンドレットを使用して、必要なアクセス許可を割り当てることがことができます。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="2d4ee-146">など、このコマンドは、RTCUniversalUserAdmins グループにユーザー、連絡先、および Inetorgperson の OU のアクセス許可を使用します。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="2d4ee-147">詳細については、[テスト CsOUPermission コマンドレットのヘルプ トピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d4ee-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
