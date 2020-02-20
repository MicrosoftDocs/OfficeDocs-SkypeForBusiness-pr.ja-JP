---
title: Lync Server 2013 Active Directory のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 193ebaedd11c239ba380937da3051ec8336578a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="ef262-102">Lync Server 2013 での Active Directory のサポート</span><span class="sxs-lookup"><span data-stu-id="ef262-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef262-103">_**トピックの最終更新日:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="ef262-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="ef262-104">Lync Server 2013 でサポートされている Active Directory ドメインサービスのオンプレミストポロジは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ef262-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="ef262-105">単一のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="ef262-105">Single forest with single domain</span></span>

  - <span data-ttu-id="ef262-106">単一のツリーと複数のドメインを含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="ef262-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="ef262-107">複数のツリーと不整合の名前空間を含む単一のフォレスト</span><span class="sxs-lookup"><span data-stu-id="ef262-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="ef262-108">中央フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="ef262-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="ef262-109">リソース フォレスト トポロジの複数のフォレスト</span><span class="sxs-lookup"><span data-stu-id="ef262-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef262-110">Lync Server 2013 では、単一ラベルドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ef262-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="ef262-111">たとえば、 <STRONG>contoso</STRONG>という名前のルートドメインを持つフォレストはサポートされていますが、 <STRONG>local</STRONG>という名前の単一ラベルルートドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ef262-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="ef262-112">詳細については、「Microsoft サポート技術情報の記事300684」を参照してください<A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>。単一ラベル DNS 名のドメインに対する Windows の構成については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef262-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ef262-113">Lync Server 2013 では、ドメイン名の変更はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ef262-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="ef262-114">Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから Lync Server を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef262-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="ef262-115">オンプレミス展開でサポートされるトポロジと要件の詳細については、「計画」のドキュメントの「 [Active Directory ドメインサービスの要件、サポート、および Lync Server 2013 のトポロジ](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef262-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

