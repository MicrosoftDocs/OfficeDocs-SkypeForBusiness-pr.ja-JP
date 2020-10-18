---
title: アナログ デバイスの移行
description: アナログデバイスを移行します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579403"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="cf3e2-103">アナログ デバイスの移行</span><span class="sxs-lookup"><span data-stu-id="cf3e2-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf3e2-104">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="cf3e2-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cf3e2-105">Lync Server は、アナログデバイスのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="cf3e2-106">具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="cf3e2-107">Lync Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="cf3e2-108">Lync Server 2010 から Lync Server 2013 に移行した後、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="cf3e2-109">Lync server 管理シェルを使用して、まず Lync Server 2010 のアナログデバイスに関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="cf3e2-110">アナログ デバイスを移行するには</span><span class="sxs-lookup"><span data-stu-id="cf3e2-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="cf3e2-111">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cf3e2-112">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="cf3e2-113">すべての連絡先オブジェクトが Lync Server 2013 プールに移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="cf3e2-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="cf3e2-115">すべての連絡先オブジェクトが Lync Server 2013 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf3e2-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

