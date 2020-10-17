---
title: 'Lync Server 2013: Hosted Exchange UM ルーティング'
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
ms.openlocfilehash: 31091da9a80dc03c798cbf674c1c46e0ea7b901c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533114"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="40886-102">Lync Server 2013 での Hosted Exchange UM ルーティング</span><span class="sxs-lookup"><span data-stu-id="40886-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40886-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="40886-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="40886-104">Exchange UM ルーティングアプリケーションは、フロントエンドサーバー上で実行され、オンプレミスの Microsoft Exchange Server ユニファイドメッセージング (UM) 展開または hosted Exchange UM サービスに呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="40886-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="40886-105">ExUM ルーティング アプリケーション</span><span class="sxs-lookup"><span data-stu-id="40886-105">The ExUM Routing Application</span></span>

<span data-ttu-id="40886-106">Lync Server 2013 Exchange UM ルーティングアプリケーションは、次の図に示すように、ユーザーアカウント設定およびホストボイスメールポリシーパラメーターから情報を使用して、ホストされているボイスメッセージングの呼び出しをルーティングする方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="40886-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="40886-107">**Exchange UM ルーティングが混在している展開の例**</span><span class="sxs-lookup"><span data-stu-id="40886-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="40886-108">![オンプレミスの Lync Server Exchange UM 展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")</span><span class="sxs-lookup"><span data-stu-id="40886-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="40886-109">Exchange UM ルーティングは、オンプレミスの Exchange UM に対して有効になっているユーザー、またはホストされた Exchange UM が有効になっているユーザー、またはその2つの組み合わせに対して、呼び出しをルーティングするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="40886-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="40886-110">たとえば、Roy のメールボックスと Exchange UM サービスがオンプレミスの Exchange 展開に所属しているとします。</span><span class="sxs-lookup"><span data-stu-id="40886-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="40886-111">Roy のユーザーアカウントからのプロキシアドレス情報は、ExUM ルーティングアプリケーションが、その呼び出しを社内 Exchange UM サーバーにルーティングするために使用する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="40886-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="40886-112">Alice のメールボックスと Exchange UM サービスは、hosted Exchange サービスプロバイダーのデータセンターにあります。</span><span class="sxs-lookup"><span data-stu-id="40886-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="40886-113">自分の Exchange UM 呼び出しのルーティングは、次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="40886-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="40886-114">Alice のユーザー アカウントの msExchUCVoiceMailSettings 属性に設定された値は、ExUM ルーティング アプリケーションに対して、ホスト ボイス メール ポリシーのルーティング情報を確認するように示しています。</span><span class="sxs-lookup"><span data-stu-id="40886-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40886-115">MsExchUCVoiceMailSettings 属性の値は、Exchange サービスプロバイダーまたは Lync Server 2013 のいずれかの管理者が設定できます。</span><span class="sxs-lookup"><span data-stu-id="40886-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="40886-116">前の図に示した例では、値 (CsHostedVoiceMail = 1) が Lync Server 2013 管理者によって設定され、Alice のホストボイスメールを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="40886-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="40886-117">この属性の詳細については、「 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 の Hosted Exchange user management</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40886-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="40886-118">Alice のユーザー アカウントに割り当てられたホスト ボイス メール ポリシーは、次のルーティング情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="40886-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="40886-119">Destination は hosted Exchange UM サービスプロバイダー (ls.ExUm. \<hostedExchangeServer\> .この例の com。</span><span class="sxs-lookup"><span data-stu-id="40886-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="40886-120">組織は、ls にある Exchange Server テナントの SIP メッセージのルーティング Fqdn であるテナント Id で識別されます。ExUm. \<hostedExchangeServer\> .com (この例では corp.contoso.com および corp.litwareinc.com)。</span><span class="sxs-lookup"><span data-stu-id="40886-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="40886-121">Exchange Online の FQDN は exap.um.outlook.com です。</span><span class="sxs-lookup"><span data-stu-id="40886-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="40886-122">詳細については、「 [Lync Server 2013 のホストボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40886-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40886-123">msExchUCVoiceMailSettings 属性と UM プロキシ アドレス設定の両方がユーザー アカウントに設定されている場合、msExchUCVoiceMailSettings 属性が優先されます。</span><span class="sxs-lookup"><span data-stu-id="40886-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

