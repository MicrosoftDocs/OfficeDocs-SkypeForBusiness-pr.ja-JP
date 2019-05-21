---
title: Skype for Business Server で管理者権限をテストする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server で管理権限をテストする方法
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279250"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="0964a-103">Skype for Business Server で管理者権限をテストする</span><span class="sxs-lookup"><span data-stu-id="0964a-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="0964a-104">確認のスケジュール</span><span class="sxs-lookup"><span data-stu-id="0964a-104">Verification schedule</span></span>|<span data-ttu-id="0964a-105">初めての Skype for Business Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="0964a-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="0964a-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="0964a-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="0964a-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="0964a-107">Testing tool</span></span>|<span data-ttu-id="0964a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0964a-108">Windows PowerShell</span></span>|
|<span data-ttu-id="0964a-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0964a-109">Permissions required</span></span>|<span data-ttu-id="0964a-110">Skype for Business Server 管理シェルを使用してローカルで実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0964a-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="0964a-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、CsOUPermission コマンドレットを実行するためのアクセス許可が与えられた RBAC の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0964a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="0964a-112">このコマンドレットを使うことができるすべての RBAC ロールの一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0964a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="0964a-113">を\|取得します。-オブジェクト {$ _コマンドレット-match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="0964a-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="0964a-114">説明</span><span class="sxs-lookup"><span data-stu-id="0964a-114">Description</span></span>

<span data-ttu-id="0964a-115">Skype for Business Server をインストールすると、セットアッププログラムによって実行されたタスクの1つに、RTCUniversalUserAdmins グループにユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory アクセス許可が付与されます。連絡.</span><span class="sxs-lookup"><span data-stu-id="0964a-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="0964a-116">Active Directory でアクセス許可の継承を無効にしている場合、セットアップでは、これらのアクセス許可を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0964a-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="0964a-117">この結果、RTCUniversalUserAdmins グループのメンバーは、Skype for Business Server のエンティティを管理することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="0964a-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="0964a-118">これらの管理権限は、ドメイン管理者のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="0964a-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="0964a-119">ユーザー、コンピューター、その他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーで設定されていることを確認するために、CsOUPermission のテストコマンドレットを確認します。</span><span class="sxs-lookup"><span data-stu-id="0964a-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="0964a-120">これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission コマンドレット](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission)を実行することで、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="0964a-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="0964a-121">ただし、権限の付与は、RTCUniversalUserAdmins グループのメンバーに対してのみ権限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0964a-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="0964a-122">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="0964a-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="0964a-123">別のユーザーまたはグループにユーザー管理のアクセス許可を与える必要がある場合は、そのユーザー (またはグループ) を RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0964a-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="0964a-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="0964a-124">Running the test</span></span>

<span data-ttu-id="0964a-125">コンテナーに管理権限が設定されていることを確認するには、CsOUPermission コマンドレットを実行し、その後に、コンテナーの識別名と確認するアクセス許可の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0964a-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="0964a-126">たとえば、次のコマンドは、ユーザー権限が OU ou で設定されているかどうかを確認します。 Redmond、dc = litwareinc、dc = com:</span><span class="sxs-lookup"><span data-stu-id="0964a-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="0964a-127">1つのコマンドを使用して複数のアクセス許可を確認するには、それぞれのアクセス許可の種類を引用符で囲んで囲み、コンマを使用してそれらの型を区切ります。</span><span class="sxs-lookup"><span data-stu-id="0964a-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="0964a-128">たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="0964a-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="0964a-129">詳細については、「 [CsOUPermission のテスト」コマンドレットのヘルプトピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0964a-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0964a-130">成功または失敗を確認する</span><span class="sxs-lookup"><span data-stu-id="0964a-130">Determining success or failure</span></span>

<span data-ttu-id="0964a-131">必要なアクセス許可が既に設定されている場合、テスト用の CsOUPermission は1単語の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="0964a-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="0964a-132">True</span><span class="sxs-lookup"><span data-stu-id="0964a-132">True</span></span>

<span data-ttu-id="0964a-133">必要なアクセス許可が設定されていない場合は、"False" という値が返されます。</span><span class="sxs-lookup"><span data-stu-id="0964a-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="0964a-134">この値を検索するには、少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0964a-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="0964a-135">通常は、いくつかの関連する警告内に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="0964a-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="0964a-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0964a-136">For example:</span></span>

<span data-ttu-id="0964a-137">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup許可ReadProperty;ContainerInherit;フォルダーbf967aba-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="0964a-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="0964a-138">警告: オブジェクト "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="0964a-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="0964a-139">False</span><span class="sxs-lookup"><span data-stu-id="0964a-139">False</span></span> 

<span data-ttu-id="0964a-140">警告: "Test-CsOUPermission" 処理は警告で完了しています。</span><span class="sxs-lookup"><span data-stu-id="0964a-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="0964a-141">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="0964a-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="0964a-142">警告: 詳細な結果は "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0964a-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0964a-143">テストに失敗した可能性がある理由</span><span class="sxs-lookup"><span data-stu-id="0964a-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="0964a-144">RTCUniversalUserAdmins のテストに失敗した場合、通常は、指定したアクセス許可がグループに割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0964a-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="0964a-145">この問題を解決して、必要なアクセス許可を割り当てるには、アクセス許可の付与コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0964a-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="0964a-146">たとえば、次のコマンドを実行すると、ユーザー、連絡先、inetOrgPersons に対して、RTCUniversalUserAdmins グループに OU 権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="0964a-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="0964a-147">詳細については、「 [CsOUPermission のテスト」コマンドレットのヘルプトピック](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0964a-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
