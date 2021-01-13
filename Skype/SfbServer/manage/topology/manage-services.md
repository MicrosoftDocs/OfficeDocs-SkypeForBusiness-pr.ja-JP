---
title: Skype for Business Server でサービスを管理する
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
description: サービスの状態の表示、サービスの開始と停止、およびサービスのセッションの防止を行う方法について学習します。
ms.openlocfilehash: 6071526febcd3a4c1cb925ae3fb704eca6db575c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826317"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="7c1e3-103">Skype for Business Server でサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="7c1e3-104">Skype for Business Server コントロール パネルを使用すると、トポロジ内で Skype for Business Server を実行しているすべてのコンピューターの一覧の表示、サービスの状態の表示、サービスの開始または停止、およびサービスのセッションの防止を行えます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="7c1e3-105">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="7c1e3-106">Skype for Business のコンピューターで実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="7c1e3-107">Skype for Business サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="7c1e3-108">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="7c1e3-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="7c1e3-109">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="7c1e3-110">Skype for Business Server コントロール パネルを使用して、トポロジ内で Skype for Business を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="7c1e3-111">この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="7c1e3-112">Skype for Business Server の定義済みの管理者の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="7c1e3-113">詳細については [、Skype for Business Server の役割ベースのアクセス制御 (RBAC) を参照してください](../../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="7c1e3-114">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7c1e3-115">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-116">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="7c1e3-117">[状態] ページで、必要に応じて次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="7c1e3-118">[**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="7c1e3-119">[**更新**] をクリックして、最新の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="7c1e3-120">検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="7c1e3-121">Skype for Business のコンピューターで実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="7c1e3-122">Skype for Business Server のコントロール パネルを使用して、Skype for Business Server トポロジ内の特定のコンピューターで実行しているすべてのサービスを表示し、各サービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="7c1e3-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="7c1e3-124">ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="7c1e3-125">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-126">左側のナビゲーション バーで [**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="7c1e3-127">[状態] ページで、必要に応じてリストを並べ替えまたは検索して対象のコンピューターを見つけ、そのコンピューター名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="7c1e3-128">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-128">Do either of the following:</span></span>
    - <span data-ttu-id="7c1e3-129">コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="7c1e3-130">コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7c1e3-131">Windows PowerShell コマンドレットを使用してサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7c1e3-132">また、サービスの状態を表示するには、Windows PowerShellコマンドレットをGet-CsWindowsServiceします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="7c1e3-133">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7c1e3-134">詳細については [、Skype for Business Server 管理シェル を参照してください](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="7c1e3-135">**サービス状態を表示するには**</span><span class="sxs-lookup"><span data-stu-id="7c1e3-135">**To view service status**</span></span>

<span data-ttu-id="7c1e3-136">コンピューターのサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="7c1e3-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-137">This command returns information similar to the following:</span></span>

```console
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

<span data-ttu-id="7c1e3-138">詳細については [、「Get-CsWindowsService」を参照してください](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="7c1e3-139">Skype for Business サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="7c1e3-140">Skype for Business Server コントロール パネルを使用して、特定のコンピューターで実行しているすべての Skype for Business Server サービスを開始または停止したり、特定のサービスを開始または停止したりします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="7c1e3-141">コンピューター上のすべての Skype for Business Server サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="7c1e3-142">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="7c1e3-143">CsServerAdministrator または CsAdministrator RBAC の役割が割り当てられているかどうかを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. <span data-ttu-id="7c1e3-144">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7c1e3-145">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-146">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="7c1e3-147">[状態] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="7c1e3-148">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-148">Click **Action**.</span></span>
6. <span data-ttu-id="7c1e3-149">[**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="7c1e3-150">特定のサービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="7c1e3-151">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="7c1e3-152">ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="7c1e3-153">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-154">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="7c1e3-155">[状態] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="7c1e3-156">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-156">Click **Properties**.</span></span>
6. <span data-ttu-id="7c1e3-157">必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="7c1e3-158">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-158">Click **Action**.</span></span>
8. <span data-ttu-id="7c1e3-159">[**サービスの開始**] または [**サービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="7c1e3-160">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="7c1e3-161">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="7c1e3-161">Prevent sessions for services</span></span>

<span data-ttu-id="7c1e3-162">Skype for Business コントロール パネルを使用して、特定のコンピューターで実行しているすべての Skype for Business Server サービスの新しいセッションを回避したり、特定のサービスの新しいセッションを回避したりします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="7c1e3-163">コンピューター上のすべての Skype for Business Server サービスに対して新しいセッションを回避する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="7c1e3-164">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="7c1e3-165">ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="7c1e3-166">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-167">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="7c1e3-168">[状態] ページで、必要に応じて一覧を並べ替えまたは検索し、新しいセッションを回避するサービスを実行しているコンピューターを見つけてクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="7c1e3-169">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-169">Click **Action**.</span></span>
6. <span data-ttu-id="7c1e3-170">[すべての **サービスに対して新しいセッションを使用できない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="7c1e3-171">特定のサービスに対して新しいセッションを回避する</span><span class="sxs-lookup"><span data-stu-id="7c1e3-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="7c1e3-172">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="7c1e3-173">ブラウザー ウィンドウを開き、管理 URL を入力してコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="7c1e3-174">Skype for Business Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「管理ツールをインストールして開く [」を参照してください](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="7c1e3-175">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="7c1e3-176">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-176">Click **Properties**.</span></span>
5. <span data-ttu-id="7c1e3-177">必要に応じてサービスの一覧を並べ替え、新しいセッションを回避するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="7c1e3-178">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-178">Click **Action**.</span></span>
7. <span data-ttu-id="7c1e3-179">[サービス **の新しいセッションを回避する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="7c1e3-180">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c1e3-180">Click **Close**.</span></span>
