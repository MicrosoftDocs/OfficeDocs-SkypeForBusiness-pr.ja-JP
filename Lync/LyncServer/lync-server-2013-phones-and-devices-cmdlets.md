---
title: 'Lync Server 2013: 電話とデバイスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5e698c23c87f679302c6612bec138bcbae39f71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a7168-102">Lync Server 2013 の電話とデバイスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a7168-102">Phones and devices cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7168-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="a7168-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="a7168-104">Microsoft Lync Server 2013 には、電話やその他のハードウェアデバイスを管理するための多数のコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a7168-104">Microsoft Lync Server 2013 provides a number of cmdlets that enable you to manage telephones and other hardware devices.</span></span> <span data-ttu-id="a7168-105">これにはボイスオーバー IP (VoIP) 電話のようなものが含まれます。一般的なエリア電話 (建物のロビー、カフェテリア、またはその他の公共の場所にある電話など)さらに、アナログ電話でも、Lync Phone Edition を実行できない電話にも対応しています。</span><span class="sxs-lookup"><span data-stu-id="a7168-105">This includes such things as Voice over IP (VoIP) phones; common area phones (for example, a phone in a building lobby, cafeteria, or other public location); and even analog phones, phones that are not capable of running Lync Phone Edition.</span></span>

<div>

## <a name="phones-and-devices-cmdlets"></a><span data-ttu-id="a7168-106">電話とデバイスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="a7168-106">Phones and Devices Cmdlets</span></span>

<span data-ttu-id="a7168-107">**Csdeviceupdate**のコマンドレットを使って、管理者がファームウェアの更新を電話や Lync Phone Edition を実行しているその他のデバイスに配布できるようにする Lync Server コンポーネントである、デバイス更新 Web サービスを管理します。</span><span class="sxs-lookup"><span data-stu-id="a7168-107">The **CsDeviceUpdate** cmdlets are used to manage the Device Update Web service, a Lync Server component that enables administrators to distribute firmware updates to telephones and other devices running Lync Phone Edition.</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-108">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-108">[Get-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-109">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-109">[Move-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-110">[新規-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-110">[New-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-111">[Remove-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-112">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-112">[Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-113">[Get-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-114">[Move-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-115">[新規-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-115">[New-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-116">[Remove-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-117">[Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-118">[Get-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-119">[新規-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-119">[New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-120">[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-121">[Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-122">[インポート-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-122">[Import-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-123">[CsDeviceUpdateConfiguration 入手](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-123">[Get-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-124">[新規-CsDeviceUpdateConfiguration 「」](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-124">[New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-125">[CsDeviceUpdateConfiguration 削除](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-125">[Remove-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-126">[Set-CsDeviceUpdateConfiguration 設定](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-126">[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-127">[Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-128">[Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-129">[Approve-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-130">[Get-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-131">[Remove-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-132">[CsDeviceUpdateRule のリセット](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-132">[Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-133">[復元-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-133">[Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-134">[Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="a7168-135">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-135">[Get-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-136">[新規-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-136">[New-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-137">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-137">[Remove-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="a7168-138">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7168-138">[Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7168-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7168-139">See Also</span></span>


[<span data-ttu-id="a7168-140">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="a7168-140">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

