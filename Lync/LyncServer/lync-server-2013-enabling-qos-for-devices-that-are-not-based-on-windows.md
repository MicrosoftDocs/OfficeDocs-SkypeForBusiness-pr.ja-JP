---
title: 'Lync Server 2013: Windows に基づかないデバイスの QoS の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94d7a8fc9a2cea4fc59a9ec404486042225915df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="cd11e-102">Windows に基づかないデバイスに対して Lync Server 2013 で QoS を有効にする</span><span class="sxs-lookup"><span data-stu-id="cd11e-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd11e-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cd11e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cd11e-104">Microsoft Lync Server 2013 をインストールする場合、Windows 以外のオペレーティングシステムを使用する組織で使用されているデバイスでは、サービスの品質 (QoS) は有効になりません。</span><span class="sxs-lookup"><span data-stu-id="cd11e-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="cd11e-105">これを確認するには、Lync Server 2013 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd11e-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="cd11e-106">メディア構成設定に何も変更を加えていなければ、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd11e-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="cd11e-107">EnableQoS プロパティが False (前の出力のように) に設定されている場合は、Windows 以外のオペレーティングシステムを使用するコンピューターとデバイスでサービスの品質が有効になっていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cd11e-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="cd11e-108">Lync Phone Edition デバイスでは、既定で QoS が有効になっています。ただし、Lync Phone Edition のサービスの品質を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd11e-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="cd11e-109">グローバルスコープでサービスの品質を有効にするには、Lync Server 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd11e-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cd11e-p103">このコマンドを実行すると QoS がグローバル スコープで有効になります。ただし、メディア構成設定はサイト スコープにも適用できるという点に注意してください。サービスの品質を特定のサイトで有効にする必要がある場合は、Set-CsMediaConfiguration を呼び出すときに構成設定の Identity を指定します。たとえば、次のコマンドは Redmond サイトで QoS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cd11e-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="cd11e-p104">QoS をサイト スコープで有効にする必要があるかどうかは、状況によって異なります。サイト スコープに割り当てた設定は、グローバル スコープに割り当てた設定に優先します。たとえば、QoS をグローバル スコープで有効にし、サイト スコープ (Redmond サイト) では無効にしているとします。この場合、Redmond サイトではサービスの品質が無効になります。サイトの設定が優先するからです。Redmond サイトで QoS を有効にするには、サイトに適用されるメディア構成設定を使用して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd11e-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="cd11e-118">すべてのメディア構成設定 (スコープに関係なく) に対して QoS を同時に有効にする場合は、Lync Server 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd11e-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cd11e-119">Windows 以外のオペレーティングシステムを使用しているデバイスでは、EnableQoS プロパティの値を False に設定することで QoS を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd11e-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="cd11e-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cd11e-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="cd11e-121">これにより、ネットワーク (Redmond サイトなど) の一部で QoS を実装しながら、ネットワークの他の部分では QoS を無効のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd11e-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="cd11e-122">QoS は、Windows PowerShell を使用して有効または無効にすることができます。これらのオプションは、Lync Server コントロールパネルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cd11e-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

