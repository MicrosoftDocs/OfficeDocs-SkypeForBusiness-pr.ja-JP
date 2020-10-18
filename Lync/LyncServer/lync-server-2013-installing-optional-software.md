---
title: 'Lync Server 2013: オプションのソフトウェアのインストール'
description: 'Lync Server 2013: オプションのソフトウェアのインストール。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573913"
---
# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="49bf9-103">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="49bf9-103">Installing optional software in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49bf9-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="49bf9-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="49bf9-105">Microsoft Lync Server 2013、計画ツールは、Microsoft Excel および Microsoft Visio にエクスポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="49bf9-105">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="49bf9-106">これらのアプリケーションは、計画ツールの操作に必要ではありませんが、設計の展開とドキュメントに大きな価値が追加されています。</span><span class="sxs-lookup"><span data-stu-id="49bf9-106">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="49bf9-107">オプション ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="49bf9-107">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="49bf9-108">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="49bf9-108">Microsoft Excel</span></span>

<span data-ttu-id="49bf9-109">デザインを Microsoft Excel にエクスポートすると、スプレッドシートに7つのタブを表示するレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-109">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="49bf9-110">概要-ユーザー数、容量の設定、サーバープロファイル情報など、サイトの構成に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="49bf9-110">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="49bf9-111">ハードウェアのプロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成についてのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="49bf9-111">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="49bf9-112">サーバーコンポーネントの数量および推奨仕様も含まれています。</span><span class="sxs-lookup"><span data-stu-id="49bf9-112">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="49bf9-113">さらに、各サーバーはサイトごとに定義されており、サイトごとにサーバーの要件を完全に表現します。</span><span class="sxs-lookup"><span data-stu-id="49bf9-113">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="49bf9-114">[ポートの要件] –有効になっているすべてのポートのレポートと、ドメインネームシステムの負荷分散 (DNS LB) およびハードウェアロードバランサー (HLB) への関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-114">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="49bf9-115">このレポートを使用して、ファイアウォールと DNS LB および HLB の構成を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49bf9-115">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="49bf9-116">[概要レポート]: エッジサーバーネットワークの設定に必要な設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="49bf9-116">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="49bf9-117">証明書レポート-エッジサーバーを実行するのに必要な証明書に必要なサブジェクト名とサブジェクトの別名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-117">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="49bf9-118">ファイアウォールレポート-外部および内部インターフェイスの送信元と宛先のポートと IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-118">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="49bf9-119">DNS レポート-作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-119">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="49bf9-120">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="49bf9-120">Microsoft Visio</span></span>

<span data-ttu-id="49bf9-p104">設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49bf9-124">3台以上のフロントエンドサーバーを必要とする程度のサイズの設計では、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、および Fqdn に対して追加のページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-124">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="49bf9-125">グローバルトポロジ–構成された Lync Server 2013 サイトの図。</span><span class="sxs-lookup"><span data-stu-id="49bf9-125">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="49bf9-126">[サイト名] タブ–エッジサーバー、ファイアウォール、公衆交換電話網 (PSTN) とゲートウェイを使用したサイト構成トポロジ、および内部サーバー展開が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-126">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="49bf9-127">内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバー、仲介サーバー、および常設チャットサーバーを含む、構成済みのサーバーとプールから構成されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-127">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="49bf9-128">エッジネットワーク図–関連する IP アドレスと Fqdn を使用したエッジサーバー構成の詳細な図。</span><span class="sxs-lookup"><span data-stu-id="49bf9-128">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="49bf9-129">DNS 負荷分散とロードバランサー機器も含まれています。</span><span class="sxs-lookup"><span data-stu-id="49bf9-129">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="49bf9-130">さらに、ディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。これには、関連付けられた DNS LB または HLB と、割り当てられた IP アドレス (計画ツールは、IPv4 と IPv6 の両方のアドレスをサポートします) と FQDN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49bf9-130">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49bf9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="49bf9-131">See Also</span></span>


[<span data-ttu-id="49bf9-132">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="49bf9-132">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

