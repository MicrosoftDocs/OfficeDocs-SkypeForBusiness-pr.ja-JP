---
title: 'Lync Server 2013: Hosted Exchange UM 統合のアーキテクチャ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fbb815514d9a338412b638bdf373a285ebf6f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="77ed8-102">Lync Server 2013 の Hosted Exchange UM 統合のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="77ed8-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77ed8-103">_**最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="77ed8-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="77ed8-104">Lync Server 2013 ExUM ルーティングアプリケーションでは、オンプレミスの Exchange ユニファイドメッセージング (UM) 展開との統合、サービスプロバイダーによってホストされている Exchange UM、またはこの2つの組み合わせをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77ed8-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="77ed8-105">次の図は、3つのすべての可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="77ed8-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="77ed8-106">**オンプレミスの Exchange UM 展開と2つのホストされた Exchange プロバイダーとの統合**</span><span class="sxs-lookup"><span data-stu-id="77ed8-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="77ed8-107">![オンプレミスの Lync Server Exchange UM の展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "オンプレミスの Lync Server Exchange UM の展開")</span><span class="sxs-lookup"><span data-stu-id="77ed8-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="77ed8-108">次のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="77ed8-108">The following modes are supported:</span></span>

  - <span data-ttu-id="77ed8-109">**オンプレミスの展開:** Lync Server 2013 と Exchange UM は両方とも、エンタープライズ内のローカルサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="77ed8-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="77ed8-110">**クロスプレミスの展開:** Lync Server 2013 は企業内のローカルサーバーに展開され、Exchange UM は Microsoft Exchange Online のデータセンターなどのオンラインサービスプロバイダーの機能でホストされます。</span><span class="sxs-lookup"><span data-stu-id="77ed8-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="77ed8-111">**混在展開:** Lync Server 2013 の展開では、一部のユーザーのメールボックスが企業内のローカル Exchange サーバー上にあり、一部のメールボックスは、ホスティングされている Exchange service データセンターに置かれています。</span><span class="sxs-lookup"><span data-stu-id="77ed8-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ed8-112">混在展開は、ユーザーをホストされた Exchange UM に移行するときの移行ソリューションとして使用することができます。また、他のユーザーを転送した後で、一部のユーザーの Exchange UM サービスをオンプレミスのままにしておくと、永続的なソリューションとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="77ed8-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="77ed8-113">共有 SIP アドレス空間</span><span class="sxs-lookup"><span data-stu-id="77ed8-113">Shared SIP Address Space</span></span>

<span data-ttu-id="77ed8-114">Lync Server 2013 をオンプレミスの Exchange UM 展開に統合するには、Lync Server 2013 権限を付与して、Exchange UM Active Directory ドメインサービスオブジェクトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="77ed8-115">この方法は、ホストされた Exchange UM との統合には対応していません。ただし、Lync Server 2013 と Exchange UM は別々のフォレストにインストールされているため、信頼関係がありません。</span><span class="sxs-lookup"><span data-stu-id="77ed8-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="77ed8-116">Lync Server 2013 をホストされた Exchange UM と統合するには、*共有 SIP アドレス空間*を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="77ed8-117">この構成では、Lync Server 2013 と hosted Exchange UM サービスプロバイダーの両方で同じ SIP ドメインアドレス空間を利用できます。</span><span class="sxs-lookup"><span data-stu-id="77ed8-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77ed8-118">共有 SIP アドレス空間の使用は、クロスプレミスの Lync Server 2013 環境で使用されているアプローチと似ています。一部のユーザーはオンプレミスの展開に所属していて、一部のユーザーは、社内の展開 (Lync Online など) であるためです。</span><span class="sxs-lookup"><span data-stu-id="77ed8-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="77ed8-119">SIP ドメインが分割されます。</span><span class="sxs-lookup"><span data-stu-id="77ed8-119">The SIP domain is split between them.</span></span> <span data-ttu-id="77ed8-120">Lync Server 2013 をホストされた Exchange UM と統合する場合は、共有 SIP アドレス空間に Exchange UM サービスプロバイダーが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="77ed8-121">Exchange UM サービスプロバイダーと統合するために共有 SIP アドレス空間を構成するには、次のようにエッジサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="77ed8-122">次のパラメーターを設定するには、 **CsAccessEdgeConfiguration**コマンドレットを実行して、フェデレーション用にエッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="77ed8-123">\*\*UseDnsSrvRouting \*\* は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="77ed8-p105">\*\*AllowFederatedUsers \*\* は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="77ed8-126">**Enablepartnerdiscovery** Lync Server 2013 で DNS レコードを使用して、Active Directory で許可されているドメインの一覧に含まれていないパートナードメインを検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="77ed8-127">False の場合、Lync Server 2013 は、[許可したドメイン] 一覧にあるドメインのみをフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="77ed8-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="77ed8-128">DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="77ed8-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="77ed8-129">ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="77ed8-130">中央管理ストアをエッジサーバーにレプリケートし、レプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="77ed8-131">詳細については、展開ドキュメントの「 [Lync Server 2013 トポロジをエクスポートして、microsoft edge インストール用の外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77ed8-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="77ed8-132">次のパラメーターを設定するには、**新しい-CsHostingProvider**コマンドレットを実行して、エッジサーバーで*ホスティングプロバイダー*を構成します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="77ed8-133">**Id**は、ホストされている**Exchange UM**など、作成しているホスティングプロバイダーの一意の文字列値識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="77ed8-134">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="77ed8-135">**True**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="77ed8-136">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="77ed8-137">**True**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="77ed8-138">**Hostているユーザー**は、ホスティングプロバイダーが Lync Server 2013 アカウントをホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="77ed8-139">**False**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="77ed8-140">**Proxyfqdn**は、ホスティングプロバイダーによって使用されるプロキシサーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、 **proxyserver.fabrikam.com**のように指定します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="77ed8-141">この情報については、ホスティングプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="77ed8-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="77ed8-142">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="77ed8-142">This value cannot be modified.</span></span> <span data-ttu-id="77ed8-143">ホスティングプロバイダーがプロキシサーバーを変更した場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="77ed8-144">**Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server 2013 トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="77ed8-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="77ed8-145">**False**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77ed8-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

