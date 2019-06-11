---
title: 'Lync Server 2013: リバース プロキシ サーバーの DNS レコードの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5608e3dd851c943e890fe3f718a38c2df02c1c08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="c5d88-102">Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="c5d88-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5d88-103">_**最終更新日:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="c5d88-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="c5d88-104">外部 DNS を作成する Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー 2006 SP1、Forefront Threat Management Gateway 2010 Server、または Internet Information Server アプリケーション要求ルーティングのパブリック外部インターフェイスを指すレコード「 [Lync Server 2013 での microsoft edge サポートのための DNS の構成](lync-server-2013-configure-dns-for-edge-support.md)」で説明します。</span><span class="sxs-lookup"><span data-stu-id="c5d88-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="c5d88-105">各プール、ディレクター (またはディレクタープール)、および各シンプル URL について、外部 Web サービス Fqdn 用の DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5d88-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="c5d88-106">リバースプロキシに対するクライアントの解決に関する最小の DNS レコードは、次のレコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5d88-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="c5d88-107">ディレクターおよびディレクタープールに対して公開された外部 web サービスを定義する Host (A) レコード ( **webdirext.contoso.com**など)</span><span class="sxs-lookup"><span data-stu-id="c5d88-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="c5d88-108">任意のフロントエンドプールおよび Standard Edition サーバーの役割 (たとえば、 **webext.contoso.com**) でホストされている外部 web サービスに対して公開されている外部 web サービスを定義する Host (A) レコード</span><span class="sxs-lookup"><span data-stu-id="c5d88-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="c5d88-109">単純な Url (たとえば、 **dialin.contoso.com**や**meet.contoso.com**) のホスト (A) レコード</span><span class="sxs-lookup"><span data-stu-id="c5d88-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="c5d88-110">Lync Discover 外部レコードのホスト (A) レコード。また、Lync Web App、scheduler、モビリティなどのすべての Web アプリ (たとえば、 **lyncdiscover.contoso.com**) の自動検出へのポインターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5d88-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="c5d88-111">Office Web Apps サーバーの URL のホスト (A) レコード (たとえば、 **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="c5d88-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="c5d88-112">詳細については、「 [DNS の概要-Lync Server 2013 のリバースプロキシ](lync-server-2013-dns-summary-reverse-proxy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5d88-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

