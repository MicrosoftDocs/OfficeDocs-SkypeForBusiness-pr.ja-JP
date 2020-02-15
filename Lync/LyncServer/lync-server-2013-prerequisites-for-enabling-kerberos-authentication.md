---
title: 'Lync Server 2013: Kerberos 認証を有効にするための前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecbba3403024663e529cef7653b310148faa2e2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="149b5-102">Lync Server 2013 で Kerberos 認証を有効にするための前提条件</span><span class="sxs-lookup"><span data-stu-id="149b5-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="149b5-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="149b5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="149b5-104">Kerberos 認証を有効にする前に、すべての前提条件の構成とインフラストラクチャの準備を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="149b5-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="149b5-105">Lync Server 2013 に対して Active Directory スキーマが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="149b5-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="149b5-106">Lync Server 2013 の Active Directory フォレストの準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="149b5-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="149b5-107">Lync Server 2013 の Active Directory ドメインの準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="149b5-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="149b5-108">中央管理ストアが正常にインストールされ、使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="149b5-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="149b5-109">トポロジは、トポロジビルダーを使用して作成および発行されています。</span><span class="sxs-lookup"><span data-stu-id="149b5-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="149b5-110">Web サービスを必要とするサーバーと役割 (フロントエンドサーバー、Standard Edition サーバー、ディレクターなど) が定義および展開されている。</span><span class="sxs-lookup"><span data-stu-id="149b5-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="149b5-111">Lync Server 2013 の Web サービスをサポートするために推奨される役割サービスを使用して、インターネットインフォメーションサービス (IIS) が構成および展開されている。</span><span class="sxs-lookup"><span data-stu-id="149b5-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="149b5-112">前提条件が満たされていない場合は、展開で Kerberos 認証に使用する Web サービスのアカウントを1つ以上作成することができます。</span><span class="sxs-lookup"><span data-stu-id="149b5-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="149b5-113">少なくとも、展開ごとに Kerberos 認証アカウントを1つ作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="149b5-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="149b5-114">ただし、サイトごとにローカル Kerberos 認証を提供するために、サイトごとにアカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="149b5-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="149b5-115">サイトごとに1つの Kerberos 認証アカウントのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="149b5-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

