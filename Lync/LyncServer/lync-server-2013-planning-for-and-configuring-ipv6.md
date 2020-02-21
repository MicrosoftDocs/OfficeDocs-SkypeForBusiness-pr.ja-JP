---
title: 'Lync Server 2013: IPv6 の計画と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 193c0db95b88a5436043bd06d63b62bc8e45a3f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="9e49f-102">Lync Server 2013 での IPv6 の計画と構成</span><span class="sxs-lookup"><span data-stu-id="9e49f-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e49f-103">_**トピックの最終更新日:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="9e49f-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="9e49f-104">Lync Server 2013 には、ip バージョン 6 (IPv6) アドレスのサポートと共に IP バージョン 4 (IPv4) アドレスの継続的なサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e49f-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="9e49f-105">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。</span><span class="sxs-lookup"><span data-stu-id="9e49f-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="9e49f-106">世界中のデバイスの数が増加しているため、使用可能な IPv4 アドレスが不足しています。そのため、多くの新しいデバイスは IPv6 アドレスの使用に移行しています。</span><span class="sxs-lookup"><span data-stu-id="9e49f-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="9e49f-107">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e49f-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="9e49f-108">これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="9e49f-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="9e49f-109">典型的な IPv4 アドレスの例には 192.0.2.235 などがありますが、IPv6 アドレスでは 2001:0db8:85a3:0000:0000:8a2e:0370:7334 のようになります。</span><span class="sxs-lookup"><span data-stu-id="9e49f-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="9e49f-110">IPv6 アドレスを使用するデバイスの書式設定と機能の変更には、Lync Server 2013 のインストールでの展開と構成に関する考慮事項がいくつか必要です。</span><span class="sxs-lookup"><span data-stu-id="9e49f-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e49f-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9e49f-111">In This Section</span></span>

  - [<span data-ttu-id="9e49f-112">Lync Server 2013 の IP アドレスの種類の概要</span><span class="sxs-lookup"><span data-stu-id="9e49f-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="9e49f-113">Lync Server 2013 での IPv6 の技術要件</span><span class="sxs-lookup"><span data-stu-id="9e49f-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="9e49f-114">Lync Server 2013 での IPv6 の移行と共存の考慮事項</span><span class="sxs-lookup"><span data-stu-id="9e49f-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="9e49f-115">Lync Server 2013 での IP アドレスの種類の構成</span><span class="sxs-lookup"><span data-stu-id="9e49f-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

