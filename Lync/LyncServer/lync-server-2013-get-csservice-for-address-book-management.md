---
title: 'Lync Server 2013: アドレス帳管理の Get-CsService'
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
ms.openlocfilehash: 43c2c6ada55c1bc7db6c8593ee14028b986a2b78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512624"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="48162-102">Lync Server 2013 でのアドレス帳管理の Get-CsService</span><span class="sxs-lookup"><span data-stu-id="48162-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48162-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="48162-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="48162-p101">このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Get-CsService コマンドレットのローカル実行を承認されています。RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="48162-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="48162-106">Get-CsService は、インフラストラクチャで定義されている Web サービスの現在の構成を取得して表示するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48162-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="48162-107">このコマンドレットは、プールの完全修飾ドメイン名 (FQDN) および WebServer パラメーターを定義することで、アドレス帳のハンドラーおよび配布リストの拡張 URI など、サーバーが提供する Web ベースのサービスを戻します。</span><span class="sxs-lookup"><span data-stu-id="48162-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="48162-108">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="48162-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="48162-109">このコマンドレットは、次の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="48162-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="48162-110">Identity: WebServer/pool01. .net</span><span class="sxs-lookup"><span data-stu-id="48162-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="48162-111">ファイルストア: ファイルストア: dc01. .net</span><span class="sxs-lookup"><span data-stu-id="48162-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="48162-112">UserServer: UserServer: pool01. .net</span><span class="sxs-lookup"><span data-stu-id="48162-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="48162-113">PrimaryHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="48162-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="48162-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="48162-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="48162-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="48162-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="48162-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="48162-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="48162-117">PublishedPrimaryHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="48162-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="48162-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="48162-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="48162-119">PublishedExternalHttpPort:80</span><span class="sxs-lookup"><span data-stu-id="48162-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="48162-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="48162-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="48162-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="48162-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="48162-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="48162-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="48162-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="48162-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="48162-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="48162-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="48162-125">LIServiceInternalUri: https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="48162-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="48162-126">Abハンドラ Internaluri: https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="48162-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="48162-127">Abハンドラ Externaluri: https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="48162-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="48162-128">Dlのこの Uri: https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="48162-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="48162-129">Dlます。 Externaluri: https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="48162-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="48162-130">Caハンドラ Internaluri: https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="48162-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="48162-132">共に、次のようにします。 https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="48162-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="48162-133">共に、外部 Uri: https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="48162-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="48162-134">Caハンドラ Externaluri: https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="48162-135">DeviceUpdateDownloadInternalUri: https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="48162-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="48162-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="48162-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="48162-137">DeviceUpdateStoreInternalUri: http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="48162-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="48162-138">DeviceUpdateStoreExternalUri: https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="48162-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="48162-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="48162-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="48162-141">MeetExternalUri : https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="48162-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="48162-142">ダイヤルイン Externaluri: https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="48162-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="48162-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="48162-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="48162-144">ReachExternalUri : https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="48162-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="48162-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="48162-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="48162-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="48162-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="48162-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="48162-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48162-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="48162-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="48162-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="48162-150">DependentServiceList: {レジストラー: pool01. ConferencingServer: pool01.. .net}</span><span class="sxs-lookup"><span data-stu-id="48162-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="48162-151">ServiceId: 1-1</span><span class="sxs-lookup"><span data-stu-id="48162-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="48162-152">SiteId: サイト: Redmond</span><span class="sxs-lookup"><span data-stu-id="48162-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="48162-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="48162-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="48162-154">バージョン: 5</span><span class="sxs-lookup"><span data-stu-id="48162-154">Version : 5</span></span>

<span data-ttu-id="48162-155">役割: WebServer</span><span class="sxs-lookup"><span data-stu-id="48162-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="48162-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="48162-156">See Also</span></span>


[<span data-ttu-id="48162-157">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="48162-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

