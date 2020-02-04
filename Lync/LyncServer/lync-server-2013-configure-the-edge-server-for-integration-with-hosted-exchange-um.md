---
title: Hosted Exchange UM との統合のためのエッジ サーバーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="d4b64-102">Hosted Exchange UM との統合のためのエッジ サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="d4b64-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b64-103">_**最終更新日:** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="d4b64-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="d4b64-104">Lync Server 2013 ユーザーが、ホストされた Exchange ユニファイドメッセージング (UM) でボイスメール機能を利用できるようにするには、エッジサーバーで次の構成タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b64-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="d4b64-105">フェデレーションのためにエッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="d4b64-106">全体管理ストアデータをエッジサーバーにレプリケートし、レプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="d4b64-107">エッジ サーバーのホスティング プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="d4b64-108">詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b64-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="d4b64-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d4b64-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="d4b64-110">[新規-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d4b64-110">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d4b64-111">これらの手順を実行する前に、Hosted Exchange サービス用の外部 DNS SRV レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b64-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="d4b64-112">詳細については、「ホストされ<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">た EXCHANGE UM と統合するための DNS SRV レコードを作成</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b64-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="d4b64-113">フェデレーションのためにエッジ サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="d4b64-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="d4b64-114">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4b64-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d4b64-p102">Set-CsAccessEdgeConfiguration コマンドレットを実行して、フェデレーションのためにサーバーを構成します。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="d4b64-117">上述の例では、次のパラメーターが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4b64-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="d4b64-118">\*\*UseDnsSrvRouting \*\* は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="d4b64-p103">\*\*AllowFederatedUsers \*\* は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="d4b64-121">**Enablepartnerdiscovery** Lync SERVER で DNS レコードを使用して、Active Directory の許可ドメインリストに表示されていないパートナードメインを検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="d4b64-122">False の場合、Lync Server 2013 は、[許可したドメイン] 一覧にあるドメインとのみフェデレーションされます。</span><span class="sxs-lookup"><span data-stu-id="d4b64-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="d4b64-123">DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="d4b64-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="d4b64-124">ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="d4b64-125">データをエッジ サーバーにレプリケートし、レプリケーションを確認するには</span><span class="sxs-lookup"><span data-stu-id="d4b64-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="d4b64-126">エッジ サーバーへのレプリケーションが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="d4b64-127">手順については、「 [Lync Server 2013 で内部サーバーとエッジサーバー間の接続を確認](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b64-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="d4b64-128">エッジ サーバーのホスティング プロバイダーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d4b64-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="d4b64-129">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4b64-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d4b64-130">**New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="d4b64-131">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="d4b64-132">上述の例では、次のパラメーターが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4b64-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="d4b64-p107">\*\*Identity \*\* では、作成するホスティング プロバイダーの文字列値から成る一意識別子を指定します。この例では \*\*Fabrikam.com \*\* です。既存のプロバイダーがその ID で既に構成されている場合には、このコマンドは失敗することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4b64-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="d4b64-p108">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を \*\*True \*\* に設定しないと、2 つの組織間でメッセージを交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4b64-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="d4b64-137">\*\*EnabledSharedAddressSpace \*\* では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="d4b64-138">True に設定<CODE>EnableSharedAddressSpace</CODE>する前に、内部でフェデレーション SRV レコードを解決してみてください。</span><span class="sxs-lookup"><span data-stu-id="d4b64-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="d4b64-139">このレコードを内部で解決できない場合は、_sipfederationtls _tcp のレコードを作成する必要があります。&lt;ドメイン&gt;と _sip _tls。&lt;内部&gt; DNS のドメイン。</span><span class="sxs-lookup"><span data-stu-id="d4b64-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="d4b64-140">これらのレコードは Edge Server のアクセス インターフェイスの外部 IP アドレスをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b64-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="d4b64-141">**Hostているユーザー**は、ホスティングプロバイダーが Lync Server 2013 アカウントをホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="d4b64-142">\*\*False \*\* は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="d4b64-p111">\*\*ProxyFQDN \*\* では、ホスティング プロバイダーで使用されているプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この例では \*\*proxyserver.fabrikam.com \*\* です。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b64-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="d4b64-146">**Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server 2013 トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="d4b64-147">\*\*VerficationLevel \*\* は、ホスティング プロバイダーとのメッセージ送受信に対して許可された確認レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="d4b64-148">ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b64-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="d4b64-149">このレベルが指定されない場合は、メッセージは確認できないため拒否されます。</span><span class="sxs-lookup"><span data-stu-id="d4b64-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4b64-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4b64-150">See Also</span></span>


[<span data-ttu-id="d4b64-151">エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="d4b64-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="d4b64-152">Lync Server 2013 での内部サーバーとエッジ サーバーの間の接続の検証</span><span class="sxs-lookup"><span data-stu-id="d4b64-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="d4b64-153">[新規-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d4b64-153">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

