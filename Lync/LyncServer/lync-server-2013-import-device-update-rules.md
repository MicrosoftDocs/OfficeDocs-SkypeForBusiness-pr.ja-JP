---
title: 'Lync Server 2013: デバイス更新ルールのインポート'
description: 'Lync Server 2013: デバイス更新ルールをインポートします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7b936a4b7be96332343e8f96134d5ba1b879be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547853"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="9179e-103">Lync Server 2013 でのデバイス更新ルールのインポート</span><span class="sxs-lookup"><span data-stu-id="9179e-103">Import Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9179e-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9179e-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9179e-105">デバイス更新ルールは、Windows PowerShell と **インポート-CsDeviceUpdate** コマンドレットを使用してのみインポートできます。</span><span class="sxs-lookup"><span data-stu-id="9179e-105">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="9179e-106">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9179e-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9179e-107">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="9179e-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="9179e-108">デバイス更新ルールを1つの web サーバーにインポートするには</span><span class="sxs-lookup"><span data-stu-id="9179e-108">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="9179e-109">次のコマンドは、デバイス更新ルールを Web サーバー atl-cs-001.litwareinc.com にインポートします。</span><span class="sxs-lookup"><span data-stu-id="9179e-109">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="9179e-110">デバイス更新ルールをすべての web サーバーにインポートするには</span><span class="sxs-lookup"><span data-stu-id="9179e-110">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="9179e-111">この例では、デバイス更新ルールは、組織内に展開されているすべての Web サーバーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="9179e-111">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="9179e-112">このコマンドを動作させるには、フォルダー \\ \\ Atl-fs-001.litwareinc.com の更新を \\ 共有し、すべての Web サーバーで使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9179e-112">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="9179e-113">詳細については、「 [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9179e-113">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9179e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9179e-114">See Also</span></span>


[<span data-ttu-id="9179e-115">Lync Server 2013 でのデバイス更新ルールに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="9179e-115">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="9179e-116">Lync Server 2013 でのデバイス更新ルールの承認</span><span class="sxs-lookup"><span data-stu-id="9179e-116">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

