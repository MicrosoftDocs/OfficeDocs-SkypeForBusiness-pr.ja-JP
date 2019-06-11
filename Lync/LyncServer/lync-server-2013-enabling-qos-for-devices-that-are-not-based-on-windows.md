---
title: 'Lync Server 2013: Windows ベースではないデバイスの QoS を有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="fc5d6-102">Windows ベースではないデバイスの Lync Server 2013 で QoS を有効にする</span><span class="sxs-lookup"><span data-stu-id="fc5d6-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc5d6-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fc5d6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fc5d6-104">Microsoft Lync Server 2013 をインストールすると、Windows 以外のオペレーティングシステムを使用しているすべてのデバイスで、サービスの品質 (QoS) が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="fc5d6-105">これを確認するには、Lync Server 2013 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="fc5d6-106">メディア構成の設定を変更していない場合は、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="fc5d6-107">EnableQoS プロパティが False に設定されている場合 (上記の出力の場合)、Windows 以外のオペレーティングシステムを使用するコンピューターやデバイスではサービスの品質が有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="fc5d6-108">Lync Phone Edition デバイスでは、QoS は既定で有効になっています。ただし、Lync Phone Edition のサービス品質を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="fc5d6-109">グローバルスコープでサービスの品質を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="fc5d6-110">上のコマンドはグローバルスコープで QoS を有効にします。ただし、メディア構成の設定はサイトのスコープにも適用できることに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="fc5d6-111">サイトのサービス品質を有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに構成設定の Id を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="fc5d6-112">たとえば、次のコマンドは、Redmond サイトの QoS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="fc5d6-113">サイトスコープで QoS を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="fc5d6-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="fc5d6-114">ケースバイケースです。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-114">That depends.</span></span> <span data-ttu-id="fc5d6-115">サイトの範囲に割り当てられている設定は、グローバルスコープに割り当てられている設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="fc5d6-116">グローバルスコープで QoS が有効になっているが、サイトのスコープ (Redmond サイト) で無効になっているとします。その場合、Redmond サイトのサービスの品質は無効になります。これは、サイトの設定が優先されるためです。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="fc5d6-117">Redmond サイトの QoS を有効にするには、そのサイトに適用されているメディア構成設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="fc5d6-118">スコープに関係なく、すべてのメディア構成の設定で QoS を同時に有効にする場合は、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="fc5d6-119">Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することにより、QoS を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="fc5d6-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="fc5d6-121">これにより、ネットワークの他の部分でサービスの品質を無効にしたまま、ネットワークの一部の部分 (レドモンドサイトなど) に QoS を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="fc5d6-122">QoS を有効または無効にするには、Windows PowerShell を使用する必要があります。これらのオプションは、Lync Server のコントロールパネルでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="fc5d6-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

