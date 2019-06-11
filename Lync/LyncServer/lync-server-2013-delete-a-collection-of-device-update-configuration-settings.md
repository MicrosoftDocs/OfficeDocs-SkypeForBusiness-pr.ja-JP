---
title: 'Lync Server 2013: デバイス更新プログラムの構成設定のコレクションを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6de7e3e6ecef8338a3a5514cf3a84180e05ca276
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e7b43-102">Lync Server 2013 でデバイス更新設定のコレクションを削除する</span><span class="sxs-lookup"><span data-stu-id="e7b43-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b43-103">_**最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e7b43-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e7b43-104">デバイス更新プログラムの設定は、Windows PowerShell と、 **CsdeviceUpdateConfiguration**コマンドレットを使用して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7b43-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="e7b43-105">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7b43-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e7b43-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b43-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="e7b43-107">デバイスの更新設定の特定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="e7b43-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="e7b43-108">このコマンドは、Redmond サイトに適用されているデバイスの更新設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="e7b43-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e7b43-109">サイトの範囲に適用されているすべてのデバイス更新設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="e7b43-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="e7b43-110">このコマンドは、サイトスコープに適用されているすべてのデバイス更新構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="e7b43-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="e7b43-111">LogCleanUpInterval プロパティの値に基づいてデバイス更新の構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="e7b43-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="e7b43-112">次のコマンドは、ログのクリーンアップ間隔が10日 (10.00:00:00) よりも大きいデバイスの更新設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e7b43-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="e7b43-113">詳細については、「 [CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration)オプションの削除」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b43-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

