---
title: Skype for Business Server での管理者権限のテスト
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
description: Skype for Business Server で管理者権限をテストする方法
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030160"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="4201c-103">Skype for Business Server での管理者権限のテスト</span><span class="sxs-lookup"><span data-stu-id="4201c-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="4201c-104">検証スケジュール</span><span class="sxs-lookup"><span data-stu-id="4201c-104">Verification schedule</span></span>|<span data-ttu-id="4201c-105">最初の Skype for business Server の展開後。</span><span class="sxs-lookup"><span data-stu-id="4201c-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="4201c-106">必要に応じて、アクセス許可に関連する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="4201c-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="4201c-107">テストツール</span><span class="sxs-lookup"><span data-stu-id="4201c-107">Testing tool</span></span>|<span data-ttu-id="4201c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4201c-108">Windows PowerShell</span></span>|
|<span data-ttu-id="4201c-109">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4201c-109">Permissions required</span></span>|<span data-ttu-id="4201c-110">Skype for Business Server 管理シェルを使用してローカルに実行する場合、ユーザーは RTCUniversalServerAdmins セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4201c-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="4201c-111">Windows PowerShell のリモートインスタンスを使用して実行する場合、ユーザーには、テスト用の CsOUPermission コマンドレットを実行する権限を持つ RBAC の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4201c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="4201c-112">このコマンドレットを使用できるすべての RBAC の役割の一覧を表示するには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4201c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="4201c-113">-オブジェクト {$ _ \|の場所で-CsAdminRole を取得します。コマンドレット-一致 "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="4201c-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="4201c-114">説明</span><span class="sxs-lookup"><span data-stu-id="4201c-114">Description</span></span>

<span data-ttu-id="4201c-115">Skype for Business Server をインストールすると、セットアッププログラムによって実行されたタスクの1つによって、ユーザー、コンピューター、連絡先、アプリケーションの連絡先、および InetOrg を管理するために必要な Active Directory のアクセス許可が RTCUniversalUserAdmins グループに付与されます。員.</span><span class="sxs-lookup"><span data-stu-id="4201c-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="4201c-116">Active Directory でのアクセス許可の継承が無効になっている場合、セットアップはそれらのアクセス許可を割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="4201c-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="4201c-117">その結果、RTCUniversalUserAdmins グループのメンバーは、Skype for Business Server のエンティティを管理することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="4201c-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="4201c-118">これらの管理権限は、ドメイン管理者のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="4201c-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="4201c-119">Test-CsOUPermission コマンドレットは、ユーザー、コンピューター、およびその他のオブジェクトを管理するために必要なアクセス許可が Active Directory コンテナーに設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4201c-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="4201c-120">これらのアクセス許可が設定されていない場合は、 [Grant-CsOUPermission コマンドレット](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)を実行することによって、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="4201c-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="4201c-121">RTCUniversalUserAdmins グループのメンバーに対してアクセス許可を割り当てることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4201c-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="4201c-122">このコマンドレットを使用して、任意のユーザーまたはグループにアクセス許可を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="4201c-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="4201c-123">別のユーザーまたはグループにユーザー管理アクセス許可を付与する場合は、そのユーザーまたはグループを RTCUniversalUserAdmins グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4201c-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="4201c-124">テストの実行</span><span class="sxs-lookup"><span data-stu-id="4201c-124">Running the test</span></span>

<span data-ttu-id="4201c-125">管理アクセス許可がコンテナーに設定されていることを確認するには、Test-CsOUPermission コマンドレットを実行した後に、コンテナーの識別名、および検証するアクセス許可の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4201c-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="4201c-126">たとえば、次のコマンドは、ユーザーのアクセス許可が OU ou = Redmond, dc = litwareinc, dc = com で設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4201c-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="4201c-127">単一のコマンドを使用して複数のアクセス許可を確認するには、各アクセス許可の種類を二重引用符で囲み、コンマを使用してそれらの種類を区切ります。</span><span class="sxs-lookup"><span data-stu-id="4201c-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="4201c-128">たとえば、次のコマンドは、ユーザー、コンピューター、および連絡先のアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="4201c-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="4201c-129">詳細については、 [Test-CsOUPermission コマンドレットのヘルプトピック](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4201c-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4201c-130">成功または失敗を判断する</span><span class="sxs-lookup"><span data-stu-id="4201c-130">Determining success or failure</span></span>

<span data-ttu-id="4201c-131">必要なアクセス許可が既に設定されている場合、Test-CsOUPermission は1単語の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="4201c-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="4201c-132">はい</span><span class="sxs-lookup"><span data-stu-id="4201c-132">True</span></span>

<span data-ttu-id="4201c-133">必要なアクセス許可が設定されていない場合、Test-CsOUPermission は値 False を返します。</span><span class="sxs-lookup"><span data-stu-id="4201c-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="4201c-134">この値を見つけるには、少し時間を置いて検索する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="4201c-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="4201c-135">通常は、いくつかの付随する警告に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="4201c-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="4201c-136">例:</span><span class="sxs-lookup"><span data-stu-id="4201c-136">For example:</span></span>

<span data-ttu-id="4201c-137">警告: アクセス制御エントリ (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup;使うReadPropertyContainerInherit;子孫bf967aba-0de6-11d0-00aa003049e2;d819615a-4738 3b9b-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="4201c-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="4201c-138">警告: オブジェクト "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" のアクセス制御エントリ (Ace) の準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="4201c-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="4201c-139">False</span><span class="sxs-lookup"><span data-stu-id="4201c-139">False</span></span> 

<span data-ttu-id="4201c-140">警告: "Test-CsOUPermission" 処理は完了しましたが、警告があります。</span><span class="sxs-lookup"><span data-stu-id="4201c-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="4201c-141">この実行中に警告が記録されました。</span><span class="sxs-lookup"><span data-stu-id="4201c-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="4201c-142">警告: 詳細な結果は、"C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html" にあります。</span><span class="sxs-lookup"><span data-stu-id="4201c-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4201c-143">テストが失敗した理由</span><span class="sxs-lookup"><span data-stu-id="4201c-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="4201c-144">Test-CsOUPermission に失敗した場合は、通常、指定されたアクセス許可が RTCUniversalUserAdmins グループに割り当てられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4201c-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="4201c-145">この問題を解決して、Grant-CsOUPermission コマンドレットを使用して必要なアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4201c-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="4201c-146">たとえば、次のコマンドを実行すると、ユーザー、連絡先、および inetOrgPersons の OU 権限が RTCUniversalUserAdmins グループに付与されます。</span><span class="sxs-lookup"><span data-stu-id="4201c-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="4201c-147">詳細については、 [Test-CsOUPermission コマンドレットのヘルプトピック](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4201c-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
