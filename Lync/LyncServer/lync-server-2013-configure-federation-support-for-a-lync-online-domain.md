---
title: 'Lync Server 2013: Lync Online ドメインのフェデレーションサポートを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="077d9-102">Lync Server 2013 での Lync Online ドメインのフェデレーションサポートの構成</span><span class="sxs-lookup"><span data-stu-id="077d9-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="077d9-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="077d9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="077d9-104">Microsoft Lync Online 2010 とのフェデレーションのお客様は、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="077d9-105">Lync Online 2010 顧客のドメイン (たとえば、contoso.onmicrosoft.com) のサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="077d9-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="077d9-106">このドキュメントの「lync [Server 2013 で Lync Online 顧客とのフェデレーションを行うための前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」で説明されているように、組織のフェデレーションを既に有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="077d9-107">フェデレーションを有効にするには、フェデレーションドメインによるアクセスを制御するために使用するメソッドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="077d9-108">検出機能を使用するように組織を構成している場合、ドメインを組織の許可リストに追加するオプションは省略できます。</span><span class="sxs-lookup"><span data-stu-id="077d9-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="077d9-109">ドメインの検出を有効にしなかった場合は、Lync Online のユーザーのドメイン名を、許可ドメインの一覧に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="077d9-110">ドメイン名を追加するには、Lync Server コントロールパネルを使用するか、または**新しい-CSAllowedDomain**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="077d9-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="077d9-111">Lync Server コントロールパネルの使用について詳しくは、「ドメインの検出を有効にする」をご覧ください。運用マニュアルの「 [Lync server 2013 で組織の SIP フェデレーションプロバイダーを管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="077d9-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="077d9-112">**新しい-csalloweddomain**コマンドレットを使用してドメインを追加する方法について詳しくは、操作のドキュメントにある「[新しい-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="077d9-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="077d9-113">Lync Online のユーザーは、複数のドメインを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="077d9-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="077d9-114">複数のドメインとフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインのサポートを構成する必要があります。また、Lync Online のユーザーの管理者がフェデレーションを有効にするには、それぞれのドメインに対してフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="077d9-115">フェデレーションを行う Lync Online 2010 顧客ドメインのホスティングプロバイダーのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="077d9-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="077d9-116">このセクションの手順を使用して、ホスティングプロバイダーのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="077d9-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="077d9-117">この手順は、Lync Online の顧客のドメインとのフェデレーションの場合にのみ必要です。フェデレーションパートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには使用できません。</span><span class="sxs-lookup"><span data-stu-id="077d9-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="077d9-118">ホスティングプロバイダーのサポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="077d9-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="077d9-119">フロントエンドサーバーから、Lync Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="077d9-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="077d9-120">**新しい-CsHostingProvider**コマンドレットを実行して、ホスティングプロバイダーを作成し、構成します。</span><span class="sxs-lookup"><span data-stu-id="077d9-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="077d9-121">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="077d9-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="077d9-122">上述の例では、次のパラメーターが設定されます。</span><span class="sxs-lookup"><span data-stu-id="077d9-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="077d9-123">**Id**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="077d9-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="077d9-124">既存のプロバイダーが既にその Id で構成されている場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="077d9-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="077d9-125">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="077d9-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="077d9-126">この値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="077d9-126">This value cannot be modified.</span></span> <span data-ttu-id="077d9-127">ホスティングプロバイダーによってプロキシサーバーが変更された場合は、削除して、そのプロバイダーのエントリを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077d9-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="077d9-128">**VerificationLevel**は、ホスティングプロバイダーから送信されたメッセージを、そのプロバイダーから送信されたものであるかどうかを確認するために、どのようにするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="077d9-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="077d9-p107">\*\*Enabled \*\* は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を \*\*True \*\* に設定しないと、2 つの組織間でメッセージを交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="077d9-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="077d9-131">\*\*EnabledSharedAddressSpace \*\* では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="077d9-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="077d9-132">**Hostているユーザー**は、ホスティングプロバイダーが Lync Server アカウントをホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="077d9-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="077d9-133">\*\*False \*\* は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="077d9-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="077d9-134">**Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="077d9-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="077d9-135">このコマンドレットの使い方の詳細については、操作のドキュメントの「[新規-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="077d9-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

