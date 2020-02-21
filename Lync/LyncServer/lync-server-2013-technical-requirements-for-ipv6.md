---
title: Lync Server 2013 IPv6 の技術要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="345d0-102">Lync Server 2013 での IPv6 の技術要件</span><span class="sxs-lookup"><span data-stu-id="345d0-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="345d0-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="345d0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="345d0-104">IPv6 の Lync Server 2013 の構成を計画している場合は、次の要件に留意してください。</span><span class="sxs-lookup"><span data-stu-id="345d0-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="345d0-105">Lync Server で IPv6 アドレスを使用するには、検出して IPv6 アドレスに解決する必要があるレコードに対してドメインネームシステム (DNS) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="345d0-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="345d0-106">IPv6 DNS はホスト AAAA (クアッド A) レコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="345d0-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="345d0-107">展開内で IPv4 と IPv6 の両方を使用する場合は、IPv4 用のホスト A レコードと IPv6 用のホスト AAAA レコードの両方を構成し保持するのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="345d0-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="345d0-108">自身の展開を IPv6 に完全に移行した場合でも、IPv4 を使用する外部ユーザーのために IPv4 DNS ホスト レコードが引き続き必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="345d0-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="345d0-109">IPv6 DNS ホスト レコードは IPv6 の使用を始める前から展開できます。</span><span class="sxs-lookup"><span data-stu-id="345d0-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="345d0-110">クライアントまたはサーバーが IPv6 を使用しない場合、そのレコードは参照されません。</span><span class="sxs-lookup"><span data-stu-id="345d0-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="345d0-111">移行時のテクノロジは、どのレコードを使用するかを、移行テクノロジの構成およびポリシーに基づいて判断します。</span><span class="sxs-lookup"><span data-stu-id="345d0-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="345d0-112">各 IPv6 アドレスにはスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="345d0-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="345d0-113">IPv6 アドレス指定に使用できる3つのスコープは、IPv6 グローバルアドレス (パブリック IPv4 アドレスと類似)、IPv6 固有のローカルアドレス (プライベート IPv4 アドレスの範囲に類似)、IPv6 リンクローカルアドレス (自動プライベート IP アドレスに似ています) です。Windows Server for IPv4)。</span><span class="sxs-lookup"><span data-stu-id="345d0-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="345d0-114">プール内のすべてのサーバーは、同じスコープの IPv6 アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="345d0-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="345d0-115">IPv6 は複雑なトピックで、Windows Server レベルおよび Lync Server 2013 レベルで割り当てたアドレスが期待どおりに動作することを確認するために、ネットワークチームとインターネットプロバイダーについて慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="345d0-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="345d0-116">IPv6 アドレス指定および計画に関するその他のリソースについては、このトピックの最後にあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="345d0-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="345d0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="345d0-117">See Also</span></span>


[<span data-ttu-id="345d0-118">IP バージョン6アドレス指定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="345d0-118">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="345d0-119">IPv6 グローバルユニキャストアドレス形式</span><span class="sxs-lookup"><span data-stu-id="345d0-119">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="345d0-120">一意のローカル IPv6 ユニキャストアドレス</span><span class="sxs-lookup"><span data-stu-id="345d0-120">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

