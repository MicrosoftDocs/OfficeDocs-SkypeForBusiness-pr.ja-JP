---
title: 'Lync Server 2013: セキュリティの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72563df128f86ae7d52d850dbe015e33c1552eed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="274c8-102">Lync Server 2013 のセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="274c8-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="274c8-103">_**最終更新日:** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="274c8-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="274c8-104">このセキュリティセクションを使用して、Lync Server 2013 の展開に関するセキュリティリスクを評価して管理します。</span><span class="sxs-lookup"><span data-stu-id="274c8-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="274c8-105">Lync Server 2013 の展開が妥当である場合でも、ネットワークには、独自のセキュリティドキュメントが含まれているコンポーネントが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="274c8-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="274c8-106">そのため、このセクションでは、展開に関連するすべてのコンポーネントと領域のセキュリティに関するすべての側面について説明しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="274c8-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="274c8-107">このセクションは、Lync Server 2013 の展開のセキュリティに対応するための出発点として使用してください。</span><span class="sxs-lookup"><span data-stu-id="274c8-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="274c8-108">一般的なガイドラインと、最も一般的なセキュリティリスクを評価および管理するためのベストプラクティスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="274c8-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="274c8-109">各トピックの最後には、追加の製品とセキュリティのリソースが記載されています。</span><span class="sxs-lookup"><span data-stu-id="274c8-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="274c8-110">セキュリティは、絶えず進化するトピックです。</span><span class="sxs-lookup"><span data-stu-id="274c8-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="274c8-111">新しい脅威や解決策が発生したため、古いドキュメント、ソリューション、方法、および手順は最新の資料に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="274c8-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="274c8-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="274c8-112">In This Section</span></span>

  - [<span data-ttu-id="274c8-113">Lync Server 2013 の主要なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="274c8-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="274c8-114">モダンなコンピューティングでの一般的なセキュリティの脅威</span><span class="sxs-lookup"><span data-stu-id="274c8-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="274c8-115">Lync Server 2013 用のウイルス スキャン除外範囲</span><span class="sxs-lookup"><span data-stu-id="274c8-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="274c8-116">Lync Server 2013 のセキュリティフレームワーク</span><span class="sxs-lookup"><span data-stu-id="274c8-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="274c8-117">Lync Server 2013 向けのコアインフラストラクチャへの脅威への対応</span><span class="sxs-lookup"><span data-stu-id="274c8-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="274c8-118">Lync Server 2013 で SQL Server の非標準ポートおよびエイリアスを展開する</span><span class="sxs-lookup"><span data-stu-id="274c8-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

