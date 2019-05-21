---
title: Skype for Business Server のサービスを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: この記事では、Skype for Business Server のトポロジで実行されているサービスを管理する方法について説明します。
ms.openlocfilehash: 9d1a79226422da57eee36e27590769f76b89b560
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279621"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="bbc0c-103">Skype for Business Server のサービスを管理する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="bbc0c-104">この記事では、Skype for Business Server のトポロジで実行されているサービスを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="bbc0c-105">Skype for Business Server を実行しているコンピューターの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="bbc0c-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc0c-106"></span></span>

<span data-ttu-id="bbc0c-107">Skype for Business Server コントロールパネルを使用して、トポロジで Skype for Business Server を実行しているすべてのコンピューターの一覧を表示し、それぞれのサービスの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="bbc0c-108">リストは、コンピューター、プール、またはサイトによって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="bbc0c-109">Skype for Business Server を実行しているコンピューターの一覧を表示するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="bbc0c-110">Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="bbc0c-111">Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「**ロールベースのアクセス制御の計画**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="bbc0c-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="bbc0c-113">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="bbc0c-114">[**状態**] ページで、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="bbc0c-115">**コンピューター**、**プール**、または**サイト**の列見出しをクリックし、上矢印または下矢印をクリックして、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="bbc0c-116">最新のリストを表示するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="bbc0c-117">検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="bbc0c-118">Skype for Business server で実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="bbc0c-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc0c-119"></span></span>

<span data-ttu-id="bbc0c-120">Skype for Business Server コントロールパネルを使用して、Skype for Business Server のトポロジに含まれる特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="bbc0c-121">コンピューターで実行されているサービスの状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="bbc0c-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="bbc0c-123">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-124">左側のナビゲーションバーで、[**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="bbc0c-125">[**状態**] ページで、必要に応じてリストを並べ替えるか検索して、目的のコンピューターを見つけ、コンピューター名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="bbc0c-126">次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-126">Do any of the following:</span></span>
   - <span data-ttu-id="bbc0c-127">コンピューター上で実行されているサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="bbc0c-128">コンピューター上で実行されている特定のサービスの一覧と各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックしてリストに戻ります。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="bbc0c-129">Windows Powershell コマンドレットを使用してサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="bbc0c-130">また、Windows PowerShell と、ユーザーの**取得-CsWindowsService**コマンドレットを使用して、サービスの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="bbc0c-131">このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bbc0c-132">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bbc0c-133">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="bbc0c-134">サービスの状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-134">To view service status</span></span>

<span data-ttu-id="bbc0c-135">コンピューターでサービスの状態を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="bbc0c-136">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="bbc0c-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="bbc0c-137">**RoleName**</span></span>|<span data-ttu-id="bbc0c-138">**状態**</span><span class="sxs-lookup"><span data-stu-id="bbc0c-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bbc0c-139">W3SVC</span><span class="sxs-lookup"><span data-stu-id="bbc0c-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="bbc0c-140">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-140">Running</span></span>  <br/> |
|<span data-ttu-id="bbc0c-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="bbc0c-142">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-142">Running</span></span> <br/> |
|<span data-ttu-id="bbc0c-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="bbc0c-144">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-144">Running</span></span>  <br/> |
|<span data-ttu-id="bbc0c-145">{レジストラー、UserServer、EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="bbc0c-146">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-146">Running</span></span>  <br/> |
|<span data-ttu-id="bbc0c-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="bbc0c-148">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-148">Running</span></span>  <br/> |
|<span data-ttu-id="bbc0c-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="bbc0c-150">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-150">Running</span></span>  <br/> |
|<span data-ttu-id="bbc0c-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="bbc0c-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="bbc0c-152">実行</span><span class="sxs-lookup"><span data-stu-id="bbc0c-152">Running</span></span>  <br/> |
   
<span data-ttu-id="bbc0c-153">詳細については、「 [CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="bbc0c-154">サービスについての詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-154">View details about a service</span></span>
<span data-ttu-id="bbc0c-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc0c-155"></span></span>

<span data-ttu-id="bbc0c-156">Skype for Business Server コントロールパネルを使うと、トポロジ内の特定のコンピューターで実行されている各サービスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="bbc0c-157">各サービスの状態と、関連するデータベース、ポート、依存サービスなどの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="bbc0c-158">サービスの詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-158">To view details for a service</span></span>

1. <span data-ttu-id="bbc0c-159">Skype for Business Server の事前定義された管理者ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="bbc0c-160">Skype for Business Server で利用可能な定義済みの管理者ロールの詳細については、「**ロールベースのアクセス制御の計画**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="bbc0c-161">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-162">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="bbc0c-163">[**状態**] ページで、リストを並べ替えるか検索して、表示するコンピューターをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="bbc0c-164">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-164">Click **Properties**.</span></span>
6. <span data-ttu-id="bbc0c-165">[**コンピューターの詳細の表示**] ウィンドウで、必要に応じてサービスの一覧を並べ替えて、表示するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="bbc0c-166">必要に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="bbc0c-167">特定のサービスの最新の状態を表示するには、[**サービスの状態を取得**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="bbc0c-168">特定のサービスの詳細を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="bbc0c-169">トポロジに含まれるすべてのコンピューターの一覧に戻るには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="bbc0c-170">Skype for Business Server サービスを開始または停止する</span><span class="sxs-lookup"><span data-stu-id="bbc0c-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="bbc0c-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc0c-171"></span></span>

<span data-ttu-id="bbc0c-172">Skype for Business Server コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスを開始または停止することができます。また、特定のサービスを開始または停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="bbc0c-173">コンピューター上のすべての Skype for Business サービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="bbc0c-174">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bbc0c-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="bbc0c-175">次のようなコマンドを実行すると、CsServerAdministrator または CsAdministrator の RBAC 役割が割り当てられているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="bbc0c-176">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-177">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="bbc0c-178">[**状態**] ページで、必要に応じて一覧を並べ替えて検索するか、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="bbc0c-179">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-179">Click **Action**.</span></span>
6. <span data-ttu-id="bbc0c-180">[**すべてのサービスの開始**] または [**すべてのサービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="bbc0c-181">特定のサービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="bbc0c-182">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="bbc0c-183">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-184">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="bbc0c-185">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="bbc0c-186">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-186">Click **Properties**.</span></span>
6. <span data-ttu-id="bbc0c-187">必要に応じてサービスの一覧を並べ替え、開始または停止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="bbc0c-188">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-188">Click **Action**.</span></span>
8. <span data-ttu-id="bbc0c-189">[**サービスの開始**] または [**サービスの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="bbc0c-190">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="bbc0c-191">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="bbc0c-191">Prevent sessions for services</span></span>
<span data-ttu-id="bbc0c-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="bbc0c-192"></span></span>

<span data-ttu-id="bbc0c-193">Skype for Business Server コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Skype for Business Server サービスの新しいセッションを禁止したり、特定の Skype for Business Server サービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="bbc0c-194">コンピューター上のすべての Skype for Business サービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="bbc0c-195">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bbc0c-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="bbc0c-196">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-197">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="bbc0c-198">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="bbc0c-199">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-199">Click **Action**.</span></span>
6. <span data-ttu-id="bbc0c-200">[**すべてのサービスに対して新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="bbc0c-201">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="bbc0c-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="bbc0c-202">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.</span><span class="sxs-lookup"><span data-stu-id="bbc0c-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="bbc0c-203">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="bbc0c-204">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="bbc0c-205">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="bbc0c-206">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-206">Click **Properties**.</span></span>
6. <span data-ttu-id="bbc0c-207">必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="bbc0c-208">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-208">Click **Action**.</span></span>
8. <span data-ttu-id="bbc0c-209">[**サービスの新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="bbc0c-210">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbc0c-210">Click **Close**.</span></span>
    

