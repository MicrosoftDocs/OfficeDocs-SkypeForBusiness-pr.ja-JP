---
title: 'Lync Server 2013: ハイブリッド展開のための自動検出の構成'
description: 'Lync Server 2013: ハイブリッド展開のための自動検出の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562493"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="c3805-103">Lync Server 2013 でのハイブリッド展開の自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="c3805-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3805-104">_**トピックの最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c3805-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c3805-105">ハイブリッド展開は、Microsoft Lync Online cloud service とオンプレミス展開の両方を使用する構成です。</span><span class="sxs-lookup"><span data-stu-id="c3805-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="c3805-106">この種類の構成では、自動検出サービスは、ユーザーの実際の場所を特定できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c3805-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="c3805-107">つまり、自動検出では、ユーザーアカウントを検索し、ユーザーのアカウントをホストしているサーバーがオンプレミスの展開にあるか、Lync Online の展開であるかに関係なく、ユーザーアカウントをホストしている場所に支援します。</span><span class="sxs-lookup"><span data-stu-id="c3805-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="c3805-108">たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように実行されます。これは、 *発見*性と呼ばれるプロセスにあります。</span><span class="sxs-lookup"><span data-stu-id="c3805-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="c3805-109">ユーザーは、内部設置型展開である **contoso.com** への接続を試行します.</span><span class="sxs-lookup"><span data-stu-id="c3805-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="c3805-110">この試行は、自動検出サーバーに関連付けられた DNS 名である lyncdiscover.contoso.com に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c3805-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="c3805-111">自動検出は、contoso.com オンプレミス展開の前提となるレジストラープールを参照し、Lync Online でホストされているユーザーのホームサーバー上の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3805-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="c3805-112">その後、自動検出はユーザーに、**lync.com** オンライン自動検出サービスへの紹介を送信します。</span><span class="sxs-lookup"><span data-stu-id="c3805-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="c3805-113">ユーザーは lync.com オンライン自動検出サービスへの接続を試行し、ユーザーのアカウントおよびユーザーのホーム サーバーが特定されます。</span><span class="sxs-lookup"><span data-stu-id="c3805-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="c3805-114">クライアントが、ユーザーのホームサーバーが配置されている展開を検出できるようにするには、新しい uniform resource locator (URL) を使用して自動検出サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3805-114">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c3805-115">自動検出サービスを構成するには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c3805-115">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="c3805-116">ハイブリッド展開のための自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="c3805-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="c3805-117">トピック「 [Lync Server 2013 の自動検出サービス要件](lync-server-2013-autodiscover-service-requirements.md)」では、Get-CsHostingProvider を使用して、属性 proxyfqdn の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c3805-117">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="c3805-118">Lync Server 管理シェルで、と入力します。</span><span class="sxs-lookup"><span data-stu-id="c3805-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="c3805-119">\[Id \] は、共有 SIP アドレススペースのドメイン名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c3805-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3805-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3805-120">See Also</span></span>


[<span data-ttu-id="c3805-121">取得-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c3805-121">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="c3805-122">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c3805-122">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

