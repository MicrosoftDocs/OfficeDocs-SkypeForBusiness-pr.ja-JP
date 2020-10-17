---
title: 'Lync Server 2013: デバイスに関連付けられていないデバイス更新ファイルを削除する'
description: 'Lync Server 2013: デバイスに関連付けられていないデバイス更新ファイルを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8338f7274d1d27e2290d822324986238f4856fe4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553503"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="72cf6-103">Lync Server 2013 でデバイスに関連付けられていないデバイス更新ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="72cf6-103">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72cf6-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="72cf6-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="72cf6-105">新しいデバイス更新プログラムがシステムにアップロードされるたびに、対応するデバイス更新ルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-105">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="72cf6-106">既定では、これらの新しいデバイス更新ルールは保留状態に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-106">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="72cf6-107">これは、これらのルールはテストデバイスでダウンロードおよびインストールできますが、運用デバイスではインストールできないため、更新プログラムをテストしてからユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-107">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="72cf6-108">テストに基づいて、更新を承諾して、展開するか、または拒否して削除します。</span><span class="sxs-lookup"><span data-stu-id="72cf6-108">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="72cf6-109">更新を拒否すると、デバイスの更新はデバイス更新ルールから関連付けが解除されます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-109">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="72cf6-110">デバイスに関連付けられていないデバイス更新ファイルは、Windows PowerShell と、 **CsDeviceUpdateFile** コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-110">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="72cf6-111">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-111">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72cf6-112">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="72cf6-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="72cf6-113">たとえば、次のコマンドを実行すると、デバイスに関連付けられていない、Web サーバー atl-cs-001.litwareinc.com 上のデバイス更新ルールがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="72cf6-113">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="72cf6-114">詳細につい [ては、このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72cf6-114">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

