---
title: 'Lync Server 2013: デバイス ハードウェアのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="a0c80-102">Lync Server 2013 でのデバイス ハードウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="a0c80-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c80-103">_**最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="a0c80-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="a0c80-104">IP 電話とアナログデバイスを展開する前に、特定のハードウェア構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c80-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="a0c80-105">Lync Phone Edition を実行している IP 電話は、Link Layer Discovery Protocol-メディア Endpoint Discovery (LLDP-MED) と Power over Ethernet (PoE) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a0c80-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="a0c80-106">LLDP を利用するには、スイッチは IEEE 802.1 AB と ANSI/TIA-1057 をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c80-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="a0c80-107">PoE を活用するには、スイッチは PoE 802.3 AF または 802.3 at に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c80-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="a0c80-108">LLDP を有効にするには、管理者は、[コンソールの切り替え] ウィンドウを使って LLDP を有効にし、適切なボイス VLAN ID を使用して LLDP ネットワークポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c80-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="a0c80-109">また、展開にアナログデバイスが含まれている場合は、Lync Server を使用するようにアナログゲートウェイを設定する必要があります。また、ゲートウェイは以下のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c80-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="a0c80-110">アナログ電話アダプター (ATA)</span><span class="sxs-lookup"><span data-stu-id="a0c80-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="a0c80-111">PSTN アナログゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="a0c80-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="a0c80-112">PSTN アナログゲートウェイを含む Survivable Branch アプライアンス</span><span class="sxs-lookup"><span data-stu-id="a0c80-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="a0c80-113">ATA と通信する PSTN ゲートウェイが含まれている Survivable Branch アプライアンス</span><span class="sxs-lookup"><span data-stu-id="a0c80-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="a0c80-114">アナログゲートウェイを構成する方法については、Lync Server 2010 TechNet ライブラリの「 [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)アナログデバイスの展開を計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c80-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="a0c80-115">(アナログデバイス2010は、lync server 2013 での動作と同じように機能します)。</span><span class="sxs-lookup"><span data-stu-id="a0c80-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a0c80-116">スイッチでサポートされている場合は、強化された 9-1-1 (E9) のスイッチを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0c80-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

