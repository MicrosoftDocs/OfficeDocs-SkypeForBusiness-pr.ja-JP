---
title: 'Lync Server 2013: Lync Server 2013 と Office Web Apps サーバーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a88a9a1649d8842c9c2c4a1f55aefcfc7853e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="d00bb-102">Lync Server 2013 と Office Web Apps サーバーの統合の構成</span><span class="sxs-lookup"><span data-stu-id="d00bb-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d00bb-103">_**最終更新日:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="d00bb-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="d00bb-104">Lync Server 2013 は、PowerPoint プレゼンテーションを処理するために Office Web Apps サーバーを採用しています。</span><span class="sxs-lookup"><span data-stu-id="d00bb-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="d00bb-105">この方法の利点については、「 [Lync Server 2013 での web 会議の概要](lync-server-2013-web-conferencing-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d00bb-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="d00bb-106">これらの新機能を使用するには、管理者が Office Web Apps サーバーをインストールしている必要があります。また、管理者は、Office Web Apps サーバーと通信するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d00bb-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="d00bb-107">このドキュメントでは、Lync Server 2013 を Office Web Apps サーバーと連携するように構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d00bb-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="d00bb-108">このドキュメントでは、Office Web Apps サーバー自体をインストールする方法について説明していません。この情報については、の Microsoft Office Web Apps 展開<http://go.microsoft.com/fwlink/p/?linkid=257525>web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d00bb-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="d00bb-109">このガイドには、Office Web Apps サーバーの必要な情報がすべて含まれています。Office Web Apps サーバーは、Lync Server、Microsoft SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンコンピューターにインストールする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d00bb-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="d00bb-110">(そのコンピューターには Microsoft Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用するコンピューターには、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。これらの要件と、証明書およびインターネットインフォメーションサービス (IIS) を構成する方法については、Microsoft Office Web Apps 展開の web <http://go.microsoft.com/fwlink/p/?linkid=257525>サイトで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d00bb-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d00bb-111">Office Web Apps サーバーの最新のイテレーションは、Lync Server 2013 でサポートされている Office Online Server という名前です。</span><span class="sxs-lookup"><span data-stu-id="d00bb-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="d00bb-112">詳細については、「 <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server のドキュメント</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d00bb-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="d00bb-113">このドキュメントでは、次のトピック領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="d00bb-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="d00bb-114">Office Web Apps サーバーで動作するように Lync Server 2013 を構成する</span><span class="sxs-lookup"><span data-stu-id="d00bb-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="d00bb-115">リバースプロキシサーバーを使用して Lync Server 2013 で Office Web Apps サーバーを発行する</span><span class="sxs-lookup"><span data-stu-id="d00bb-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="d00bb-116">Lync Server 2013 で Office Web Apps サーバーの構成を検証する</span><span class="sxs-lookup"><span data-stu-id="d00bb-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="d00bb-117">Lync Server 2013 のクライアントで Office Web Apps サーバーを使用するように構成する</span><span class="sxs-lookup"><span data-stu-id="d00bb-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

