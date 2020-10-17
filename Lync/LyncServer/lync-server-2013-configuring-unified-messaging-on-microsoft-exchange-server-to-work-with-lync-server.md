---
title: 'Lync Server 2013: Lync Server で動作するように Microsoft Exchange Server でユニファイドメッセージングを構成する'
description: 'Lync Server 2013: Lync Server で動作するように Microsoft Exchange Server でユニファイドメッセージングを構成する。'
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
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548243"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="fda16-103">Lync Server 2013 で動作するように Microsoft Exchange Server でユニファイドメッセージングを構成する</span><span class="sxs-lookup"><span data-stu-id="fda16-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda16-104">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="fda16-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fda16-105">Exchange ユニファイドメッセージング (UM) を使用して、エンタープライズ Voip ユーザーの通話応答、Outlook Voice Access、または自動応答サービスを提供する場合は、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画</A> 」を読んで、このセクションの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="fda16-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="fda16-106">エンタープライズ Voip を使用するように Exchange ユニファイドメッセージング (UM) を構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda16-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="fda16-107">Exchange ユニファイドメッセージング (UM) サービスを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="fda16-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fda16-108">すべてのクライアントアクセスサーバーおよびメールボックスサーバーをすべての UM SIP URI ダイヤルプランに追加します。</span><span class="sxs-lookup"><span data-stu-id="fda16-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="fda16-109">そうでない場合は、発信通話のルーティングが期待どおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="fda16-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="fda16-110">必要に応じて、1つまたは複数の UM SIP URI ダイヤルプランと、サブスクライバーアクセス用の電話番号を作成し、対応する Lync Server のダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="fda16-111">**exchucutil.ps1**スクリプトを使用して、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="fda16-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="fda16-112">UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="fda16-113">UM ハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="fda16-114">UM Active Directory ドメインサービスオブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="fda16-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="fda16-115">UM 自動応答オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="fda16-116">サブスクライバーアクセスオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="fda16-117">各ユーザーの SIP URI を作成し、ユーザーと UM SIP URI ダイヤルプランを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fda16-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="fda16-118">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="fda16-118">Requirements and Recommendations</span></span>

<span data-ttu-id="fda16-119">開始する前に、このセクションのドキュメントでは、次の Exchange 2013 の役割 (クライアントアクセスとメールボックス) を展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fda16-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="fda16-120">Microsoft Exchange Server 2013 では、Exchange UM はこれらのサーバー上でサービスとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="fda16-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="fda16-121">Exchange 2013 の展開の詳細については、「」の「Exchange 2013 TechNet ライブラリ」を参照してください。 [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="fda16-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="fda16-122">以下の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="fda16-122">Also note the following:</span></span>

  - <span data-ttu-id="fda16-123">Exchange UM が複数のフォレストにインストールされている場合は、Exchange サーバーの統合手順を各 UM フォレストに対して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda16-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="fda16-124">また、Lync Server 2013 が展開されているフォレストを信頼するように各 UM フォレストを構成する必要があります。また、Lync Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda16-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="fda16-125">統合手順は、ユニファイドメッセージングサービスが実行されている Exchange サーバーの役割と、Lync Server 2013 を実行しているサーバーの両方で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fda16-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="fda16-126">Lync Server 2013 の統合手順を実行する前に、Exchange Server ユニファイドメッセージングの統合手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda16-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fda16-127">どのサーバーに対してどの統合手順が実行されるか、および管理者の役割がどのようになるかを確認するには、「 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fda16-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="fda16-128">Exchange UM を実行している各サーバーで、次のツールが使用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda16-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="fda16-129">Exchange 管理シェル</span><span class="sxs-lookup"><span data-stu-id="fda16-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="fda16-130">**exchucutil.ps1** スクリプト。このスクリプトは以下のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="fda16-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="fda16-131">各 Lync Server 2013 の UM IP ゲートウェイを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="fda16-132">各ゲートウェイのハント グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="fda16-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="fda16-133">各ハントグループのパイロット id は、ゲートウェイに関連付けられているフロントエンドプールまたは Standard Edition サーバーによって使用される UM SIP URI ダイヤルプランを指定します。</span><span class="sxs-lookup"><span data-stu-id="fda16-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="fda16-134">Active Directory ドメインサービスの Exchange UM オブジェクトを読み取るための Lync Server 2013 アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="fda16-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fda16-135">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fda16-135">In This Section</span></span>

  - [<span data-ttu-id="fda16-136">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="fda16-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="fda16-137">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="fda16-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

