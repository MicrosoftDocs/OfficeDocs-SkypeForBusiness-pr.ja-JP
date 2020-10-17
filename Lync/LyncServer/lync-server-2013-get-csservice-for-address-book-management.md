---
title: 'Lync Server 2013: アドレス帳管理の Get-CsService'
description: 'Lync Server 2013: アドレス帳管理用に Get-CsService します。'
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
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554653"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理の Get-CsService

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

このコマンドレットを実行できる人は次のとおりです。 既定では、次のグループのメンバーが、Get-CsService コマンドレットのローカル実行を承認されています。RTCUniversalUserAdmins、RTCUniversalServerAdmins。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-CsService は、インフラストラクチャで定義されている Web サービスの現在の構成を取得して表示するのに役立ちます。 このコマンドレットは、プールの完全修飾ドメイン名 (FQDN) および WebServer パラメーターを定義することで、アドレス帳のハンドラーおよび配布リストの拡張 URI など、サーバーが提供する Web ベースのサービスを戻します。

次にその例を示します。

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

このコマンドレットは、次の情報を返します。

Identity: WebServer/pool01. .net

ファイルストア: ファイルストア: dc01. .net

UserServer: UserServer: pool01. .net

PrimaryHttpPort:80

PrimaryHttpsPort: 443

ExternalHttpPort: 8080

ExternalHttpsPort: 4443

PublishedPrimaryHttpPort:80

PublishedPrimaryHttpsPort: 443

PublishedExternalHttpPort:80

PublishedExternalHttpsPort: 443

ReachPrimaryPsomServerPort: 8060

ReachExternalPsomServerPort: 8061

AppSharingPortStart: 49152

AppSharingPortCount: 16383

LIServiceInternalUri: https://internalweb.contoso.net/locationinformation/liservice.svc

Abハンドラ Internaluri: https://internalweb.contoso.net/abs/handler

Abハンドラ Externaluri: https://csweb.contoso.com/abs/handler

Dlのこの Uri: https://internalweb.contoso.net/groupexpansion/service.svc

Dlます。 Externaluri: https://csweb.contoso.com/groupexpansion/service.svc

Caハンドラ Internaluri: https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

共に、次のようにします。 https://internalweb.contoso.net/CollabContent

共に、外部 Uri: https://csweb.contoso.com/CollabContent

Caハンドラ Externaluri: https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri: https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri: http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri: https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri : https://csweb.contoso.com/Meet

ダイヤルイン Externaluri: https://csweb.contoso.com/Dialin

CscpInternalUri : https://internalweb.contoso.net/Cscp

ReachExternalUri : https://csweb.contoso.com/Reach

ReachInternalUri : https://internalweb.contoso.net/Reach

WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {レジストラー: pool01. ConferencingServer: pool01.. .net}

ServiceId: 1-1

SiteId: サイト: Redmond

PoolFqdn: pool01.contoso.net

バージョン: 5

役割: WebServer

<div>

## <a name="see-also"></a>関連項目


[取得-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

