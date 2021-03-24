---
title: Skype for Business Server のサービスを管理する
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: この記事では、Skype for Business Server トポロジで実行されているサービスを管理する方法について説明します。
ms.openlocfilehash: d0669eab34795de3241c954f2eda593eda474193
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104383"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="3e76d-103">Skype for Business Server のサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="3e76d-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="3e76d-104">この記事では、Skype for Business Server トポロジで実行されているサービスを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="3e76d-105">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="3e76d-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="3e76d-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="3e76d-106"><a name="view_list"> </a></span></span>

<span data-ttu-id="3e76d-107">Skype for Business Server コントロール パネルを使用すると、トポロジで Skype for Business Server を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービス状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="3e76d-108">この一覧は、コンピューター、プール、またはサイトごとに並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="3e76d-109">Skype for Business Server を実行しているコンピューターの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="3e76d-110">Skype for Business Server の定義済みの管理役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="3e76d-111">Skype for Business Server で使用できる定義済みの管理役割の詳細については、「Planning for Role-Based **アクセス制御」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="3e76d-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="3e76d-112">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="3e76d-113">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="3e76d-114">[**状態**] ページで、必要に応じて、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="3e76d-115">[**コンピューター**]、[**プール**]、または [**サイト**] 列の見出しをクリックし、上矢印または下矢印をクリックして、一覧を並べ変えます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="3e76d-116">[**更新**] をクリックして、最新の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="3e76d-117">検索フィールドにコンピューター名を入力することで、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="3e76d-118">Skype for Business サーバーで実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="3e76d-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="3e76d-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="3e76d-119"><a name="view-status"> </a></span></span>

<span data-ttu-id="3e76d-120">Skype for Business Server コントロール パネルを使用すると、Skype for Business Server トポロジ内の特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="3e76d-121">コンピューターで実行されているサービスの状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="3e76d-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="3e76d-123">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-124">左側のナビゲーション バーで [**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="3e76d-125">[状態 **] ページで** 、必要に応じてリストを並べ替えまたは検索して、必要なコンピューターを検索し、コンピューター名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="3e76d-126">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3e76d-126">Do any of the following:</span></span>
   - <span data-ttu-id="3e76d-127">コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="3e76d-128">コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3e76d-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="3e76d-129">Windows Powershell コマンドレットを使用してサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="3e76d-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="3e76d-130">また、サービスの状態を表示するには、Windows PowerShell **Get-CsWindowsService コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="3e76d-131">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e76d-132">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e76d-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3e76d-133">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="3e76d-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="3e76d-134">サービス状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-134">To view service status</span></span>

<span data-ttu-id="3e76d-135">コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルに次のようなコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="3e76d-136">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="3e76d-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="3e76d-137">**RoleName**</span></span>|<span data-ttu-id="3e76d-138">**状態**</span><span class="sxs-lookup"><span data-stu-id="3e76d-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e76d-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="3e76d-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="3e76d-140">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-140">Running</span></span>  <br/> |
|<span data-ttu-id="3e76d-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="3e76d-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="3e76d-142">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-142">Running</span></span> <br/> |
|<span data-ttu-id="3e76d-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="3e76d-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="3e76d-144">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-144">Running</span></span>  <br/> |
|<span data-ttu-id="3e76d-145">{レジストラー, UserServer, EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="3e76d-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="3e76d-146">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-146">Running</span></span>  <br/> |
|<span data-ttu-id="3e76d-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="3e76d-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="3e76d-148">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-148">Running</span></span>  <br/> |
|<span data-ttu-id="3e76d-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="3e76d-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="3e76d-150">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-150">Running</span></span>  <br/> |
|<span data-ttu-id="3e76d-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="3e76d-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="3e76d-152">実行中</span><span class="sxs-lookup"><span data-stu-id="3e76d-152">Running</span></span>  <br/> |
   
<span data-ttu-id="3e76d-153">詳細については [、「Get-CsWindowsService」を参照してください](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3e76d-153">For details, see [Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="3e76d-154">サービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3e76d-154">View details about a service</span></span>
<span data-ttu-id="3e76d-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="3e76d-155"><a name="view_details"> </a></span></span>

<span data-ttu-id="3e76d-156">Skype for Business Server コントロール パネルを使用して、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="3e76d-157">各サービスの状態と、関連付けられたデータベース、ポート、依存サービスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="3e76d-158">サービスの詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-158">To view details for a service</span></span>

1. <span data-ttu-id="3e76d-159">Skype for Business Server の定義済みの管理役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="3e76d-160">Skype for Business Server で使用できる定義済みの管理役割の詳細については、「Planning for Role-Based **アクセス制御」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="3e76d-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="3e76d-161">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-162">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e76d-163">[**状態**] ページで、一覧を並べ替えるか検索して、表示するコンピューターをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="3e76d-164">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-164">Click **Properties**.</span></span>
6. <span data-ttu-id="3e76d-165">[**コンピューター詳細の表示**] ウィンドウで、必要な場合はサービスの一覧を並べ替えてから、表示するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="3e76d-166">必要に応じて、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="3e76d-167">指定したサービスの最新の状態を表示するには、[**サービスの状態の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="3e76d-168">指定したサービスの詳細を表示するには、[**プロパティ**] をクリックしてから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="3e76d-169">トポロジ内のすべてのコンピューターの一覧を返すには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="3e76d-170">Skype for Business Server サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="3e76d-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="3e76d-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="3e76d-171"><a name="StartStop"> </a></span></span>

<span data-ttu-id="3e76d-172">Skype for Business Server コントロール パネルを使用すると、特定のコンピューターで実行されている Skype for Business Server サービスの開始または停止、または特定のサービスの開始または停止を行えます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="3e76d-173">コンピューター上のすべての Skype for Business サービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="3e76d-174">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="3e76d-175">CsServerAdministrator または CsAdministrator RBAC の役割が割り当てられているかどうかを確認するには、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e76d-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="3e76d-176">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-177">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e76d-178">[**状態**] ページで、必要に応じてリストを並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを見つけ、クリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="3e76d-179">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-179">Click **Action**.</span></span>
6. <span data-ttu-id="3e76d-180">[**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="3e76d-181">特定のサービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="3e76d-182">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="3e76d-183">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-184">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e76d-185">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="3e76d-186">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-186">Click **Properties**.</span></span>
6. <span data-ttu-id="3e76d-187">必要に応じて、サービスのリストを並べ替え、開始または停止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="3e76d-188">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-188">Click **Action**.</span></span>
8. <span data-ttu-id="3e76d-189">[**サービスの開始**] または [**サービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="3e76d-190">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="3e76d-191">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="3e76d-191">Prevent sessions for services</span></span>
<span data-ttu-id="3e76d-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="3e76d-192"><a name="prevent_session"> </a></span></span>

<span data-ttu-id="3e76d-193">Skype for Business Server コントロール パネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを防止したり、特定の Skype for Business Server サービスの新しいセッションを防止したりできます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="3e76d-194">コンピューター上のすべての Skype for Business サービスの新しいセッションを防止するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="3e76d-195">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="3e76d-196">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-197">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e76d-198">[状態 **] ページ** で、必要に応じて一覧を並べ替えまたは検索して、新しいセッションを防止するサービスを実行しているコンピューターを検索し、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="3e76d-199">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-199">Click **Action**.</span></span>
6. <span data-ttu-id="3e76d-200">[すべての **サービスの新しいセッションを防止する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3e76d-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="3e76d-201">特定のサービスの新しいセッションを防止するには</span><span class="sxs-lookup"><span data-stu-id="3e76d-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="3e76d-202">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="3e76d-203">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e76d-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="3e76d-204">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="3e76d-205">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="3e76d-206">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-206">Click **Properties**.</span></span>
6. <span data-ttu-id="3e76d-207">必要に応じてサービスの一覧を並べ替え、新しいセッションを防止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="3e76d-208">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-208">Click **Action**.</span></span>
8. <span data-ttu-id="3e76d-209">[サービス **の新しいセッションを防止する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3e76d-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="3e76d-210">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e76d-210">Click **Close**.</span></span>
