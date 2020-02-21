---
title: 'Lync Server 2013: リバースプロキシサーバーの DNS レコードの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c583f5c25ea58f0d1a2ea32246db8eec8f7740
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="1b401-102">Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="1b401-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b401-103">_**トピックの最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="1b401-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="1b401-104">「 [Lync server 2013 での DNS の構成](lync-server-2013-configure-dns-for-edge-support.md)」で説明されているように、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、Forefront Threat Management Gateway 2010 server、または Internet Information Server アプリケーション要求ルーティングのパブリック外部インターフェイスをポイントする外部 DNS A レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b401-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="1b401-105">各プール、ディレクター (またはディレクタープール)、および各簡易 URL に対して、外部 Web サービス Fqdn の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b401-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="1b401-106">リバースプロキシへのクライアント解決用の最小 DNS レコードは、次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b401-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="1b401-107">ディレクターおよびディレクタープール用に公開された外部 web サービスを定義するホスト (A) レコード (たとえば、 **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1b401-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="1b401-108">任意のフロントエンドプールおよび Standard Edition サーバーの役割でホストされている外部 web サービスに対して発行された外部 web サービスを定義するホスト (A) レコード (たとえば、 **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1b401-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="1b401-109">簡易 Url のホスト (A) レコード (たとえば、 **dialin.contoso.com**および**meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1b401-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="1b401-110">Lync discovery External record のホスト (A) レコード。また、Lync Web App、scheduler、モビリティ (たとえば、 **lyncdiscover.contoso.com**) を含むすべての web アプリの自動検出へのポインターも提供します。</span><span class="sxs-lookup"><span data-stu-id="1b401-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="1b401-111">Office Web Apps サーバーの URL のホスト (A) レコード (たとえば**officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1b401-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="1b401-112">詳細については、「 [DNS の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-dns-summary-reverse-proxy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b401-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

