---
title: 'Lync Server 2013: フロントエンド プールのペアリング データのセキュリティ'
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
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="3ccd7-102">Lync Server 2013 でのフロントエンド プールのペアリング データのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3ccd7-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ccd7-103">_**最終更新日:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="3ccd7-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="3ccd7-104">バックアップサービスは、Lync Server 2013 で導入されたデータレプリケーションメカニズムであり、2つのペアのフロントエンドプール間でユーザーデータと会議コンテンツを、障害回復のために2つのデータセンター間で連続して転送します。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="3ccd7-105">ユーザーデータには、ユーザー SIP Uri に加えて、連絡先リストと設定も含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="3ccd7-106">会議コンテンツには、Microsoft PowerPoint 2010 アップロードと、会議で使用されるホワイトボードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="3ccd7-107">ソースプールでは、ユーザーデータと会議のコンテンツはローカルストレージからエクスポートされ、ターゲットプールに転送され、圧縮されてローカルストレージにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="3ccd7-108">バックアップサービスは、2つのデータセンター間の通信リンクがインターネットから保護されている企業ネットワーク内にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="3ccd7-109">この方法では、2つのデータセンター間で転送されたデータは暗号化されません。 HTTPS などのセキュリティで保護されたプロトコル内ではネイティブにカプセル化されません。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="3ccd7-110">そのため、社内ネットワーク内の社内スタッフからの man-in-the-middle 攻撃を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="3ccd7-111">セキュリティリスクの評価</span><span class="sxs-lookup"><span data-stu-id="3ccd7-111">Evaluating Security Risks</span></span>

<span data-ttu-id="3ccd7-112">複数のデータセンターに Lync Server 2013 を展開し、障害回復機能を使用する企業は、データセンター間のトラフィックが企業のイントラネットによって保護されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="3ccd7-113">内部攻撃保護を考慮する企業は、データセンター間の通信リンクをセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="3ccd7-114">企業のデータセンターは企業イントラネットの背後で保護されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="3ccd7-115">これらのデータセンターの間では、他にも多くの種類の企業機密データが転送されています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="3ccd7-116">このようなデータセンター間のリンクが保護されていない場合、企業の IT インフラストラクチャはどんな切迫のリスクを持ちます。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="3ccd7-117">企業ネットワーク内では中間者攻撃のリスクが存在しますが、トラフィックをインターネットに露出することに比べればまだ無難です。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="3ccd7-118">具体的には、バックアップサービス (SIP Uri など) によって公開されたユーザーデータは、一般に、Exchange やその他のディレクトリソフトウェアによるグローバルアドレス帳などの他の手段で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="3ccd7-119">したがって、2つのペアのプールの間でバックアップサービスを使用してデータをコピーする場合は、2つのデータセンター間の WAN のセキュリティを確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="3ccd7-120">セキュリティのリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="3ccd7-120">Mitigating Security Risks</span></span>

<span data-ttu-id="3ccd7-121">バックアップサービストラフィックのセキュリティ保護を強化するには、2つのデータセンター間の WAN トランスポートをセキュリティで保護するために、データセンターへのアクセスを制限するさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="3ccd7-122">ほとんどの場合、Lync Server 2013 を展開する企業には、必要なセキュリティインフラストラクチャが用意されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="3ccd7-123">ガイダンスを探している企業には、セキュリティで保護された IT インフラストラクチャの構築方法の例として、Microsoft がソリューションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="3ccd7-124">ただし、これは唯一の解決策ではないというわけではありません。これは、Lync Server のお勧めのソリューションであることを意味するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="3ccd7-125">企業のお客様は、IT セキュリティインフラストラクチャと要件に基づいて、ソリューションを特定のニーズに合わせて選ぶことをお勧めします。Microsoft のソリューションの例では、IPSec とグループポリシーを使用してサーバーおよびドメインを分離しています。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="3ccd7-126">詳細について[http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="3ccd7-127">質問とコメントについては、secwish@microsoft.com にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="3ccd7-128">もう 1 つのソリューションは、バックアップ サービスそのものによって送信されたデータのセキュリティ保護だけに IPSec を使用するというものです。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="3ccd7-129">この方法を採用する場合は、プール A とプール B が 2 つのペアになったフロント エンド プールになっている次のサーバーについて、SMB プロトコルの IPSec ルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="3ccd7-130">プール A の各フロント エンド サーバーからプール B によって使用されるファイル ストアへの SMB サービス (TCP/445)。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="3ccd7-131">プール B の各フロント エンド サーバーからプール A によって使用されるファイル ストアへの SMB サービス (TCP/445)。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3ccd7-132">IPsec は、SSL/TLS のようなアプリケーション レベルのセキュリティに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="3ccd7-133">IPsec を使用する利点の 1 つは、既存のアプリケーションを変更することなく、ネットワーク トラフィックのセキュリティを提供できることです。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="3ccd7-134">単に 2 つのデータ センター間のトランスポートを保護したい企業は、それぞれのネットワーク ハードウェア ベンダーに対し、ベンダーの機器を使用してセキュリティで保護された WAN 接続を構築する方法を相談してください。</span><span class="sxs-lookup"><span data-stu-id="3ccd7-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

