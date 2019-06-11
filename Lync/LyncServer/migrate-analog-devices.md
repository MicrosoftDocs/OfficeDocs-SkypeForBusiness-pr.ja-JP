---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="c9265-102">アナログ デバイスの移行</span><span class="sxs-lookup"><span data-stu-id="c9265-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9265-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c9265-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c9265-104">Lync Server は、アナログデバイスのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9265-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="c9265-105">特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。</span><span class="sxs-lookup"><span data-stu-id="c9265-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c9265-106">Lync Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c9265-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="c9265-107">Lync Server 2010 から Lync Server 2013 に移行した後、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9265-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c9265-108">Lync server 管理シェルを使用して、Lync Server 2010 アナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="c9265-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="c9265-109">アナログデバイスを移行するには</span><span class="sxs-lookup"><span data-stu-id="c9265-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="c9265-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9265-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c9265-111">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9265-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="c9265-112">すべての連絡先オブジェクトが Lync Server 2013 プールに移動されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9265-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c9265-113">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9265-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="c9265-114">すべての連絡先オブジェクトが Lync Server 2013 プールと関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9265-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

