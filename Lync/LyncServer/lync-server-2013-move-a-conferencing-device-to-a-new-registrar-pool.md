---
title: 'Lync Server 2013: 会議デバイスを新しいレジストラープールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7cf8b9e9fefc8dee60392a122d127e87d011446
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="9d6e1-102">Lync Server 2013 で会議デバイスを新しいレジストラープールに移動する</span><span class="sxs-lookup"><span data-stu-id="9d6e1-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d6e1-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9d6e1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9d6e1-104">「 **Csmove room** 」コマンドレットを使用して、1つのレジストラープールから別の場所に会議デバイスを移動します。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="9d6e1-105">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d6e1-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="9d6e1-107">会議デバイスを新しいレジストラープールに移動する</span><span class="sxs-lookup"><span data-stu-id="9d6e1-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="9d6e1-108">会議デバイスを移動するには、移動するチャットルームの id を指定する必要があります。その後、ターゲットパラメーターに、デバイスの移動先のレジストラープールの完全修飾ドメイン名 (FQDN) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="9d6e1-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="9d6e1-110">詳細については、「 [Csroom 会議室の移動](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6e1-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

