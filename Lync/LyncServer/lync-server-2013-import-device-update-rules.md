---
title: 'Lync Server 2013: デバイス更新ルールをインポートする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cef7e14806a1f4c7853d157d0c4ce304583b9720
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="aa402-102">Lync Server 2013 でデバイス更新ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="aa402-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa402-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aa402-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aa402-104">デバイス更新ルールをインポートするには、Windows PowerShell と**インポート-CsDeviceUpdate**コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa402-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="aa402-105">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="aa402-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa402-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa402-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="aa402-107">デバイス更新ルールを1つの web サーバーにインポートするには</span><span class="sxs-lookup"><span data-stu-id="aa402-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="aa402-108">次のコマンドは、デバイス更新ルールを Web サーバー atl-cs-001.litwareinc.com にインポートします。</span><span class="sxs-lookup"><span data-stu-id="aa402-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="aa402-109">すべての web サーバーにデバイス更新ルールをインポートするには</span><span class="sxs-lookup"><span data-stu-id="aa402-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="aa402-110">この例では、デバイス更新ルールは、組織に展開されているすべての Web サーバーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa402-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="aa402-111">このコマンドが動作するためには\\ \\、\\フォルダーの atl-fs-001.litwareinc.com の更新が共有され、すべての Web サーバーで利用できるようになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa402-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="aa402-112">詳細については、「[インポート-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa402-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa402-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa402-113">See Also</span></span>


[<span data-ttu-id="aa402-114">Lync Server 2013 でのデバイス更新ルールに関する情報を確認する</span><span class="sxs-lookup"><span data-stu-id="aa402-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="aa402-115">Lync Server 2013 でデバイス更新ルールを承認する</span><span class="sxs-lookup"><span data-stu-id="aa402-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

