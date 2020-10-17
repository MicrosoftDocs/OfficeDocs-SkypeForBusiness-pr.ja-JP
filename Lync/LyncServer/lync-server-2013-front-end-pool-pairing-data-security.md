---
title: 'Lync Server 2013: フロントエンドプールのペアリングデータのセキュリティ'
description: 'Lync Server 2013: フロントエンドプールのペアリングデータのセキュリティ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a2ce72752819392429c8407649e663494f1daf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567133"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="f3dfa-103">Lync Server 2013 でのフロントエンドプールのペアリングデータのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="f3dfa-103">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3dfa-104">_**トピックの最終更新日:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="f3dfa-104">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="f3dfa-105">バックアップサービスは、Lync Server 2013 で導入されたデータレプリケーションメカニズムです。このメカニズムでは、2つのペアのフロントエンドプール間で、障害復旧のためにユーザーデータと会議コンテンツを継続的に2つのデータセンター間で転送します。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-105">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="f3dfa-106">ユーザーデータには、ユーザーの SIP Uri だけでなく、連絡先のリストと設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-106">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="f3dfa-107">会議コンテンツには、Microsoft PowerPoint 2010 のアップロード、および会議で使用されるホワイトボードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-107">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="f3dfa-108">移行元プールから、ユーザーデータと会議コンテンツがローカルストレージ (zip 形式) からエクスポートされ、移行先プールに転送されて、ローカルストレージにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-108">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="f3dfa-109">バックアップサービスは、2つのデータセンター間の通信リンクが、インターネットから保護されている企業ネットワーク内にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-109">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="f3dfa-110">2つのデータセンター間で転送されるデータは暗号化されません。 HTTPS などの安全なプロトコル内にネイティブにカプセル化されることもありません。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-110">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="f3dfa-111">そのため、企業ネットワーク内の社内の従業員からの man-in-the-middle 攻撃を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-111">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="f3dfa-112">セキュリティ リスクの評価</span><span class="sxs-lookup"><span data-stu-id="f3dfa-112">Evaluating Security Risks</span></span>

<span data-ttu-id="f3dfa-113">複数のデータセンターに Lync Server 2013 を展開し、障害復旧機能を使用するエンタープライズは、データセンター間のトラフィックが企業イントラネットで保護されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-113">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="f3dfa-114">内部攻撃からの保護を求める企業は、データ センター間の通信リンクをセキュアにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-114">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="f3dfa-p103">企業のデータ センターは企業イントラネット内部で保護されているという前提は標準的です。こうしたデータ センター間で転送される企業の重要データには、ほかにも多くの種類があります。こうしたデータ センター間のリンクが保護されていなければ、企業の IT インフラストラクチャは深刻なリスクにさらされます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-p103">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard. There are many other types of corporate sensitive data transferred among these data centers. The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="f3dfa-p104">企業ネットワーク内では中間者攻撃のリスクが存在する一方で、トラフィックをインターネットに露出することに比べればまだ無難です。具体的にいうと、バックアップ サービスによって露出されるユーザー データ (SIP URI など) は一般的に、その他の手段 (Exchange やその他のディレクトリ ソフトウェアによるグローバル アドレス帳など) によって、社内の従業員全員が利用できます。そのため、ペアになった 2 つのプール間でデータをコピーするためにバックアップ サービスを使用する場合は、2 つのデータ センター間の WAN を保護することに重点を置くべきです。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-p104">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet. Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software. Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="f3dfa-121">セキュリティ リスクの軽減</span><span class="sxs-lookup"><span data-stu-id="f3dfa-121">Mitigating Security Risks</span></span>

<span data-ttu-id="f3dfa-122">バックアップサービストラフィックのセキュリティ保護を強化する方法は多数あります。つまり、データセンターへのアクセスを制限して、2つのデータセンター間で WAN トランスポートを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-122">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="f3dfa-123">ほとんどの場合、Lync Server 2013 を展開する企業には、必要なセキュリティインフラストラクチャが既に配置されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-123">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="f3dfa-124">ガイダンスを探している企業では、セキュリティで保護された IT インフラストラクチャを構築する方法の例として、Microsoft がソリューションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-124">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="f3dfa-125">ただし、これは、唯一の解決策であるとは言えません。また、これが Lync Server にとって推奨されるソリューションであるという意味でもありません。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-125">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="f3dfa-126">企業のお客様は、IT セキュリティインフラストラクチャと要件に基づいて、特定のニーズに適合するソリューションを選択することをお勧めします。Microsoft ソリューションの例では、サーバーとドメインの分離に IPSec およびグループポリシーを採用しています。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-126">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="f3dfa-127">詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) 。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-127">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="f3dfa-128">質問とコメントについては、secwish@microsoft.com にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-128">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="f3dfa-129">別の方法として、IPSec を使用してバックアップサービス自体によって送信されたデータをセキュリティで保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-129">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="f3dfa-130">この方法を選択する場合は、次のサーバーの SMB プロトコルの IPSec ルールを構成する必要があります。ここで、プール A とプール B は2つのフロントエンドプールとペアになります。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-130">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="f3dfa-131">プール A の各フロントエンドサーバーから、プール B で使用されるファイルストアへの SMB サービス (TCP/445)。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-131">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="f3dfa-132">プール B の各フロントエンドサーバーからプール A で使用されるファイルストアへの SMB サービス (TCP/445)。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-132">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f3dfa-133">IPsec は、アプリケーションレベルのセキュリティ (SSL/TLS など) の代替として使用することを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-133">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="f3dfa-134">IPsec を使用する利点の1つは、既存のアプリケーションを変更することなく、ネットワークトラフィックのセキュリティを提供できることです。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-134">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="f3dfa-135">2つのデータセンター間のトランスポートをセキュリティで保護するだけの企業は、ベンダーの機器を使用してセキュリティで保護された WAN 接続をセットアップする方法について、それぞれのネットワークハードウェアベンダーに問い合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3dfa-135">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

