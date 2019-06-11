---
title: 'Lync Server 2013: Hosted Exchange UM のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="2f240-102">Lync Server 2013 Hosted Exchange UM のルーティング</span><span class="sxs-lookup"><span data-stu-id="2f240-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f240-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2f240-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2f240-104">Exchange UM ルーティングアプリケーションは、オンプレミスの Microsoft Exchange Server ユニファイドメッセージング (UM) 展開またはホストされた Exchange UM サービスのいずれかに、通話をルーティングするために、フロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2f240-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="2f240-105">ExUM ルーティングアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2f240-105">The ExUM Routing Application</span></span>

<span data-ttu-id="2f240-106">Lync Server 2013 Exchange UM ルーティングアプリケーションでは、次の図に示すように、ユーザーアカウントの設定とホストされたボイスメールポリシーのパラメーターから情報を使って、ホストされている音声メッセージの着信をルーティングする方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="2f240-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="2f240-107">**混在展開の Exchange UM ルーティングの例**</span><span class="sxs-lookup"><span data-stu-id="2f240-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="2f240-108">![オンプレミスの Lync Server EXCHANGE UM の展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "オンプレミスの Lync Server EXCHANGE UM の展開")</span><span class="sxs-lookup"><span data-stu-id="2f240-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="2f240-109">Exchange UM ルーティングは、オンプレミスの Exchange UM を有効にしているユーザー、またはホストされている Exchange UM を有効にしているユーザー、またはこの2つの組み合わせに対して、着信をルーティングするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f240-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="2f240-110">たとえば、Roy のメールボックスと Exchange UM サービスがオンプレミスの Exchange 展開のホームにあるとします。</span><span class="sxs-lookup"><span data-stu-id="2f240-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="2f240-111">Roy のユーザーアカウントからのプロキシアドレス情報は、ExUM ルーティングアプリケーションがオンプレミスの Exchange UM サーバーへの呼び出しをルーティングするために使用する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2f240-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="2f240-112">アリスのメールボックスと Exchange UM サービスは、ホスティングされている Exchange サービスプロバイダーのデータセンターにあります。</span><span class="sxs-lookup"><span data-stu-id="2f240-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="2f240-113">Exchange UM の呼び出しに対するルーティングは、次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="2f240-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="2f240-114">Alice のユーザーアカウントの msExchUCVoiceMailSettings 属性で設定された値は、ExUM ルーティングアプリケーションに対して、ホストされたボイスメールポリシーでルーティングの詳細を確認するように指示します。</span><span class="sxs-lookup"><span data-stu-id="2f240-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f240-115">MsExchUCVoiceMailSettings 属性の値は、Exchange サービスプロバイダーまたは Lync Server 2013 管理者のいずれかで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2f240-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="2f240-116">上の図の例では、Lync Server 2013 管理者によって、ホストされたボイスメールを有効にするように値 (CsHostedVoiceMail = 1) が設定されていました。</span><span class="sxs-lookup"><span data-stu-id="2f240-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="2f240-117">この属性の詳細については、「 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 でのホスト型 Exchange ユーザーの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f240-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="2f240-118">Alice のユーザーアカウントに割り当てられているホスト型ボイスメールのポリシーによって、ルーティングの詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2f240-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="2f240-119">[Destination] は、ホストされている Exchange UM サービスプロバイダーです (ls)。ExUm。\<この例では、\>hostedexchangeserver を使用しています)。</span><span class="sxs-lookup"><span data-stu-id="2f240-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="2f240-120">組織は、ls に配置されている Exchange Server テナントの SIP メッセージのルーティング Fqdn であるテナント Id によって識別されます。ExUm。\<この例では、corp.contoso.com と corp.litwareinc.com を使用し\>ます。</span><span class="sxs-lookup"><span data-stu-id="2f240-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2f240-121">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="2f240-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="2f240-122">詳細については、「 [Lync Server 2013 のホスト型ボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f240-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f240-123">ユーザーアカウントに msExchUCVoiceMailSettings 属性と UM プロキシアドレスの両方の設定が含まれている場合は、msExchUCVoiceMailSettings 属性が優先されます。</span><span class="sxs-lookup"><span data-stu-id="2f240-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

