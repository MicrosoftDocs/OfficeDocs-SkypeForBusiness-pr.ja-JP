---
title: 'Lync Server 2013: Active Directory ドメイン サービスの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e1d7285d743da2270121389bbb5a510fe3b12d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="282f8-102">Lync Server 2013 用の Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="282f8-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282f8-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="282f8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="282f8-104">Lync Server 2013 を展開して運用する前に、スキーマを拡張し、オブジェクトを作成して構成することによって、Active Directory ドメインサービスを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="282f8-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="282f8-105">スキーマの拡張機能によって、Lync Server で必要な Active Directory のクラスと属性が追加されます。</span><span class="sxs-lookup"><span data-stu-id="282f8-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="282f8-106">このセクションのトピックでは、Lync Server を展開するために AD DS を準備する方法と、セットアップおよび組織単位 (OU) の権限を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="282f8-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="282f8-107">Lync Server に必要なスキーマ変更の詳細については、「 [Active Directory スキーマの拡張機能、クラス、および Lync server 2013 で使用される属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="282f8-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="282f8-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="282f8-108">In This Section</span></span>

  - [<span data-ttu-id="282f8-109">Lync Server 2013 に関する Active Directory インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="282f8-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="282f8-110">Lync Server 2013 の Active Directory ドメイン サービスの準備の概要</span><span class="sxs-lookup"><span data-stu-id="282f8-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="282f8-111">Lync Server 2013 での Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="282f8-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="282f8-112">Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備</span><span class="sxs-lookup"><span data-stu-id="282f8-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="282f8-113">Lync Server 2013 でのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="282f8-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

