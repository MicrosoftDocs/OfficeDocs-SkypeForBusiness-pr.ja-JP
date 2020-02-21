---
title: 'Lync Server 2013: セキュリティの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db9ec867032875484c6bab3db3c433716fa7c889
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="ee57f-102">Lync Server 2013 でのセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="ee57f-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee57f-103">_**トピックの最終更新日:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="ee57f-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="ee57f-104">このセキュリティセクションを使用して、Lync Server 2013 の展開に対するセキュリティリスクを評価および管理します。</span><span class="sxs-lookup"><span data-stu-id="ee57f-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="ee57f-105">Lync Server 2013 の展開が適度な場合でも、ネットワークには独自のセキュリティドキュメントを持つコンポーネントが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee57f-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="ee57f-106">そのため、このセクションでは、展開に関連するすべてのコンポーネントと領域のセキュリティのすべての側面について説明することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="ee57f-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="ee57f-107">このセクションは、Lync Server 2013 の展開のセキュリティに対応するための出発点として使用します。</span><span class="sxs-lookup"><span data-stu-id="ee57f-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="ee57f-108">最も一般的なセキュリティリスクを評価および管理するための一般的なガイドラインとベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee57f-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="ee57f-109">各トピックの最後に、追加の製品とセキュリティのリソースが記載されています。</span><span class="sxs-lookup"><span data-stu-id="ee57f-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee57f-110">セキュリティは常に進化しているトピックです。</span><span class="sxs-lookup"><span data-stu-id="ee57f-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="ee57f-111">新しい脅威とソリューションが発生した場合、古くなったドキュメント、ソリューション、方法、および手順は、最新の資料に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee57f-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee57f-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee57f-112">In This Section</span></span>

  - [<span data-ttu-id="ee57f-113">Lync Server 2013 の主なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="ee57f-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="ee57f-114">最近のコンピューティングでの一般的なセキュリティの脅威</span><span class="sxs-lookup"><span data-stu-id="ee57f-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="ee57f-115">Lync Server 2013 のウイルススキャン除外</span><span class="sxs-lookup"><span data-stu-id="ee57f-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="ee57f-116">Lync Server 2013 のセキュリティフレームワーク</span><span class="sxs-lookup"><span data-stu-id="ee57f-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="ee57f-117">Lync Server 2013 のコアインフラストラクチャに対する脅威への対応</span><span class="sxs-lookup"><span data-stu-id="ee57f-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="ee57f-118">Lync Server 2013 での SQL Server の標準以外のポートとエイリアスの展開</span><span class="sxs-lookup"><span data-stu-id="ee57f-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

