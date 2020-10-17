---
title: 'Lync Server 2013: Hosted Exchange UM ルーティング'
description: 'Lync Server 2013: Hosted Exchange UM ルーティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550133"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="c14d2-103">Lync Server 2013 での Hosted Exchange UM ルーティング</span><span class="sxs-lookup"><span data-stu-id="c14d2-103">Hosted Exchange UM routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c14d2-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c14d2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c14d2-105">Exchange UM ルーティングアプリケーションは、フロントエンドサーバー上で実行され、オンプレミスの Microsoft Exchange Server ユニファイドメッセージング (UM) 展開または hosted Exchange UM サービスに呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c14d2-105">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="c14d2-106">ExUM ルーティング アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c14d2-106">The ExUM Routing Application</span></span>

<span data-ttu-id="c14d2-107">Lync Server 2013 Exchange UM ルーティングアプリケーションは、次の図に示すように、ユーザーアカウント設定およびホストボイスメールポリシーパラメーターから情報を使用して、ホストされているボイスメッセージングの呼び出しをルーティングする方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c14d2-107">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="c14d2-108">**Exchange UM ルーティングが混在している展開の例**</span><span class="sxs-lookup"><span data-stu-id="c14d2-108">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="c14d2-109">![オンプレミスの Lync Server Exchange UM 展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")</span><span class="sxs-lookup"><span data-stu-id="c14d2-109">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="c14d2-110">Exchange UM ルーティングは、オンプレミスの Exchange UM に対して有効になっているユーザー、またはホストされた Exchange UM が有効になっているユーザー、またはその2つの組み合わせに対して、呼び出しをルーティングするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="c14d2-110">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="c14d2-111">たとえば、Roy のメールボックスと Exchange UM サービスがオンプレミスの Exchange 展開に所属しているとします。</span><span class="sxs-lookup"><span data-stu-id="c14d2-111">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="c14d2-112">Roy のユーザーアカウントからのプロキシアドレス情報は、ExUM ルーティングアプリケーションが、その呼び出しを社内 Exchange UM サーバーにルーティングするために使用する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c14d2-112">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="c14d2-113">Alice のメールボックスと Exchange UM サービスは、hosted Exchange サービスプロバイダーのデータセンターにあります。</span><span class="sxs-lookup"><span data-stu-id="c14d2-113">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="c14d2-114">自分の Exchange UM 呼び出しのルーティングは、次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="c14d2-114">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="c14d2-115">Alice のユーザー アカウントの msExchUCVoiceMailSettings 属性に設定された値は、ExUM ルーティング アプリケーションに対して、ホスト ボイス メール ポリシーのルーティング情報を確認するように示しています。</span><span class="sxs-lookup"><span data-stu-id="c14d2-115">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c14d2-116">MsExchUCVoiceMailSettings 属性の値は、Exchange サービスプロバイダーまたは Lync Server 2013 のいずれかの管理者が設定できます。</span><span class="sxs-lookup"><span data-stu-id="c14d2-116">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="c14d2-117">前の図に示した例では、値 (CsHostedVoiceMail = 1) が Lync Server 2013 管理者によって設定され、Alice のホストボイスメールを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="c14d2-117">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="c14d2-118">この属性の詳細については、「 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 の Hosted Exchange user management</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14d2-118">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="c14d2-119">Alice のユーザー アカウントに割り当てられたホスト ボイス メール ポリシーは、次のルーティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c14d2-119">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="c14d2-120">Destination は hosted Exchange UM サービスプロバイダー (ls.ExUm. \<hostedExchangeServer\> .この例の com。</span><span class="sxs-lookup"><span data-stu-id="c14d2-120">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="c14d2-121">組織は、ls にある Exchange Server テナントの SIP メッセージのルーティング Fqdn であるテナント Id で識別されます。ExUm. \<hostedExchangeServer\> .com (この例では corp.contoso.com および corp.litwareinc.com)。</span><span class="sxs-lookup"><span data-stu-id="c14d2-121">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c14d2-122">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="c14d2-122">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="c14d2-123">詳細については、「 [Lync Server 2013 のホストボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14d2-123">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c14d2-124">msExchUCVoiceMailSettings 属性と UM プロキシ アドレス設定の両方がユーザー アカウントに設定されている場合、msExchUCVoiceMailSettings 属性が優先されます。</span><span class="sxs-lookup"><span data-stu-id="c14d2-124">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

