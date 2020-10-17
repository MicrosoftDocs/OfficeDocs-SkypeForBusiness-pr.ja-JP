---
title: 'Lync Server 2013: Office Web Apps サーバーと Lync Server 2013 の有効化'
description: 'Lync Server 2013: Office Web Apps サーバーと Lync Server 2013 を有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546523"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="bed54-103">Office Web Apps Server および Lync Server 2013 との統合の構成</span><span class="sxs-lookup"><span data-stu-id="bed54-103">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed54-104">_**トピックの最終更新日:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="bed54-104">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="bed54-105">Lync Server 2013 は、Office Web Apps サーバーを採用して PowerPoint プレゼンテーションを処理します。</span><span class="sxs-lookup"><span data-stu-id="bed54-105">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="bed54-106">このアプローチの利点については、「 [Lync Server 2013 の web 会議の概要](lync-server-2013-web-conferencing-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bed54-106">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="bed54-107">これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールする必要があります。また、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bed54-107">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="bed54-108">このドキュメントでは、Office Web Apps サーバーを使用するように Lync Server 2013 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bed54-108">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="bed54-109">このドキュメントでは、Office Web Apps サーバー自体をインストールする方法について説明します。その情報については、「Microsoft Office Web Apps 展開 web サイト」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="bed54-109">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="bed54-110">このガイドには、Office Web Apps サーバーの完全な前提条件に関する情報が含まれています。Office Web Apps サーバーは、Lync Server、Microsoft SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンのコンピューターにインストールする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bed54-110">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="bed54-111">(そのコンピューターに Microsoft Office のバージョンがインストールされていないことが必要です。)Office Web Apps サーバーを実行するために使用するコンピューターには、(.NET Framework 4.5 および Windows PowerShell 3.0 を含む) 特定のソフトウェアセットがインストールされている必要もあります。これらの要件と、証明書およびインターネットインフォメーションサービス (IIS) の構成に関する情報については、「Microsoft Office Web Apps 展開 web サイト」を参照して <https://go.microsoft.com/fwlink/p/?linkid=257525> ください。</span><span class="sxs-lookup"><span data-stu-id="bed54-111">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bed54-112">Office Web Apps サーバーの最新のイテレーションは、Lync Server 2013 でサポートされている Office Online Server と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="bed54-112">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="bed54-113">詳細については、 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server のドキュメント</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bed54-113">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="bed54-114">このドキュメントでは、次のトピックの分野について説明します。</span><span class="sxs-lookup"><span data-stu-id="bed54-114">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="bed54-115">Office Web Apps サーバーで動作するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="bed54-115">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="bed54-116">Lync Server 2013 でのリバースプロキシサーバーを使用した Office Web Apps サーバーの発行</span><span class="sxs-lookup"><span data-stu-id="bed54-116">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="bed54-117">Lync Server 2013 での Office Web Apps サーバーの構成の検証</span><span class="sxs-lookup"><span data-stu-id="bed54-117">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="bed54-118">Office Web Apps サーバーで使用する Lync Server 2013 のクライアントの構成</span><span class="sxs-lookup"><span data-stu-id="bed54-118">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

