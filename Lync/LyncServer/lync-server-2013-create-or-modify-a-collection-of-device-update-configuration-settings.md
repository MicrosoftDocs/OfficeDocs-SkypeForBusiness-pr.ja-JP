---
title: デバイス更新の構成設定のコレクションの作成または変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e550f48e37ab9c225e5a4919cbc65a13fe09e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d4b8b-102">Lync Server 2013 でのデバイス更新の構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="d4b8b-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b8b-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d4b8b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d4b8b-104">デバイス更新の構成設定は Windows PowerShell および **New-CsDeviceUpdateConfiguration** コマンドレットを使用して (サイト スコープでのみ) 作成でき、**Set-CsDeviceUpdateConfiguration** コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="d4b8b-105">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d4b8b-106">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="d4b8b-107">既定値を使用するデバイス更新の構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="d4b8b-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="d4b8b-108">このコマンドは、Redmond サイト用にデバイス更新の構成設定の新しいセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="d4b8b-109">前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないので、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="d4b8b-110">デバイス更新の構成設定の作成時に 1 つのプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="d4b8b-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="d4b8b-111">異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を含めるだけです。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="d4b8b-112">たとえば、規定で古いログファイルを 21 日ごとに削除するデバイス更新の構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="d4b8b-113">デバイス更新の構成設定の作成時に複数のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="d4b8b-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="d4b8b-114">複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="d4b8b-115">たとえば、次のコマンドでは、ログのクリーンアップ間隔を 21 日に設定し、さらにログのフラッシュ間隔を 30 分に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="d4b8b-116">既存のデバイス構成設定の変更の詳細については、[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="d4b8b-117">構成設定コレクションの作成の詳細については、 [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b8b-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

