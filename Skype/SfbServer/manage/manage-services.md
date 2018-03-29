---
title: ビジネス サーバー 2015 の Skype のサービスを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: この資料では、ビジネス サーバー 2015 トポロジの場合、Skype で実行されているサービスを管理する方法について説明します。
ms.openlocfilehash: f8406d473b1d2ae644ac56d071313d2b488169fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-services-for-skype-for-business-server-2015"></a><span data-ttu-id="ac4a3-103">ビジネス サーバー 2015 の Skype のサービスを管理します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-103">Manage services for Skype for Business Server 2015</span></span>

<span data-ttu-id="ac4a3-104">この資料では、ビジネス サーバー 2015 トポロジの場合、Skype で実行されているサービスを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-104">This article describes how to manage services running in a Skype for Business Server 2015 topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a><span data-ttu-id="ac4a3-105">ビジネス サーバー 2015 の Skype を実行しているコンピューターの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-105">View a list of computers running Skype for Business Server 2015</span></span>
<span data-ttu-id="ac4a3-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4a3-106"></span></span>

<span data-ttu-id="ac4a3-107">Skype ビジネス サーバーのコントロール パネルを使用するには、トポロジ内のビジネス サーバー 2015 の Skype を実行しているし、それぞれのサービスの状態を表示するすべてのコンピューターの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server 2015 in your topology and see the service status of each.</span></span> <span data-ttu-id="ac4a3-108">コンピューター、プール、またはサイトでリストを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="ac4a3-109">Skype をビジネスのサーバーを実行しているコンピューターの一覧を表示するのには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="ac4a3-110">、Skype のビジネス サーバー 2015 の定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server 2015, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="ac4a3-111">ビジネス サーバー 2015 の Skype で利用できる定義済みの管理者の役割についての詳細は、**役割ベースのアクセス制御のための計画**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-111">For details about the predefined administrative roles available in Skype for Business Server 2015, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="ac4a3-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="ac4a3-113">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="ac4a3-114">[**状態**] ページで、必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="ac4a3-115">**コンピューター**、**プール**、または**サイト**列の見出しをクリックし、上向き矢印または下向きの矢印をクリックし、リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="ac4a3-116">最新のリストを表示するのには**更新**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="ac4a3-117">検索フィールドにコンピューター名を入力して、特定のコンピューターを検索します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a><span data-ttu-id="ac4a3-118">Skype ビジネス 2015年サーバーで実行されているサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-118">View the status of services running on a Skype for Business 2015 server</span></span>
<span data-ttu-id="ac4a3-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4a3-119"></span></span>

<span data-ttu-id="ac4a3-120">ビジネス サーバー トポロジの場合、Skype で特定のコンピューター上で実行され、各サービスの状態を表示するすべてのサービスを表示するのには、ビジネス サーバーのコントロール パネルの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="ac4a3-121">コンピューターで実行されているサービスのステータスを表示するのには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="ac4a3-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="ac4a3-123">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-124">左側のナビゲーション ・ バーでは、**トポロジー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="ac4a3-125">[**状態**] ページで、並べ替えやを知り、コンピューターを検索するのには、必要に応じて、リストを検索、[コンピューター名] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="ac4a3-126">次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-126">Do any of the following:</span></span>
   - <span data-ttu-id="ac4a3-127">コンピューター上で実行されているサービスの最新の状態を表示するには、**サービスのステータスを取得する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="ac4a3-128">コンピューターと各サービスの状態で実行されている特定のサービスの一覧を表示するには、**プロパティ**] をクリックし、**閉じる**一覧に戻る] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="ac4a3-129">Windows Powershell コマンドレットでサービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="ac4a3-130">Windows PowerShell と**Get CsWindowsService**コマンドレットを使用してサービスの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="ac4a3-131">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ac4a3-132">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ac4a3-133">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="ac4a3-134">サービスの状態を表示するのには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-134">To view service status</span></span>

<span data-ttu-id="ac4a3-135">コンピューターでサービスの状態を表示するのには、Skype でビジネス サーバー管理シェルの次のようなコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="ac4a3-136">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="ac4a3-137">**役割名**</span><span class="sxs-lookup"><span data-stu-id="ac4a3-137">**RoleName**</span></span>|<span data-ttu-id="ac4a3-138">**状態**</span><span class="sxs-lookup"><span data-stu-id="ac4a3-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac4a3-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="ac4a3-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="ac4a3-140">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-140">Running</span></span>  <br/> |
|<span data-ttu-id="ac4a3-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="ac4a3-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="ac4a3-142">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-142">Running</span></span> <br/> |
|<span data-ttu-id="ac4a3-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="ac4a3-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="ac4a3-144">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-144">Running</span></span>  <br/> |
|<span data-ttu-id="ac4a3-145">{登録、UserServer、edgeserver があります。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="ac4a3-146">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-146">Running</span></span>  <br/> |
|<span data-ttu-id="ac4a3-147">{アプリケーション サーバー。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="ac4a3-148">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-148">Running</span></span>  <br/> |
|<span data-ttu-id="ac4a3-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="ac4a3-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="ac4a3-150">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-150">Running</span></span>  <br/> |
|<span data-ttu-id="ac4a3-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="ac4a3-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="ac4a3-152">実行しています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-152">Running</span></span>  <br/> |
   
<span data-ttu-id="ac4a3-153">詳細については、 [Get CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="ac4a3-154">サービスに関する詳細を表示</span><span class="sxs-lookup"><span data-stu-id="ac4a3-154">View details about a service</span></span>
<span data-ttu-id="ac4a3-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4a3-155"></span></span>

<span data-ttu-id="ac4a3-156">Skype ビジネス サーバーのコントロール パネルを使用するには、トポロジ内の特定のコンピューターで実行されている各サービスについての詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="ac4a3-157">各サービスおよび関連するデータベース、ポート、および依存するサービスなどの詳細の状態を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="ac4a3-158">サービスの詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-158">To view details for a service</span></span>

1. <span data-ttu-id="ac4a3-159">、Skype のビジネス サーバー 2015 の定義済みの管理者の役割のいずれかに割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server 2015, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="ac4a3-160">ビジネス サーバー 2015 の Skype で利用できる定義済みの管理者の役割についての詳細は、**役割ベースのアクセス制御のための計画**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-160">For details about the predefined administrative roles available in Skype for Business Server 2015, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="ac4a3-161">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-162">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="ac4a3-163">**状態**] ページでは、並べ替え、リストを検索やコンピューターを表示する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="ac4a3-164">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-164">Click **Properties**.</span></span>
6. <span data-ttu-id="ac4a3-165">**コンピューター詳細の表示**] ウィンドウで、必要に応じて、サービスの一覧を並べ替えるを表示しサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="ac4a3-166">必要に応じて次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="ac4a3-167">その特定のサービスの最新の状態を表示するには、**サービスのステータスを取得する**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="ac4a3-168">その特定のサービスの詳細を表示するには、**プロパティ**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="ac4a3-169">戻るには、トポロジ内のすべてのコンピューターの一覧に、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a><span data-ttu-id="ac4a3-170">開始または Skype をビジネス サーバー 2015 サービスの停止</span><span class="sxs-lookup"><span data-stu-id="ac4a3-170">Start or stop Skype for Business Server 2015 services</span></span>
<span data-ttu-id="ac4a3-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4a3-171"></span></span>

<span data-ttu-id="ac4a3-172">Skype ビジネス サーバーのコントロール パネルを使用するにを開始または停止する特定のコンピューターで実行されているサーバー 2015 のビジネス サービスのすべての Skype を開始または特定のサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server 2015 services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="ac4a3-173">起動またはコンピューター上のすべての Skype のビジネス ・ サービスを停止するには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="ac4a3-174">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="ac4a3-175">かどうかが割り当てられている、CsServerAdministrator または CsAdministrator の RBAC の役割には、次のようなコマンドを実行することによって判断できます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"

  ```

2. <span data-ttu-id="ac4a3-176">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-177">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="ac4a3-178">**状態**] ページで、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="ac4a3-179">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-179">Click **Action**.</span></span>
6. <span data-ttu-id="ac4a3-180">**開始のすべてのサービス**または**サービスをすべて停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="ac4a3-181">開始または特定のサービスを停止するには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="ac4a3-182">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="ac4a3-183">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-184">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="ac4a3-185">**状態**] ページで、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="ac4a3-186">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-186">Click **Properties**.</span></span>
6. <span data-ttu-id="ac4a3-187">必要に応じて、サービスの一覧を並べ替えるし、サービスを開始または停止する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="ac4a3-188">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-188">Click **Action**.</span></span>
8. <span data-ttu-id="ac4a3-189">**サービスを開始**または**停止するサービス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="ac4a3-190">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="ac4a3-191">サービスのセッションを防止します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-191">Prevent sessions for services</span></span>
<span data-ttu-id="ac4a3-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4a3-192"></span></span>

<span data-ttu-id="ac4a3-193">サーバー 2015 のビジネス サービスの特定の Skype の新しいセッションを防ぐためにまたは特定のコンピューターで実行されているサーバー 2015 のビジネス サービスのすべての Skype の新しいセッションを防ぐためには、ビジネス サーバーのコントロール パネルの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server 2015 services running on a specific computer or to prevent new sessions for a specific Skype for Business Server 2015 service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="ac4a3-194">コンピューター上のビジネス サービスのすべての Skype の新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="ac4a3-195">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
2. <span data-ttu-id="ac4a3-196">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-197">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="ac4a3-198">[**状態**] ページで、並べ替えまたはとしてリストを検索は、新しいセッションを禁止し、クリックするサービスを実行しているコンピューターを検索するのには必要です。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="ac4a3-199">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-199">Click **Action**.</span></span>
6. <span data-ttu-id="ac4a3-200">**すべてのサービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="ac4a3-201">特定のサービスの新しいセッションを防止するには</span><span class="sxs-lookup"><span data-stu-id="ac4a3-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="ac4a3-202">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは2015。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
2. <span data-ttu-id="ac4a3-203">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="ac4a3-204">左側のナビゲーション ・ バーで [**トポロジ**] をクリックし、**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="ac4a3-205">**状態**] ページで、並べ替え、またはサービスを実行しているコンピューターを検索するのには、必要に応じてリストを検索するか、開始、停止、および、クリックしています。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="ac4a3-206">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-206">Click **Properties**.</span></span>
6. <span data-ttu-id="ac4a3-207">必要に応じて、サービスの一覧を並べ替えるし、サービスの新しいセッションを禁止する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="ac4a3-208">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-208">Click **Action**.</span></span>
8. <span data-ttu-id="ac4a3-209">**サービスの新しいセッションを禁止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="ac4a3-210">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4a3-210">Click **Close**.</span></span>
    

