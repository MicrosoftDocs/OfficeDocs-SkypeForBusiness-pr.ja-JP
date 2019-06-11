---
title: 'Lync Server 2013: オプションのソフトウェアをインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="eade9-102">Lync Server 2013 でオプションのソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="eade9-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eade9-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eade9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eade9-104">Microsoft Lync Server 2013 の計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="eade9-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="eade9-105">これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を加えることになります。</span><span class="sxs-lookup"><span data-stu-id="eade9-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="eade9-106">オプション ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="eade9-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="eade9-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="eade9-107">Microsoft Excel</span></span>

<span data-ttu-id="eade9-108">デザインを Microsoft Excel にエクスポートすると、次の 7 つのタブがあるスプレッドシートを表示するレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eade9-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="eade9-109">概要 - ユーザー数、容量の設定値、サーバー プロファイル情報などの、サイトの構成情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="eade9-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="eade9-p102">ハードウェアのプロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成についてのレポートを表示します。サーバー コンポーネントの数量および推奨仕様も含まれます。各サーバーはサイト別に定義されているので、サイトごとのサーバー要件を詳細に示します。</span><span class="sxs-lookup"><span data-stu-id="eade9-p102">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface. The quantity and recommended specifications for the server components are also included. In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="eade9-p103">ポートの要件 - 有効にされているすべてのポートのレポートと、DNS 負荷分散 (DNS LB) およびロード バランサー機器 (HLB) への関連付けのレポートを表示します。このレポートは、ファイアウォール、DNS LB、および HLB の構成を計画するために使用します。</span><span class="sxs-lookup"><span data-stu-id="eade9-p103">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB). You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="eade9-115">概要レポート–エッジサーバーネットワークのセットアップに必要な設定の一般的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eade9-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="eade9-116">証明書レポート–エッジサーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクトの代替名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eade9-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="eade9-117">ファイアウォール レポート - 内部および外部インターフェイス用の発信元および宛先のポートと IP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="eade9-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="eade9-118">DNS レポート - 作成する DNS エントリごとに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="eade9-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="eade9-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="eade9-119">Microsoft Visio</span></span>

<span data-ttu-id="eade9-p104">設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eade9-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eade9-123">3台以上のフロントエンドサーバーが必要な設計の場合は、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、Fqdn の追加ページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eade9-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="eade9-124">グローバルトポロジ–構成済みの Lync Server 2013 サイトの図。</span><span class="sxs-lookup"><span data-stu-id="eade9-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="eade9-125">[サイト名] タブ– Edge Server、ファイアウォール、公衆交換電話網 (PSTN)、および内部サーバーの展開を使用して、サイトの構成トポロジを表示します。</span><span class="sxs-lookup"><span data-stu-id="eade9-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="eade9-126">内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバーなど、構成済みのサーバーとプールで構成されます。仲介サーバーと常設チャットサーバー。</span><span class="sxs-lookup"><span data-stu-id="eade9-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="eade9-127">エッジネットワーク図–関連する IP アドレスと Fqdn を含むエッジサーバー構成の詳細な図。</span><span class="sxs-lookup"><span data-stu-id="eade9-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="eade9-128">DNS 負荷分散やロード バランサー機器も含まれます。</span><span class="sxs-lookup"><span data-stu-id="eade9-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="eade9-129">さらに、関連付けられた DNS LB または HLB および割り当てられた IP アドレス (計画ツールが IPv4 アドレスと IPv6 アドレスの両方をサポートします) と FQDN が表示されたディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eade9-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eade9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="eade9-130">See Also</span></span>


[<span data-ttu-id="eade9-131">Lync Server 2013 での計画ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="eade9-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

