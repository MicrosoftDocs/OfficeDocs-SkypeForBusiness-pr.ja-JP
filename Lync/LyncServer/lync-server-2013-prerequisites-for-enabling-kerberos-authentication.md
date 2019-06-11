---
title: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="c9d73-102">Lync Server 2013 で Kerberos 認証を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="c9d73-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9d73-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c9d73-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c9d73-104">Kerberos 認証を有効にする前に、必要な構成とインフラストラクチャの準備がすべて完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c9d73-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="c9d73-105">Lync Server 2013 の Active Directory スキーマが拡張されています。</span><span class="sxs-lookup"><span data-stu-id="c9d73-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="c9d73-106">Lync Server 2013 の Active Directory フォレストの準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="c9d73-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="c9d73-107">Lync Server 2013 の Active Directory ドメインの準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="c9d73-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="c9d73-108">中央管理ストアが正常にインストールされ、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c9d73-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="c9d73-109">トポロジは、トポロジビルダーを使用して作成および公開されています。</span><span class="sxs-lookup"><span data-stu-id="c9d73-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="c9d73-110">Web サービスを必要とするサーバーと役割は、フロントエンドサーバー、標準エディションサーバー、およびディレクターなど、定義および展開されています。</span><span class="sxs-lookup"><span data-stu-id="c9d73-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="c9d73-111">Lync Server 2013 で Web サービスをサポートするために推奨される役割サービスを使用して、インターネットインフォメーションサービス (IIS) を構成し、展開します。</span><span class="sxs-lookup"><span data-stu-id="c9d73-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="c9d73-112">前提条件が満たされた後で、展開のために Kerberos 認証に使用する1つ以上のアカウントを Web サービス用に作成する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d73-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="c9d73-113">少なくとも、展開ごとに1つの Kerberos 認証アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d73-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="c9d73-114">ただし、サイトにローカルの Kerberos 認証を提供するために、各サイトのアカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c9d73-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="c9d73-115">1つのサイトにつき1つの Kerberos 認証アカウントのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c9d73-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

