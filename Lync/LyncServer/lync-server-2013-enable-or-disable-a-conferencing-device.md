---
title: 'Lync Server 2013: 会議デバイスを有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="a5a68-102">Lync Server 2013 で会議デバイスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a5a68-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5a68-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a5a68-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a5a68-104">お使いの会議デバイスを有効または無効にするには、 **Csroom room**コマンドレットと**csroom room**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a68-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="a5a68-105">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5a68-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5a68-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a68-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="a5a68-107">会議デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="a5a68-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="a5a68-108">会議デバイスを有効にするには、 **Csroom room**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a68-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="a5a68-109">会議デバイスを有効にする場合は、会議デバイス id、b) 会議室のアカウントが所属するレジストラープール、およびそのアカウントに割り当てられる SIP アドレスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5a68-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="a5a68-110">会議デバイスの無効化</span><span class="sxs-lookup"><span data-stu-id="a5a68-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="a5a68-111">会議デバイスを無効にするには、 **Csroom room**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a68-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="a5a68-112">無効にする会議デバイスの id を指定していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5a68-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="a5a68-113">詳細については、「 [Csroom room room](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) !」コマンドレットと「 [csroom room room](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom)コマンドレットを無効にする」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a68-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

