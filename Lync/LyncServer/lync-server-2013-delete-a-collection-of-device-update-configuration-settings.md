---
title: 'Lync Server 2013: デバイス更新の構成設定のコレクションの削除'
description: 'Lync Server 2013: デバイス更新の構成設定のコレクションの削除。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566653"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f9cf0-103">Lync Server 2013 でのデバイス更新の構成設定のコレクションの削除</span><span class="sxs-lookup"><span data-stu-id="f9cf0-103">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9cf0-104">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f9cf0-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f9cf0-105">デバイス更新の構成設定は、Windows PowerShell と **Remove-CsdeviceUpdateConfiguration** コマンドレットを使用しても削除できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-105">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="f9cf0-106">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f9cf0-107">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="f9cf0-108">デバイス更新の構成設定の特定のコレクションを削除するには</span><span class="sxs-lookup"><span data-stu-id="f9cf0-108">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="f9cf0-109">次のコマンドは、Redmond サイトに適用されたデバイス更新の構成設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-109">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f9cf0-110">サイト スコープに適用されたデバイス更新の構成設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="f9cf0-110">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="f9cf0-111">次のコマンドは、サイト スコープに適用されたデバイス更新の構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-111">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="f9cf0-112">LogCleanUpInterval プロパティの値に基づいてデバイス更新の構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="f9cf0-112">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="f9cf0-113">次のコマンドは、ログのクリーンアップ間隔が 10 日 (10.00:00:00) を超えている場合にデバイス更新の構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-113">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="f9cf0-114">詳細については、[Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) コマンドレットに関するヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cf0-114">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

