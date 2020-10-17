---
title: オンプレミスの Lync Server と Exchange Online の統合の構成
description: オンプレミスの Lync Server と Exchange Online の統合を構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553939"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="23389-103">社内の Lync Server 2013 と Exchange Online との統合の構成</span><span class="sxs-lookup"><span data-stu-id="23389-103">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23389-104">_**トピックの最終更新日:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="23389-104">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="23389-105">オンプレミスの Lync Server 2013 展開を使用しているお客様は、ハイブリッド展開モードで Microsoft Exchange Online の Microsoft Outlook Web App との相互運用性を構成できます。</span><span class="sxs-lookup"><span data-stu-id="23389-105">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="23389-106">相互運用性機能には、Outlook Web App インターフェイスとのシングルサインオン、インスタントメッセージング (IM)、プレゼンス統合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="23389-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="23389-107">この統合を有効にするには、次のタスクを完了して、オンプレミスの Lync Server 展開でエッジサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-107">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="23389-108">共有 SIP アドレススペースを構成する</span><span class="sxs-lookup"><span data-stu-id="23389-108">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="23389-109">エッジサーバーのホスティングプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="23389-109">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="23389-110">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="23389-110">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="23389-111">Lync Server 2013 が Exchange Online と統合されている場合、OWA から IM にサインインしようとしているユーザーは、リモートユーザーまたは外部ユーザーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="23389-111">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="23389-112">このシナリオでは、このユーザーに、次のオプションを選択した外部アクセスポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-112">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="23389-113">**リモートユーザーとの通信を有効にする**</span><span class="sxs-lookup"><span data-stu-id="23389-113">**Enable communications with remote users**</span></span>

<span data-ttu-id="23389-114">ユーザーがファイアウォールの外側にいて、在宅勤務中のユーザーなど、インターネット経由で Lync Server に接続できる組織内のユーザーがいる場合は、このオプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="23389-114">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="23389-115">詳細については、「 [Lync Server 2013 の外部アクセスポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23389-115">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="23389-116">共有 SIP アドレススペースを構成する</span><span class="sxs-lookup"><span data-stu-id="23389-116">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="23389-117">オンプレミスの Lync Server 2013 を Exchange Online と統合するには、共有 SIP アドレススペースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-117">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="23389-118">Lync Server と Exchange Online サービスの両方で、同じ SIP ドメインアドレススペースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="23389-118">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="23389-119">Lync Server 管理シェルを使用して、次の例に示されているパラメーターを使用して、 **set-csaccessedgeconfiguration** コマンドレットを実行して、フェデレーション用にエッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="23389-119">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="23389-120">**AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="23389-120">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="23389-121">このプロパティは、内部ユーザーが Lync Server および Exchange Online を使用して、共有 SIP アドレススペースシナリオのユーザーと通信できるかどうかも決定します。</span><span class="sxs-lookup"><span data-stu-id="23389-121">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="23389-122">Lync Server 管理シェルの使用方法の詳細については、「 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23389-122">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="23389-123">エッジサーバーのホスティングプロバイダーを構成する</span><span class="sxs-lookup"><span data-stu-id="23389-123">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="23389-124">Lync Server 管理シェルを使用して、エッジサーバーのホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="23389-124">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="23389-125">これを行うには、次の例のパラメーターを使用して、 **新しい-CsHostingProvider** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23389-125">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="23389-126">中国で21Vianet が運用している Office 365 を使用している場合は、この例の <STRONG>Proxyfqdn</STRONG> パラメーター ("exap.um.outlook.com") の値を、21vianet が運用しているサービスの FQDN に置き換えます。 "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="23389-126">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="23389-127">**Identity** は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します (例: "Exchange Online")。</span><span class="sxs-lookup"><span data-stu-id="23389-127">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="23389-128">スペースを含む値は、二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-128">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="23389-129">**Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23389-129">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="23389-130">**True**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-130">This must be set to **True**.</span></span>

  - <span data-ttu-id="23389-131">**EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23389-131">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="23389-132">**True**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-132">This must be set to **True**.</span></span>

  - <span data-ttu-id="23389-133">**Hostソケット Susers** は、ホスティングプロバイダーが Office Communications server または Lync Server をホストするために使用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23389-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="23389-134">この値は **False**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-134">This must be set to **False**.</span></span>

  - <span data-ttu-id="23389-135">**ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="23389-135">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="23389-136">Exchange Online の場合、FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="23389-136">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="23389-137">**Islocal** は、ホスティングプロバイダーによって使用されるプロキシサーバーが Lync server トポロジ内に含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23389-137">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="23389-138">この値は **False**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23389-138">This must be set to **False**.</span></span>

  - <span data-ttu-id="23389-139">**VerificationLevel** は、ホストされているプロバイダーとの間で送受信されるメッセージに対して許可される確認レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="23389-139">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="23389-140">の **ように指定します**。</span><span class="sxs-lookup"><span data-stu-id="23389-140">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="23389-141">このオプションは、ホスティングプロバイダーから送信されるメッセージに含まれる検証レベルに依存します。</span><span class="sxs-lookup"><span data-stu-id="23389-141">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="23389-142">このレベルが指定されていない場合、メッセージは検証不能として拒否されます。</span><span class="sxs-lookup"><span data-stu-id="23389-142">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="23389-143">更新された中央管理ストアのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="23389-143">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="23389-144">前のセクションのコマンドレットを使用して加えた変更は、エッジサーバーに自動的に適用され、通常はレプリケーションに1分未満かかります。</span><span class="sxs-lookup"><span data-stu-id="23389-144">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="23389-145">次のコマンドレットを使用して、レプリケーションの状態を確認し、変更がエッジサーバーに適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="23389-145">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="23389-146">Lync Server 展開の内部サーバーでレプリケーションの更新を確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23389-146">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="23389-147">変更が適用されたことを確認するには、エッジサーバーで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="23389-147">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23389-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="23389-148">See Also</span></span>


[<span data-ttu-id="23389-149">Lync Server 2013 ユーザーに hosted Exchange UM のボイスメールを提供する</span><span class="sxs-lookup"><span data-stu-id="23389-149">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="23389-150">Lync Server 2013 でのホスト型 Exchange ユニファイドメッセージングの統合</span><span class="sxs-lookup"><span data-stu-id="23389-150">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
