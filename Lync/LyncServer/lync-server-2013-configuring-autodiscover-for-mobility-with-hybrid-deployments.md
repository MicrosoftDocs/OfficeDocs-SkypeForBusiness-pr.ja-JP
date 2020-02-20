---
title: ハイブリッド展開でのモビリティの自動検出の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ecf62a26ed13b2e0cf33b9d29fb45be8d71d74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="ce1fc-102">Lync Server 2013 での自動検出の構成 (ハイブリッド展開を使用したモビリティ)</span><span class="sxs-lookup"><span data-stu-id="ce1fc-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce1fc-103">_**トピックの最終更新日:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="ce1fc-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="ce1fc-104">ハイブリッド展開は、Microsoft Lync Online cloud service とオンプレミス展開の両方を使用する構成です。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="ce1fc-105">この種類の構成では、自動検出サービスは、ユーザーの実際の場所を特定できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="ce1fc-106">つまり、自動検出では、ユーザーアカウントを検索し、ユーザーのアカウントをホストしているサーバーがオンプレミスの展開にあるか、Lync Online の展開であるかに関係なく、ユーザーアカウントをホストしている場所に支援します。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="ce1fc-107">たとえば、ユーザーのアカウントが Lync Online のサーバーでホストされている場合、ユーザーの検索は次のように実行されます。これは、*発見*性と呼ばれるプロセスにあります。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="ce1fc-108">ユーザーは、内部設置型展開である **contoso.com** への接続を試行します.</span><span class="sxs-lookup"><span data-stu-id="ce1fc-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="ce1fc-109">この試行は、自動検出サーバーに関連付けられた DNS 名である lyncdiscover.contoso.com に送信されます。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="ce1fc-110">自動検出は、contoso.com オンプレミス展開の前提となるレジストラープールを参照し、Lync Online でホストされているユーザーのホームサーバー上の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="ce1fc-111">その後、自動検出はユーザーに、**lync.com** オンライン自動検出サービスへの紹介を送信します。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="ce1fc-112">ユーザーは lync.com オンライン自動検出サービスへの接続を試行し、ユーザーのアカウントおよびユーザーのホーム サーバーが特定されます。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="ce1fc-p103">ユーザー ホーム サーバーがある場所でモバイル クライアントが展開を検出できるようにするには、新しい URL (uniform resource locator) で自動検出サービスを構成する必要があります。自動検出サービスを構成するには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="ce1fc-115">ハイブリッド展開のための自動検出の構成</span><span class="sxs-lookup"><span data-stu-id="ce1fc-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="ce1fc-116">属性 ProxyFQDN の値を取得するには、Get-CsHostingProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="ce1fc-117">Lync Server 管理シェルで、と入力します。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="ce1fc-118">\[Id\]は、共有 SIP アドレススペースのドメイン名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ce1fc-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce1fc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce1fc-119">See Also</span></span>


<span data-ttu-id="ce1fc-120">[取得-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ce1fc-120">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="ce1fc-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ce1fc-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

