---
title: 'Lync Server 2013: ハイブリッド展開の自動検出の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc2c28d42569d2f52b55dd04a90f5a788969c3ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="526af-102">ハイブリッド展開用の Lync Server 2013 での自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="526af-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526af-103">_**最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="526af-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="526af-104">ハイブリッド展開とは、Microsoft Lync Online クラウドサービスとオンプレミスの展開の両方を使用する構成です。</span><span class="sxs-lookup"><span data-stu-id="526af-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="526af-105">この種類の構成では、自動検出サービスは、ユーザーが実際に配置されている場所を見つけることができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="526af-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="526af-106">つまり、自動検出によってユーザーアカウントが検索され、オンプレミスの展開または Lync Online の展開のどちらであるかに関係なく、ユーザーのアカウントをホストしているサーバーはどこにあるかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="526af-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="526af-107">たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように行われます。これは、 \*\* 次のようなプロセスで行われます。</span><span class="sxs-lookup"><span data-stu-id="526af-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="526af-108">ユーザーがオンプレミスの展開、 **contoso.com**への接続試行を開始します。</span><span class="sxs-lookup"><span data-stu-id="526af-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="526af-109">試行は、自動検出サービスに関連付けられている DNS 名 lyncdiscover.contoso.com に送信されます。</span><span class="sxs-lookup"><span data-stu-id="526af-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="526af-110">自動検出は、contoso.com オンプレミスの展開で想定されるレジストラープールを指し、ユーザーの実際のホームサーバー上で Lync Online でホストされている情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="526af-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="526af-111">次に、自動検出によって**lync.com** Online 自動検出サービスへの紹介がユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="526af-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="526af-112">ユーザーは lync.com online 自動検出サービスへの接続試行を開始し、ユーザーのアカウントとユーザーのホームサーバーを特定できます。</span><span class="sxs-lookup"><span data-stu-id="526af-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="526af-113">クライアントでユーザーのホームサーバーが配置されている場所を検出できるようにするには、新しい uniform resource locator (URL) を使用して自動検出サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="526af-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="526af-114">自動検出サービスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="526af-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="526af-115">ハイブリッド展開の自動検出を構成する</span><span class="sxs-lookup"><span data-stu-id="526af-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="526af-116">「 [Lync Server 2013 の自動検出サービス要件](lync-server-2013-autodiscover-service-requirements.md)」では、"Get-CsHostingProvider" を使って Attribute proxyfqdn の値を取得しています。</span><span class="sxs-lookup"><span data-stu-id="526af-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="526af-117">Lync Server 管理シェルで、「</span><span class="sxs-lookup"><span data-stu-id="526af-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="526af-118">ここ\[で\] 、id は共有 SIP アドレス空間のドメイン名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="526af-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="526af-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="526af-119">See Also</span></span>


[<span data-ttu-id="526af-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="526af-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="526af-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="526af-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

