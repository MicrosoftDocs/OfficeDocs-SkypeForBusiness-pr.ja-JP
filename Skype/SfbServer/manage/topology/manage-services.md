---
title: Skype for Business Server でサービスを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: サービスの状態の表示、サービスの開始と停止、サービスのセッションの無効化などの方法について説明します。
ms.openlocfilehash: c3c0ad3a61543caf7866582413a67968c4c1c2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275151"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="45384-103">Skype for Business Server でサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="45384-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="45384-104">Skype for Business Server コントロールパネルを使用して、トポロジでの Skype for Business Server を実行しているすべてのコンピューターの一覧を表示したり、サービスの状態を表示したり、サービスを開始または停止したり、サービスのセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="45384-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="45384-105">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="45384-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="45384-106">Skype for Business のコンピューターで実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="45384-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="45384-107">Skype for Business サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="45384-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="45384-108">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="45384-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="45384-109">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="45384-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="45384-110">Skype for Business Server コントロールパネルを使用して、トポロジで Skype for Business を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="45384-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="45384-111">リストは、コンピューター、プール、またはサイトによって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="45384-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="45384-112">Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="45384-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="45384-113">詳細については、「 [Skype For Business Server の役割ベースのアクセス制御 (RBAC)](../../plan-your-deployment/security/role-based-access-control-rbac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45384-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="45384-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="45384-115">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-116">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="45384-117">[状態] ページで、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45384-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="45384-118">**コンピューター**、**プール**、または**サイト**の列見出しをクリックし、上矢印または下矢印をクリックして、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="45384-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="45384-119">最新のリストを表示するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="45384-120">検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="45384-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="45384-121">Skype for Business のコンピューターで実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="45384-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="45384-122">Skype for Business Server コントロールパネルを使用して、Skype for Business Server トポロジの特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="45384-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="45384-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="45384-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="45384-124">ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="45384-125">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-126">左側のナビゲーションバーで、[**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="45384-127">[状態] ページで、必要に応じてリストを並べ替えるか検索して、目的のコンピューターを見つけ、コンピューター名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="45384-128">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="45384-128">Do either of the following:</span></span>
    - <span data-ttu-id="45384-129">コンピューター上で実行されているサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="45384-130">コンピューター上で実行されている特定のサービスの一覧と各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックしてリストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="45384-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="45384-131">Windows PowerShell コマンドレットを使用してサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="45384-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="45384-132">また、Windows PowerShell と、ユーザーの取得-CsWindowsService コマンドレットを使用して、サービスの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="45384-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="45384-133">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="45384-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="45384-134">詳細については、「 [Skype For Business Server 管理シェル](../management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45384-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="45384-135">**サービスの状態を表示するには**</span><span class="sxs-lookup"><span data-stu-id="45384-135">**To view service status**</span></span>

<span data-ttu-id="45384-136">コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="45384-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

<span data-ttu-id="45384-137">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="45384-137">This command returns information similar to the following:</span></span>

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

<span data-ttu-id="45384-138">詳細については、「 [CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45384-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="45384-139">Skype for Business サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="45384-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="45384-140">Skype for Business Server コントロールパネルを使用して、特定のコンピューターで実行されているすべての Skype for Business Server サービスを開始または停止するか、特定のサービスを開始または終了します。</span><span class="sxs-lookup"><span data-stu-id="45384-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="45384-141">コンピューター上のすべての Skype for Business Server サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="45384-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="45384-142">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="45384-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="45384-143">次のようなコマンドを実行すると、CsServerAdministrator または CsAdministrator の RBAC 役割が割り当てられているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="45384-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. <span data-ttu-id="45384-144">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="45384-145">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-146">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="45384-147">[状態] ページで、必要に応じて一覧を並べ替えて検索するか、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="45384-148">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-148">Click **Action**.</span></span>
6. <span data-ttu-id="45384-149">[**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="45384-150">特定のサービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="45384-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="45384-151">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="45384-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="45384-152">ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="45384-153">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-154">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="45384-155">[状態] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="45384-156">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-156">Click **Properties**.</span></span>
6. <span data-ttu-id="45384-157">必要に応じてサービスの一覧を並べ替え、開始または停止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="45384-158">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-158">Click **Action**.</span></span>
8. <span data-ttu-id="45384-159">[**サービスの開始**] または [**サービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="45384-160">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="45384-161">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="45384-161">Prevent sessions for services</span></span>

<span data-ttu-id="45384-162">Skype for Business コントロールパネルを使用して、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを禁止するか、特定のサービスの新しいセッションを禁止します。</span><span class="sxs-lookup"><span data-stu-id="45384-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="45384-163">コンピューター上のすべての Skype for Business Server サービスの新しいセッションを禁止する</span><span class="sxs-lookup"><span data-stu-id="45384-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="45384-164">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="45384-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="45384-165">ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="45384-166">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-167">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="45384-168">[状態] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="45384-169">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-169">Click **Action**.</span></span>
6. <span data-ttu-id="45384-170">[**すべてのサービスに対して新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="45384-171">特定のサービスの新しいセッションを禁止する</span><span class="sxs-lookup"><span data-stu-id="45384-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="45384-172">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="45384-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="45384-173">ブラウザーのウィンドウを開き、管理 URL を入力してコントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="45384-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="45384-174">Skype for Business Server コントロールパネルの起動に使用できるさまざまな方法について詳しくは、「[管理ツールをインストールして開く](../../management-tools/install-and-open-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45384-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="45384-175">左側のナビゲーション バーで **[トポロジ]** をクリックし、**[状態]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="45384-176">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-176">Click **Properties**.</span></span>
5. <span data-ttu-id="45384-177">必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="45384-178">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-178">Click **Action**.</span></span>
7. <span data-ttu-id="45384-179">[**サービスの新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="45384-180">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45384-180">Click **Close**.</span></span>
