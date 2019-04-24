---
title: Skype のサービスをビジネス サーバーを管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: サービスの状態を表示、起動し、サービスを停止し、サービスのセッションを防止する方法を説明します。
ms.openlocfilehash: 6913ce2cbef6c12a61d7d4751b35a71371ffb991
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215172"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="f2e39-103">Skype のサービスをビジネス サーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="f2e39-104">ビジネス サーバーのコントロール パネルの Skype を使用するにはビジネスのサーバー トポロジでは、Skype を実行しているすべてのコンピューターの一覧を表示、サービスの状態を表示、開始またはサービスを停止およびサービスのセッションを防止します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="f2e39-105">Skype をビジネスのサーバーを実行しているコンピューターの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="f2e39-106">ビジネス用の Skype でのコンピューターで実行されているサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="f2e39-107">開始または Skype をビジネス ・ サービスの停止</span><span class="sxs-lookup"><span data-stu-id="f2e39-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="f2e39-108">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="f2e39-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="f2e39-109">Skype をビジネスのサーバーを実行しているコンピューターの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="f2e39-110">ビジネス サーバーのコントロール パネルの Skype を使用して、トポロジでは、ビジネス用の Skype を実行しているし、それぞれのサービスの状態を表示するすべてのコンピューターの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="f2e39-111">コンピューター、プール、またはサイトでリストを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2e39-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="f2e39-112">、Skype のビジネス サーバーの定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="f2e39-113">詳細については、 [Skype のビジネス サーバーの役割に基づくアクセス制御 (RBAC)](../../plan-your-deployment/security/role-based-access-control-rbac.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="f2e39-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f2e39-115">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-116">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="f2e39-117">[状態] ページで、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2e39-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="f2e39-118">**コンピューター**、**プール**、または**サイト**列の見出しをクリックし、上向き矢印または下向きの矢印をクリックし、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="f2e39-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="f2e39-119">最新のリストを表示するのには**更新**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="f2e39-120">検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="f2e39-121">ビジネス用の Skype でのコンピューターで実行されているサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="f2e39-122">ビジネス サーバーのコントロール パネルの Skype を使用すると、ビジネスのサーバー トポロジの場合、Skype で特定のコンピューター上で実行され、各サービスの状態を確認するすべてのサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="f2e39-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="f2e39-124">、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="f2e39-125">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-126">左側のナビゲーション ・ バーでは、**トポロジー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="f2e39-127">[状態] ページで、並べ替えやを知り、コンピューターを検索するのには、必要に応じて、リストを検索、[コンピューター名] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="f2e39-128">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2e39-128">Do either of the following:</span></span>
    - <span data-ttu-id="f2e39-129">コンピューター上で実行されているサービスの最新の状態を表示するには、**サービスのステータスを取得する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="f2e39-130">コンピューターと各サービスの状態で実行されている特定のサービスの一覧を表示するには、**プロパティ**] をクリックし、**閉じる**一覧に戻る] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2e39-131">Windows PowerShell コマンドレットを使用してサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f2e39-132">Windows PowerShell と Get CsWindowsService コマンドレットを使用してサービスの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2e39-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="f2e39-133">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f2e39-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2e39-134">詳細については、 [Skype ビジネス サーバー管理シェル](../management-shell.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="f2e39-135">**サービスの状態を表示するのには**</span><span class="sxs-lookup"><span data-stu-id="f2e39-135">**To view service status**</span></span>

<span data-ttu-id="f2e39-136">コンピューターでサービスの状態を表示するのには、Skype のビジネス サーバー管理シェルには、次のようなコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

<span data-ttu-id="f2e39-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-137">This command returns information similar to the following:</span></span>

```
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

<span data-ttu-id="f2e39-138">詳細については、 [Get CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="f2e39-139">開始または Skype をビジネス ・ サービスの停止</span><span class="sxs-lookup"><span data-stu-id="f2e39-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="f2e39-140">開始または停止する特定のコンピューターで実行されているビジネスのサーバー サービスのすべての Skype または開始または特定のサービスを停止するには、ビジネス サーバーのコントロール パネルの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="f2e39-141">開始またはコンピューターでビジネス サービスのすべての Skype を停止します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="f2e39-142">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="f2e39-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="f2e39-143">かどうかが割り当てられている、CsServerAdministrator または CsAdministrator の RBAC の役割には、次のようなコマンドを実行することによって判断できます。</span><span class="sxs-lookup"><span data-stu-id="f2e39-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. <span data-ttu-id="f2e39-144">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f2e39-145">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-146">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="f2e39-147">状態のページ、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="f2e39-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="f2e39-148">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-148">Click **Action**.</span></span>
6. <span data-ttu-id="f2e39-149">**開始のすべてのサービス**または**サービスをすべて停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="f2e39-150">開始または特定のサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="f2e39-151">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="f2e39-152">、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="f2e39-153">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-154">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="f2e39-155">状態のページ、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="f2e39-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="f2e39-156">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-156">Click **Properties**.</span></span>
6. <span data-ttu-id="f2e39-157">必要に応じて、サービスの一覧を並べ替えるし、サービスを開始または停止する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="f2e39-158">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-158">Click **Action**.</span></span>
8. <span data-ttu-id="f2e39-159">**サービスを開始**または**停止するサービス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="f2e39-160">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="f2e39-161">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="f2e39-161">Prevent sessions for services</span></span>

<span data-ttu-id="f2e39-162">ビジネス サーバー サービスが特定のコンピューターで実行されているすべての Skype の新しいセッションを禁止したり、特定のサービスの新しいセッションを防ぐためには、ビジネス コントロール パネルの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="f2e39-163">ビジネス サービスのコンピューター上のすべての Skype の新しいセッションを禁止します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="f2e39-164">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="f2e39-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="f2e39-165">、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="f2e39-166">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-167">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="f2e39-168">[状態] ページで、並べ替えまたはとしてリストを検索は、新しいセッションを禁止し、クリックするサービスを実行しているコンピューターを検索するのには必要です。</span><span class="sxs-lookup"><span data-stu-id="f2e39-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="f2e39-169">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-169">Click **Action**.</span></span>
6. <span data-ttu-id="f2e39-170">**すべてのサービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="f2e39-171">特定のサービスの新しいセッションを防止します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="f2e39-172">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="f2e39-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="f2e39-173">、ブラウザー ウィンドウを開くし、コントロール パネルを開くための管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2e39-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="f2e39-174">ビジネス サーバーのコントロール パネルの Skype を起動することができますを使用するさまざまな方法についての詳細は、[インストールと管理ツールを開く](../../management-tools/install-and-open-administrative-tools.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e39-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="f2e39-175">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="f2e39-176">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-176">Click **Properties**.</span></span>
5. <span data-ttu-id="f2e39-177">必要に応じて、サービスの一覧を並べ替えるし、サービスの新しいセッションを禁止する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="f2e39-178">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-178">Click **Action**.</span></span>
7. <span data-ttu-id="f2e39-179">**サービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="f2e39-180">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2e39-180">Click **Close**.</span></span>
