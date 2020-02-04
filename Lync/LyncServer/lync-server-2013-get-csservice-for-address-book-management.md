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

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>Lync Server 2013 でのアドレス帳管理のための CsService

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーは、RTCUniversalUserAdmins、RTCUniversalServerAdmins のように、ローカルで CsService コマンドレットを実行することを許可されています。 このコマンドレットが割り当てられているすべての役割ベースのアクセス制御 (RBAC) ロールのリストを返すには (自分自身で作成したカスタム RBAC ロールを含む)、Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

CsService は、インフラストラクチャで定義された Web サービスの現在の構成を取得して表示するのに役立ちます。 プールの完全修飾ドメイン名 (FQDN) とパラメーター WebServer を定義することによって、サーバーによって提供される web ベースのサービス (アドレス帳ハンドラー、配布リスト展開の Uri など) が返されます。

次に例を示します。

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

このコマンドレットは、次の値を返します。

Identity: WebServer: pool01. net.tcp

FileStore: FileStore: dc01. net

UserServer: UserServer: pool01. net

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

LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc

Abハンドラ Internaluri:https://internalweb.contoso.net/abs/handler

Abハンドラ Externaluri:https://csweb.contoso.com/abs/handler

Dlのお持ちの Uri:https://internalweb.contoso.net/groupexpansion/service.svc

Dlの外部の Uri:https://csweb.contoso.com/groupexpansion/service.svc

Caハンドラ Internaluri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

他のコンテンツ:https://internalweb.contoso.net/CollabContent

他のコンテンツ:https://csweb.contoso.com/CollabContent

Caハンドラ Externaluri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri:http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri:https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

ダイヤルイン Externaluri:https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {レジストラー: pool01. net、ConferencingServer: pool01. net}

ServiceId: 1-1-1

SiteId: サイト: レドモンド

PoolFqdn: pool01.contoso.net

バージョン: 5

役割: WebServer

<div>

## <a name="see-also"></a>関連項目


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

