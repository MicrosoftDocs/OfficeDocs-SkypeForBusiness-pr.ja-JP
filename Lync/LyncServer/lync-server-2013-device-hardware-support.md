---
title: Lync Server 2013 デバイスのハードウェアサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="377fd-102">Lync Server 2013 でのデバイスハードウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="377fd-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="377fd-103">_**トピックの最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="377fd-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="377fd-104">IP 電話およびアナログ デバイスを展開する前に、特定のハードウェア構成を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377fd-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="377fd-105">Lync Phone Edition を実行している IP 電話サポート Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) および Power over Ethernet (PoE)。</span><span class="sxs-lookup"><span data-stu-id="377fd-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="377fd-106">LLDP-MED を利用するには、スイッチが IEEE802.1AB および ANSI/TIA-1057 をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="377fd-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="377fd-107">PoE を利用するには、スイッチが PoE802.3AF または 802.3at をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="377fd-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="377fd-108">LLDP-MED を有効にするには、管理者がスイッチ コンソール ウィンドウを使用して LLDP を有効にし、LLDP-MED ネットワーク ポリシーに適切な音声 VLAN ID を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377fd-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="377fd-109">また、展開にアナログデバイスが含まれている場合は、Lync Server を使用するようにアナログゲートウェイを構成する必要があり、ゲートウェイは次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="377fd-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="377fd-110">アナログ電話アダプター (ATA)</span><span class="sxs-lookup"><span data-stu-id="377fd-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="377fd-111">PSTN アナログ ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="377fd-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="377fd-112">PSTN アナログ ゲートウェイを含む存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="377fd-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="377fd-113">ATA と通信する PSTN ゲートウェイを含む存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="377fd-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="377fd-114">アナログゲートウェイを構成する方法については、Lync Server 2010 TechNet ライブラリの「 [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537)アナログデバイスの展開を計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="377fd-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="377fd-115">(Lync server 2010 の場合と同じように、アナログデバイスは Lync Server 2013 でも同様に動作します)。</span><span class="sxs-lookup"><span data-stu-id="377fd-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="377fd-116">スイッチがこれをサポートする場合、Enhanced 9-1-1 (E9-1-1) のスイッチを構成できます。</span><span class="sxs-lookup"><span data-stu-id="377fd-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

