---
title: 'Lync Server 2013: Lync Server と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="bdbae-102">Lync Server 2013 と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="bdbae-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdbae-103">_**最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="bdbae-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bdbae-104">Exchange ユニファイドメッセージング (UM) を使用して、通話応答、Outlook Voice Access、またはエンタープライズ Voip サービスを提供する場合は、計画ドキュメントの「 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 での Exchange ユニファイドメッセージングの統合の計画</A>」を参照して、このセクションの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="bdbae-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="bdbae-105">エンタープライズ Voip と連携するように Exchange ユニファイドメッセージング (UM) を構成するには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbae-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="bdbae-106">Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="bdbae-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdbae-107">すべてのクライアントアクセスとメールボックスサーバーを UM SIP のすべての URI ダイヤルプランに追加します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="bdbae-108">そうしないと、発信通話のルーティングが予期したとおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="bdbae-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="bdbae-109">必要に応じて、サブスクライバーアクセス用電話番号と共に1つまたは複数の UM SIP URI ダイヤルプランを作成して、対応する Lync Server ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="bdbae-110">次のような操作を実行するために**exchucutil**スクリプトを使います。</span><span class="sxs-lookup"><span data-stu-id="bdbae-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="bdbae-111">UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="bdbae-112">UM ハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="bdbae-113">UM Active Directory ドメインサービスオブジェクトを読み取るために Lync Server 2013 のアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="bdbae-114">UM 自動応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="bdbae-115">サブスクライバーアクセスオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="bdbae-116">ユーザーごとに SIP URI を作成し、UM SIP URI ダイヤルプランを使用してユーザーを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="bdbae-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="bdbae-117">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="bdbae-117">Requirements and Recommendations</span></span>

<span data-ttu-id="bdbae-118">作業を始める前に、このセクションのドキュメントでは、次の Exchange 2013 の役割 (クライアントアクセスとメールボックス) が展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bdbae-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="bdbae-119">Microsoft Exchange Server 2013 では、Exchange UM はこれらのサーバーでサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="bdbae-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="bdbae-120">Exchange 2013 の展開について詳しくは2013、[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="bdbae-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="bdbae-121">次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="bdbae-121">Also note the following:</span></span>

  - <span data-ttu-id="bdbae-122">Exchange UM が複数のフォレストにインストールされている場合は、各 UM フォレストで Exchange Server の統合手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbae-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="bdbae-123">さらに、各 UM フォレストが、Lync Server 2013 が展開されているフォレストを信頼するように構成されている必要があります。また、Lync Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbae-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="bdbae-124">統合手順は、ユニファイドメッセージングサービスが実行されている Exchange Server の役割と、Lync Server 2013 を実行しているサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bdbae-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="bdbae-125">Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージング統合の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbae-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdbae-126">どのサーバーに対して実行される統合手順と管理者の役割を確認するには、「<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスユニファイドメッセージングと Lync Server 2013 を統合する展開プロセス</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdbae-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="bdbae-127">Exchange UM を実行している各サーバーでは、次のツールを使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbae-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="bdbae-128">Exchange 管理シェル</span><span class="sxs-lookup"><span data-stu-id="bdbae-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="bdbae-129">スクリプト**exchucutil**は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="bdbae-130">各 Lync Server 2013 に対して UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="bdbae-131">各ゲートウェイのハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="bdbae-132">各ハントグループのパイロット識別子は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤルプランを指定します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="bdbae-133">Active Directory ドメインサービスで Exchange UM オブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="bdbae-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bdbae-134">このセクション中</span><span class="sxs-lookup"><span data-stu-id="bdbae-134">In This Section</span></span>

  - [<span data-ttu-id="bdbae-135">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="bdbae-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="bdbae-136">Lync Server 2013 向けの Microsoft Exchange でユニファイドメッセージングを構成する</span><span class="sxs-lookup"><span data-stu-id="bdbae-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

