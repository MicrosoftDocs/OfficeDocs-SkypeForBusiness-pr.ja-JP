---
title: 'Lync Server 2013: アドレス帳管理のための CsService'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f4533-102">Lync Server 2013 でのアドレス帳管理のための CsService</span><span class="sxs-lookup"><span data-stu-id="f4533-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4533-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f4533-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f4533-104">このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、RTCUniversalUserAdmins、RTCUniversalServerAdmins のように、ローカルで CsService コマンドレットを実行することを許可されています。</span><span class="sxs-lookup"><span data-stu-id="f4533-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f4533-105">このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4533-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="f4533-106">CsService は、インフラストラクチャで定義された Web サービスの現在の構成を取得して表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4533-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="f4533-107">プールの完全修飾ドメイン名 (FQDN) とパラメーター WebServer を定義することによって、サーバーによって提供される web ベースのサービス (アドレス帳ハンドラー、配布リスト展開の Uri など) が返されます。</span><span class="sxs-lookup"><span data-stu-id="f4533-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="f4533-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f4533-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="f4533-109">このコマンドレットは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f4533-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="f4533-110">Identity: WebServer: pool01. net.tcp</span><span class="sxs-lookup"><span data-stu-id="f4533-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="f4533-111">FileStore: FileStore: dc01. net</span><span class="sxs-lookup"><span data-stu-id="f4533-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="f4533-112">UserServer: UserServer: pool01. net</span><span class="sxs-lookup"><span data-stu-id="f4533-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="f4533-113">PrimaryHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="f4533-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="f4533-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="f4533-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="f4533-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="f4533-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="f4533-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="f4533-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="f4533-117">PublishedPrimaryHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="f4533-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="f4533-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="f4533-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="f4533-119">PublishedExternalHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="f4533-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="f4533-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="f4533-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="f4533-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="f4533-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="f4533-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="f4533-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="f4533-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="f4533-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="f4533-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="f4533-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="f4533-125">LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="f4533-126">Abハンドラ Internaluri:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="f4533-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="f4533-127">Abハンドラ Externaluri:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="f4533-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="f4533-128">Dlのお持ちの Uri:https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="f4533-129">Dlの外部の Uri:https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="f4533-130">Caハンドラ Internaluri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="f4533-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="f4533-132">他のコンテンツ:https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="f4533-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="f4533-133">他のコンテンツ:https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="f4533-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="f4533-134">Caハンドラ Externaluri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="f4533-135">DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="f4533-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="f4533-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="f4533-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="f4533-137">DeviceUpdateStoreInternalUri:http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="f4533-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="f4533-138">DeviceUpdateStoreExternalUri:https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="f4533-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="f4533-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="f4533-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="f4533-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="f4533-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="f4533-142">ダイヤルイン Externaluri:https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="f4533-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="f4533-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="f4533-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="f4533-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="f4533-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="f4533-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="f4533-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="f4533-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="f4533-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="f4533-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="f4533-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4533-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="f4533-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f4533-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="f4533-150">DependentServiceList: {レジストラー: pool01. net、ConferencingServer: pool01. net}</span><span class="sxs-lookup"><span data-stu-id="f4533-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="f4533-151">ServiceId: 1-1-1</span><span class="sxs-lookup"><span data-stu-id="f4533-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="f4533-152">SiteId: サイト: レドモンド</span><span class="sxs-lookup"><span data-stu-id="f4533-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="f4533-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f4533-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="f4533-154">バージョン: 5</span><span class="sxs-lookup"><span data-stu-id="f4533-154">Version : 5</span></span>

<span data-ttu-id="f4533-155">役割: WebServer</span><span class="sxs-lookup"><span data-stu-id="f4533-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f4533-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4533-156">See Also</span></span>


[<span data-ttu-id="f4533-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="f4533-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

